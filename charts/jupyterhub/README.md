# Jupyter
Jupyter Helm.

#### Setup a jupiter environment
To spin up a Jupyter cluster: https://zero-to-jupyterhub.readthedocs.io/en/latest/jupyterhub/installation.html.

#### Resources assignment MiniKube
`minikube delete && minikube start --cpus 4 --memory 8192`

#### To initialise loadbalancer within MiniKube
`minikube tunnel`

#### Install a new release of jupiter
```bash
helm upgrade --cleanup-on-fail \
  --install jupyter . \
  --namespace jupyter \
  --version=1.0.0
```