[![N|Solid](https://www.bobit.us/images/bobit-logo.png)](https://www.bobit.us/)

# DOCKER INTRODUCTION

Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications. By taking advantage of Docker’s methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

# The Docker Platform

Docker provides the ability to package and run an application in a loosely isolated environment called a container. The isolation and security allow you to run many containers simultaneously on a given host. Containers are lightweight because they don’t need the extra load of a hypervisor, but run directly within the host machine’s kernel. This means you can run more containers on a given hardware combination than if you were using virtual machines. You can even run Docker containers within host machines that are actually virtual machines!

Docker provides tooling and a platform to manage the lifecycle of your containers:
  - Develop your application and its supporting components using containers.
  - The container becomes the unit for distributing and testing your application.
  - When you’re ready, deploy your application into your production environment, as a container or an orchestrated service. This works the same whether your production environment is a local data center, a cloud provider, or a hybrid of the two.

# Docker Engine

Docker Engine is a client-server application with these major components:
 - A server which is a type of long-running program called a daemon process (the **dockerd** command).
 - A REST API which specifies interfaces that programs can use to talk to the daemon and instruct it what to do.
 - A command line interface (CLI) client (the **docker** command).

[![N|Solid](https://docs.docker.com/engine/images/engine-components-flow.png)]()

# Docker architecture
 
Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers. The Docker client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon. The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface.

[![N|Solid](https://docs.docker.com/engine/images/architecture.svg)]()
