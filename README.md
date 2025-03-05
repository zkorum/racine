# ZKorum's Reference Implementation of the Racine Protocol

Racine is a **meta-protocol** designed for **verifiable provenance**, capturing the **semantics** and **origin** of data, independent of storage location or transfer protocol.  

It introduces an **authentication layer** based on trustless zero-knowledge proofs, allowing real-life credentials (e.g., biometrics passports, verifiable credentials) to serve as the primary digital identifier for end-users while protecting privacy. This ensures context-based proof of humanity (1 account = 1 human), with the **ZKP nullifier** acting as the **root of identity**, establishing trust while maintaining anonymity.

Racine also introduces a **universal API** that allows data to be collected and shared from any source, no matter how the data is stored or transmitted. It aims to be compatible with a wide range of existing data transfer protocols such as centralized HTTP server, IPFS, Filecoin, Waku, Nostr or AT Proto (think cross-posting but beyond just social).

Racine is primarily designed for **zk-anonymous apps**, but also supports use cases that add **auditability** and **transparency** to otherwise fully centralized applications, with minimal infrastructure changes.

ZKorum's [Agora Citizen Network](https://agoracitizen.network) is the first product built on top of the Racine Protocol.

Currently, Racine is direclty integrated within the [Agora code base](https://github.com/zkorum/agora), we're working towards exporting this protocol away from it.

## Features

- Trust Source Flexibility: Developers can choose the trust source for verifiable data provenance. Whether tied to a zk-proof of identity (relying on the credential issuer) or a trusted provider like phone number verification, the protocol ensures data verifiability independent of storage location.
- Privacy and Self-Censorship-Resistance: 
    - We provide integration with the Rarimo protocol. Rarimo can turn linkable credentials into issuer-unlinkable credentials, protecting the zero-knowledge proofs against dictionary attacks from the issuing authority.
    - Unless intentionally misused by app developers, Racine is designed to never transmit Personal Identifiable Information (PII) across the network.
    - We provide tools for developers to enable users to broadcast messages via third-party proxy servers (e.g., apps relying on Racine), allowing users to protect their IP address with optional mixnet routing (e.g., Tor).
- Right to Be Forgotten:
    - Payloads are optional—only sending proofs is required.
    - Edit and delete requests can be broadcast to the network when needed.
- Optional Full Censorship Resistance: Depending on how developers use Racine, users can broadcast messages directly and verify data authenticity locally, without intermediaries.
- Centralized, Decentralized, and Hybrid Models: Supports applications ranging from fully censorship-resistant to more centralized systems that use the protocol for data consistency auditing.
- Unopinionated and Flexible: Developers and users have full control over trusted provenance sources, data storage, semantics and transmission.
- Optional Batteries-Included: Offers a set of best practices, along with simple, ready-to-use tools and techniques for various use cases, available at the developer's discretion to simplify app development without enforcing any specific paradigm.

## Waku

See: https://waku.org/

## FAQ

### Why "Racine"

"Racine," meaning "Root" in French, refers to the concept of the "root of identity" and verifiable data provenance, which lies at the core of the protocol.
