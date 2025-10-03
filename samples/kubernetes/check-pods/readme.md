# Kubernetes Samples

This directory contains sample configurations and rules for running Kexa in a Kubernetes environment.

## Directory Structure

- `config/`: Contains Kubernetes configuration files
- `rules/`: Contains Kexa rules and policies
- `docker-compose.yaml`: Local development setup for testing

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
