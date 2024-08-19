# Project Name - Technical Architecture

- [Project Name - Technical Architecture](#project-name---technical-architecture)
  - [Overview](#overview)
    - [System Context Diagram](#system-context-diagram)
    - [Container Diagram](#container-diagram)
    - [Component Diagram (optional)](#component-diagram-optional)
    - [Code Diagram (optional)](#code-diagram-optional)
    - [Deployment Diagram](#deployment-diagram)


## Overview
This document outlines the proposed technical architecture, using the C4 model for software architecture visualization: https://c4model.com/ 


### System Context Diagram
The system context diagram defines how this entire system fits in to the world around it. It identifies the users who will interact with the system, and any external services.

![Placeholder](https://via.placeholder.com/500x300)

### Container Diagram
The container diagram breaks down the components that make up this system, where each component is generally a single deployable entity (e.g. a backend service, a user-persona, a web app, a VM). 

![Placeholder](https://via.placeholder.com/500x300)

### Component Diagram (optional)
Component diagrams further breaks down a single component into the specific code modules that make it up (e.g. different modules in an Angualr app, or controllers, business-logic services, data-access services).

Not everything needs a component diagram, usually it's enough to do System Context and Containers.

![Placeholder](https://via.placeholder.com/500x300)

### Code Diagram (optional)
Code diagrams are low-level UML diagrams used for documentign specific implementation details, like state machines, ERDs, etc.. 

Just like the component diagram, these are optional, and many systems won't need this level of detail.

![Placeholder](https://via.placeholder.com/500x300)


### Deployment Diagram
This diagram is what many think of as a "technical architecture" diagram. It outlines the infrastructure compoents that make up the technical solution.

Here, you'd call out any cloud services, key technologies (like load balancers, reverse-proxies, firewalls), and anything else that is used in the actual deployment of your system.

![Placeholder](https://via.placeholder.com/500x300)