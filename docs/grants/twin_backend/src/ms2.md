
# Milestone 2: Security, Redundancy and Scalability

In milestone one we have been able to demonstrate that the system can be setup and the basic ping service is working.

This milestone is all about Security, Redundancy and Scalability

Its important in such a system we finetune the components to make sure that minimal required perofrmance and scale can be achieve.

## Acceptance criteria for milestone 2:

* [ ] performance / Scalability
    * [ ] 1000 twins can be deployed < 2h
    * [ ] 1000 twins can be communicate to each other for at least 1 message per sec
    * [ ] **+5000 transactions per second can be achieved over total system**
    * [ ] architecture insight (based on logic), that this sytem can scale to millions of users
* [ ] global approach
    * [ ] Deploy twins over +10 countries
    * [ ] Demonstrate how the twins can communicate to each other using different ISP's
    * [ ] Demonstrate how a broken node gets twins to relocate and continue operations
* [ ] security
    * [ ] each message is end2end encrypted
    * [ ] each message cannot get corrupted
* [ ] redundancy
    * [ ] when network link goes down, and there is still another network link possible the system can find the new path < 2 minutes worst case
    * [ ] if a direct network connection is not possible, the system can route traffic over another node (hop over nodes)
    * [ ] any node going down should not have impact on uptime of system
    * [ ] If network is down, the messages will be queued and retried untill timeout
