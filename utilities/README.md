# Utility

This directory contains a collection of tools that can be self-hosted for offline use.  These tools have been tested on Docker Desktop for Windows, using Linux containers.

## Utility Tool sets

### Utility Toolset
The primary utility toolset (`docker-compose-utilities.yml`) contains the following applications:
- [CyberChef](#cyberchef)
- [Draw IO](#draw-io)
- [Heimdall](#heimdall)
- [Kiwix](#kiwix)
- [Mitre ATT&CK Navigator](#mitre-attck-navigator)

The utility toolset can be ran using the `docker-compose-utilities.yml` file. Be sure to go through [setup](#setup) before running docker compose.

### All Utilities
The full utility toolset (`docker-compose-all-utilities.yml`) contains the following applications:
- [CyberChef](#cyberchef)
- [Draw IO](#draw-io)
- [Heimdall](#heimdall)
- [Kiwix](#kiwix)
- [Mitre ATT&CK Navigator](#mitre-attck-navigator)
- [CTFd](#ctfd)
- SpeedTest

You can run all of the tools using the `docker-compose-all-utilities.yml` file. Be sure to go through [setup](#setup) before running docker compose.

## Setup

See the [Setup section](../README.md#setup) in the [main README in the repo](../README.md).

### Importing Docker Images

See the [Importing Docker Images section](../README.md#importing-docker-images) in the [main README in the repo](../README.md).

### Downloading Docker Images

See the [Downloading Docker Images section](../README.md#downloading-docker-images) in the [main README in the repo](../README.md).

### Updating and Exporting Docker images

See the [Updating and Exporting Docker Images section](../README.md#updating-and-exporting-docker-images) in the [main README in the repo](../README.md).


## Tools

This section needs to be completed.
```
### Tool Template

This section needs to be completed, including a description of the tool.
- Website: 
- Container used: ``

***IMPORTANT***:

Container information:
- GitHub: 
- Docker: 

```

### CTFd

CTFd is a Capture The Flag framework focusing on ease of use and customizability.
- Website: https://ctfd.io/
- Container used: `ctfd/ctfd:mark-3.3.0`

***IMPORTANT***: We are using CTFd version 3.3.0 so we can export and import challenges. Newer versions of the CTFd container do not support the ability to import `.zip` files.

Container information:
- GitHub: http://github.com/CTFd/CTFd/
- Docker: https://hub.docker.com/r/ctfd/ctfd


### CyberChef

The Cyber Swiss Army Knife. CyberChef is a web app for encryption, encoding, compression and data analysis.
- Website: https://github.com/gchq/CyberChef
- Container used: `mpepping/cyberchef`

Container information:
- GitHub: https://github.com/mpepping/docker-cyberchef
- Docker: https://hub.docker.com/r/mpepping/cyberchef/

### Draw IO

draw.io is a JavaScript, client-side editor for general diagramming and whiteboarding.
- Website: https://www.diagrams.net/
- Container used: `jgraph/drawio`

Container information:
- GitHub: https://github.com/jgraph/drawio
- Docker: https://hub.docker.com/r/jgraph/drawio


### Heimdall

Heimdall is an Application dashboard and launcher
- Website: https://heimdall.site/
- Container used: `lscr.io/linuxserver/heimdall`

***IMPORTANT***: You must create an `appdata/heimdall/` directory (where the `docker-compose` files exist) before starting the container.

Container information:
- GitHub: https://github.com/linuxserver/Heimdall
- Docker: https://hub.docker.com/r/linuxserver/heimdall


### Kiwix

[Kiwix](https://www.kiwix.org/) is an offline reader for online content like Wikipedia, Project Gutenberg, or TED Talks.
- Website: https://www.kiwix.org/
- Container used: `kiwix/kiwix-serve:3.4.0`

Content can be downloaded from the [Kiwix library](https://library.kiwix.org/) (URL: https://library.kiwix.org/), as a `.zim` file then loaded into the Kiwix server.

***IMPORTANT***: The `kiwix-serve` container will not run without any `.zim` files stored in the `./zim-files/` directory. At least one `.zim` file must exist in the `./zim-files/` directory.

Container information:
- GitHub: https://github.com/kiwix/kiwix-tools
- Docker: https://hub.docker.com/r/kiwix/kiwix-serve


### Mitre ATT&CK Navigator

The [ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator/) is a web-based tool for annotating and exploring ATT&CK matrices.
- Website: https://mitre-attack.github.io/attack-navigator/
- Container used: `reuteras/container-attack-navigator`

Container information:
- GitHub: https://github.com/reuteras/container-attack-navigator
- Docker: https://hub.docker.com/r/reuteras/container-attack-navigator


