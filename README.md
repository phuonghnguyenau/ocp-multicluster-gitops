# OpenShift Multicluster GitOps

This repository contains an implementation of GitOps using Argo CD, Red Hat Advanced Cluster Management for Kubernetes (RHACM) and Red Hat Cluster Security for Kubernetes (RHACS). This can be used as a template for adding additional operators and configuration onto OpenShift clusters.

Used my gitops-demo repository as a starting point, but is intended to be a lot more comprehensive.

## Directory structure
The following describes what each directory is used for:
* `cluster-apps` - contains the ApplicationSet definitions for each OpenShift cluster
* `post-config` - defines the OCP post installation configuration for each cluster using kustomize

In turn, each subdirectory in the `post-config` directory contains the following:
* `auth` - identity, access and management configuration for the OpenShift cluster
* `cluster-config` - general OpenShift cluster configuration
* `infra` - defining infrastructure node components
* `logging-operator` - cluster logging
* `oadp-operator` - OpenShift Application Data Protection operator components
* `rhacm` - Red Hat Advanced Cluster Management for Kubernetes (RHACM), installed on an OpenShift Hub/Management cluster

## Scripts
* `bootstrap-gitops.sh` - a simple method of initialising Argo CD/OpenShift GitOps onto an OpenShift cluster, as long as the cluster's overlay has been defined and cluster app exists
* `start-hub.sh` - an interim method of building out the OpenShift Hub cluster
