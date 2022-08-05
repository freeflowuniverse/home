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



## Accomplishments

### Automated Install

The recommended architecture for running Digital Twin should be automated via infrastructure script (terraform like);

#### Acceptance criteria:

* Should be able to run, stop and restart the entire infrastructure using commands.
* Create a module that will set it up the v lang backend 
    * Clear documentation on how to run each module of terraform with minimum interdependency. The user (dev) must be able to run, stop or restart 

### Embedded Monitoring Status

Required services health check running.

#### Acceptance criteria:

* Should be able to make an HTTP request to an endpoint and get a JSON response from all service statuses.
    * Node service 
    * Gossip protocol 
    * RMB rust engine 
    * Vlang handler 
* All the services must have a /status endpoint or method that will return a JSON response with relevant health data.

