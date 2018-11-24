# Running WildFly on AWS EKS

The goal of this repo is to provide a hands-on example for a the third step in the AWS EKS tutorial series.

The series aims to familiarize the user with the use and application of Kubernetes and to provide them with hands-on experience with AWS EKS.

The first and second tutorials covered areas such as how to create a docker image, how to configure it and host it in private and public repos on DockerHub, as well as how to create an EKS cluster and install ```aws``` and ```kubectl``` commands and configure them to use the cluster.

This tutorial goes in-depth on creating helm charts that contain different components of the application. it contains a collection of helm charts that show the bare minimum requirements to deploy a WildFly application on AWS EKS, which uses its own MySQL pod and runs ActiveMQ in a separate pod.

In particular, this repo demonstrates is how to combine ```PersistentVolumeClaims``` and ```InitContainers``` to initialize and persist MySQL Database, run ActiveMQ out of process for a WildFly installation, wireup the Wildfly deployments to use the othe pods, and the appropriate ```Readiness and Liveliness probes``` for each of the three types of pods (Wildfly, ActiveMQ, and MySQL).

Replication and scaling have been removed for the sake of simplicity and will be covered in the next tutorials. The reader is encouraged to compare how different deployments deal with initialization, healthchecks, and deployment of their respective components. It would be essential to have clear understanding of this matter as we move on to talk about chart dependencies, scaling, tainting, affinity and other subjects in the comming tutorials.




 
