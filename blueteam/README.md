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

## Tools

The following tools are part of the Blue Team Tools:
- [OpenVAS](#openvas)

### OpenVAS

OpenVAS is a full-featured vulnerability scanner. The [`immauss/openvas` container](https://github.com/immauss/openvas) runs the Greenbone Vulnerability Manager.
- Website: https://openvas.org/
- Container used: `immauss/openvas`

***IMPORTANT***:  Before starting the container, be sure to update the `PASSWORD` variable (in the `enviornment` section) within the `docker-compose` file for OpenVAS. The password stored in the publicly available compose file should not be used.

Container information:
- GitHub: https://github.com/immauss/openvas
- Docker: https://hub.docker.com/r/immauss/openvas

