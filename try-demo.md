---
layout: page
title: Demo Example ( Java agent )
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

***


## Demo Example ( JS agent )
> ATTENTION: experimental functionality

Work on JavaScript agent is still in progress, but we are pleased to provide you with the opportunity to try it out.  
#### Clone example repository:
```console

git clone https://github.com/Drill4J/todomvc

```
#### Run docker-compose from project directory:
>it includes Drill Admins services

```console

docker-compose up -d

```
>Drill admin UI is available on [http://localhost:9091](http://localhost:9091)

#### If browser extension isn't installed, please follow the link:  
#### [**drill-browser-extension**](https://github.com/Drill4J/browser-extension/releases/tag/v0.3.13)

#### Configure browser extension:

Add new domain and set:
>Host = todomvc.com   
Agent id = todomvc-typescript-angular  
Agent URL = localhost:9404  
Agent Type = JS  

#### Open [http://todomvc.com/examples/typescript-angular/](http://todomvc.com/examples/typescript-angular/) and
### start testing with Drill!

## We would appreciate for any feedback.

