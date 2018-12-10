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

## Persistence
The persistence can be enabled by updating this value:

- ```rstudio.persistence.enabled```
