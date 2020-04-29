---
layout: page
title: Microservices support
permalink: /microservices-support/
---

# Drill supports apps with microservices architecture  

### How it works?
 
We introduced such a concept as a **service group**.
A service group is an agent set of microservice applications.
To combine agents into a service group, you need to add only one more parameter to start the agent - **groupId**  

After that, your application looks like a monolith for testing with Drill4J and you need to use **groupId** instead 
of **agentId** for autotests [here](/autotest-agent-guide/)
> drill browser extension detects service group automatically

Docker-compose file for your application may look like this
```yaml
version: '2'

services:

  some-non-jvm-service:
    image: repo/some-non-jvm-service:3.1.0
    ports:
      - 8082:8082

  some-jvm-service-one:
    image: repo/some-jvm-service-two:0.1.0
    ports:
      - 8080:8080
    volumes:
      - ./distr:/data
    environment:
      - JAVA_OPTS=-agentpath:/data/libdrill_agent.so=drillInstallationDir=/data,adminAddress=host.docker.internal:8090,agentId=service-one,groupId=app,buildVersion=0.1.0

  some-jvm-service-two:
    image: repo/some-jvm-service-one:0.2.1
    ports:
      - 8081:8081
    volumes:
      - ./distr:/data
    environment:
      - JAVA_OPTS=-agentpath:/data/libdrill_agent.so=drillInstallationDir=/data,adminAddress=host.docker.internal:8090,agentId=service-two,groupId=app,buildVersion=0.2.1

```

After app starts you can see in drill admin: 
<a href="/assets/img/microservices/services_1.png" title="click here to see the full sized image and back to return"><img src="/assets/img/microservices/services_1.png"></a>
....you can see your Microservice application in Drill admin
