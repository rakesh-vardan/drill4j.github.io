---
layout: page
title: Autotests agent installation guidelines
permalink: /auto-tests-agent-guid/
---

For using Drill4J **Code coverage plugin** with api autotests (RESTful API) we need to add 
special auto tests agent to your test automation framework.

### 1. Clone [auto-tests-agent](https://github.com/Drill4J/auto-tests-agent) project
```console
git clone https://github.com/Drill4J/auto-tests-agent.git
```
### ...and build

```console
./gradlew clean build
```

### 2. Add to framework build configuration following instructions

_Gradle_ (to test task):
```gradle
dependsOn(jar)
setJvmArgs(listOf("-javaagent:${jar.get().archivePath}=adminUrl=localhost:8090,agentId=Agent1"))
```
_Maven_ (to configuration):
```pom
<argLine>
   -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005
   -javaagent:${agentPath}=adminUrl=${admin.url},agentId=${agent.id}
</argLine>
```

### 3. Run your auto tests with agent

For example, if you use _gradle_ then command may be looks like:

```console
./gradlew clean test
```
...or for _maven_:

```console
mvn clean test -Dadmin.url=localhost:8090 -Dagent.id=Agent1 -DagentPath=../auto-tests-agent/build/libs/auto-tests-agent.jar
```
...where **admin.url** is a url of your _Drill Admin_, **agent.id** is _ID_ of _Drill Agent_ and **agentPath** is a path to
 **jar** file of the agent (we built this jar in _step 1_)
 

