# Busbar-Minikube

A [Busbar](https://github.com/busbar-io/busbar-server) Chart for Kubernetes running on Minikube.

## Installation

Busbar will set up a Busbar API Server, a MongoDB pod and a Redis pod.

This chart is inteded to be used against a Minikube Kubernetes installation.

To install a Busbar test environment run the following command:

```bash
helm install busbar-minikube --name busbario --namespace busbar
```

To install a Busbar development environment run the following command (and follow the 'Development Environment' section instructions from the documentation):

```bash
helm install busbar-minikube --name busbario --namespace busbar --set image.busbar.repository=127.0.0.1:31000/busbar
```

## Available Options

| Parameter                         | Description                                    | Default                           |
|-----------------------------------|------------------------------------------------|-----------------------------------|
| `image.busbar.repository`         | Busbar Docker registry/Image                   | busbario/busbar                   |
| `image.busbar.tag`                | Busbar Image tag to use on installation        | latest                            |
| `image.busbar.pullPolicy`         | Busbar Image pull policy                       | Always                            |
| `image.kubeconfig.repository`     | KubeConfig Docker registry/Image               | 127.0.0.1:5000/kubeconfig         |
| `image.kubeconfig.tag`            | KubeConfig Image tag to use on installation    | latest                            |
| `image.kubeconfig.pullPolicy`     | KubeConfig Image pull policy                   | Always                            |
| `clusterName`                     | Kubernetes Cluster Name                        | minikube                          |
| `privateDomainName`               | Private Domain Name                            | private                           |
| `publicDomainName`                | Public Domain Name                             | example.com                       |

## Image Repositories:

- Busbar - https://github.com/busbar-io/busbar-server
- MongoDB - https://github.com/bitnami/bitnami-docker-mongodb
- Redis - https://github.com/bitnami/bitnami-docker-redis
