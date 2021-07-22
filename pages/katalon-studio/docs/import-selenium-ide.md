---
title: "Import Selenium IDE version 3 projects"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/import-selenium-ide.html
---

In addition to [importing Selenium/TestNG/JUnit projects](https://docs.katalon.com/katalon-studio/docs/selenium-testng-junit-migration.html) into Katalon Studio, from version 7.5.10 onwards, you can also import a Selenium IDE project for execution with Katalon Studio.

[Selenium IDE](https://www.selenium.dev/selenium-ide/) is an integrated development environment for Selenium tests. It is implemented as a Chrome add-on and Firefox extension, which allows users to record, edit, and debug tests. Katalon Studio supports the latest versions of Selenium IDE projects (v3.x).

This manual shows you how to import a Selenium IDE project to a project in Katalon Studio and how Katalon Studio maps the imported test artifacts. Also, a sample Selenium IDE project is provided for you to try out our newly supported feature.

**Requirements**

* Katalon Studio version 7.5.10 onwards

## Import a Selenium IDE project

**In Katalon Studio**

1. Create or open a project
2. From the menu bar, select **File/Import Selenium IDE Project** and browse your Selenium IDE file (a single file with a `.side` extension) to open. Please wait for the import progress to complete.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/import-selenium-ide/selenium-ide.png" width=763>

## Map Selenium IDE with Katalon Studio test artifacts

A Selenium IDE project contains Tests, Suites, and Executing. Katalon Studio only imports Tests and Suites.

### Selenium IDE Suites - Katalon Studio Test Suites

Under **Test Suites** in Tests Explorer, Katalon Studio creates an **Imported from Selenium IDE Scripts** folder to store the imported suites. Once the import process is done, Katalon Studio open the test suites automatically.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/import-selenium-ide/test-suites.png">

Notes:

* If your Katalon project already has an **Imported from Selenium IDE Scripts** folder under Test Suites, the new folder should be **Imported from Selenium IDE Scripts (1)**.
* Katalon Studio does not create an **Imported from Selenium IDE Scripts** folder under Test Suites if there is no suite in the imported Selenium IDE project.

### Selenium IDE Tests - Katalon Studio Test Cases

Under **Test Cases** in Tests Explorer, Katalon Studio creates an **Imported from Selenium IDE Scripts/&lt;suite name&gt;** folder to store the imported tests.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/import-selenium-ide/test-cases.png">

An imported test case contains a set of Selenium commands recorded by Selenium IDE.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/import-selenium-ide/test.png">

Notes:

* Supported element locators include identifier, id, name, dom, xpath, link, css, and ui. [More details](https://www.selenium.dev/selenium/docs/api/java/com/thoughtworks/selenium/Selenium.html)

## Usage Sample

A sample project for importing a Selenium IDE project to Katalon Studio is available [here](https://github.com/katalon-studio-samples/import-selenium-ide-sample).

> Learn more with our Katalon Academy course: [Migrate from Selenium to Katalon Studio – Everything You Should Know](https://academy.katalon.com/courses/migrate-selenium/?utm_source=kat_docs_side&utm_medium=bottom_link&utm_campaign=academy_promotion).