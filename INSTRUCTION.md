# Deployment and Validation Instructions

This document provides instructions on how to deploy the DaemonSet and CronJob manifests to the Kubernetes cluster and how to validate that they are working correctly.

## Prerequisites
* Make sure you have a running Kubernetes cluster.
* Make sure the `kubectl` CLI tool is installed and configured to communicate with your cluster.
* Ensure that the ToDo application and its ClusterIP service are already deployed in the cluster.

## 1. Deployment Steps

First, ensure that the target namespace `mateapp` exists. If not, create it:
```bash
kubectl create namespace mateapp