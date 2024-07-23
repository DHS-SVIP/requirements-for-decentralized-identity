---
title: Trust Architecture
layout: page
permalink: /TrustArchitecture/

sidenav: secondary
subnav:
  - text: Digital Signatures & PKI
    href: '#digital-signatures--pki' 
  - text: Domain Name System & DNSSEC
    href: '#domain-name-system--dnssec'
  - text: Decentralized Identifiers
    href: '#decentralized-identifiers'
  - text: Using the Building Blocks
    href: '#using-the-building-blocks'
sticky_sidenav: true

---

Today, the web is taken for granted as the public trust infrastructure available for all digital communications.  Paradoxically, the web’s greatest strength, its ubiquitous availability, has exposed a fundamental weakness of the internet; there is no common way to signal public trust and to facilitate trusted introductions between entities using a widely adopted technology infrastructure.

This architecture uses identifiers that can facilitate trusted introductions between entities using existing internet infrastructure. Confidence, or high assurance, that the identifiers can be trusted (i.e., “trusted identifiers”) to represent and are controlled by the entities participating in the transactions are a necessary first step for conducting high value transactions. 

<div class="usa-alert usa-alert--info usa-alert--slim">
  <div class="usa-alert__body">
    <p class="usa-alert__text">
With trusted identifiers, digital transactions can now be conducted between entities using trusted introductions over the internet’s widely available infrastructure in a manner that is provider neutral, attestation data format neutral, and transfer protocol neutral. 
    </p>
  </div>
</div>

These trusted introductions enable higher order capabilities such as verifiable attestations for use in high value digital transactions.

The set of technical building blocks that make trusted identifiers and trusted introductions possible are:

![Web of Public Trust]({{ site.baseurl }}/assets/img/TrustedIntroductions.png)

### Digital Signatures & PKI

As a digital analogue to a written signature, a digital signature provides assurances that the claimed signatory signed the information, and the information was not modified after signature generation.

Signature generation uses a private cryptographic key to generate a digital signature; signature verification uses a public cryptographic key that corresponds to, but is not the same as, the private key. Each signatory possesses a private and public key pair. Public keys may be known by the public; private keys are kept secret. Anyone can verify the signature by employing the signatory’s public key. Only the entity that possesses the private key can perform signature generation.

A public key infrastructure (PKI) is a framework that is established to issue, maintain, and revoke public key certificates. A Certificate Authority (CA) in a PKI is the entity responsible for issuing certificates and exacting compliance with PKI policy.

### Domain Name System & DNSSEC

The Domain Name System (DNS) is a distributed computing system that enables access to Internet resources by user-friendly domain names rather than IP addresses, by translating domain names to IP addresses and back.

Domain Name System Security Extensions (DNSSEC) provide origin authentication and integrity protection for DNS data, as well as a means of public key distribution.

Uniform Resource Identifier (URI) DNS records provide a way to publish mappings from domain names to URIs. Transport Layer Security Authentication (TLSA) DNS records associate a certificate or public key with the domain name where the record is found, thus providing a form of certificate pinning.

### Decentralized Identifiers

Decentralized Identifiers (DIDs), a global standard from the World Wide Web Consortium (W3C), are a type of URI that is globally unique, highly available, and cryptographically verifiable with no required central authority. DIDs associate an entity (DID Subject) with metadata describing the entity (DID Document) and how to interact with it.

A standardized capability to translate a DID to its DID Document enables useful and important functionality such as metadata and public key distribution, authentication, attestation signing, authorization, key rotation and more without those functions affecting the entity's identifier.

## Using the Building Blocks

### Motivation & Constraints

Capabilities implemented using the standardized building blocks of this trust architecture must scale from an individual, to an organization, to a State, and ultimately to a Global context. It should enable participation by an entity in digital transactions without requiring a centralized trust registry or public key directory, new CAs, changes to DNS infrastructure, or changes to browser trust store governance processes.

### Trusted identifiers

An entity requires trusted identifiers it owns and controls for enabling trusted introductions and conducting trustworthy digital transactions. An entity’s DID is a standards-based identifier it controls that can be globally verified using authoritative DNS and PKI.

DNS and PKI are long established, well understood, and widely used in digital transactions. Both infrastructures have established processes for the lifecycle management of entities that use their services and are a cornerstone of global digital interactions.

The implementation process below uses these existing mechanisms to enhance the authenticity and discoverability of DIDs by:
- Digitally signing the DID Document with a Digital Signature Certificate from a PKI, to ensure a binding between the DID and the signatory.
- Registering and storing information in DNS, that in turn is protected by DNSSEC, to enhance the discoverability and ensure a binding between the DID and the domain owner.

Much like the use of multi-factor authentication to provide a higher level of assurance, the use of DNS and PKI, two independent, well established and authoritative infrastructures, enables a very high assurance ownership verification of the DID by demonstrating the same entity's control over the Digital Signature Certificate, the DNS record, and the DID Document.

The DID can now be used in higher order capabilities such as verifiable attestations that are components of many digital transactions.

#### Implementation Process

The implementation is a straightforward process:

1.  Create a unique `DID` and it's `DID document`, associated with an authoritative domain
2.  Register the `DID`, via a DNS `URI` record, with the authoritative domain to bind the domain to the `DID` and enable it's secure distribution
3.  Obtain a Digital Signature Certificate, from an authoritative CA
4.  Use the private key to generate a digital signature on the `DID Document`, to ensure the document's integrity and to bind the document to the signatory
5.  Register the public key that can verify the digital signature, via a DNS `TLSA` record, with the authoritative domain to bind the domain to the digital signature certificate, and enable it's secure distribution

### Verifiable attestations

A compelling use of trusted identifiers is the capability is to “sign with my domain”. Simply put, your domain name, as a well-known website to your users, becomes a trusted identifier you can use to sign anything.

“Sign with my domain”  provides an immediate benefit to domain name owners using domain name registrars and CAs to enable the implementation of trusted identifiers. It works regardless of whether they are a government organization or an individual - it works for everyone because this approach embraces the open web.

For example, the .gov top level domain (TLD) is a globally recognized root of trust. The world does not question the authority of the usa.gov or usajobs.gov websites. Any posts, news releases, or job openings hosted on those sites have the full confidence that they are authentic and issued with the full authority of the U.S. Government (USG).

Similarly, GSA’s PKI Shared Services Provider Program offers Digital Signature Certificate Services to help Agencies achieve digital signature interoperability.

In the current world of deep-fakes and inauthentic information, this DID-enabled “sign with my domain name” ability can extend the confidence of authority in the .gov TLD to the world of attestations such that they can be independently verified that it was issued by a USG entity using widely available standards-based mechanisms.  

An easily recognizable DID (e.g. did:web:agency.gov) could be used to sign official attestations such that they can be globally verified. 

- Attestations can use a variety of data formats (VCDM, binary, JSON, mdoc, XML etc) and can be moved from point to point via a variety of transfer protocols (websocket, HTTPS, SCIM, BLE, NFC, issuance and exchange protocols etc). 

However, this architecture will use attestation data formats, digital signature mechanisms, and transfer protocols chosen to meet DHS requirements for security, privacy and interoperability.

* * *
The terminology and the descriptions of the building blocks are adapted from authoritative descriptions of the same by NIST, IETF and W3C. The concepts around linking DNS with DIDs were first articulated in the IETF Internet Draft “High Assurance DIDs with DNS” by J. Carter & J. Latour (CIRA), M. Glaude (Northern Block), T. Bouma (Digital Governance Council)