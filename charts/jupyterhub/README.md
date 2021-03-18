# Jupyter
Jupyter Helm.

## Setup a jupyter environment
To spin up a Jupyter cluster: https://zero-to-jupyterhub.readthedocs.io/en/latest/jupyterhub/installation.html.

### Resources assignment MiniKube
`minikube delete && minikube start --cpus 4 --memory 8192`

### To initialise loadbalancer within MiniKube
`minikube tunnel`

### Local settings
Enable `ingress` and change the `callback url` in the `values.yml`.

### Install a new release of jupiter
```bash
helm upgrade --cleanup-on-fail \
  --install jupyter . \
  --namespace jupyter \
  --version=1.0.0 \
  --create-namespace \
  --timeout 10m0s 
```

The instance will exposed on http://127.0.0.1.

## Troubleshooting

## Timeout when starting a notebook (500 error)
Get container logging from the notebook: `kubectl logs #pod# -c notebook -n jupyter`. 
If the container logging does not work can run it locally by executing:
`docker run -ti molgenis/rstudio-jupyter:x.x.x /usr/lib/rstudio-server/bin/rserver`
You check the output for errors.

