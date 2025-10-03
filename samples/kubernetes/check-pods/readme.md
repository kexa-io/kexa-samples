# Kubernetes Samples

This directory contains sample configurations and rules for running Kexa in a Kubernetes environment.

## Directory Structure

- `config/`: Contains Kubernetes configuration files
- `rules/`: Contains Kexa rules and policies
- `docker-compose.yaml`: Local development setup for testing

## kubeconfig
In order to use kexa with kubernete you must use token authentification.
/!\ oct-2025 : Kexa use bun kubernete library . This library is not able to make certificate authentification with bunjs. /!\
### How to create kubeconfig token
Create the service account
```bash
kubectl -n default create serviceaccount kexa-sa
```
Assign cluster role
```bash
kubectl create clusterrolebinding kubeconfig-cluster-admin-token --clusterrole=cluster-admin --serviceaccount=default:kexa-sa
```
Create the Token
```bash
kubectl apply -f - <<EOF
apiVersion: v1
kind: Secret
metadata:
  name: kubeconfig-cluster-admin-token-kexa
  namespace: default
  annotations:
    kubernetes.io/service-account.name: kexa-sa
type: kubernetes.io/service-account-token
EOF
```
Get the decode token
```bash
kubectl -n default get secret kubeconfig-cluster-admin-token-kexa  -o jsonpath='{.data.token}' | base64 --decode
```

You have to copy or modify your kubeconfig and delete certificate to add token like this.
```bash
- name: kind-k8s
  user:
    token: eyJhbGxxxxxxxxxxxx....
```

Beware if your using podman you must change the hostname in your kubeconfig.
replace https://127.0.0.1 with as example 
in kubeconfig.podman
```bash
server: https://host.containers.internal:60238
```

Authorize also the insecure certificate for the new url or authorize it on your kubernete.
in kubeconfig.podman
```bash
- cluster:
    insecure-skip-tls-verify: true
    server: https://host.containers.internal:60238
  name: kind-k8s
```

## Setup

1. just run

    ```bash
    # copy the example env file and update the values
    cp .env-sample .env
    # run the docker compose file
    docker-compose up [-d]
    ```

2. clean up

    ```bash
    # stop the docker compose file
    docker-compose down
    ```

## Configuration

The `config/` directory contains Kubernetes-specific configuration files for Kexa. Make sure to review and adjust these configurations according to your environment needs.

## Rules

The `rules/` directory contains Kexa rules and policies that will be applied to your Kubernetes cluster. These rules help enforce security and compliance policies.

## Usage

1. Deploy the configurations to your Kubernetes cluster
2. Monitor the application logs for any issues
3. Verify that the rules are being applied correctly

## Requirements

- Kubernetes cluster
- kubectl configured with appropriate permissions
- Docker (for local development)