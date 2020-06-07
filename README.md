# Running Wordpress in a Kubernetes Cluster

A collection of YAML files to deploy Wordpress in k8s with NGINX Ingress Controller in a Kubernetes Cluster.

This specific version of the yaml files collection will assume that we can create a k8s PV and PVC over a Gluster Filesystem exporting a volume called "k8s-udf-storage".

YAML files are written to deploy the Wordpress pod in the "blog-apps" k8s tenant 

As another prerequisite, in that specific volume on the GlusterFS Server, a path called "blog-apps/wordpress/wordpress" directory must be present and filled with content taken from latest.tar.gz official wordpress repository.

The pod will execute Wordpress and will need to access this directory with UID=999 and GID=999