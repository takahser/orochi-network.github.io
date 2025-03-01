# Summary

- [Orochi Network](./orochi-network/orochi-network.md)
  - [Orand V1](./orochi-network/orand-v1.md)
  - [Orochi Network SDK](./orochi-network/sdk.md)
  - [Orand Contract Integration](./orochi-network/contract-integration.md)
  - [Orand Code Integration](./orochi-network/code-integration.md)
  - [API Reference](./orochi-network/api-reference.md)
- [Verifiable Random Function (VRF)](./ecvrf/verifiable-random-function.md)
  - [Overview of VRF](./ecvrf/ecvrf-summary/overview-of-vrf.md)
    - [Introduction to VRF](./ecvrf/ecvrf-summary/introduction.md)
    - [VRF Algorithms](./ecvrf/ecvrf-summary/vrf-syntax.md)
    - [VRF Security Properties](./ecvrf/ecvrf-summary/vrf-properties.md)
    - [History of VRF](./ecvrf/ecvrf-summary/vrf-history.md)
  - [VRF Based on Elliptic Curve (ECVRF)](./ecvrf/ecvrf-construction/vrf-based-on-elliptic-curve.md)
    - [Why using ECVRF](./ecvrf/ecvrf-construction/why-using-ecvrf.md)
    - [ECVRF Construction](./ecvrf/ecvrf-construction/ecvrf-construction.md)
    - [ECVRF Auxiliary Function](./ecvrf/ecvrf-construction/ecvrf-auxiliary-function.md)
    - [Implementation](./ecvrf/ecvrf-construction/implementation-python.md)
- [Distributed Key Generation (DKG)](./dkg/dkg.md)
  - [Overview of DKG](./dkg/dkg-summary/chapter.md)
    - [DKG Properties](./dkg/dkg-summary/dkg-properties.md)
    - [DKG Application](./dkg/dkg-summary/dkg-application.md)
  - [Verifiable Secret Sharing (VSS)](./dkg/verifiable-secret-sharing/chapter.md)
    - [Introduction](./dkg/verifiable-secret-sharing/introduction.md)
    - [Syntax and Properties](./dkg/verifiable-secret-sharing/syntax.md)
    - [Pedersen's Construction](./dkg/verifiable-secret-sharing/pedersen-construction.md)
  - [Construction](./dkg/dkg-construction/chapter.md)
    - [Why Gennaro et al's Construction?](./dkg/dkg-construction/why-gennaro.md)
    - [Gennaro et al's Construction](./dkg/dkg-construction/dkg-construction.md)
- [Threshold Signature](./threshold-ecdsa/chapter.md)
  - [Introduction](./threshold-ecdsa/threshold-ecdsa-introduction/introduction.md)
  - [Definition and Security](./threshold-ecdsa/threshold-ecdsa-introduction/definition.md)
  - [Construction](./threshold-ecdsa/threshold-ecdsa-construction/introduction.md)
    - [Key Generation](./threshold-ecdsa/threshold-ecdsa-construction/actual-construction/keygen.md)
    - [Signing](./threshold-ecdsa/threshold-ecdsa-construction/actual-construction/sign.md)
    - [Verification](./threshold-ecdsa/threshold-ecdsa-construction/actual-construction/verify.md)
    - [Supporting Algorithms](./threshold-ecdsa/threshold-ecdsa-construction/actual-construction/supporting-algorithms.md)
    - [Identifying Aborts](./threshold-ecdsa/threshold-ecdsa-construction/actual-construction/abort-identification.md)
  - [Implementation Guideline](./threshold-ecdsa/intended-implementation/our-intended-implementation.md)
- [Isogeny Based Crypto](./isogeny-based-crypto/chapter.md)
  - [Overview of Supersingular Isogeny Graph](./isogeny-based-crypto/supersingular-isogeny-graph/chapter.md)
    - [Elliptic Curves](./isogeny-based-crypto/supersingular-isogeny-graph/background/elliptic-curve.md)
    - [Isogenies](./isogeny-based-crypto/supersingular-isogeny-graph/background/isogeny.md)
    - [Supersingular Elliptic Curves](./isogeny-based-crypto/supersingular-isogeny-graph/background/supersingular-elliptic-curve.md)
    - [Supersingular Isogeny Graph (Pizer Graphs)](./isogeny-based-crypto/supersingular-isogeny-graph/graph/supersingular-isogeny-graph.md)
    - [Applications of Pizer Graphs](./isogeny-based-crypto/supersingular-isogeny-graph/graph/application.md)
- [KZG Polynomial Commitment Scheme](./kzg-polynomial-commitment-scheme/chapter.md)
  - [Polynomial Commitment Scheme - Definition](./kzg-polynomial-commitment-scheme/pcs-definition/section.md)
    - [Syntax](./kzg-polynomial-commitment-scheme/pcs-definition/syntax.md)
    - [Security Requirements](./kzg-polynomial-commitment-scheme/pcs-definition/security-requirement.md)
  - [Technical Overview](./kzg-polynomial-commitment-scheme/technical-overview/section.md)
    - [Commitment to Polynomial Without Hiding Property](./kzg-polynomial-commitment-scheme/technical-overview/commitment-without-hiding.md)
    - [Correct Evaluation from the Commitment](./kzg-polynomial-commitment-scheme/technical-overview/correct-evaluation-from-commitment.md)
    - [Dealing with Hiding](./kzg-polynomial-commitment-scheme/technical-overview/dealing-with-hiding.md)
- [PlonK](./plonk/chapter.md)
  - [PlonK's Arithmetization](./plonk/arithmetization/section.md)
    - [Circuit Specification](./plonk/arithmetization/circuit-specification.md)
    - [Breaking Circuit](./plonk/arithmetization/breaking-circuit.md)
    - [Gate Constraints](./plonk/arithmetization/gate-constraints.md)
    - [Copy Constraints](./plonk/arithmetization/copy-constraints.md)
- [Halo 2 for Dummies](./halo2-for-dummies/chapter.md)
  <!-- - [Overview](./halo2_for_dummies/overview/section.md) -->
  - [PLONKish Arithemetization](./halo2-for-dummies/plonkish/section.md)
    - [A Simple Arithmetic Circuit](./halo2-for-dummies/plonkish/simple-arithmetic-circuit.md)
    - [Transforming to PLONKish Arithmetization](./halo2-for-dummies/plonkish/transforming-to-plonkish-arithmetization.md)
  - [A Simple Halo 2 Program](./halo2-for-dummies/simple-example/section.md)
- [zkDatabase](./zkdatabase/chapter.md)
  - [Accumulation](./zkdatabase/accumulation/accumulation.md)
  - [B-Tree](./zkdatabase/b-tree/b-tree.md)
  - [Composability](./zkdatabase/composability/composability.md)
  - [Serialization](./zkdatabase/serialization/serialization.md)
  - [Data Collection](./zkdatabase/data-collection/data-collection.md)
  - [Distributed-Storage-Engine](./zkdatabase/distributed-storage-engine/section.md)
    - [IPFS](./zkdatabase/distributed-storage-engine/ipfs.md)
    - [Storage-Engine](./zkdatabase/distributed-storage-engine/storage-engine.md)
  - [Merkle-Tree](./zkdatabase/merkle-tree/merkle-tree.md)