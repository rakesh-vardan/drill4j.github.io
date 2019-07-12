---
layout: page
title: Autotests agent installation guidelines
permalink: /auto-tests-agent-guid/
---

For using Drill4J **Code coverage plugin** with api autotests (RESTful API) you need to add 
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
val agentPath = System.getProperty("agentPath")
val adminUrl = System.getProperty("admin.url")
val adminId = System.getProperty("agent.id")
setJvmArgs(listOf("-javaagent:$agentPath=adminUrl=$adminUrl,agentId=$adminId"))
```
_Maven_ (to configuration):
```pom
<systemPropertyVariables>
    <propertyName>agentPath</propertyName>
    <propertyName>admin.url</propertyName>
    <propertyName>agent.id</propertyName>
</systemPropertyVariables>
<argLine>
   -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005
   -javaagent:${agentPath}=adminUrl=${admin.url},agentId=${agent.id}
</argLine>
```

### 3. Run your auto tests with agent

For example, if you use _Gradle_ then the command may be looks like:

```console
./gradlew clean test -Dadmin.url=localhost:8090 -Dagent.id=Agent1 -DagentPath=../auto-tests-agent/build/libs/auto-tests-agent.jar
```
...or for _Maven_:

```console
mvn clean test -Dadmin.url=localhost:8090 -Dagent.id=Agent1 -DagentPath=../auto-tests-agent/build/libs/auto-tests-agent.jar
```
...where **admin.url** is a url of your _Drill Admin_, **agent.id** is _ID_ of _Drill Agent_ and **agentPath** is a path to
 **jar** file of the agent (we built this jar in _step 1_)
 

