# Docker
---
Docker is an **open-source engine** that automates ==the deployment of applications into containers. ==It was written by the team at Docker, Inc (formerly dotCloud Inc, an early player in the Platform as-a-Service (PAAS) market), and released by them under the Apache 2.0 license.

Docker adds an application **==deployment engine on top of a virtualized container execution environment==**. It is designed to provide a lightweight and fast environment in which to run your code as well as an efficient workflow to get that code from your laptop to your test environment and then into production. Docker is incredibly simple. Indeed, you can get started with Docker
on a minimal host running nothing but a compatible Linux kernel and a Docker binary.

Docker also encourages service-oriented and microservices architectures. Docker recommends that each container run a single application or process. This promotes a distributed application model where an application or service is represented by a series of inter-connected containers. This makes it easy to distribute, scale, debug and introspect your applications.

### Docker components
- The Docker client and server, also called the Docker Engine.
- Docker Images
- Registries
- Docker Containers


## Docker client and server
Docker is a client-server application. The Docker client talks to the **Docker server or daemon, which, in turn, does all the work**. You’ll also sometimes see the **Docker daemon called the Docker Engine**. Docker ships with a command line client binary, docker , as well as a *full RESTful AP*I to interact with the daemon: dockerd . You can run the Docker daemon and client on the same host or connect your local Docker client to a remote daemon running on another host.

# What can you use Docker for?
- Helping make your local development and build workflow faster, more efficient, and more lightweight. Local developers can build, run, and share Docker containers. Containers can be built in development and promoted to testing environments and, in turn, to production.
- Running stand-alone services and applications consistently across multiple environments, a concept especially useful in service-oriented architectures and deployments that rely heavily on micro-services.
- Using Docker to create isolated instances to run tests like, for example, those launched by a Continuous Integration (CI) suite like Jenkins CI.
- Building and testing complex applications and architectures on a local host prior to deployment into a production environment.
- Building a multi-user Platform-as-a-Service (PAAS) infrastructure.
- Providing lightweight stand-alone sandbox environments for developing, testing, and teaching technologies, such as the Unix shell or a programming language.
- Software as a Service applications;
- Highly performant, hyperscale deployments of hosts.


# Docker’s technical components
Docker can be run on any x64 host running a modern Linux kernel; we recommend kernel version 3.10 and later. It has low overhead and can be used on servers, desktops, or laptops. Run inside a virtual machine, you can also deploy Docker on OS X and Microsoft Windows. It includes:
-  A native Linux container format that Docker calls libcontainer .
-  Linux kernel namespaces, which provide isolation for filesystems, processes, and networks.
	-  Filesystem isolation: each container is its own root filesystem.
	- Process isolation: each container runs in its own process environment.
	- Network isolation: separate virtual interfaces and IP addressing between containers.
- Resource isolation and grouping: resources like CPU and memory are allocated individually to each Docker container using the cgroups, or control groups, kernel feature.
- Copy-on-write: filesystems are created with copy-on-write, meaning they are layered and fast and require limited disk usage.
- Logging: STDOUT , STDERR and STDIN from the container are collected, logged, and available for analysis or trouble-shooting.
- Interactive shell: You can create a pseudo-tty and attach to STDIN to provide an interactive shell to your container.  

# Docker 
 A Docker image is made up of **filesystems layered over each other**. At the base is a ==boot filesystem==, `bootfs` , which resembles the typical Linux/Unix boot filesystem. A Docker user will probably never interact with the boot filesystem. Indeed, when a container has booted, it is moved into memory, and the boot filesystem is unmounted to free up the RAM used by the `initrd` disk image.

Docker next layers a root filesystem, `rootfs` , on top of the boot filesystem. This
`rootfs` can be one or more operating systems (e.g., a Debian or Ubuntu filesys-
tem).

In a more traditional Linux boot, the root filesystem is mounted read-only and then switched to read-write after boot and an integrity check is conducted. In the ==Docker world,== however, the root filesystem stays in ==read-only mode==, and ==Docker takes advantage of a union mount to add more read-only filesystems onto the root filesystem==. A union mount is a mount that allows several filesystems to be mounted at one time but appear to be one filesystem. The union mount overlays the filesystems on top of one another so that the resulting filesystem may contain files and subdirectories from any or all of the underlying filesystems.

Docker calls each of these filesystems images. ==Images can be layered on top of one another.== The image below is called the parent image and you can traverse each layer until you reach the bottom of the image stack where the final image is called the base image. Finally, when a container is launched from an image, Docker mounts a read-write filesystem on top of any layers below. This is where whatever processes we want our Docker container to run will execute.

![](https://i.stack.imgur.com/P12n2.png)

When Docker first starts a container, the initial read-write layer is empty. As changes occur, they are applied to this layer; for example, if you want to change a file, then that file will be copied from the read-only layer below into the read-write layer. The read-only version of the file will still exist but is now hidden underneath the copy.

This pattern is traditionally called “copy on write” and is one of the features that makes Docker so powerful. Each read-only image layer is read-only; this image never changes. When a container is created, Docker builds from the stack of images and then adds the read-write layer on top. That layer, combined with the knowledge of the image layers below it and some configuration data, form the container. As we discovered in the last chapter, containers can be changed, they have state, and they can be started and stopped. This, and the image-layering framework, allows us to quickly build images and run containers with our applications
and services.