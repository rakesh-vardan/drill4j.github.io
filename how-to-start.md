---
layout: page
title: How to Start
permalink: /how-to-start/
---

![image](/assets/img/d4j_img_install_steps.png)


## 1. Install docker 
> _Whether you have Docker please skip this step_

Docker is supported by all major Linux distributions, MacOS and Windows.

[Download](https://www.docker.com/community-edition) and install Docker (Docker Engine, Compose, etc) 


**IMPORTANT** Allocate at least 3+Gb of RAM for Docker via Docker Settings > Advanced. 

## 2. Configure and deploy Drill Admin with Docker-Compose file

![image](/assets/img/d4j_img_download_docker_1.png)
<p><a href="/assets/files/stable/docker-compose.yml" download><img src="/assets/img/d4j_img_download_docker_2.png" alt="image" /></a></p>


If you want to write a docker compose manually, you can use the latest compose descriptor example in [Github repository](https://github.com/Drill4J/drill4j.github.io/blob/master/assets/files/stable/docker-compose.yml)

Start Drill using the following command and wait a bit.

```console

docker-compose up -d

```

## 3. Run your application with Drill Agent

Download the archive with the agent distribution for your OS:  
[**Linux**](https://oss.jfrog.org/artifactory/oss-release-local/com/epam/drill/drill-agent-linuxX64/0.5.0-65/drill-agent-linuxX64-0.5.0-65.zip)    
[**MacOS**](https://oss.jfrog.org/artifactory/oss-release-local/com/epam/drill/drill-agent-macosX64/0.5.0-65/drill-agent-macosX64-0.5.0-65.zip)    
[**Windows**](https://oss.jfrog.org/artifactory/oss-release-local/com/epam/drill/drill-agent-mingwX64/0.5.0-65/drill-agent-mingwX64-0.5.0-65.zip)  
  and extract files.

### Now you have drill agent files and 2 typical way to start your application with drill agent.

#### 3.1 If you use docker images of app you need to share volume with drill agent files and add JAVA parameters:
```yaml
version: '3'

services:
  example-app:
    image: repo/example-app:0.1.0
    ports:
      - 8080:8080
    volumes:
      - ./distr:/data    
    environment:
      - JAVA_TOOL_OPTIONS="-agentpath:/data/libdrill_agent.so=drillInstallationDir=/data,adminAddress=localhost:8090,agentId=ExampleAgentId,buildVersion=0.1.0"

```

> **distr** - folder with drill agent files.  
> **adminAddress** - host and backend port of you drill admin.  
> **agentId** - ID for drill agent of application.  
> **buildVersion** - build version of your application.  

#### 3.2 If you use jar for running you can start application with follow parameters:

> (example for Windows):

```console

-agentpath:distr/drill_agent.dll=drillInstallationDir=distr,adminAddress=localhost:8090,agentId=ExampleAgent,buildVersion=0.1.0

```
> Use **.dll** for Windows, **.so** for Linux and **.dylib** agent file fo MacOS

## 4. Open Drill
Open new browser tab with Drill Admin [http://localhost:8091](http://localhost:8091)

Drill is ready for login. Press Continue as a guest button to get access.
 
The **last steps** before you can start working with Drill.  
#### Download [**drill-browser-extension**](https://github.com/Drill4J/browser-extension/releases/tag/v0.3.9) and install the browser extension for manual testing.

>Do not forget to register an agent before the start testing and add Test2Code plugin

Press "Register" button and follow registration wizards steps:
  * Fill all necessary general settings
  * Configure all necessary packages of your application
  * Add **Test2code** plugin
  
## Also, if you want to try auto tests, follow this instruction:
#### [Using auto tests agent](/autotest-agent-guide/)

