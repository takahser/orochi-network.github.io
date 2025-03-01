# Composability

Composability is the ability for different decentralized applications (dApps) or smart contracts to interact with each other in a seamless manner.
**zkApp composability** refers to the ability to call zkApp methods from other zkApp methods. It uses the `callData` field on the zkApp party to connect the result of the called zkApp to the circuit/proof of the caller zkApp.

## CallData
CallData is an opaque data for communicating between zkApps. `callData`` is a specific data structure generated during the execution of a zkApp method, and it's crucial in establishing a connection between the caller and the callee during a zkApp call

### Composition of CallData

The callData is formulated within the callee's circuit, and it is composed of a hash created from a collection of elements:

- **Inputs**: The arguments that are being used to call a particular method in the smart contract, represented as an array of field elements.
- **Outputs**: The return values generated by the method, also represented as an array of field elements.
- **Method Index**: A numerical identifier for the method that is being called within the smart contract.
- **Blinding Value**: A random value that is known to both the caller and callee circuits at the time of proof generation, used to maintain the privacy of the inputs and outputs.

### Working

1. The callee smart contract first computes the callData hash with the aforementioned elements and stores it in its own callData field.

2. When the caller initiates a call to the callee zkApp, it witnesses the callee's party along with the hash of the callee's children and the method's return value.

3. Subsequently, within the caller's circuit, the same hash operation is performed as in the callee circuit, and it's compared against the callData acquired from the callee to ensure that the call was executed with the exact inputs and garnered the specified outputs.

4. This callData acts as a connecting link allowing the caller zkApp to make authenticated calls to another zkApp (callee) while maintaining the privacy and integrity of the transaction.

### Method Index
The methods are stored in a fixed order, and that order is also baked into the verification key when compiling. Order depends on the order that the @method decorators are called in, but that's an implementation detail

## AccountUpdate
An **AccountUpdate** in the Mina Protocol signifies a set of alterations and events related to a single account during a transaction.

Each zkApp transaction constructed by o1js is composed of one or more AccountUpdates, arranged in a tree-like structure. The execution of this tree adheres to a pre-order traversal pattern; initiating with the primary account, followed by the subsequent left and right branches respectively.

Each `AccountUpdate` consists of components. Essentially, it can be seen as having a core and a set of metadata surrounding it.

1. **Core Component**:

- Updates: This is the nucleus of an AccountUpdate, embodying the critical changes brought about by the transaction, including shifts in the zkApp state, alterations in permissions, and adjustments to the verification key linked to the account.

2. **Metadata Components**:

- PublicKey: The unique identifier for the account being updated, akin to its address.

- TokenId: Represents the custom token involved, defaulting to the MINA TokenId (1). It works in tandem with the PublicKey to uniquely identify an account on the Mina Protocol.

- Preconditions: Specifies the essential conditions or assertions that need to be satisfied for the successful application of the AccountUpdate. These are usually framed through a method in the o1js library.

- BalanceChange: Captures any fluctuations in the account's balance as a consequence of the transaction.

- Authorization: Dictates the mode of authorizing the zkApp, which could be either a proof (aligned with the verification key on the account) or a signature.

- MayUseToken: Signifies whether the zkApp possesses the authority to interact or manipulate its associated token.

- Layout: Allows for making assertions regarding the structural makeup of an AccountUpdate, guaranteeing its compliance and integrity.

## Return types
Only types built out of `Field` are valid return types. This includes snarkyjs primitive types and custom CircuitValues.

## Example

The CallerContract class is invoking a method in the CalleeContract class. During this interaction, two separate AccountUpdates are created to record the changes and events that occurred during the transaction - one for the parent (CallerContract) and one for the child (CalleeContract).

```ts
class CallerContract extends SmartContract {
  @method calledMethod(arg: UInt64): Bool {
     let calledContract = new CalleeContract(address);
     let result = calledContract.calledMethod(arg);
  }
}

class CalleeContract extends SmartContract {
  @method calledMethod(arg: UInt64): Bool {
     // ...
  }
}
```

- Once the child AccountUpdate is created, it is then verified in the parent's circuit, with assertions to validate that the right method was called with the correct parameters, and produced the expected outcome.

- This process also involves verifying that the right zkApp was called by checking the publicKey and tokenId, as indicated in the child AccountUpdate.

- After both AccountUpdates are verified, they are compiled into a tree-like structure, representing a cohesive record of the transaction.

- This hierarchical structure is then submitted, effectively finalizing the transaction and documenting a secure, verified record of the entire interaction between the two contracts.

These AccountUpdates work in tandem to create a comprehensive, secure, and verified record of the transaction, safeguarding the integrity of the process and ensuring transparency and accountability.