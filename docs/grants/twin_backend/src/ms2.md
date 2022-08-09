
# Milestone 2: Connect with another Digital Twin

Finding another Digital Twin by the twin id is a new use case required for exchanging information between N instances of use.
For example, the implementation of "findDigitalTwinById()" should exist upon instance DSL to provide extensibility and connectivity with multiple peers on the grid. 
This feature enables the ability to create a trusted network with different Digital Twins to establish connectivity. 
Once a Digital Twin belongs to your trusted network, you'll be able to exchange data, interact via different applications.

## Acceptance criteria for milestone 2:


* [ ] global approach
    * [ ] Demonstrate how the twins can communicate to each other using different ISP's
    * [ ] Demonstrate how a broken node gets twins to relocate and continue operations
* [ ] base features
    * [ ] ping service on each digital twin
    * [ ] ability for twins & browsers to communicate to each other (safe, scalable, secure)
    * [ ] ability for twins & twins to communicate to each other
    * [ ] reliablity, scale & performance is embedded requirement of the solution
* [ ] basic communication requirements
    * [ ] Browser can communicate over websockets to planetary network and/or digital twin
    * [ ] Browser can use typed/complex messages (type security)
    * [ ] Twins can talk to each other using PNIC (Planetary Nics)
    * [ ] PNICs can communicate to each other over websockets (or equivalent choice)
    * [ ] Ping service application that will be able to ping and ack a connected digital twin.
