# Opal
This chart is used for acceptance and production use cases.

## Containers
The created containers are:

- Opal
- MySQL
- RServer

## Provisioning
You can choose from which registry you want to pull. There is 1 one registry:
- https://hub.docker.com/obiba/

### Running the application
You can use minikube to run this chart. To install minikube please check: https://kubernetes.io/docs/setup/minikube/.

Run the chart by installing it with helm this way: ```helm install .```.

We use xip.io to resolve the local domain entry. Check the url: *.xip.io

When you are using a cluster provisioning for domain resolving you can access the instance by default on: analysis.test.molgenis.org. 
 
