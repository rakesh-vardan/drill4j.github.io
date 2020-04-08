---
layout: page
title: Microservices supporting
permalink: /microservices-supporting/
---

# Drill supports apps with microservices architecture  

### How it work?
 
We introduced such a concept as a **service group**.  
A service group is a pool of agents of microservices application.
To combine agents into a service group, you need to add only one more parameter to start the agent.
 > serviceGroupId  

After that, your application will look like a monolith for testing with Drill and you will need to use
**serviceGroupId** instead of **agentId** for autotest [here](/auto-tests-plugin-guide/)
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
      - JAVA_OPTS=-agentpath:/data/libdrill_agent.so=drillInstallationDir=/data,adminAddress=host.docker.internal:8090,agentId=service-one,serviceGroupId=app,buildVersion=0.1.0

  some-jvm-service-two:
    image: repo/some-jvm-service-one:0.2.1
    ports:
      - 8081:8081
    volumes:
      - ./distr:/data
    environment:
      - JAVA_OPTS=-agentpath:/data/libdrill_agent.so=drillInstallationDir=/data,adminAddress=host.docker.internal:8090,agentId=service-two,serviceGroupId=app,buildVersion=0.2.1

```

#### After app starts you can see in drill admin: 
<a href="/assets/img/microservices/services_1.png" title="click here to see the full sized image and back to return"><img src="/assets/img/microservices/services_1.png"></a>
