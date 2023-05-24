# Managing Container Apps

The digital library is being served using Docker containers. In a nutshell, running a Docker app requires firstly a Docker image, and secondly a Docker Container which will is the running app based on the Docker image. To create our library container, we will need to install the app Container Station. 

1. Click on AppCenter.

1. Search for and install Container Station.

1. Launch Container Station and accept all default options.

Data is managed using volumes attached from the host file system to Docker containers. For this set-up, we will set up a non-root user to run the Docker containers, alongside volumes that are needed to store the associated app data.

## Creating a Docker user

1. Click on Users in QTS.

1. Create a user named `dockuser`.

1. Set a password. Leave all settings at default options.
