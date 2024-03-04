
<!--
### Hi there 👋
**c6ai/c6ai** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on the GitHub profile.
-->

## 1stWallet Sequence Diagram v240224a:
```mermaid
%%{init: {'themeVariables': {'fontFamily': 'Bernard MT Condensed', 'fontSize': '24px','fontWeight': 'bold'}}}%%
sequenceDiagram
    participant A as Constituent VC-Holder
    participant B as SSI Custodial/Guardianship Wallet
    participant C as Verification Authenticator
    participant D as Revocation/Issuance Keycloak
    participant E as Zero-Trust Registry Service
	actor A
    Note right of D: vSPACE IaC for Trust Over IP (ToIP)
    A->>+B: Request wallet signature
    B-->>-A: Provide signature
    A->>+C: Submit signature
    Note right of B: SSI with Zero-Trust Architecture (ZTA)
    C->>+D: Verify signature provided
    loop Continuous Auth
        B-->>B: sync cached verification or extend validity of access bearer token
    end
    D->>+E: Request wallet's public key
    E-->>-D: Send wallet's public key
    D-->>-C: Use public key to verify signature
    Note right of B: Scalable, Privacy-Aware and Confidential EMS
    C-->>-A: Authentication status
```
