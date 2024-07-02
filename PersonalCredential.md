---
title: Personal Credential
description: Description of Personal Credentials
layout: page
permalink: /PersonalCredential/

sidenav: secondary
subnav:
  - text: Personal Credential Issuer
    href: '#11-dhs-personal-credential-issuer'
  - text: Personal Credential Verifier
    href: '#12-dhs-personal-credential-verifier'
  - text: Personal Credential Holder
    href: '#13-dhs-personal-credential-holder-digital-wallet'
  - text: Normative References
    href: '#14-normative-references'
---
## Implementation Principles

- Digital is not a requirement; it is a choice!
- Eliminate “phone home” architecture/technology/implementations
- Eliminate “back-channel” interactions between verifiers of the credential and the issuer, which are not visible to the credential holder
- Support non-trackable selective disclosure of information under holder control

## Credential Use (In Person)

![In Person Personal Credential Use]({{ site.baseurl }}/assets/img/Requirements-scan-to-Verify.png)

- Implemented using W3C CCG Verifiable Credential Barcodes \[VC-BARCODES\] 
  - Inclusive, global usage without the need for a mobile device
  - DHS continues to have no awareness of credential usage by a Customer
  - Enhanced content integrity & origin authenticity features on the physical card
  - Support for occasionally connected Verifiers  – DHS public keys can be resolved, downloaded and cached on the verifying device, using the resolver functionality that is part of the W3C Decentralized Identifiers (DID) standard to allow local verification to occur without network connectivity

## Credential Use (Online)

![Online Personal Credential Use]({{ site.baseurl }}/assets/img/Requirements-Online.png)

- Implemented using W3C Verifiable Credentials Data Model \[W3C-VC-DATA-MODEL\] and W3C Decentralized Identifiers  \[W3C-DID\]
  - Gives the customer agency and control over their data
  - Addresses the “phone home” problem in existing identity models
  - Provides credential aggregation and selective disclosure with informed consent
  - Removes the conflation of identifiers and authenticators
  - Supports global resolution of an Issuer’s identifier to its public key(s) & their retrieval

## 1.1. DHS Personal Credential Issuer

### 1.1.1. Accessibility & Openness

- SHALL NOT implement capabilities that enable tracking of Holder credential use
- SHALL implement the relevant portions of the W3C Web Content Accessibility Guidelines \[W3C-WCAG\] to ensure compliance with the Section 508 of the U.S. Rehabilitation Act
    - SHOULD implement the U.S. Web Design System ( https://designsystem.digital.gov/ )
- SHALL prioritize the implementation of data formats and associated security and privacy mechanisms, inclusive of public facing APIs, that utilize globally available standards and specifications that are openly developed, royalty free and freely available to implement
- SHALL enable the Holder to choose a digital wallet
- SHALL implement support for Holder applications (digital wallets) that use web platform technologies
- SHALL implement support for Holder applications (digital wallets) that use native platform technologies

### 1.1.2. Platform & Software Security

- SHALL utilize cryptographic modules validated by the joint U.S. & Canada Cryptographic Module Validation Program \[CMVP\]
- SHALL utilize \[FIPS-140\] compliant cryptographic key storage mechanisms
    - MAY utilize an operating system capability
    - MAY utilize an external device capability
    - MAY utilize a remote backend capability
- SHALL provide a Software Bill of Materials (SBOM) containing the details and supply chain relationships of various components used in building the Issuer software
    - SHALL contain the minimum elements for a SBOM as defined in the joint report by the Department of Commerce and the National Telecommunications and Information Administration
        - https://www.ntia.gov/report/2021/minimum-elements-software-bill-materials-sbom

### 1.1.3. Credential Formats & Digital Signatures

- SHALL implement the \[W3C-VC-DATA-MODEL\] using the JSON-LD Compacted Document Form
- SHALL implement the embedded proof mechanism defined in \[W3C-VC-DATA-INTEGRITY\]
- SHALL implement selective disclosure capabilities using \[W3C-VC-DATA-INTEGRITY\] proof sets to support multiple proofs in a single document
    - SHALL implement a proof that is U.S. Federal Information Processing Standards (FIPS) compliant e.g., ECDSA Cryptosuites
    - SHALL implement a proof based on non-correlatable signatures e.g., BBS Cryptosuites
    - MAY implement additional proofs e.g., PQC

### 1.1.4. Identifiers & Metadata

- SHALL implement \[W3C-DID\]
    - SHALL implement the did:web method as the Issuer (Organizational) Identifier
    - SHALL utilize the DID Document as the authoritative metadata distribution mechanism
    - SHALL implement direct DID resolution
    - SHALL implement support for external DID/Metadata resolvers
    - SHALL digitally sign the DID Document with a U.S. Federal Information Processing Standards (FIPS) compliant \[W3C-VC-DATA-INTEGRITY\] proof to enable integrity and provenance verification
- SHALL implement \[W3C-BITSTRING-STATUS-LIST\] for credential status checks inclusive of revocation checks

### 1.1.5. Vocabulary

- SHALL implement \[CITIZENSHIP-VOCAB\]

## 1.2. DHS Personal Credential Verifier

### 1.2.1. Accessibility & Openness

- SHALL NOT implement capabilities that enable Issuer tracking of Holder credential use
- SHALL implement the relevant portions of the W3C Web Content Accessibility Guidelines \[W3C-WCAG\] to ensure compliance with the Section 508 of the U.S. Rehabilitation Act
    - SHOULD implement the U.S. Web Design System ( https://designsystem.digital.gov/ )
- SHALL prioritize the implementation of data formats and associated security and privacy mechanisms, inclusive of public facing APIs, that utilize globally available standards and specifications that are openly developed, royalty free and freely available to implement
- SHALL implement in-context explanations that describe who is accessing credentials, what attributes, capabilities or inferences are accessed, for what purpose the credential is needed, and how data will be used, shared and retained
- SHALL enable the Holder to choose a digital wallet
- SHALL implement support for Holder applications (digital wallets) that use web platform technologies
- SHALL implement support for Holder applications (digital wallets) that use native platform technologies

### 1.2.2. Platform & Software Security

- SHALL utilize cryptographic modules validated by the joint U.S. & Canada Cryptographic Module Validation Program \[CMVP\]
- SHALL utilize \[FIPS-140\] compliant cryptographic key storage mechanisms
    - MAY utilize an operating system capability
    - MAY utilize an external device capability
    - MAY utilize a remote backend capability
- SHALL provide a Software Bill of Materials (SBOM) containing the details and supply chain relationships of various components used in building the Issuer software
    - SHALL contain the minimum elements for a SBOM as defined in the joint report by the Department of Commerce and the National Telecommunications and Information Administration
        - https://www.ntia.gov/report/2021/minimum-elements-software-bill-materials-sbom

### 1.2.3. Credential Formats & Digital Signatures

- SHALL implement the \[W3C-VC-DATA-MODEL\] using the JSON-LD Compacted Document Form
- SHALL implement the embedded proof mechanism defined in \[W3C-VC-DATA-INTEGRITY\]
- SHALL implement selective disclosure capabilities using \[W3C-VC-DATA-INTEGRITY\] proof sets to support multiple proofs in a single document
    - SHALL implement a proof that is U.S. Federal Information Processing Standards (FIPS) compliant e.g., ECDSA Cryptosuites
    - SHALL implement a proof based on non-correlatable signatures e.g., BBS Cryptosuites
    - SHALL verify all presented proofs in the proof set
    - SHOULD prioritize minimal disclosure of data and metadata by the Holder when negotiating the use of a mutually supported proof, while respecting jurisdictional constraints
    - MAY implement additional proofs e.g., PQC
- MAY implement additional credential data formats and associated proof mechanisms

### 1.2.4. Identifiers & Metadata

- SHALL implement \[W3C-DID\]
    - SHALL utilize the DID Document as an authoritative source of metadata
    - SHALL implement direct DID resolution
    - SHALL implement support for external DID/Metadata resolvers
    - SHALL digitally verify the U.S. Federal Information Processing Standards (FIPS) compliant \[W3C-VC-DATA-INTEGRITY\] proof on the DID Document to ensure its integrity and provenance
- SHALL implement \[W3C-BITSTRING-STATUS-LIST\] for credential status checks including revocation checks

### 1.2.5. Vocabulary

- SHALL implement \[CITIZENSHIP-VOCAB\]

## 1.3. DHS Personal Credential Holder (Digital Wallet)

### 1.3.1. Accessibility & Openness

- SHALL NOT implement capabilities that enable Issuer tracking of Holder credential use
- SHALL implement the relevant portions of the W3C Web Content Accessibility Guidelines \[W3C-WCAG\] to ensure compliance with the Section 508 of the U.S. Rehabilitation Act
    - SHOULD implement the U.S. Web Design System ( https://designsystem.digital.gov/ )
- SHALL prioritize the implementation of data formats and associated security and privacy mechanisms, inclusive of public facing APIs, that utilize globally available standards and specifications that are openly developed, royalty free and freely available to implement
- SHALL implement in-context explanations that describe who is accessing credentials, what attributes, capabilities or inferences are accessed, for what purpose the credential is needed, and how data will be used, shared and retained
- SHALL enable the Holder to choose a digital wallet
- SHOULD be implemented using web platform technologies
- MAY be implemented using native platform technologies

### 1.3.2. Platform & Software Security

- SHALL utilize cryptographic modules validated by the joint U.S. & Canada Cryptographic Module Validation Program \[CMVP\]
- SHALL utilize \[FIPS-140\] compliant cryptographic key storage mechanisms
    - MAY utilize an operating system capability
    - MAY utilize an external device capability
    - MAY utilize a remote backend capability
- SHALL provide a Software Bill of Materials (SBOM) containing the details and supply chain relationships of various components used in building the Issuer software
    - SHALL contain the minimum elements for a SBOM as defined in the joint report by the Department of Commerce and the National Telecommunications and Information Administration
        - https://www.ntia.gov/report/2021/minimum-elements-software-bill-materials-sbom

### 1.3.3. Credential Formats & Digital Signatures

- SHALL implement the \[W3C-VC-DATA-MODEL\] using the JSON-LD Compacted Document Form
- SHALL implement the embedded proof mechanism defined in \[W3C-VC-DATA-INTEGRITY\]
- SHALL implement selective disclosure capabilities using \[W3C-VC-DATA-INTEGRITY\] proof sets to support multiple proofs in a single document
    - SHALL implement a proof that is U.S. Federal Information Processing Standards (FIPS) compliant e.g., ECDSA Cryptosuites
    - SHALL implement a proof based on non-correlatable signatures e.g., BBS Cryptosuites
    - SHALL only present one or more proofs supported by the Verifier
    - SHOULD prioritize minimal disclosure of data and metadata by the Holder when negotiating the use of a mutually supported proof, while respecting jurisdictional constraints
    - MAY implement additional proofs e.g., PQC
- MAY implement additional credential data formats and associated proof mechanisms

### 1.3.4. Identifiers

- SHALL implement \[W3C-DID\]

## 1.4. Normative References

- \[W3C-VC-DATA-MODEL\] W3C Verifiable Credentials Data Model
    - https://www.w3.org/TR/vc-data-model-2.0/
- \[W3C-VC-DATA-INTEGRITY\] W3C Verifiable Credentials Data Integrity
    - https://www.w3.org/TR/vc-data-integrity/
- \[W3C-BITSTRING-STATUS-LIST\] W3C Bitstring Status List
    - https://www.w3.org/TR/vc-bitstring-status-list/
- \[W3C-DID\] W3C Decentralized Identifiers
    - https://www.w3.org/TR/did-core/
- \[W3C-WCAG\] W3C Web Content Accessibility Guidelines
    - https://www.w3.org/TR/WCAG22/
- \[VC-BARCODES\] W3C CCG Verifiable Credential Barcodes
    - https://w3c-ccg.github.io/vc-barcodes/
- \[CITIZENSHIP-VOCAB\] W3C CCG Citizenship Vocabulary
    - https://w3c-ccg.github.io/citizenship-vocab/
- \[FIPS-140\] Security Requirements for Cryptographic Modules
    - https://csrc.nist.gov/pubs/fips/140-3/final
- \[CMVP\] Cryptographic Module Validation Program
    - https://csrc.nist.gov/Projects/Cryptographic-Module-Validation-Program
