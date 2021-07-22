---
title: "How to use Katalon TestOps plugin for Jenkins on Windows" 
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/jenkins-plugin-windows.html 
description: Guidelines of how to use Jenkins plugin on Windows
---
> Katalon TestOps CI is an easier way to execute Katalon Studio tests remotely or schedule remote Katalon Studio execution. [Learn more](https://docs.katalon.com/katalon-analytics/docs/kt-remote-execution.html)

This tutorial shows you how to install and run **Katalon TestOps – Jenkins** plugin for Web UI testing on Windows platform.

## Run a Freestyle Jenkins project

### Prerequisites

* [Installing Jenkins on Windows](https://www.jenkins.io/doc/book/installing/)
* An active Katalon Runtime Engine license

### Install Katalon TestOps plugin

1. Go to **Manage Jenkins > Manage Plugins > Available tab** and search for the **Katalon TestOps** plugin.

2. Select the plugin and click **Install**.

   ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/jenkins-plugin-windows/Picture1.png)

### Create and configure a Freestyle Jenkins project

Now go back to the top page, you can start using the plugin right away.

1. Click on **New Item**

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/jenkins-plugin-windows/Picture2.png" width=40%>

2. Select a freestyle project.

   ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/jenkins-plugin-windows/Picture3.png)

3. Specify your workspace (here you can use a Git repository).

   > A sample Katalon Studio a project is available on [Github](https://github.com/katalon-studio-samples/ci-samples).

   ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/jenkins-plugin-windows/Picture4.png)

4. Add and configure the build step: **Execute Katalon Studio tests**.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/jenkins-plugin-windows/Picture5.png" width=60%>

   Katalon Studio is downloaded and installed automatically based on the version you specify.

   ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/jenkins-plugin-windows/Picture6.png)

### Troubleshoot empty videos recorded after running tests

If you encounter an issue of having empty videos recorded after running your tests on Jenkins, it is because the Web Driver hasn't launched during test execution. To fix this issue, please uninstall Jenkins of Windows services, and replace it by a DOS batch file containing the following codes:

```groovy
cd D:\Tools\Jenkins //path to Jenkins folder
java -jar --webroot=jenkins.war
```

_Credit to Sébastien Taniere and his [original topic](https://forum.katalon.com/t/video-is-empty-when-scenario-is-launched-by-katalon-runtime-trough-jenkins-windows-instance/43974)._

## Run Jenkins Pipeline (Jenkinsfile)

**Prerequisites**

* [Installing Jenkins on Windows](https://www.jenkins.io/doc/book/installing/)
* Installing [Docker](https://docs.docker.com/) in your testing machine
* An active Katalon Runtime Engine **floating** license

To run Katalon Studio scripts in Jenkins Pipeline, do as follows:

1. Create a new Jenkins Pipeline project.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/jenkins-plugin-windows/create-pipeline.png" width=70%>

2. Select **Pipeline Script from SCM**.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/jenkins-plugin-windows/git.png">

   > Please be noted that you need to specify the Jenkinsfile path.

3. In the SCM field, select **Git**. 

4. In **Repository URL**, enter your Repository URL storing Katalon Studio project or use the following sample project [https://github.com/katalon-studio-samples/ci-samples/blob/master/Jenkinsfile](https://github.com/katalon-studio-samples/ci-samples/blob/master/Jenkinsfile). 

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/jenkins-plugin-windows/git-selected.png">

4. Enter your Git credentials, save and start running the Jenkinsfile.

> Learn more with our Katalon Academy course: [Refine your CI/CD Pipeline with Automated Testing](https://academy.katalon.com/courses/automated-testing-cicd-pipeline/?utm_source=kat_docs_testops_jenkins&utm_medium=bottom_link&utm_campaign=academy_promotion).