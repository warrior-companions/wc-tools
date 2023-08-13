# Blueteam Tools

This `blueteam-compose` will spin containers that allows easy setup of blue team tools.

## Setup

1. Follow the steps in the [Setup section](../README.md#setup) in the [main README in the repo](../README.md).

2. Start the containers using the `blueteam-compose` file
    - Navigate to this `blueteam` directory
    - Issue `docker-compose -f blueteam-compose.yml up -d`
    - Example using the `blueteam-compose` file:
        ```
        cd blueteam/
        docker-compose -f blueteam-compose.yml up -d
        ```
