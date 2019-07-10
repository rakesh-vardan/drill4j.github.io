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

## 1. Install docker 
> _Whether you have Docker please skip this step_

Docker is supported by all major Linux distributions, MacOS and Windows.

>Note: for Windows users. Docker for Windows requires 64-bit Windows 10 Pro and Microsoft Hyper-V. 
If your system does not satisfy these requirements, you can install Docker Toolbox, which uses Oracle Virtual Box instead of Hyper-V.

[Download](https://www.docker.com/community-edition) and install Docker (Docker Engine, Compose, etc) 


**IMPORTANT** Allocate at least 3+Gb of RAM for Docker via Docker Settings > Advanced. 

## 2. Configure and deploy Drill4J with Docker-Compose file

[![image](/assets/img/install-drill-step2.png)](https://github.com/Drill4J/drill4j.github.io/blob/pages/master/assets/files/docker-compose.yml)

Start Drill4J using the following command and wait a bit
```console
docker-compose -p drill up -d --force-recreate
```

## 3. Open Drill4J
Open new browser tab with [Drill4J](http://localhost:9090)

Drill4J is ready for login. Press Continue as a guest button to get access. 

If you deploy Drill4J on a separate host, use [http://IP_ADDRESS:9090](http://IP_ADDRESS:9090)

_Install Drill4J extension for chrome_
Google play [link](https://chrome.google.com/webstore/detail/drill4j-browser-extension/lhlkfdlgddnmbhhlcopcliflikibeplm?hl=ru)

### You can also [deploy Drill4J from source code](/deploy-from-sources/)

