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

![image](/assets/img/d4j_img_install_steps.png)

{% include youtubePlayer.html id='hsr3sDwua40' %}

## 1. Install docker 
> _Whether you have Docker please skip this step_

Docker is supported by all major Linux distributions, MacOS and Windows.

[Download](https://www.docker.com/community-edition) and install Docker (Docker Engine, Compose, etc) 


**IMPORTANT** Allocate at least 3+Gb of RAM for Docker via Docker Settings > Advanced. 

## 2. Configure and deploy Drill4J Admin with Docker-Compose file

![image](/assets/img/d4j_img_download_docker_1.png)
<p><a href="/assets/files/docker-compose.yml" download><img src="/assets/img/d4j_img_download_docker_2.png" alt="image" /></a></p>


If you want to write a docker compose manually, you can use the latest compose descriptor example in [Github repository](https://github.com/Drill4J/drill4j.github.io/blob/master/assets/files/docker-compose.yml)

Start Drill4J using the following command and wait a bit.
```console
docker-compose -p drill up -d --force-recreate
```

## 3. Run your JVM application with Drill Agent

Download the archive [distr-0.1.9.zip](https://github.com/Drill4J/drill4j.github.io/files/3392139/distr-0.1.9.zip) with the agent distribution
and extract files.

>To demonstrate the capabilities of the product, you can use Spring PetClinic Sample Application.
>Download jar file by the link below [spring-petclinic-kotlin-2.0.0.jar](/assets/files/spring-petclinic-kotlin-2.0.0.jar)
>or use **your** project.


Run the application with follow parameters:
```console
java -agentpath:{path_to_extracted_agent_folder}\drill_agent.dll=drillInstallationDir={path_to_extracted_agent_folder},adminAddress=localhost:8090,agentId=MyIncredibleAgent -jar spring-petclinic-kotlin-2.0.0.jar
```
> Use drill_agent.**dll** for Windows or drill_agent.**so** for Linux

## 4. Open Drill4J
Open new browser tab with Drill Admin [localhost:9090](http://localhost:9090)
>If you deploy Drill4J on a separate host, use [http://IP_ADDRESS:9090](http://IP_ADDRESS:9090) 
 
Drill4J is ready for login. Press Continue as a guest button to get access.

_You're breathtaking!_  
The **last step** before you can start working with Drill4J.  
Go to the [link](https://chrome.google.com/webstore/detail/drill4j-browser-extension/lhlkfdlgddnmbhhlcopcliflikibeplm?hl=ru) and install the browser extension for manual testing.
  
### Open your application and start testing   
> If you use PetClinic as an application you can find it here [localhost:8082](http://localhost:8082)


## Also, if you want to try auto tests, follow this instruction:
[Install auto tests agent](/auto-tests-agent-guide/)


