# Opal
This chart is used for acceptance and production use cases.

## Containers
The created containers are:

- Opal
- Opal init container
- Rserver
- MongoDB
- *MySQL (instead of MongoDB if configured)*

## Provisioning
You can choose from which registry you want to pull. There are 2 registries:
- https://hub.docker.com/obiba/
- https://registry.molgenis.org/repository/helm

## Bootstrap
There are several additionas to the chart to initialise the database and RServer instance.

2 major components:
- job-bootstrap.yaml
- configmap-opalconfig.yaml 

### Job
There are two components here:

- **Service checker**
  The job initializes a initContainer which determines whether Opal is running. 
  
- **Opal bootstrapper**
  A scripting container (datashield/bootstrapper:latest) which allows us to address the Opal REST-API and configure the database.

### Config map
To specify the RServer instance you need to edit opal-config.properties. You can do this by adding the opal-config.properties as Config Map.
You need to make sure the file is writable because Opal is going to touch it after boot. Therefor you need to jump a lot of hoops.

So there is a volume mount on the initContainer and Opal refering to data . You can find the ConfigMap over there. 
Then the file is copied to ```/srv/conf``` and ```/usr/share/opal/conf```. This is the final step.

### Running the application
You can use minikube to run this chart. To install minikube please check: https://kubernetes.io/docs/setup/minikube/.

Run the chart by installing it with helm this way: ```helm install .```.

We use xip.io to resolve the local domain entry. Check the url: *.xip.io

When you are using a cluster provisioning for domain resolving you can access the instance by default on: opal.test.molgenis.org. 
 
#### Rancher
You can add the https://helm.molgenis.org to the catalog and then select Opal to install the chart.