# Kubernetes Dashboard Zarf Package

This repository defines a Zarf package for deploying the [Kubernetes Dashboard](https://github.com/kubernetes/dashboard) on a Kubernetes cluster.

## Prerequisites

To use this template, you must have the following installed:

- [Zarf CLI](https://github.com/defenseunicorns/zarf)
- A Kubernetes cluster (either local or cloud-based)

## Getting Started

To get started, clone this repository to your local machine:

```bash
git clone https://github.com/docandrew/zarf-package-kubernetes-dashboard.git
```

Then, navigate to the directory of the cloned repository:

```bash
cd zarf-package-kubernetes-dashboard
```

## Creating the Zarf Package

```bash
zarf package create
```

## Deploy the Zarf Package

```bash
zarf package deploy zarf-package-kubernetes-dashboard-amd64.tar.zst
```

This Zarf package expects the `view` ClusterRole to be present (it is by default on RKE2). 
It will create a read-only service account called `dashboard-viewer` with the necessary
`ClusterRoleBinding` to the `view` role. See [here](https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md) for more information.
