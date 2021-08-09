# Introduction to Snyk Container Workshop

Snyk Container helps you find and fix vulnerabilities in container images. With snyk container Scale your security capabilities by enabling developers to quickly eliminate a multitude of vulnerabilities by upgrading to a more secure base image or rebuilding when the base image is outdated

You may not always have access to the original source code that runs in your containers, but vulnerabilities in your code dependencies are still important. Snyk can detect and monitor open source dependencies for popular languages as part of the container scan

In this hands-on workshop we will achieve the follow:

* Step 1 Fork the Goof Application
* Step 2 Configure GitHub Integration 
* Step 3 Configure Docker Hub Integration 
* Step 4 Find vulnerabilities in Goof’s Dockerfile 
* Step 5 Fix the Dockerfile FROM tag using a Pull Request 
* Step 6 Build / Push the image to Docker Hub 
* Step 7 Test using the Snyk CLI for your goof container 
* Step 8 Test using "Add to Project” through the Docker Hub Integration
* Step 9 Container Reporting Dashboard

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

## Step 4 Find vulnerabilities in Goof’s Dockerfile

TODO://

## Step 5 Fix the Dockerfile FROM tag using a Pull Request

TODO://

## Step 6 Build / Push the image to Docker Hub

TODO://

## Step 7 Test using the Snyk CLI for your goof container

TODO://

## Step 8 Test using the “Add to Project” Docker Hub Integration

TODO://

## Step 9 Container Reporting Dashboard

TODO://

Thanks for attending and completing this workshop

![alt tag](https://i.ibb.co/7tnp1B6/snyk-logo.png)

<hr />
Pas Apicella [pas at snyk.io] is an Solution Engineer at Snyk APJ
