---
layout: home
title: Welcome to Drill4J 
---
![image](/assets/img/drill-logo.png)

**Drill4J** is the tool for real-time application profiling that doesn’t affect codebase. Provide the ability to make white box functional testing, via access to access to application instructions and memory.

## Measure code coverage 
via any types of tests (manual, automated, integration, performance, etc.)​
## Build Code to Test mapping
shows which test case trigger which methods in-app code, and vice versa. ​
## Test results visualization
Simplify code analysis and testing process

> _**3 easy steps** to get started with Drill4J_


![image](/assets/img/install-drill-step1.png)

## Install docker 
> _Whether you have Docker please skip this step_

Docker is supported by all major Linux distributions, MacOS and Windows.

>Note: for Windows users. Docker for Windows requires 64-bit Windows 10 Pro and Microsoft Hyper-V. 
If your system does not satisfy these requirements, you can install Docker Toolbox, which uses Oracle Virtual Box instead of Hyper-V.

Download and install Docker (Docker Engine, Compose, etc)

**IMPORTANT** If you use Docker for Windows or MacOS, make sure there is at least 3gb dedicated for Docker. 
    
## Run Drill4J

![image](/assets/img/install-drill-step2.png)

## Run Drill4J backend
Install JDK 8. Installation path should NOT have space characters.


Open CMD and enter commands:

     git clone https://github.com/Drill4J/Drill4J.git

     cd <path_to_the_project_folder>\docker-compose

    ./gradlew --no-daemon cleanDistr :plugins:drill-coverage-plugin:buildToDistr :plugins:drill-exception-plugin:buildToDistr :drill-admin:jibDockerBuild

     cd <path_to_the_project_folder>\drill-admin

     docker-compose up -d

## Run Dril4J frontend
Open CMD and enter commands:

     git clone https://github.com/Drill4J/admin-ui.git 

     cd <path_to_the_folder>\docker-compose
    
     ./buildup.sh


Install Drill4J extension for chrome

## Open Drill4J
Open new browser tab with Drill4J

Drill4J is ready for login. Press Continue as a guest button to get access. 

If you deploy Drill4J on a separate host, use http://IP_ADDRESS:9090.

