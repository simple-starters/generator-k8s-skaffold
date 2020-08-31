# Simple generator for Kubernetes resources

This generator creates the Kubernetes `service` and `deploymnet` resources files to deploy a Spring Boot application using Skaffold with the generated `skaffold.yaml`

You will need to install the following command line tool:

* [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
* [skaffold](https://skaffold.dev/docs/install/)

## Application

### Build the application and deploy to Kubernetes

This command will build the container image, deploy the application and port-forward the service to `localhost:8080`

```bash
skaffold run --port-forward
```

Open another terminal window to interract with the application or Kubernetes API server.

You can use `kubectl get all` to verify that the resources created.

If you leave out the `--port-forward` option then accessing the application's endpoint varies based on the type of Kubernetes cluster and ingress configuration you are using.

## Generator

`k8s-simple new` creates

* A `kubernetes` directory with a `service.yaml` and `deployment.yaml`

### Generator installation

```bash
tss generator install --go-getter-url=github.com/markpollack/generator-k8s-simple
```

To use the install command you need to install [go-getter](https://github.com/hashicorp/go-getter#installation-and-usage) CLI.
