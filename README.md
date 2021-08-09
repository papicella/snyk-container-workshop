# Introduction to Snyk Container Workshop

Snyk Container helps you find and fix vulnerabilities in container images. With snyk container Scale your security capabilities by enabling developers to quickly eliminate a multitude of vulnerabilities by upgrading to a more secure base image or rebuilding when the base image is outdated

You may not always have access to the original source code that runs in your containers, but vulnerabilities in your code dependencies are still important. Snyk can detect and monitor open source dependencies for popular languages as part of the container scan

In this hands-on workshop we will achieve the follow:

* Step 1 Fork the Goof Application
* Step 2 Configure GitHub Integration 
* Step 3 Configure Docker Hub Integration 
* Step 4 Test using the “Add to Project” Docker Hub Integration
* Step 5 Find vulnerabilities in Goof’s Dockerfile
* Step 6 Fix the Dockerfile FROM tag using a Pull Request
* Step 7 Container Test using the Snyk CLI
* Step 8 Container Reporting Dashboard

## Prerequisites

* public GitHub account - http://github.com
* git CLI - https://git-scm.com/downloads
* snyk CLI - https://support.snyk.io/hc/en-us/articles/360003812538-Install-the-Snyk-CLI
* Registered account on Snyk App - http://app.snyk.io
* Docker Desktop running locally - https://www.docker.com/products/docker-desktop

# Workshop Steps

_Note: It is assumed your using a mac for these steps but it should also work on windows or linux with some modifications to the scripts potentially_

## Step 1 Fork the Goof Application

Navigate to the following GitHub repo - https://github.com/snyk/goof

* Click on the "**Fork**" button
* Ensure you are forking this repo to your public GitHub account
* Click done

![alt tag](https://i.ibb.co/Gdf7N2W/snyk-starter-open-source-2.png)

## Step 2 Configure GitHub Integration

First we need to connect Snyk to GitHub so we can import our Repository. Do so by:

* Login to http://app.snyk.io Sign up if you haven't already.
* Navigating to Integrations -> Source Control -> GitHub
* Fill in your Account Credentials to Connect your GitHub Account.

![alt tag](https://i.ibb.co/bPqqybM/snyk-starter-open-source-1.png)

## Step 3 Configure Docker Hub Integration

Enable integration between Docker Hub and Snyk, to start managing your container vulnerabilities. To do that we must first connect to Docker Hub 

* Navigating to Integrations -> Container Registries -> Docker Hub 
* Enter your Docker Hub username and Access Token and then click Save

Snyk tests the connection values and the page reloads, now displaying Docker Hub integration information and the Add your Docker Hub images to Snyk button. A confirmation message that the details were saved also appears in green at the top of the screen. In addition, if the connection to Docker Hub failed, a notification appears

Note: As the access token, you can either use your DockerHub password or an [access token](https://docs.docker.com/docker-hub/access-tokens/) created in DockerHub. In case 2FA is activated on your account, access token only is applicable

![alt tag](https://i.ibb.co/hYyb7RD/snyk-container-1.png)

![alt tag](https://i.ibb.co/pWkKGmh/snyk-container-2.png)

## Step 4 Test using the “Add to Project” Docker Hub Integration

You may already have images in your Dockerhub Registries but lets go and add a new one to your Docker Hub account. 

* Login to Docker Hub as shown below. These will be the same credentials you used in Step 3 above.

```bash
$ docker login -u DOCKER_HUB_USERNAME -p YOIUR_ACCESS_TOKEN_OR_PASSWORD
Login Succeeded
```

* Pull down the following image as shown below. 

```bash
$ docker pull pasapples/docker-goof
Using default tag: latest
latest: Pulling from pasapples/docker-goof
Digest: sha256:be2d6b0f5041315f632f44e3528ea513c452cc95ed4a40bc3d70f943ab293e5f
Status: Downloaded newer image for pasapples/docker-goof:latest
docker.io/pasapples/docker-goof:latest
```

* Run the following commands to TAG and PUSH the image to your Docker Hub account. 
  
Note: Replace DOCKER_HUB_USERNAME with your Docker Bub username. 

```bash
$ docker tag pasapples/docker-goof:latest DOCKER_HUB_USERNAME/docker-goof:latest

$ $ docker push DOCKER_HUB_USERNAME/docker-goof:latest
The push refers to repository [docker.io/pasapples/docker-goof]
1bc5d83ccce7: Layer already exists
35bda1fbb3d0: Layer already exists
5f70bf18a086: Layer already exists
fbd39f37d7c2: Layer already exists
938fc2ad056c: Layer already exists
c24944d2eccc: Layer already exists
02a318dedbea: Layer already exists
7972420bc26e: Layer already exists
17c76043bf23: Layer already exists
496d6557f1e3: Layer already exists
867786449541: Layer already exists
92d17ee6d9da: Layer already exists
e54368741774: Layer already exists
5a6c4d956b5d: Layer already exists
86ab2c6c5d58: Layer already exists
latest: digest: sha256:be2d6b0f5041315f632f44e3528ea513c452cc95ed4a40bc3d70f943ab293e5f size: 3466
```

* Return to the Snyk Dashboard and click on "**Add your Docker Hub Images to Snyk**"

* Search for "**docker-goof**" and then select it and click "**Add Selected Repositories**"

![alt tag](https://i.ibb.co/mq421V8/snyk-container-3.png)

* This may take a few minutes, so you can view the Import using the link provided as follows

![alt tag](https://i.ibb.co/PQy4pzq/snyk-container-4.png)

* Once complete your container scan should appear as follows

![alt tag](https://i.ibb.co/NTX9KV2/snyk-container-5.png)

When Snyk Container scans an image, using any of the available integrations, we first find the software installed in the image, including:

1. dpkg, rpm and apk operating systems packages.
1. Popular unmanaged software, ie. installed outside a package manager.
1. Application packages based on the presence of a manifest file.

_Note: the container does not need to be run as Snyk reads the info from the file system; therefore, no container or foreign code needs to be run in order to successfully scan._

After we have the list of installed software, we look that up against our vulnerability database, which combines public sources with proprietary research

* Let's go ahead and click on the "**latest**" link to view the container issues as part of the scan

![alt tag](https://i.ibb.co/HGS4MSP/snyk-container-7.png)

One thing you will notice is recommendations for upgrading the base image. This is handy as we can remove a substantial amount of issues just by using an alternative base image from minor upgrades to major upgrades if available will be shown including what issues will remain if the basde image is changed and the container re-built.  


## Step 5 Find vulnerabilities in Goof’s Dockerfile

TODO://

## Step 6 Fix the Dockerfile FROM tag using a Pull Request

TODO://

## Step 7 Container Test using the Snyk CLI

TODO://

## Step 8 Container Reporting Dashboard

TODO://

Thanks for attending and completing this workshop

![alt tag](https://i.ibb.co/7tnp1B6/snyk-logo.png)

<hr />
Pas Apicella [pas at snyk.io] is an Solution Engineer at Snyk APJ
