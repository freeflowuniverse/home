# Milestone 1: Basic working & Setup

## What do we want to achieve in milestone 1

- first basic working of digital twin technology
- deployment & basic testing of digital twins
- ping service implemented (prove the concept is working)
- demonstrate the basic working network primitives

## Chosen technologies:

There is a **considerable shift to have guaranteed** that the most remote community would have access to every fundamental resource in terms of access and connectivity. We are very proud of collaborating with ThreeFold, which is building an entire grid to provide all those benefits.


### TFGrid

* The infrastructure is the network of 3Node that the digital twin will be hosted on.
* see https://www.threefold.io

### Digital Twin Technology (FreeFlow Twin)

* The code will be in https://github.com/freeflowuniverse
* is NodeJS or VLANG based user centric app, deployed on Zero-OS using FFChain & Planetary network for communication

see [Digital Twin Architects](architecture/twins.md)

### FFChain

* Is a local blockchain which is deployed together with the Planetary network & nodes
* Choice to be made which blockchain we go for could be Algorand Sidechain, Casperlabs, Cosmos...

### Zero OS

* Ultra scalable low level operting system
* Repository: [https://github.com/threefoldtech/zos](https://github.com/threefoldtech/zos)

### Planetary Network

* Repository: https://github.com/freeflowuniverse/freeflow_network
* see [Planetary Network Architects](architecture/planetary_network.md)

## Implementation Remarks

Finding another Digital Twin by the twin id is a new use case required for exchanging information between N instances of use.

For example, the implementation of "findDigitalTwinById()" should exist upon instance DSL to provide extensibility and connectivity with multiple peers on the grid. 

This milestone will be achieved by implementing the primitives both on NodeJS Backend and Rust DSL Engine.

This feature enables the ability to create a trusted network with different Digital Twins to establish connectivity. 

Once a Digital Twin belongs to your trusted network, you'll be able to exchange data, interact via different applications, and build customized apps that can be shared with the network.

A trusted network helps create high-level relationships between different nodes. This trust will boost the creation of a new business that positively impacts the network value.

* Should be able to run queries on grid network;
* Should be able to check the result of each query
* The query result should contain identity/location information from a different twin.


## Acceptance criteria for milestone 1:

* [ ] base features
    * [ ] ping service on each digital twin
    * [ ] ability for twins & browsers to communicate to each other (safe, scalable, secure)
    * [ ] ability for twins & twins to communicate to each other
    * [ ] reliablity, scale & performance is embedded requirement of the solution
* [ ] technology choices
    * [ ] blockchain has been chosen and can be deployed, minimal requirements met
    * [ ] RMB is created in golang or vlang
    * [ ] PNIC is created in golang or vlang
    * [ ] Digital Twin is created in vlang or nodejs
* [ ] infrastrucure as code concept:
    * [ ] Should be able to run, stop and restart the entire infrastructure using IAC concept
    * [ ] by means of a vlang based script
    * [ ] by means of a terraform based script
    * [ ] by means of kubernetes scripts
    * [ ] chosen blockchain can be deployed
    * [ ] twins can be deployed
    * [ ] planetary network be deployed (with integrated RMB)
* [ ] basic communication requirements
    * [ ] Browser can communicate over websockets to planetary network and/or digital twin
    * [ ] Browser can use typed/complex messages (type security)
    * [ ] Twins can talk to each other using PNIC (Planetary Nics)
    * [ ] PNICs can communicate to each other over websockets (or equivalent choice)
* [ ] monitoring
    * [ ] rest based endpoints are available to check health
* [ ] compatibility
    * [ ] need to be able to demonstrate how every javascript based project will be able to communicate & work with this backend technology