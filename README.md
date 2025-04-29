# Kexa Samples

This repository contains sample configurations and Docker Compose files for running Kexa locally or in a virtual machine environment. These samples serve as reference implementations and starting points for your own Kexa deployments.

## Repository Structure

```bash
.
├── .github/                     # GitHub specific files
│   ├── ISSUE_TEMPLATE.md        # Issue template
│   └── PULL_REQUEST_TEMPLATE.md # Pull request template
├── docs/                        # Additional documentation
├── samples/                     # Sample configurations
│   ├── http/                    # HTTP-based deployment samples
│   └── kubernetes/              # Kubernetes deployment samples
├── CONTRIBUTING.md              # Contributing guidelines
├── CODE_OF_CONDUCT.md           # Code of conduct
├── LICENSE                      # Project license
└── README.md                    # This file
```

## Getting Started

### Prerequisites

- [Docker](https://docs.docker.com/engine/install/) and [Docker Compose](https://docs.docker.com/compose/install/) installed on your system
- Basic understanding of containerization concepts

### Usage

1. Navigate to the desired sample directory (e.g., `samples/http/` or `samples/kubernetes/`)
2. Review the configuration files and adjust them according to your needs
3. Use Docker Compose to start the services:

   ```bash
   docker-compose up -d
   ```

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## Code of Conduct

Please read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for details on our code of conduct.

## License

This project is licensed under the terms of the included LICENSE file.

## Support

For support, please open an issue in this repository or contact the maintainers.
