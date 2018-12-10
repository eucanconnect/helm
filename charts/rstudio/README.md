# MOLGENIS - RStudio Helm Chart

An RStudio instance to support DataSHIELD users in setting up a central analysis server instance.

## Containers

This chart will deploy the following container:

- rstudio (with DataSHIELD packages)

## Provisioning
You can choose for the RStudio image from which repository you want to pull. Experimental builds are pushed to registry.molgenis.org and the stable builds to hub.docker.com. 
You need to fill out 2 properties to determine which repository you are going to use.

- ```rstudio.image.repository```
- ```rstudio.image.tag```

You can do this in the questions in Rancher or in the ```values.yaml```.

### Running the application
You can use minikube to run this chart. To install minikube please check: https://kubernetes.io/docs/setup/minikube/.

Run the chart by installing it with helm this way: ```helm install .```.

We use xip.io to resolve the local domain entry. Check the url: *.xip.io

When you are using a cluster provisioning for domain resolving you can access the instance by default on: analysis.test.molgenis.org. 

## Persistence
The persistence can be enabled by updating this value:

- ```rstudio.persistence.enabled```
