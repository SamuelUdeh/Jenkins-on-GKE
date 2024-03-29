Jenkins is an open-source automation server that lets you flexibly orchestrate your build, test, and deployment pipelines. Kubernetes Engine is a hosted version of Kubernetes, a powerful cluster manager and orchestration system for containers.

When you need to set up a continuous delivery (CD) pipeline, deploying Jenkins on Kubernetes Engine provides important benefits over a standard VM-based deployment:

When your build process uses containers, one virtual host can run jobs against different operating systems.

Kubernetes Engine provides ephemeral build executors, allowing each build to run in a clean environment that's identical to the builds before it.

Creating Jenkins services Jenkins provides two services that the cluster needs access to. Deploy these services separately so they can be individually managed and named.

An externally-exposed NodePort service on port 8080 that allows pods and external users to access the Jenkins user interface. This type of service can be load balanced by an HTTP load balancer.

An internal, private ClusterIP service on port 50000 that the Jenkins executors use to communicate with the Jenkins controller from inside the cluster.
