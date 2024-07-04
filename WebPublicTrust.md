---
title: Web of Public Trust
layout: page
permalink: /WebPublicTrust/

sidenav: secondary
subnav:
  - text: Digital Signatures & PKI
    href: '#digital-signatures--pki' 
  - text: Domain Name System & DNSSEC
    href: '#domain-name-system--dnssec'
  - text: Self-Certifying Identifiers & DIDs
    href: '#self-certifying-identifiers--dids'
---

<div class="usa-alert usa-alert--warning usa-alert--slim">
  <div class="usa-alert__body">
    <p class="usa-alert__text">
      We are currently evaluating various options that use existing technologies and standards to implement and demonstrate a scalable approach that does not require a centralized "trust registry", changes to DNS infrastructure, changes to Certificate Authorities, or changes to browser trust store governance processes.
    </p>
  </div>
</div>

Transactions conducted on the web between entities are reliant on trusted introductions over widely available infrastructure. 

Trusted introductions are done using identifiers that represent the entities. 

For high value transactions, such as credential issuance and verification, confidence that the identifiers represent and are controlled by the entities participating in the transactions are a necessary first step. 

The technical building blocks that make such trusted introductions possible are:

### Digital Signatures & PKI

As a digital analogue to a written signature, a digital signature provides assurances that the claimed signatory signed the information, and the information was not modified after signature generation.

Signature generation uses a private key to generate a digital signature; signature verification uses a public key that corresponds to, but is not the same as, the private key. Each signatory possesses a private and public key pair. Public keys may be known by the public; private keys are kept secret. Anyone can verify the signature by employing the signatory’s public key. Only the entity that possesses the private key can perform signature generation.

A public key infrastructure (PKI) is a framework that is established to issue, maintain and revoke the certificates. A Certificate Authority (CA) in a PKI is the entity responsible for issuing certificates that can be used for digital signature generation.

### Domain Name System & DNSSEC

The Domain Name System (DNS) is a distributed computing system that enables access to Internet
resources by user-friendly domain names rather than IP addresses, by translating domain names to IP
addresses and back.

Domain Name System Security Extensions (DNSSEC) provide origin authentication and integrity protection for DNS data, as well as a means of public key distribution.

### Self-Certifying Identifiers & DIDs

A Self-Certifying Identifier (SCID) is an identifier that is uniquely and cryptographically derived from the initial content of an identified object, and forms some or all of the object identifier.

Decentralized Identifiers (DIDs) are a type of identifier that enables the controller of a DID to prove control over it without requiring permission from any other party. DIDs associate an entity (DID Subject) with a set of set of data describing the entity (DID Document), including mechanisms such as public keys.

Using a SCID in a DID enables a set of features that allow for the implementation of critical functionality such as data integrity and pre-key-rotation, without sacrificing an entity's agency and control over its own identifier.   

## Using the Building Blocks

...

