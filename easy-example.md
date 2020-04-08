---
layout: page
title: Easy example
permalink: /easy-example/
---

### We have prepared special docker-compose file to demonstrate drill work.

<p><a href="/assets/files/0.5.0/easy-example/docker-compose.yml" download><img src="/assets/img/d4j_img_download_docker_2.png" alt="image" /></a></p>

### _and complete next steps:_

#### start drill admin


```console

docker-compose up -d drill-admin admin-ui

```


#### start container with agents files


```console

docker-compose up -d agents-files

```
#### start application with drill agent
> based on [spring petclinic](https://github.com/spring-projects/spring-petclinic)

```console

docker-compose up -d example-app

```

#### After that you can find Drill Admin on  
[http://localhost:8091](http://localhost:8091)  
#### and Application UI on  
[http://localhost:8087](http://localhost:8087)

#### Add browser extension [**drill-browser-extension.zip**](/assets/files/0.5.0/drill-browser-extension.zip) and 
### start testing with Drill!

