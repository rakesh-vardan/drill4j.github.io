---
layout: home
title: Welcome to Drill4J 
---
![image](/assets/img/drill-logo.png)

**Drill4J** is the tool for real-time application profiling that doesn’t affect codebase. Provide the ability to make white box functional testing, via access to application instructions and memory.

## Measure code coverage 
by any types of tests (manual, automated, integration, performance, etc.)​
## Build Code to Test mapping
shows which test case trigger which methods in-app code, and vice versa. ​
## Test results visualization
Simplify code analysis and testing process

***  

# How to start

![image](/assets/img/install-drill-step1.png)

## Install docker 
> _Whether you have Docker please skip this step_

Docker is supported by all major Linux distributions, MacOS and Windows.

>Note: for Windows users. Docker for Windows requires 64-bit Windows 10 Pro and Microsoft Hyper-V. 
If your system does not satisfy these requirements, you can install Docker Toolbox, which uses Oracle Virtual Box instead of Hyper-V.

[Download](https://www.docker.com/community-edition) and install Docker (Docker Engine, Compose, etc) 


**IMPORTANT** Allocate at least 3+Gb of RAM for Docker via Docker Settings > Advanced. 
    
## Run Drill4J backend
> Install **JDK 8**. Installation path should **NOT** have space characters.


Open CMD and enter commands:

```console
git clone https://github.com/Drill4J/Drill4J.git
```
```console
cd {path_to_the_project_folder}
```
```console
./gradlew --no-daemon cleanDistr :plugins:drill-coverage-plugin:buildToDistr :plugins:drill-exception-plugin:buildToDistr :drill-admin:jibDockerBuild
```
```console
cd {path_to_the_project_folder}/drill-admin
```
```console
docker-compose up -d
```
## Run Dril4J frontend
Open CMD and enter commands:
```console
git clone https://github.com/Drill4J/admin-ui.git 
```
```console
cd {path_to_the_project_folder}
```
```console    
./buildup.sh
```

_Install Drill4J extension for chrome_
Google play [link](https://chrome.google.com/webstore/detail/drill4j-browser-extension/lhlkfdlgddnmbhhlcopcliflikibeplm?hl=ru)

## Open Drill4J
Open new browser tab with [Drill4J](http://localhost:9090)

Drill4J is ready for login. Press Continue as a guest button to get access. 

If you deploy Drill4J on a separate host, use [http://IP_ADDRESS:9090](http://IP_ADDRESS:9090)

