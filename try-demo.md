---
layout: page
title: Demo Example
permalink: /try-demo/
---

#### We have prepared special docker-compose file to demonstrate drill work.  
> All you need is docker with docker-compose.
<p><a href="/assets/files/stable/demo/docker-compose.yml" download><img src="/assets/img/d4j_img_download_docker_2.png" alt="image" /></a></p>

#### Start Drill Admin:

```console

docker-compose up -d drill-admin admin-ui agent-files

```

#### Start Example App with Drill Agent:

```console

docker-compose up -d example-app

```

#### After that you can find Drill Admin on [http://localhost:8091](http://localhost:8091)  
#### and Application UI on [http://localhost:8087](http://localhost:8087) 
> app based on [spring petclinic](https://github.com/spring-projects/spring-petclinic)  

#### Add browser extension [**drill-browser-extension**](https://github.com/Drill4J/browser-extension/releases/tag/v0.3.13) and 
### start testing with Drill!

