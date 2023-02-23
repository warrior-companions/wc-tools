# Offline Tools

This repo contains a collection of tools that can be self-hosted for offline use.  These tools have been tested on Docker Desktop for Windows, using Linux containers.

## Tool sets

### Research Toolset
The research toolset contains the following tools:
- [CyberChef](#cyberchef)
- [Draw IO](#draw-io)
- [Heimdall](#heimdall)
- [Kiwix](#kiwix)
- [Mitre ATT&CK Navigator](#mitre-attck-navigator)

The research toolset can be ran using the `docker-compose-research.yml` file. Be sure to [setup offline-tools](#setup) before running docker compose.

### All tools
You can run all of the tools using the `docker-compose-all.yml` file. Be sure to [setup offline-tools](#setup) before running docker compose.

## Setup

For our initial release of offline-tools, we are using `docker-compose` file(s) to run the different tools.  In order to use the `docker-compose` file, you will need to complete the following:
1. [Install Docker](https://docs.docker.com/install/)
2. [Install Docker Compose](https://docs.docker.com/compose/install/)
3. Clone this **wc-offline-tools** repository with `git clone https://github.com/warrior-companions/wc-offline-tools.git`
4. Determine which `docker-compose` file you will use
    - Make note of the file name, as it will be used in the next step
    - Review the file and make updates as needed
5. (Optional) [Import already existing docker images](#importing-docker-images)
    - This should be completed for each Docker image you do not want Docker to attempt to download
6. Start the containers using the selected `docker-compose` file
    - Navigate to the `wc-offline-tools` directory
    - Issue `docker-compose -f docker-compose-<selected_file>.yml up -d`
    - Example running the [research toolset](#research-toolset) file:
        ```
        docker-compose -f docker-compose-research.yml up -d
        ```


### Importing Docker Images

If you already have Docker images stored as `.tar` files, you can import them using the [`docker load`](https://docs.docker.com/engine/reference/commandline/load/) command.
- Example loading the [`immauss/openvas`](https://hub.docker.com/r/immauss/openvas) image from the `openvas.tar` file:
    ```
    docker load -i D:\path-to\docker-image-files\openvas.tar
    ```
- Docker should respond with: 
    > Loaded image: immauss/openvas:latest


### Downloading Docker Images

If you have not downloaded any Docker images, you can download them using the [`docker pull`](https://docs.docker.com/engine/reference/commandline/pull/) command.
- Example downloading the [`mpepping/cyberchef`](https://hub.docker.com/r/mpepping/cyberchef/) image:
    ```
    docker pull mpepping/cyberchef
    ```

You can also pull [`tagged images`](https://www.geeksforgeeks.org/docker-using-image-tags/) by including the `tag` after the image name.
- Example downloading the [`kiwix/kiwix-serve:3.4.0`](https://hub.docker.com/layers/kiwix/kiwix-serve/3.4.0/images/sha256-734cbd70a982102b7e5403d8d08f37201360af88ebd9ea85ee82e2ce2e575a6b?context=explore) image:
    ```
    docker pull kiwix/kiwix-serve:3.4.0
    ```


### Updating and Exporting Docker images

If you find you want to export a downloaded image, you can use the [`docker save`](https://docs.docker.com/engine/reference/commandline/save/) command.
- Example saving the `mpepping/cyberchef` image to the `cyberchef.tar` file:
    ```
    docker save -o D:\path-to\docker-image-files\cyberchef.tar mpepping/cyberchef
    ```

You can also save [`tagged images`](https://www.geeksforgeeks.org/docker-using-image-tags/) by including the `tag` after the image name.
- Example saving the `kiwix/kiwix-serve:3.4.0` image to the `kiwix-serve-3.4.0.tar` file:
    ```
    docker save -o D:\path-to\docker-image-files\kiwix-serve-3.4.0.tar kiwix/kiwix-serve:3.4.0
    ```

### Differences between import and load in Docker

In case you are interested more about importing and loading Docker images, here is a [stack overflow response](https://stackoverflow.com/questions/36925261/what-is-the-difference-between-import-and-load-in-docker/36932570#36932570) with an excellent overview of these commands:

<details><summary> overview of docker import and docker load </summary>

Text from [stack overflow](https://stackoverflow.com/questions/36925261/what-is-the-difference-between-import-and-load-in-docker/36932570#36932570):
> [`docker save`](https://docs.docker.com/engine/reference/commandline/save/) will indeed produce a tarball, but with all parent layers, and all tags + versions.
> 
> [`docker export`](https://docs.docker.com/engine/reference/commandline/export/) does also produce a tarball, but without any layer/history.
> 
> It is often used when one wants to ["flatten" an image](https://stackoverflow.com/q/22713551/6309), as illustrated in "[Flatten a Docker container or image](http://tuhrig.de/flatten-a-docker-container-or-image/)" from [Thomas Uhrig](http://tuhrig.de/about/):
> `docker export <CONTAINER ID> | docker import - some-image-name:latest`
> 
> However, once those tarballs are produced, load/import are there to:
> - [`docker import`](https://docs.docker.com/engine/reference/commandline/import/) creates _one_ image from _one_ tarball which is _not even_ an image (just a filesystem you want to import as an image)
>> Create an **empty filesystem image** and import the contents of the tarball
> 
> - [`docker load`](https://docs.docker.com/engine/reference/commandline/load/) creates potentially _multiple_ images from a tarred repository (since `docker save` can save _multiple_ images in a tarball).
>> Loads a tarred repository from a file or the standard input stream


</details>

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


### OpenVAS

OpenVAS is a full-featured vulnerability scanner. The `immauss/openvas` container runs the Greenbone Vulnerability Manager.
- Website: https://openvas.org/
- Container used: `immauss/openvas`

***IMPORTANT***:  Before starting the container, be sure to update the `PASSWORD` variable (in the `enviornment` section) within the `docker-compose` file for OpenVAS. The password stored in the publicly available compose file should not be used.

Container information:
- GitHub: https://github.com/immauss/openvas
- Docker: https://hub.docker.com/r/immauss/openvas

