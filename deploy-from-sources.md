---
layout: page
title: Deploy from source code
permalink: /deploy-from-sources/
---

### Run Drill4J backend

> Install **JDK 8**. Installation path should **NOT** have space characters.

Open CMD and enter commands:

```console
git clone https://github.com/Drill4J/Drill4J.git
```
```console
cd {path_to_the_project_folder}
```
```console
./gradlew --no-daemon cleanDistr :plugins:drill-coverage-plugin:buildToDistr :plugins:drill-exception-plugin:buildToDistr :drill-admin:jibDockerBuild
```
```console
cd {path_to_the_project_folder}/drill-admin
```
```console
docker-compose up -d
```
### Run Dril4J frontend
Open CMD and enter commands:
```console
git clone https://github.com/Drill4J/admin-ui.git 
```
```console
cd {path_to_the_project_folder}
```
```console    
./buildup.sh
```