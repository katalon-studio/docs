---
title: "Record Web Utility" 
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/record-web-utility.html 
redirect_from:
    - "/display/KD/Record+Web+Utility/"
    - "/display/KD/Record%20Web%20Utility/"
    - "/x/RwnR/"
    - "/katalon-studio/docs/record-web-utility/"
    - "/display/KD/Recording+WebUI+Test/"
    - "/display/KD/Recording%20WebUI%20Test/"
    - "/x/IA3R/"
    - "/katalon-studio/docs/recording-webui-test/"
    - "/katalon-studio/docs/recording-webui-test.html"
    - "/x/BoIw/"
    - "/katalon-studio/docs/record-web-utility-version-48-and-below/"
    - "/katalon-studio/docs/record-web-utility-version-48-and-below.html"
    - "/x/ZxhO/"
    - "/katalon-studio/docs/record-web-utility-version-50-to-54/"
    - "/katalon-studio/docs/record-web-utility-version-50-to-54.html"
description: 
---
Test recording is the easiest way for a tester to create an automation test script. This mean you just need to manually interact with your Web site and perform all the desired actions as a real user while the Katalon Recorder Utility record them.

> From **version 7.7+**, Katalon Studio supports adding Mouse Over and Verification steps by a right-click on an element in the AUT when recording with Chrome, Edge (Chromium-based), and Firefox.

You can create a new test script or edit an existing test script by using the Katalon Recorder Utility. This manual includes a tutorial of how to record test scripts and a brief introduction to each panel of the Katalon Web Recorder.

## Record a New Test Case

To record a new test case, please do as follows:

1. Click on the **Web Record Utility** ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/Screen-Shot-2018-06-27-at-09.41.37.png) icon to open the Web Recorder.

2. Enter a URL of your web application. For example, https://katalon-demo-cura.herokuapp.com/

3. Select a browser to start recording (either Chrome or Firefox from '**New Browser**' type is recommended). You can see the very first test step named "Open Browser" is recorded.

   Katalon Studio's default browser is Chrome and its icon is displayed in the top right corner. If you prefer other supported browsers, you can change the default browser in **Project/Settings/Execution/Default execution**, or click on the drop-down button to select your preferred one: 

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/browser.png">

    <table><thead><tr><th>Type</th><th>Description</th><th>Note</th></tr></thead><tbody><tr><td>New Browsers</td><td>Start a new browser</td><td><strong>Supported browsers:</strong><br>- Firefox<br>- Chrome<br>- Internet Explorer (only on Windows)<br>- Microsoft Edge (Chromium) (from version 7.5.10 onwards)</td></tr><tr><td>Active Browsers</td><td>Use the current browser (only Chrome)</td><td>Katalon Studio will install <a class="external-link" href="https://chrome.google.com/webstore/detail/katalon-recorder-selenium/ljdobmomdgdljniojadhoplhkpialdid" rel="nofollow">Katalon Recorder</a> as an add-on to help with recording for this type of browser<br><br><strong>Supported browsers:</strong><br>- Chrome<br>- Firefox</td></tr></tbody></table>

4. A browser instance is launched automatically. Wait for your web page to load and interact with its elements.

5. The browser highlights and displays its correspondent XPath (on the top of the page) when you hover that element.

   > Tip: You can use hotkey to capture objects (pressing the combination of `<Alt + back quote>`). The captured object will be highlighted with a green border.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/xpath.png">

6. Interact with the web page. In this example, try signing in with the provided credentials. The recorded steps will be generated automatically in **Recorded Actions**. When you type in a **Password** field, Katalon Web Recorder uses '[Set Encrypted Text](/display/KD/%5BWebUI%5D+Set+Encrypted+Text)' keyword automatically. The input's value will be encrypted to ensure security.
   
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/Screen-Shot-2018-06-27-at-10.05.19.png">

7. Stop recording and save your script. 

   During your recording, Katalon captures the objects that you have interacted with. When saving test script, **Katalon Web Recorder** exports a list of objects used in the test case. Choose a directory you want your test objects to reside to continue. 

   > Notes: 
   >
   > You can learn more in chapter 2 of our Katalon Academy course: [Create and Execute Test Cases](https://academy.katalon.com/courses/create-execute-test-cases/?utm_source=kat_docs_record&utm_medium=bottom_link&utm_campaign=academy_promotion).

## Record Using Existing Test Case

With the new Web Recorder, users can be more productive while modifying existing test cases. Instead of creating a brand new test case whenever there are changes to the UI, risks of overlooking how new changes might effect existing features are now minimized.

1. Open any existing test case to continue recording.
2. Click on the **Record** icon to open Web Recorder.
   
   All the existing test steps and [Test Case variables](/display/KD/Variable+Types#VariableTypes-Localvariables) will be imported to the **Recorded Actions** and **Variables** tabs in Web Recorder respectively. You won't need to repeat the test steps having been recorded.

   ![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/Screen-Shot-2018-06-27-at-11.23.30.png)

3. Interact with the AUT.

When saving your script, Katalon Studio automatically detects similar existing objects in **Objects Repository** and asks you for further action to optimize Object Repository.

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/image2018-6-26-143A183A9.png)

## Validate UI elements

> From **version 7.7+**, Katalon supports adding Mouse Over and Verification Steps by a right-click on an element displayed in the AUT when recording with Chrome, Edge (Chromium-based), and Firefox.

Given that you enter incorrect username or password, you can validate if the website displays an error message indicating a failed login attempt.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/validate-UI-elements.png">

Or you can verify if the next screen after a successful login is "right" by verifying if a specific UI element is present.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/Validate-2.png">

In the drop-down list of the **Run** button, you can find some Run options. The two of them labeled with "Debug" are advanced options for validating recorded script, and saving you from running all test steps over and over again if you have a Katalon Studio Enterprise license:

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/tutorials/introduction-to-web-testing/77.png)
 
* **Run all steps**: Execute ALL steps that are enabled on Web Recorder
* **Debug: Run selected steps**: Execute only one or many selected steps. 

   You can select multiple steps using either Ctrl or Shift key. The selected steps will be highlighted (e.g. steps #2, #6, #9 and #11 are selected for running).
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/Screen-Shot-2018-06-27-at-11.45.48.png">

* **Debug: Run from selected step**: Execute the currently selected step and all the steps after the selected one (e.g. run the test from step #4.
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/Screen-Shot-2018-06-27-at-11.51.07.png"> 

## Katalon Web Recorder Utility's Components

### Recorded Actions

Available actions in Katalon Web Recorder Utility is the same as Katalon Studio's [built-in keywords](/display/KD/Built-in+Keywords). You can add any action, call another test case, and/or use Custom Keywords.

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/Screen-Shot-2018-06-27-at-11.30.37.png)

### Captured Objects

During your recording, Katalon captures the objects that you have interacted with. When saving test script, **Katalon Web Recorder** exports a list of objects used in the test case. [Learn more about Web UI test objects](/x/tQTR).

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/captured-objects.png" width=50%>

### Variables

In Katalon Web Recorder, you can manage the [variables](/x/RoIw) directly related to your recording.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/var.png">

### Logs

When running the recorded actions, you can investigate the execution by looking at its real-time detailed logs. Execution logs are displayed on the **Logs** tab.

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/record-web-utility/Screen-Shot-2018-06-27-at-11.54.27.png)

For advanced features such as branching, looping or validation, you can refer to following articles: 

* [Common Validation](https://www.katalon.com/tutorials/common-validation/) 
* [Control Statements](/display/KD/Control+Statements)
