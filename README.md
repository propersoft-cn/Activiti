Activiti
========

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.activiti/activiti-engine/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.activiti/activiti-engine)

Homepage: http://activiti.org/


Activiti is a light-weight workflow and Business Process Management (BPM) Platform targeted at business people, developers and system admins. Its core is a super-fast and rock-solid BPMN 2 process engine for Java. It's open-source and distributed under the Apache license. Activiti runs in any Java application, on a server, on a cluster or in the cloud. It integrates perfectly with Spring, it is extremely lightweight and based on simple concepts. 

Activiti JIRA: https://activiti.atlassian.net

Activiti QA: http://ec2-54-217-5-246.eu-west-1.compute.amazonaws.com:8080/jenkins/


web-designer branch
-------------------

This branch use `Gradle` build system to pack Activiti front-end static resources from `activiti-webapp-explorer2` module (diagram-viewer, editor-app, modeler.html) into `activiti-web-designer-xxx.jar` as `Acitiviti Web Designer`.

Static resources are packed under `META-INF/resources/` in the jar, which could be used as a dependency of the main web app.

### Current version

Now this branch has merged `activiti-5.22.0` tag, and you can find diff [here](https://github.com/Activiti/Activiti/5.22.0...AlphaHinex:web-designer)

### How to use

Clone this repo and add upstream, you should only do this once:

    $ git clone https://github.com/AlphaHinex/Activiti.git
    $ cd Activiti
    $ git remote add upstream https://github.com/Activiti/Activiti.git

Merge with Activiti release every time you want to update your jar

    $ git checkout master
    $ git pull upstream activiti-x.xx.x
    $ git checkout web-designer
    $ git merge master
    # change version string in jar filename
    $ vi modules/activiti-webapp-explorer2/build.gradle
    
and then pack with

    $ ./gradlew clean pack
    
and you could find the `activiti-web-designer-xxx.jar` at `modules/activiti-webapp-explorer2/build/libs`
