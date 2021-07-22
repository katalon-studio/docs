---
title: "Release Notes - 8.x" 
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/new/version-8x.html
redirect_from:
    - "/katalon-studio/new/all-versions.html"
description: Release notes 8.x
---

> Download [here](https://www.katalon.com/download/).

## Official Release - Version 8.1.0

### New features

* Introduced the Condition to stop test execution feature. See [doc's name](url)
* [Mobile][Keyword] Introduced `waitForElementNotPresent`. See [doc's name](url)

### Enhancements

* Supported Chrome 92.
* Supported Microsoft Edge (Chromium) 92.
* [TestRail Integration] Published new plugin version 1.1.0.
* [Slack Integration] Published new plugin version 1.0.8.
* [Sealights Integration] Published new APIs platform.
* [Azure DevOps Integration] Submitted Release details and Test Run properties to Azure DevOps. See [doc's name](url)
* [Katalon Studio Enterprise] Enhanced Retry Immediately Strategy. See [doc's name](url)
* [Kobiton Integration] Supported customizing remote server protocol.
* [Kobiton Integration] Supported customizing device name.
* Introduced options to include or exclude timestamps in .properties files in the Project Settings folder. See [doc's name](url)
* [Katalon Studio Enterprise] [Katalon Runtime Engine] Supported three times auto-retry once the activation was failed.

### Fixes

* Fixed UI issues:
    * [Azure DevOps] Expanding Submission Options broke the UI.
    * [macOS Big Sur] Could not switch to Object Properties View.
    * [macOS Big Sur] Text of selecting items on table and tree were hidden.
    * [macOS Big Sur] Could not updating Log Viewer when the execution items were changed on the Job Progress.
    * Fixed labels and added referral link in the Library Management.
    * [Mobile Object Spy] Fixed typo error "Application ID".
* Bug: [Slack Integration] Failed to connect to Slack.
* Bug: [Katalon Studio Enterprise] Could not select Run from here and Debug from here.
* Bug: [Katalon Runtime Engine] Could not find the attached device in AWS Device Farm.
* Bug: [Katalon Runtime Engine] Failed to replace excluded built-in libraries with external libraries in CLI/CI execution.
* Bug: [Cucumber] An issue of not displaying Executed steps in the Console log.
* Bug: [API Testing] An incorrect response thrown when leaving the parameter blank in the request URL path.
* Bug: [Keyword] `waitForImagePresent` returned False despite the image was on the page.
* Bug: [Keyword] `verifyElementPropertyValue` threw an error message.
* Bug: [Performance] Saving a Test Case with many variables took a long time.
* Bug: An error message thrown when continuing recording the scripts with an existing test case.
* Bug: Browser-based recorder could not record videos for the second test case if reusing opened browser.
* Bug: Project Settings Explorer was not working.
* Bug: Updated warning message when the broken Test Object could not be moved.

## Version 8.0.5

### Improvements

* Introduced an option to Record Web with a packed extension, now available on the Chrome Web Store. See [Record Web Utility using Chrome with Profile](https://docs.katalon.com/katalon-studio/docs/record-web-utility-using-chrome-with-profile.html).
* Enhanced [Time Capsule](https://docs.katalon.com/katalon-studio/docs/time-capsule.html) by leveraging a built-in ChromeDevTools function to create a MHTML snapshot. Credited to Kazurayam for suggesting [Saving Web Page as MHTML in Katalon Studio](https://forum.katalon.com/t/saving-web-page-as-mhtml-in-katalon-studio/49368).
* [Web UI] Introduced new parameters for `WebUI.takeScreenshot` keyword to print text on captured screenshots. See [Take screenshots with WebUI keywords](https://docs.katalon.com/katalon-studio/docs/webui-take-screenshot.html).

### Fixes

* Fixed Katalon Docker Image not sending reports to Katalon TestOps.
* Fixed issues with Custom Keywords where:
    * Back and Forth navigation in the Editor was not working.
    * Hyperlink was not working.
    * Javadoc was not working.
    * The Declaration of the keyword could not be opened.
    * [Cucumber] Custom Keywords in Step definitions were not working.
* Bug: Resolved activation issue of Enterprise-exclusive plugins.
* Bug: Resolved Test Suite stopped executing after some test cases.
* Fixed reports parsing issues:
    * [Katalon Runtime Engine] Could not generate and submit JUnit report to Katalon TestOps.
    * Could not generate reports due to `Null` character in log files.
    * [Katalon Runtime Engine] Katalon Studio Image could not send report to Katalon TestOps.
* Fixed Katalon Runtime Engine hanging issues when:
    * Running tests with Selenium Grid.
    * [Test Suite Collection] The number of Java threads kept increasing during execution.

## Version 8.0.0 - 8.0.1

### New Features

* [Katalon Studio Enterprise] Supported native integration with Azure DevOps Test Plans. [Learn more](/katalon-studio/docs/azure-devops-test-plans.html)
* [Katalon Studio Enterprise] Imported/Exported desired capabilities. [Learn more](/katalon-studio/docs/import-export-desired-capabilities.html)
* [Katalon Runtime Engine License] Added a parameter to release the previous execution session before checking the license. [Learn more](https://docs.katalon.com/katalon-studio/docs/console-mode-execution.html#general-options)
* Provided Product Tours for new Web UI and Web Service users.

### Improvements

* Supported Chrome 90.
* Supported Microsoft Edge (Chromium) 90.
* Updated the embedded GeckoDriver to 0.29 (Firefox 88).
* Improved Performance: Load large projects faster and consume less memory during execution.
* Edge Chromium was now the default **embedded browser** (used to be Internet Explorer).
* [Windows OS] Replaced embedded Oracle JRE 8 with Azul Zulu OpenJDK 8.
* Enhanced Katalon TestOps Integration:
    * [Katalon Runtime Engine] Supported query for Test Suite Collection. [Learn more](https://docs.katalon.com/katalon-studio/docs/console-mode-execution.html#general-options)
    * [Katalon Runtime Engine] Supported new parameters for the new Build concept. [Learn more](https://docs.katalon.com/katalon-studio/docs/console-mode-execution.html#general-options)
* [Katalon Runtime Engine] Passed HashMap for Global Variables from CLI.
* [Katalon Runtime Engine] Added an option to Command Builder for updating WebDriver automatically.
* [Enhanced Report] Added profile details to the email reports.

### Changes

* Katalon accounts registered with personal email are eligible for Katalon Studio Enterprise and Katalon Runtime Engine trial licenses for 30 days.
* MySQL became an external library. To keep it in use, follow [this guide](/katalon-studio/how-to-guides/how-to-implement-ddt-mysql.html) to configure MySQL database connection.

### Fixes

* Bug: Fixed all blocker & critical security vulnerabilities reported by SonarQube in static code analysis and 3rd-party libraries scanning tools. 
* Bug: [Katalon Runtime Engine] Lacking of tracking event for activation.
* Bug: [Windows] Missing Network connection Preference.
* Bug: [Chrome 86] Recorder utility was not working.
* Bug: Could not import Swagger JSON files.
* Bug: The Bypass Certificate validation option was not working.
* Bug: [Katalon Runtime Engine] An issue of not sending emails via command syntax `sendMail`.
* Bug: An issue of deleting scripts when renaming the folder name.
* Bug: Could not drag and drop a custom keyword from Keyword Browser.
* Bug: Could not update References of Called Test Cases when the test cases are moved by drag and drop or cut and paste.
* Bug: [Mobile testing] Could not capture object(s) while testing.
