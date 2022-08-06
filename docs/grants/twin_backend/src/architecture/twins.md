
# Architecture Twins

Each user has a digital twin, the user interacts with the digital twin through e.g. a browser but in future can be voice, chat, metaverse exerpience.

```mermaid
graph TD
    User1[User 1] ---  Browser1
    Browser1 --- |websockets| TWIN1
    User2[User 2] ---  Browser2    
    Browser2 --- |websockets| TWIN2
    User3[User 3] ---  Browser3    
    Browser3 --- |websockets| TWIN3
    TWIN1 --- p{PLANETARY NETWORK}
    TWIN2 --- p{PLANETARY NETWORK}
    TWIN3 --- p{PLANETARY NETWORK}

```

- Each digital twin is private for the user and only the user has access to it.
- The browser communicates over websockets (private and encrypted) per user to their twin.
- The twins talk to each other over the planetary network

## Experiences

```mermaid
graph TD
    User ---  Browser
    Browser --> a1[Whatsapp Alternative]
    Browser --> a2[Gdocs Alternative]
    Browser --> a3[Zoom Alternative]
    Browser --> a4[LinkedIn Alternative]
    Browser --> a5[Facebook Alternative]
    Browser --> a6[many more ...]
        a1 --> TWIN
    a2 --> TWIN
    a3 --> TWIN
    a4 --> TWIN
    a5 --> TWIN
    a6 --> TWIN
    TWIN --- p{PLANETARY NETWORK}

```

## Each twin has multiple experiences

Some example applications ready to be launched on top of the digital twin, it requires the purpose of this grant which is an improved communication mechanism between the twins.

### Metaverse


![](img/metaverse.png)  

### Gdoc/Whatsapp/... alternative

![](img/uhuru.png)  


