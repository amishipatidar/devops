## Task 4: Docker Overlay Network

### What is an Overlay Network?

A Docker overlay network allows containers running on different Docker hosts to communicate with each other through a single virtual network.

### Use Cases

Overlay networks are useful for distributed applications where containers or services run across multiple Docker hosts.

Common use cases include:
- Docker Swarm
- Distributed applications
- Microservices running across multiple servers
- Communication between containers on different Docker hosts

### How Overlay Networks Work

An overlay network creates a virtual network that spans multiple Docker hosts. Containers connected to the overlay network can communicate with each other even when they are running on different physical or virtual machines.

### Bridge vs Overlay Network

| Feature | Bridge Network | Overlay Network |
|---|---|---|
| Scope | Single Docker host | Multiple Docker hosts |
| Container communication | Same host | Across multiple hosts |
| Distributed applications | Limited | Supported |
| Common use | Local containers | Distributed applications |
| Docker Swarm | Not required | Commonly used |
