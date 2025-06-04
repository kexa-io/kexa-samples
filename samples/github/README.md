# GitHub Sample

This directory contains a sample of configuration and rules for running Kexa through a GitHub environment.

## Directory Structure

- `config/`: Contains GitHub configuration files
- `rules/`: Contains Kexa rules and policies
- `output/`: Contains the output of the Kexa scan
- `docker-compose.yaml`: Local development setup for testing

## Requirements

- GitHub repository
- GitHub PAT (personal access token for the GitHub API)
- Docker & docker-compose (for local development)

## Setup

1. Copy the example env file and update the values

    ```bash
    cp .env-sample .env
    ```

2. Run the docker compose file

    ```bash
    docker-compose up [-d]
    ```

3. Clean up

    ```bash
    # stop the docker compose file
    docker-compose down

    # remove the Docker image
    docker rmi github-kexa:latest
    ```

## Configuration

The `config/` directory contains GitHub-specific configuration files for Kexa. Make sure to review and adjust these configurations according to your environment needs.

## Rules

The `rules/` directory contains Kexa rules and policies that will be applied to your GitHub repository. These rules help enforce security and compliance policies.

## Output

The `output/` directory contains the output of the Kexa scan.

## Usage

1. Deploy the configurations to check your GitHub repository
2. Monitor the application logs for any issues
3. Verify that the rules are being applied correctly
