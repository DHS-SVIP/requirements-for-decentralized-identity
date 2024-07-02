---
title: Under Consideration
layout: page
permalink: /UnderConsideration/

sidenav: secondary
subnav:
  - text: Issuance Protocol
    href: '#issuance-protocol-personal-credential'
  - text: Exchange Protocol
    href: '#exchange-protocol-personal-credential'
  - text: Credential Rendering
    href: '#credential-rendering-personal-credential'

---

## Issuance Protocol (Personal Credential)

<div class="usa-alert usa-alert--warning usa-alert--slim">
  <div class="usa-alert__body">
    <p class="usa-alert__text">
      Following many-to-many, multi-vendor interoperability testing, DHS will update the requirements for issuance protocols
    </p>
  </div>
</div>

- DHS hopes to support multiple issuance protocols
- Issuance protocol SHALL:
    - support required credential format & digital signature mechanisms
    - support required metadata and vocabulary distribution and verification mechanisms
    - enable the Holder to choose a digital wallet
    - disregard (via implementation profiles) external dependencies that are duplicative or not utilized by the DHS Issuer
- Options under consideration include:
    - W3C CCG VC-API
    - W3C CCG VC-API + W3C CCG CHAPI
    - OIDF DCP OID4VCI
    - OIDF DCP OID4VCI + W3C CCG CHAPI

## Exchange Protocol (Personal Credential)

<div class="usa-alert usa-alert--warning usa-alert--slim">
  <div class="usa-alert__body">
    <p class="usa-alert__text">
      Following many-to-many, multi-vendor interoperability testing, DHS will update the requirements for exchange protocols
    </p>
  </div>
</div>

- DHS hopes to support multiple exchange protocols
- Exchange protocol SHALL:
    - support required credential format & digital signature mechanisms
    - support required metadata and vocabulary distribution and verification mechanisms
    - enable the Holder to choose a digital wallet
    - disregard (via implementation profiles) external dependencies that are duplicative or not utilized by the DHS Verifier
- Options under consideration include:
    - W3C CCG VC-API
    - W3C CCG VC-API + W3C CCG CHAPI
    - OIDF DCP OID4VP
    - OIDF DCP OID4VP + W3C CCG CHAPI
    - W3C WICG Digital Credentials API

## Credential Rendering (Personal Credential)

<div class="usa-alert usa-alert--warning usa-alert--slim">
  <div class="usa-alert__body">
    <p class="usa-alert__text">
      Following testing and evaluation, DHS will update the requirements for credential rendering
    </p>
  </div>
</div>

- DHS is seeking a protocol independent mechanism for visually rendering an issued credential in a manner that preserves DHS branding
- Currently exploring the *renderMethod* extensibility point built into the \[W3C-VC-DATA-MODEL\]. More information can be found at [W3C CCG Verifable Credential Rendering Methods](https://w3c-ccg.github.io/vc-render-method/)
