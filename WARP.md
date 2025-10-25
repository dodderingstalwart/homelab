# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Overview
This repo is an infra-focused homelab for running the Carnac app on a self-hosted k3s Kubernetes cluster. It contains raw Kubernetes manifests (no Helm/Kustomize here) and a minimal GitHub Actions workflow. Nodes are provisioned/managed outside this repo (Ansible is mentioned in README but playbooks are not included). Monitoring is via Prometheus (not configured in this repo).

Key intent from README:
- k3s control plane with two worker nodes; Docker for containerization; persistent volumes for app data (not yet defined here).
- Goal: learn/build a CI/CD pipeline and self-host Carnac.

## Commands
Kubernetes (requires a working kube-context pointing to your cluster):
- Apply all manifests in this repo:
  - kubectl apply -f k8s/
- Apply a single manifest:
  - kubectl apply -f k8s/nginx-deployment.yaml
- Validate without changing cluster state:
  - kubectl apply --dry-run=client -f k8s/
  - kubectl diff -f k8s/
- Inspect and debug:
  - kubectl get deploy,po
  - kubectl rollout status deploy/nginx-deployment
  - kubectl logs deploy/nginx-deployment -f
  - kubectl port-forward deploy/nginx-deployment 8080:80
- Remove resources:
  - kubectl delete -f k8s/

Build/lint/tests:
- There is no build system, linter, or test suite defined in this repo. Use kubectl dry-run/diff for basic validation of manifests.

## Repository structure and architecture
- k8s/: Raw manifests for the cluster.
  - nginx-deployment.yaml: Simple Deployment (replicas=2) exposing containerPort 80. No Service/Ingress provided here; reach via port-forward or add a Service/Ingress in the cluster.
  - tele_test.yaml: OpenTelemetryCollector CR with OTLP receivers and a debug exporter. This assumes the OpenTelemetry Operator CRDs are already installed in the cluster.
- .github/workflows/updates.yml: Minimal CI placeholder (echo). No build/test/deploy steps yet.

What’s not here (but referenced in README):
- Ansible playbooks/inventory; Prometheus stack manifests; PV/PVC definitions for app data; Carnac app manifests.

## CI/CD
- GitHub Actions workflow “updates” runs on push/PR to main and is currently a placeholder. Extend this to validate manifests (e.g., kubectl diff against a target cluster) and to deploy if desired.
