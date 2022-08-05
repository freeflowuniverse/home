


Digital Twin primitive: composable self-contained for sovereign digital life


# 



    * 

# 
    *Use of Funds

    * This first grant application supports a proof of concept platform development to meet the technological and business needs of _Digital Twin_


## Proof of Concept

- Building first primitives
    - Implement first functionalities inside Domain Specific Language
        - Find a digital twin by his twin_id (or handle)
            - Request connection permission 
                - Approve
                - Create trusted circles with pairs of digital twins 
                - Deny permission 
                - Revoke permission 
        - Start message chat with another digital twin 
            - Send a text message (no interface)

- Expand and solidify phase (primitive DSL) 
    - _Connect with different blockchains through the digital twin _
    - _Exchange files using the decentralized grid _
    - _Permission access layer to specific files inside my cloud storage_
    - _Interface UI/UX_
    - _Deploy production Digital Twin on the decentralized grid _
    - _The first production uses cases (alternative zoom, WhatsApp, storage)

- Build dAPP to set us free from big corporation services 
    - Alternative to Spotify 
    - Alternative Airbnb 
    - Alternative Uber eats
    - Alternative TicketMaster


## Project Scope

The scope of this grant refers to item 1 described above. The same enrollment process will be done when the previous one is finished. The aiming goal is to complete all the three steps of development of the technology itself to achieve its full potential 

All the specific milestone described and detailed below refers again to proof of concept item 1


# Milestone 1: Build and Setup the first primitive implementation

## Chosen technologies:


ThreeFold is a reliable system that guarantees that data can never be lost or corrupted. The local instance of the internet would always be running, even though the public internet goes down. 

There is a **considerable shift to have guaranteed** that the most remote community would have access to every fundamental resource in terms of access and connectivity. We are very proud of collaborating with ThreeFold, which is building an entire grid to provide all those benefits.


### Threefold Grid3

* The infrastructure is the network of 3Node that the digital twin will be hosted on.

### Planetary Network

* Network of twins and nodes on TF Grid, used for finding and sending messages to twins via RMB.
* Uses YGGDRASIL _(Is an overlay network implementation of a new routing scheme for mesh networks. It is designed to be a future-proof decentralized alternative to the structured routing protocols commonly used today on the Internet and other networks.) Repository: https://github.com/yggdrasil-network/yggdrasil-go_
* Repository: https://github.com/threefoldtech/planetary_network

### Zero OS

* Repository: [https://github.com/threefoldtech/zos](https://github.com/threefoldtech/zos)

### Reliable Message Bus

* Rust RMB Repository: [https://github.com/threefoldtech/rmb-rs](https://github.com/threefoldtech/rmb-rs) 
* Rust RMB SDK Repository: [https://github.com/threefoldtech/rmb-sdk-rs](https://github.com/threefoldtech/rmb-sdk-rs) 
* TS Client: [https://github.com/threefoldtech/rmb_ts](https://github.com/threefoldtech/rmb_ts) 
* RMB Vlang: [https://github.com/threefoldtech/rmb](https://github.com/threefoldtech/rmb) 
* RMB Go: [https://github.com/threefoldtech/rmb_go](https://github.com/threefoldtech/rmb_go) 
* Design Document: [https://github.com/threefoldtech/rmb-rs/blob/development/docs/readme.md](https://github.com/threefoldtech/rmb-rs/blob/development/docs/readme.md)  \

* 

Accomplishments:



* The recommended architecture for running Digital Twin should be automated via infrastructure script (terraform like);
    * **Acceptance criteria:** 
        * Should be able to run, stop and restart the entire infrastructure using commands.
        * Create a molude that will set it up the v lang backend 
            * Clear documentation on how to run each module of terraform with minimum interdependency. The user (dev) must be able to run, stop or restart 
* Enable an infrastructure status check endpoint;
    * Required services health check running.
        * **Acceptance criteria:**
        * Should be able to make an HTTP request to an endpoint and get a JSON response from all service statuses.
            * Node service 
            * Gossip protocol 
            * RMB rust engine 
            * Vlang handler 
        * All the services must have a /status endpoint or method that will return a JSON response with relevant health data.


## Milestone 2: Connect with another Digital Twin

Finding another Digital Twin by the twin id is a new use case required for exchanging information between N instances of use.

For example, the implementation of "findDigitalTwinById()" should exist upon instance DSL to provide extensibility and connectivity with multiple peers on the grid. 

This milestone will be achieved by implementing the primitives both on NodeJS Backend and Rust DSL Engine.

**_Accomplishments_**:



* Setup Redis for Reliable Message Bus usage; provide a fail-safe, cluster-based deployment that will guarantee that the messages will be consistent in disaster scenarios
    * **Acceptance Criteria:**
        * The Redis infrastructure must have a cluster with at least three instances, periodic disk/static storage snapshots, and recovery from crashes
        * When recovering from a crash/unexpected stop, all events should be processed as expected without integrity issues
* NodeJS Backend up and running; 
    * **Acceptance Criteria:** \
	-  HTTP server that will be integrated with RMB return the status response, and be as stateless as possible
        * Should be able to make HTTP requests with success and failures status.
        * SSL must be used in all connections
    * Implementation:
        * Security validations are required to be performed on each endpoint (using a middleware that must sanitize the user inputs)
        * GET/POST /query?params={params} => Receives the arguments and relay them to the RMB client. Hang the connection until the query is sent to rmb and a corresponding response is received.
        * GET/POST /query?async=true&params={params} => Receives the arguments and relay them to the RMB client. Returns an transaction_id that will be used to obtain the response
            * GET /query/{id} obtains the response for the async operation
        * GET/POST /op?params={params} => Perform transaction on the Blockchain such as receiving mnemonics from the user, accessing an account  or performing transactions on a chain (except for TF Grid)
        * Outbound RMB: Will relay messages received through the HTTP methods to Rust Engine via RMB client  and receive a transaction-id.
        * Inbound RMB: Will query for messages on RMB using the transaction id. The inbound messages will be received from Rust Engine.
* Use of V lang handler to make communicate with Rust
    * **Acceptance Criteria:**
        * Must be able to run primitives through RMB on Rust Engine; 
        * Must implement business logic that will be used to call DSLs on Rust Engine
    * **Implementation**:
        * **Inbound RMB**: WIll receive inbound messages via RMB from Rust Engine. The messages will contain information on the target twin-id, perform access control and obtain twin data via Twin Client.
        * **Outbound RMB**: Will forward resulting twin data to Rust Engine
* Implement the Gossip Protocol to enable the search through the grid
    * **Acceptance Criteria:**
        * Should be able to run queries on grid network;
        * Should be able to check the result of each query
        * The query result should contain identity/location information from a different twin.


## Milestone 3: Setup, a Digital Twin, trusted network

This feature enables the ability to create a trusted network with different Digital Twins to establish connectivity. 

Once a Digital Twin belongs to your trusted network, you'll be able to exchange data, interact via different applications, and build customized apps that can be shared with the network.

A trusted network helps create high-level relationships between different nodes. This trust will boost the creation of a new business that positively impacts the network value.

**Accomplishments:**


* The connection sent should contain a list of required properties to share information.
* Ask permission to connect with a different digital twin through TF Grid Client and Rust RMB Client.
* Implement the "Grant connection" feature on the DSL Engine
* Implement the "Deny connection" feature on the DSL Engine
* Implement the "Revoke connection" feature on the DSL Engine
* Only selected properties should be shared with another digital twin
    * The control of the data should belong to the digital twin's owner
* Via API should be possible to list all your trusted network
    * Show only granted data by each digital twin

 -  The "chat" app should be running upon node instance, and the data should be stored using P2P technology



    * Using threefold technologies, we can guarantee the data's security, privacy, and reliability.
* Implement a POC application that will be able to ping and ack a connected digital twin. 

**Acceptance criteria:**



* Must be able to get connection request messages. For example: _"Twin_ID XXX wants to create a connection and share the location and a list of all available Apps."_
* The grant, deny and revoke connection should use OAuth 2.0 and OpenId Connect to ensure a trustable and transparent process for the information sharing. 
* Should be able to get information data from a digital twin via API (HTTP request)
* Should be able to list all succeeded grant request permissions
* Should be able to list all denied grant request permissions
* The ping application must restrict the communication to the minimal amount of data used to check if the connected twin is still active. 

**Implementation**

* **Grant**, **Revoke** and **Deny** features will be provided via a Oauth 2.0 implementation ([RFC](https://datatracker.ietf.org/doc/html/rfc6749)):
    * Track
        * **POST **/track

                **action**=action-id

            * List twin's authorization requests, denials and approvals. Will be used only for the owner of the Twin Account to check their own history.
    * Authorization flow
        * **GET **/authorize  **response_type**=code&**client_id**={twin_id_requester}&**redirect_uri**=https://callback.from.app&**scope**=data+that+twin+will+access&**state**=state_validation&**code_challenge**=pkce_validation&**code_challenge_method**=S256: renders authorization page. 
        * **POST **/authorize  **response_type**=code&**client_id**={twin_id_requester}&**redirect_uri**=https://callback.from.app&**scope**=data+that+twin+will+access&**state**=state_validation&**code_challenge**=pkce_validation&**code_challenge_method**=S256: submits authorization accept and receives authorization code
        * **POST **/token

            **grant_type=**authorization_code


            **&client_id=**twin_id


            **&client_secret=**twin_secret


            **&redirect_uri=**https://callback.from.app


            **&code=**code_received_on_post_authorize


            **&code_verifier=**verifier_from_authorize: submits authorization validation and obtains twin access token and refresh token

    * Revoke flow
        * **POST **/revoke

            **twin-id**=twin_id_whon_will_revoke_access: invalidate refresh token used by this twin-id.  



# Milestones Breakdown


# KPIs and Beta Launch Outcomes

We will accomplish the essential proof of concept functionality when 500 users create their digital twins and invite at least one new user to build their trusted network.


# Development Approach

We've broken down our technical milestones into three modules for this grant proposal with a total project duration of 7 months and a budget of 300,000 Euros.

We provide a more detailed breakdown of the development during each milestone in the Milestone section of the application.

Platform development uses Rust, NodeJS, VLang, and Redis.


# Explanation as to how your proposed project would benefit the DEVxDAO ecosystem AND/OR support transparent and open source scientific research and/ or development if applicable.

_ASK ROBERT HELP  IN HERE_


# Under which open source license(s) will you publish any research and development associated with your proposed Project? All research papers or the like should be in Creative Commons.

_MIT License_


# Your resume (Linkedin) or Git (For developers)

_LINKEDIN GAVA + LINKEDIN DEVs_

Grant details

Please enter the total amount you are requesting as a grant:

300.000

Will payments for this work be made to an entity such as your company or organization instead of to you personally?

DEFINIR

Please select all planned uses for your grant funds. Select all that apply and enter the estimated portion of grant funds allocated for each. All totals must equal the upper amount.

Salary and other personal compensation 

Percentage kept by OP: 25%

Travel and conferences

Percentage kept by OP: 0%

Software, tools, infrastructure 

Percentage kept by OP: 0%
