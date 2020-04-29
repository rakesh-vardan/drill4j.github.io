---
layout: page
title: FAQ
permalink: /faq/
---

**Does Drill work only with JVM?**  
Currently yes, but we're working on .Net agent and JavaScript agent. Python and Ruby agents are also possible in the future.

**Which Java versions do you support?**  
Java 8+

**Can I use Microservice applications?**  
Yes, we're supporting microservice applications.
 
**Can I use Drill for Android applications?**  
Yes, it is possible, but it's necessary to implement an agent for android application.

**Can I use .war?**  
Yes, but only monolith applications on Tomcat, Jetty, WildFly. Java 8+
 
**What method of collecting coverage are you using?**  
Probes in bytecode. So, methods can be covered in the range of 0.1 - 100. 
Also, we will add the ability to choose a method of coverage collecting. (By string and etc.)
 
**Which test types do you support?**  
Auto, Manual 
 
**Why do I need it?**  
Probably, if your project is small and doesn't have a lot of tests, then you don't need it. BUT, if it's a legacy project with a lot of tests, the tool saves your testing time via Test gap analysis and minimizing of regression suite.

# Useful links

[GitHub](https://github.com/Drill4J)

[Contribute](https://contribute.epam.com/products/136)

# Drill4J browser extension
Google play [link](https://chrome.google.com/webstore/detail/drill4j-browser-extension/lhlkfdlgddnmbhhlcopcliflikibeplm?hl=ru)

It is a small software program that customizes a browsing experience. It enables users to tailor Chrome functionality and behavior to their preferences and needs

![](https://user-images.githubusercontent.com/45354520/59715780-41f82880-921d-11e9-8727-bbf6d1c2ff94.png)


# Deployment scheme
![](/assets/img/d4j_img_wiki_Deployment_scheme.png)


# Agent and plugin decomposition
![](/assets/img/d4j_img_AP_Decomposition.png)




## Development installation:

### Front-end
See [https://github.com/Drill4J/admin-ui/tree/develop/dev-guide](https://github.com/Drill4J/admin-ui/tree/develop/dev-guide)


### Back-end
See [https://github.com/Drill4J/Drill4J/blob/develop/README.md](https://github.com/Drill4J/Drill4J/blob/develop/README.md)

