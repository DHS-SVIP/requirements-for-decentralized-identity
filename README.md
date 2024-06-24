
# DHS Technical Implementation Requirements for Decentralized Identity

These technical implementation requirements have been chosen to meet the operational needs of U.S. Citizenship and Immigration Services, U.S. Customs and Border Protection and the DHS Privacy Office for implementing digital credentialing capabilities relevant to:

- Citizenship and immigration
- Cross-border travel
- Cross-border trade

The requirements seek to balance the robustness principle with a philosophy of "AND not OR" to ensure that the capabilities that incorporate these requirements can serve the diverse and global customer base of both CBP and USCIS in a secure, privacy respecting manner while enabling global interoperability at the technical level.

> [!IMPORTANT]
> This is a work in progress. It will be updated as requirements and availability of standards-based technical choices  evolve, and testing and evaluation is conducted to verify the privacy, security, interoperability and scalability of the choices made.   

## Conventions Used

The International Organization for Standardization (ISO) uses specific verbal forms to convey clarity on what is a requirement and what is a recommendation or other type of statement.

The requirements on the following pages adopt and use the following ISO document conventions:

- Requirements - SHALL, SHALL NOT
- Recommendations - SHOULD, SHOULD NOT
- Permission - MAY, MAY NOT
- Possibility and Capability - CAN, CANNOT

## Scope of Requirements

The requirements span the use of personal credentials for both in-person and online usage scenarios, and the use of supply chain organization credentials for online usage scenarios.

![Requirements for Personal and Supply Chain Credentials](/img/Requirements-Personal-SupplyChain.png)

- [Personal Credential](PersonalCredential.md)
    - Implementation Principles
    - Distribution and Retrieval of DHS Public Key
    - Personal Credential Use (In Person)
    - Personal Credential Use (Online)
    - DHS Personal Credential Issuer
        - Accessibility & Openness
        - Platform & Software Security
        - Credential Formats & Digital Signatures
        - Metadata & Vocabulary
        - .gov Binding (TBD)
        - Issuance Protocol (TBD)
    - DHS Personal Credential Verifier
        - Accessibility & Openness
        - Platform & Software Security
        - Credential Formats & Digital Signatures
        - Metadata & Vocabulary
        - .gov Binding (TBD)
        - Exchange Protocol (TBD)
    - DHS Personal Credential Holder (Digital Wallet)
        - Accessibility & Openness
        - Platform & Software Security
        - Credential Formats & Digital Signatures
        - Issuance Protocol (TBD)
        - Exchange Protocol (TBD)
    - Normative References

- [Organization (Supply Chain) Credential](OrganizationCredential.md)
    - CBP/Trade Issuer
        - Credential Formats & Digital Signatures
        - Metadata & Vocabulary
        - Issuance Protocol
    - CBP/Trade Verifier
        - Credential Formats & Digital Signatures
        - Metadata & Vocabulary
        - Exchange Protocol   
    - Normative References

## Changelog

| Date           |  Version  |                   Comments |
|----------------|:---------:|---------------------------:|
| March 18, 2024 |   1.0.0   |        Initial Publication |

