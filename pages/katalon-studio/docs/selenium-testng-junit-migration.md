---
title: "Selenium/TestNG/JUnit Migration to Katalon Studio"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/selenium-testng-junit-migration.html
---

> This feature is available in version 7.4.0+.

Katalon Studio currently supports executing test cases from [Selenium](https://www.selenium.dev/), [TestNG](https://testng.org/doc/documentation-main.html), or [JUnit](https://junit.org/junit4/) projects. You just need to migrate them to a destination Katalon Studio project. By migrating test scripts from Selenium and TestNG/JUnit to Katalon Studio, you don't have to start everything from scratch. You can reuse your test cases and enjoy Katalon features to execute and maintain them.

> If it is not preferable or feasible to migrate your existing JUnit/TestNG test projects to Katalon Studio, we recommend integrating JUnit/TestNG and Katalon Studio test projects with [Katalon TestOps](https://analytics.katalon.com). This helps you manage test results from multiple sources from a centralized web UI regardless of the testing frameworks the test cases were written in.

This section gives instructions on how to migrate your test scripts from a Selenium and TestNG/Junit project to a Katalon project with newly supported features and keywords. Also, a sample TestNG project is provided to give you first-hand experience with our newly supported features.

Katalon Studio only supports:

* Selenium version **3.x**
* TestNG version **6.11**
* JUnit version **4.12**

Katalon Studio's new features to facilitate the migration include:

1. Supporting viewing, editing, and creating Java class files under the **Include/scripts/groovy** folder
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/java1.png" width="285" height="">

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/java-script.png" width="501" height="">

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/new-java-class.png" width="362" height="">

2. Built-in TestNG/JUnit keywords, including:

* Run TestNG Test Classes
* Run TestNG Test Suites
* Run JUnit Test Cases

## Keywords' details

You can enable the built-in keywords in the manual view by using the **TestNG/JUnit Keywords** plugin.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/testng-kw.png" width="260" height="">

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/testng-kw-2.png" width="334" height="">

After installing the [TestNG/JUnit Keywords](https://store.katalon.com/product/180/TestNG-JUnit-Keywords) plugin from Katalon Store, you need to [reload the plugin](https://docs.katalon.com/katalon-store/docs/user/access-store-in-KS.html#reload-plugins) to start using it.

To use this plugin offline, please refer to [this instruction](https://docs.katalon.com/katalon-studio/docs/offline-plugin.html#using-offline-plugins). Please note that the [TestNG/JUnit Keywords](https://store.katalon.com/product/180/TestNG-JUnit-Keywords) plugin is a *platform* plugin; hence, you need to put its `jar` file in the destination Katalon project's **<project_name>/Plugins/platform** folder.

### runTestNGTestClasses

**Syntax**: `runTestNGTestClasses(List testClasses)`\
**Description**: run TestNG test classes and generate TestNG report at the running report folder.\
**Parameters**:

* Name: testClasses
  * Type: List
  * Description: List of TestNG classes
  * Mandatory: Required
* Name: flowControl
  * Type: FailureHandling
  * Description: an instance FailureHandling that controls the running flow
  * Mandatory: optional

### runTestNGTestSuites

**Syntax**: `runTestNGTestSuites(List testSuites)`\
**Description**: run TestNG test suites and generate TestNG report at the running report folder.\
**Parameters**:

* Name: testSuites
  * Type: List
  * Description: List of TestNG suites as `.xml` files
  * Mandatory: Required
* Name: flowControl
  * Type: FailureHandling
  * Description: an instance FailureHandling that controls the running flow
  * Mandatory: optional

### runJUnitTestCases

**Syntax**: `runJUnitTestCases(List testCases)`\
**Description**: run JUnit test cases and generate JUnit report at the running report folder.\
**Parameters**:

* Name: testClasses
  * Type: List
  * Description: List of JUnit test cases as classes
  * Mandatory: Required
* Name: flowControl
  * Type: FailureHandling
  * Description: an instance FailureHandling that controls the running flow
  * Mandatory: optional

## How to migrate

**Prerequisite**:

* Install [Gradle](https://gradle.org/) version 5 or prior

To migrate Selenium/TestNG/JUnit scripts to a Katalon Studio project, please do as follows:

1. This step is required only when your JUnit/TestNG project's dependencies are not Selenium dependencies.

   1.1 Open the `.gradle` file and add Java dependencies of your Selenium/TestNG/JUnit project.
   > Katalon Studio has bundled TestNG, JUnit and Selenium dependencies, so you don't need to declare those dependencies again.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/build-gradle.png" width="629" height="">
   
   1.2 Open the Command Prompt or Terminal and navigate to the folder of your project. Enter `gradle katalonCopyDependencies`, then wait for the Gradle to build successfully.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/build-success.png" width="282" height="">

2. Create a project in Katalon Studio, which is the destination for the migrated Selenium/TestNG/JUnit test cases
3. Copy and paste the source code of your Selenium/TestNG/JUnit project in the `Include/scripts/groovy` folder of your Katalon project.
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/step5.png" width="322" height="">
4. Copy and paste other resources of your Selenium/TestNG/JUnit project in the root folder of your Katalon project.
5. Create a test case that includes TestNG keywords to run TestNG test suites or JUnit test classes.
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/step7.png" width="629" height="">

## Usage Example

A sample project of migrating TestNG scripts to Katalon Studio is available [here](https://github.com/katalon-studio-samples/TestNG-Migration).

> Learn more with our Katalon Academy course: [Migrate from Selenium to Katalon Studio – Everything You Should Know](https://academy.katalon.com/courses/migrate-selenium/?utm_source=kat_docs_selen_migration&utm_medium=bottom_link&utm_campaign=academy_promotion).