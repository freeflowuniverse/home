# Milestone 1: Basic working & Setup

## What do we want to achieve in milestone 1

- first basic working of digital twin technology
- deployment & basic testing of digital twins
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

* Should be able to run queries on grid network;
* Should be able to check the result of each query
* The query result should contain identity/location information from a different twin.


## Acceptance criteria for milestone 1:

* [ ] technology choices
    * [ ] RMB is created in golang or vlang
    * [ ] PNIC is created in golang or vlang
    * [ ] Digital Twin is created in vlang 
* [ ] infrastrucure as code concept:
    * [ ] Should be able to run, stop and restart the entire infrastructure using IAC concept
    * [ ] by means of a vlang based script
    * [ ] by means of a terraform based script
    * [ ] by means of kubernetes scripts
    * [ ] twins can be deployed
    * [ ] planetary network be deployed (with integrated RMB)
* [ ] monitoring
    * [ ] rest based endpoints are available to check health
* [ ] compatibility
    * [ ] need to be able to demonstrate how every javascript based project will be able to communicate & work with this backend technology