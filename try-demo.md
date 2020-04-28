---
layout: page
title: Demo example
permalink: /try-demo/
---

#### We have prepared special docker-compose file to demonstrate drill work.  
> All you need is docker with docker-compose.
<p><a href="/assets/files/0.5.0/easy-example/docker-compose.yml" download><img src="/assets/img/d4j_img_download_docker_2.png" alt="image" /></a></p>

#### Start example:

> If you start drill first time, create the network manually using  
> `docker network create drill4j-dev-network`

```console

docker-compose up -d

```

#### After that you can find Drill Admin on [http://localhost:8091](http://localhost:8091)  
#### and Application UI on [http://localhost:8087](http://localhost:8087) 
> app based on [spring petclinic](https://github.com/spring-projects/spring-petclinic)  

#### Add browser extension [**drill-browser-extension.zip**](/assets/files/0.5.0/drill-browser-extension.zip) and 
### start testing with Drill!

