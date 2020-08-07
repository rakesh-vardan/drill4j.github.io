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

Start Drill using the following command and wait a bit.

```console

docker-compose up -d

```

## 3. Run your application with Drill Agent

> Now you have 2 typical way to start your application with drill agent.

### 3.1 If you use docker images of app you need to share volume with drill agent files and add JAVA parameters:
```yaml
version: '3'

services:
  example-app:
    image: repo/example-app:0.1.0
    ports:
      - 8080:8080
    volumes:
      - agent-files:/data    
    environment:
      - JAVA_TOOL_OPTIONS="-agentpath:/data/libdrill_agent.so=drillInstallationDir=/data,adminAddress=localhost:8090,agentId=ExampleAgentId,buildVersion=0.1.0"

  agent-files:
    image: drill4j/java-agent:0.6.0
    volumes:
      - agent-files:/java-agent

volumes:
  agent-files:
```
> **agent-files** - container with drill agent files.  
> **adminAddress** - host and backend port (**8090** - default port for agent connection) of you drill admin.  
> **agentId** - ID for drill agent of application.  
> **buildVersion** - build version of your application.


### 3.2 If you use jar for running you can download the archive with the agent distribution for your OS:    
[**java-agent**](https://github.com/Drill4J/java-agent/releases/tag/v0.6.0) and extract files.
#### and start application with follow parameters

> (example for Windows):

```console

-agentpath:distr/drill_agent.dll=drillInstallationDir=distr,adminAddress=localhost:8090,agentId=ExampleAgent,buildVersion=0.1.0

```
> **distr** - folder with drill agent files. Use **.dll** for Windows, **.so** for Linux and **.dylib** agent file fo MacOS 
> **adminAddress** - host and backend port (**8090** - default port for agent connection) of you drill admin.  
> **agentId** - ID for drill agent of application.  
> **buildVersion** - build version of your application. 

## 4. Open Drill
Open new browser tab with Drill Admin [http://localhost:8091](http://localhost:8091)

Drill is ready for login. Press Continue as a guest button to get access.
 
The **last steps** before you can start working with Drill.  

>Do not forget to register an agent before the start testing and add Test2Code plugin.

Press "Register" button and follow registration wizards steps:
  * 1st step. Fill all necessary general settings
  * 2nd step. Configure all necessary packages of your application
  * 3rd step. Add **Test2code** plugin
  
#### Download [**drill-browser-extension**](https://github.com/Drill4J/browser-extension/releases/tag/v0.3.15) and install the browser extension for manual testing.
  
## Also, if you want to try auto tests, follow this instruction:
#### [Using auto tests agent](/autotest-agent-guide/)

