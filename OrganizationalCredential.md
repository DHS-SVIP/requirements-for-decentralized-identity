# 2.0 Supply Chain Organization Credential

### 2.1. CBP/Trade Issuer

#### 2.1.1. Credential Formats & Digital Signatures

- SHALL implement the \[W3C-VC-DATA-MODEL\] using the JSON-LD Compacted Document Form
- SHALL implement the enveloping proof mechanism defined in \[W3C-VC-JOSE-COSE\] with JOSE (Section 3.1.1)
- SHALL implement \[W3C-DID\]
- MAY implement additional \[W3C-VC-DATA-MODEL\] compliant proof mechanisms

#### 2.1.2. Metadata & Vocabulary

- SHALL implement \[W3C-BITSTRING-STATUS-LIST\] for credential status checks inclusive of revocation checks
- SHALL implement \[W3C-DID\]
    - SHALL implement the did:web method as an Organizational Identifier
    - SHALL utilize the DID Document as the authoritative metadata distribution mechanism
    - SHALL implement direct DID resolution
    - SHALL implement support for external DID/Metadata resolvers
- SHALL implement \[TRACE-VOCAB\]

#### 2.1.3. Issuance Protocol

- SHALL implement \[TRACE-API\]

### 2.2. CBP/Trade Verifier

#### 2.2.1. Credential Formats & Digital Signatures

- SHALL implement the \[W3C-VC-DATA-MODEL\] using the JSON-LD Compacted Document Form
- SHALL implement the enveloping proof mechanism defined in \[W3C-VC-JOSE-COSE\] with JOSE (Section 3.1.1)
- SHALL implement \[W3C-DID\]
- MAY implement additional \[W3C-VC-DATA-MODEL\] compliant proof mechanisms

#### 2.2.2. Metadata & Vocabulary

- SHALL implement \[W3C-BITSTRING-STATUS-LIST\] for credential status checks inclusive of revocation checks
- SHALL implement \[W3C-DID\]
    - SHALL implement the did:web method as an Organizational Identifier
    - SHALL utilize the DID Document as the authoritative metadata distribution mechanism
    - SHALL implement direct DID resolution
    - SHALL implement support for external DID/Metadata resolvers
- SHALL implement \[TRACE-VOCAB\]

#### 2.2.2. Exchange Protocol

- SHALL implement \[TRACE-API\]

### 2.3. Normative References

- \[W3C-VC-DATA-MODEL\] W3C Verifiable Credentials Data Model
    - https://www.w3.org/TR/vc-data-model-2.0/
- \[W3C-VC-JOSE-COSE\] W3C Securing Verifiable Credentials using JOSE and COSE
    - https://www.w3.org/TR/vc-jose-cose/
- \[W3C-BITSTRING-STATUS-LIST\] W3C Bitstring Status List
    - https://www.w3.org/TR/vc-bitstring-status-list/
- \[W3C-DID\] W3C Decentralized Identifiers
    - https://www.w3.org/TR/did-core/
- \[TRACE-API\] W3C CCG Open API for Supply Chain Traceability
    - https://w3c-ccg.github.io/traceability-interop/openapi/
- \[TRACE-VOCAB\] W3C CCG Supply Chain Traceability Vocabulary
    - https://w3c-ccg.github.io/traceability-vocab/