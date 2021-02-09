# Helm Chart For Drupal.
--

![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)

[Drupal](https://www.drupal.org/) is a free and open-source web content management framework written in PHP and distributed under the GNU General Public License.

# Introduction

This [Helm](https://github.com/cetic/helm-drupal) chart installs [Drupal](drupal.org) in a Kubernetes cluster.


# Prerequisites

- Kubernetes cluster 1.10+
- Helm 3.0+
- Postgresql or Mysql database ( optional ).

## Configure the chart

There are no pre-configurations required in this helm chart, everything will be configured from the installation wizard after deployment.

### Configure the way how to expose Drupal service:

- **Ingress**: The ingress controller must be installed in the Kubernetes cluster.
- **ClusterIP**: Exposes the service on a cluster-internal IP. Choosing this value makes the service only reachable from within the cluster.
- **NodePort**: Exposes the service on each Node’s IP at a static port (the NodePort). You’ll be able to contact the NodePort service, from outside the cluster, by requesting ``NodeIP:NodePort``.
- **LoadBalancer**: Exposes the service externally using a cloud provider’s load balancer.

# Installation

Add Helm repo:

```bash
helm repo add cetic https://cetic.github.io/helm-charts
```

Update repo:

```bash
helm repo update
```

Install the Drupal helm chart with a release name `my-release`:

```bash
helm install my-release cetic/drupal 
```

View the pods.

```bash
kubectl get pods 
```


# Uninstallation

To uninstall/delete the ``drupal`` deployment:

```bash
helm delete my-release
```


# License

[Apache License 2.0](/LICENSE)
