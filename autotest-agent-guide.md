---
layout: page
title: Autotest Agent Installation Guidelines
permalink: /autotest-agent-guide/
---


To use Drill **test2code plugin** with autotests (RESTful API and Selenium based UI [*](#notes)) 
add a special autotest agent to your test automation framework.

Supported test runners:
* **junit4**
* **junit5** (5.5.0+)
* **testNG**

### Gradle
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
    id 'com.epam.drill.agent.runner.autotest' version '0.1.6'
}
```
```groovy
drill {
    version = "0.3.3"
    adminHost = "localhost"
    agentId = "ExampleAgentId"
    adminPort = 8090
}
```

### Maven
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
                <version>0.1.6</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>autotest</goal>
                        </goals>
                    </execution>
                </executions>
                <configuration>
                    <drill>
                        <version>0.3.3</version>
                        <agentId>ExampleAgentId</agentId>
                        <adminHost>localhost</adminHost>
                        <adminPort>8090</adminPort>
                    </drill>
                </configuration>
            </plugin>
        </plugins>
    </build>
```

### Notes
> If you use **remote** setup for UI autotests run (Selenium GRID, SELENOID etc.)  
 you need to deploy proxy service:
```yaml
browser-proxy:
    image: drill4j/browser-proxy:0.1.0
    ports:
      - 7777:7777
```
>and add additional param **browserProxyAddress** to autotests agent config like that:  
**Gradle**
```groovy
drill {
    additionalParams = ["browserProxyAddress" : "proxyHost:7777"]
    version = "0.3.3"
    adminHost = "localhost"
    agentId = "ExampleAgentId"
    adminPort = 8090
}
```

>**Maven**
```xml
    <configuration>
        <drill>
            <additionalParams>
                <browserProxyAddress>proxyHost:7777</browserProxyAddress>
            </additionalParams>
            <version>0.3.3</version>
            <agentId>ExampleAgentId</agentId>
            <adminHost>localhost</adminHost>
            <adminPort>8090</adminPort>
        </drill>
    </configuration>
```
