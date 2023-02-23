# Redteam Tools

This `docker-compose` will spin up a Portainer container that allows easy setup of redteam tools.

## Setup

For our initial release of readteam, we are using a `docker-compose` file to launch Portainer.  In order to use the `docker-compose` file, you will need to complete the following:
1. [Install Docker](https://docs.docker.com/install/)
2. [Install Docker Compose](https://docs.docker.com/compose/install/)
3. The `docker-compose` file name is `redteam-compose.yml`.
    - Review the file and make updates as needed
4. (Optional) [Import already existing docker images](#importing-docker-images)
    - This should be completed for each Docker image you do not want Docker to attempt to download
5. Modify the `templates/templates.yml` to include any additional containers.
    - Please note some containers may not work on all hosts.
6. Start the containers using the selected `docker-compose` file
    - Navigate to the `redteam` directory
    - Issue `docker-compose -f redteam-compose.yml up -d --build`