---
layout: page
title: Autotests plugin installation guidelines
permalink: /auto-tests-plugin-guide/
---

For using Drill4J **test2code plugin** with api autotests (RESTful API) you need to add 
special auto tests plugin to your test automation framework.

Currently, drill autotests plugin support next test runners:
* **junit4**
* **junit5**
* **testNG**

### 1. Gradle
#### Add following lines to your project **settings.gradle**
```groovy
pluginManagement {
    repositories {
        maven { url 'https://oss.jfrog.org/artifactory/oss-release-local' }
    }
}
```
#### Add following lines to your project **build.gradle**
```groovy
plugins {
    id 'java'
    id 'com.epam.drill.agent.runner.autotest' version '0.1.0'
}
```
```groovy
drill {
    version = "0.1.2"
    adminHost = "localhost"
    agentId = "ExampleAgentId"
    adminPort = 8090
}
```

### 2. Maven
#### Add following lines to your project **POM**
```xml
    <pluginRepositories>
        <pluginRepository>
            <id>drill</id>
            <url>https://oss.jfrog.org/artifactory/list/oss-release-local</url>
        </pluginRepository>
    </pluginRepositories>
    <build>
        <plugins>
            <plugin>
                <groupId>com.epam.drill.agent.runner</groupId>
                <artifactId>maven</artifactId>
                <version>0.1.2</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>autotest</goal>
                        </goals>
                    </execution>
                </executions>
                <configuration>
                    <drill>
                        <agentId>ExampleAgentId</agentId>
                        <adminHost>localhost</adminHost>
                        <adminPort>8090</adminPort>
                    </drill>
                </configuration>
            </plugin>
        </plugins>
    </build>
```
