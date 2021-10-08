# Cab_hailing_application
There are two phases of this application, one uses Java and other Akka

Project 1 is done using spring framework to implement 3 microservices (CAB, RIDE_SERVICE and WALLET), each microservice was containedin a separate container. Containers were deployed using kubernetes. There were a variable number of RideService instances, from 1‑4, whichchanges at runtime based on the load. The RideService instances were stateless, so that any request can be directed to any instance (kubernetesshould manage the forwarding of requests to RideService instances using load balancing). All RideService instances uses a common databaseservice which is deployed separately outside.

Project 2 is done using Actor system in Akka framework. There were a cluster of nodes. Each cab was a cluster‑sharded entity with persistence.Therefore, if a Cab actor resides on a node and if that node goes down, the cab will be migrated automatically to some other node whilepreserving its state. The RideService actors were also a cluster‑sharded entities, but without persistence.
