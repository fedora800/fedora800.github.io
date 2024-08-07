====== Docker =====  
Docker is a container **engine/platform** that simplifies the process of building, running, managing, and distributing applications.
For kubernetes projects, we are only going to build open standards CRI containers using Docker software and Dockerfile and docker compose.
When installed on ubuntu, it will install "docker.service - Docker Application Container Engine" as well as the "containerd.service - containerd container runtime".
===== containerd =====  
In kubernetes, containerd is default CRI used for RUNNING the container instead of docker doing it.
containerd is a **Docker-developed** **container runtime** that manages the life cycle of a container on a physical or virtual machine (i.e., a host). It creates, starts, stops, and destroys containers. It can also pull container images from container registries, mount storage, and enable networking for a container.
We **CANNOT** use containerd to build container images.

migrating from docker CRI to containerd - https://zesty.co/blog/moving-from-docker-to-containerd/
===== Books =====
Docker Deep Dive - Nigel Poulton

===== Links =====
https://training.play-with-docker.com/ops-s1-hello/

===== docker registry =====
a storage and distribution system for named Docker images whose different versions are identified by their tags.
this registry contains various Docker repositories, where each repo holds all the versions of a specific image.

https://www.aquasec.com/cloud-native-academy/docker-container/docker-registry/
https://docs.docker.com/guides/docker-concepts/the-basics/what-is-a-registry/


<code>
<registry-uri>/<repository>[:tag]

examples - 
docker.io/debian:wheezy-slim		docker.io   is a registry, debian   is a repository, and wheezy-slimis an image tag.
aws_account_id.dkr.ecr.region.amazonaws.com/myrepo:1.5.200       for AWS ECR private registry
my-registry:9000/foo/bar:2.1.50          where registry=my-registry:9000    image=foo/bar    tag=2.1.50
myserver.com:443/nexus3/repository/docker-hosted/some/custom/image          for nexus, where /nexus3 = application context path, /repository/docker-hosted = base registry path, /some/custom/image = specific image path in the registry

</code>


=== docker private registry ===
https://www.tutorialspoint.com/docker/docker_private_registries.htm
https://www.aquasec.com/cloud-native-academy/docker-container/docker-registry/
https://medium.com/@mejavsh/setup-your-own-container-registry-using-harbor-ff27e0129afe  -- using harbor
https://loft.sh/blog/harbor-kubernetes-self-hosted-container-registry/  -- harbor on kubernetes
https://bluelight.co/blog/how-to-choose-a-container-registry          -- good comparison
https://github.com/features/packages                     -- free upto 500MB


