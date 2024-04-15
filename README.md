[2]: <https://ghcr-badge.egpl.dev/nmfs-opensci/container-images%2Fnmfs-opensci-python-base/latest_tag?color=%2344cc11&ignore=&label=version&trim=>
[3]: <https://ghcr-badge.egpl.dev/nmfs-opensci/container-images%2Fnmfs-opensci-python-base/size?color=%2344cc11&tag=latest&label=image+size&trim=>

# NMFS Open Science Docker Stack

These are a collection of container images to provide standardized environments for Python and R computing build off the Rocker, [Pangeo](https://github.com/pangeo-data/pangeo-docker-images) and Jupyter base images. This repo holds the (mostly) stable docker stack for specific pipelines used in Fisheries. Want to help develop the docker stack or see our gallery of other sandbox images? Go to [nmfs-opensci/container-images](https://github.com/nmfs-opensci/container-images) which is our sandbox and development location.

Watch this video from Yuvi Panda (Jupyter Project): [Why using a container image?](https://www.youtube.com/watch?v=qgLPpULvBbQ). Read about the Rocker Project in the R Project Journal [article](https://journal.r-project.org/archive/2017/RJ-2017-065/RJ-2017-065.pdf) by Carl Boettiger and Dirk Eddelbuettel.

How can I use container images? JupyterHubs, Codespaces, GitLab, Binder, VSCode on your laptop (need Docker or Podman installed). See instructions below.

nmfs-opensci-python-base [![2] ![3]](https://github.com/nmfs-opensci/container-images/pkgs/container/nmfs-opensci-python-base)

Images are hosted on [ghcr.io](https://ghcr.io/nmfs-opensci)

| Image           | Description                                   |  Size | Link |
|-----------------|-----------------------------------------------|--------------|-------------|
| arcgis          | For using ArcGIS within Jupyter Lab           | ![](https://ghcr-badge.egpl.dev/nmfs-opensci/container-images%2Fnmfs-opensci-python-base/size?color=%2344cc11&tag=latest&label=image+size&trim=) | 


*Click on the image name in the table above for a current list of installed packages and versions*


## To run images in a JupyterHub with 'bring your image'

* Go to https://itcoocean.2i2c.cloud/
* Click on the 'Bring your own image' radio button at bottom
* Paste in url to your image (or any other image)
* You will find the urls in the right nav bar under 'Packages'
* Example `ghcr.io/nmfs-opensci/jupyter-base-notebook:latest`

## Run with a JupyterHub

Should work out of the box. Put the url to the image whereever you would use images.

## Run with docker

```
docker run -p 8888:8888 ghcr.io/nmfs-opensci/jupyter-base-notebook:latest
```

On a Mac M2+ with Rosetta emulation turned on in the Docker Desktop settings.
```
docker run --platform linux/amd64 -p 8888:8888 ghcr.io/nmfs-opensci/jupyter-base-notebook:latest
```

In the terminal look for something like and put that in a browser.
```
http://127.0.0.1:8888/lab?token=6d45c7d88aba92a815647c
```

## Run with Binder

Should work out of the box. Copy the Dockerfile into a repo and put the Dockerfile in the base or in a folder called `binder`. Then put this in a browser. Note many of the Docker images are big and somewhat hairy to build. This might not work in binder.

```
https://mybinder.org/v2/gh/user-name/reponame/main
```

## With Codespaces

Still working to streamline this.

## GitPod -- like Codespaces

Still working to streamline this.

## Run on Colab?

https://github.com/indigo-dc/udocker

Installation in the Jupyter notebook
```
%%shell
pip install udocker
udocker --allow-root install
udocker --allow-root run -p 127.0.0.1:8888:8888 -v -e ghcr.io/nmfs-opensci/jupyter-base-notebook:latest
```

Or this? https://stackoverflow.com/questions/62820498/how-to-connect-google-colab-with-localhost-running-docker-image

port forwarding https://biplobsd.me/blogs/view/run-swirl-open-source-search-engine-on-google-colab.md

