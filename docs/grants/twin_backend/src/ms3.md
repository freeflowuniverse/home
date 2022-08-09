
## Milestone 3: Build first DSL engines starting creating value

This feature enables the ability to create a trusted network with different Digital Twins to establish connectivity. 
Once a Digital Twin belongs to your trusted network, you'll be able to exchange data, interact via different applications, and build customized apps that can be shared with the network.

A trusted network helps create high-level relationships between different nodes. This trust will boost the creation of a new business that positively impacts the network value.

## Acceptance criteria for milestone 1:

* [ ] functionality
    * [ ] Implement the "Grant connection" feature on the DSL Engine
    * [ ] Implement the "Deny connection" feature on the DSL Engine
    * [ ] Implement the "Revoke connection" feature on the DSL Engine
    * [ ] Only selected properties should be shared with another digital twin
        * [ ] The connection sent should contain a list of required properties to share information
    * [ ] Ask permission to connect with a different digital twin through TF Grid Client and Vlang Client.
* [ ] security
    * [ ] each message is end2end encrypted
    * [ ] each message cannot get corrupted
