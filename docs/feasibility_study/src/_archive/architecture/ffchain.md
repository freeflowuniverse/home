# FreeFlow Chain Architecture

```mermaid
graph TD
    User1[User 1] ---  Browser1
    Browser1 --- |websockets| TWIN1
    User2[User 2] ---  Browser2    
    Browser2 --- |websockets| TWIN2
    User3[User 3] ---  Browser3    
    Browser3 --- |websockets| TWIN3
    TWIN1 --- p{FreeFlow Chain}
    TWIN2 --- p{FreeFlow Chain}
    TWIN3 --- p{FreeFlow Chain}

```

The FreeFlow chain will be based on to be chosen blockchain.

The blockchain will provide following functions

- identity management
    - kyc verification (with link to 3e party providers)
    - DID support
- circles
    - people get grouped into circles
- authentication/verification
    - proof of authenticity
    - audit log of security events
- DAO features
- Address Book (like a sort of phonebook)
- Financial Management/money as relevant for this product
