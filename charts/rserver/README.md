# RServer
This chart is used for acceptance and production use cases. All the DataSHIELD actions will be deployed here.

## Containers
The created containers are:

- RServer (from Obiba)

## Provisioning
You can choose from which registry you want to pull. There are 2 registries:
- https://hub.docker.com/obiba/
- https://registry.molgenis.org/repository/helm

### Running the application
You can use minikube to run this chart. To install minikube please check: https://kubernetes.io/docs/setup/minikube/.

Run the chart by installing it with helm this way: ```helm install .```. 
 
