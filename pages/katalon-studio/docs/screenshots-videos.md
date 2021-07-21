---
title: "Capture Screenshots"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/capture-screenshots.html
---

With Katalon Studio, you can capture screenshots during test execution. Capturing screenshots helps you identify the problem when a test fails. By doing so, you can debug the test script more effectively and quickly.

By default, Katalon Studio captures screenshots automatically upon test failures. This feature is currently applicable to Web UI and Mobile testing.

## View screenshots

 When a test fails, you can view the captured screenshots in the image tab of the Test Case's Log by following these steps:

1. Open the test's **Result** tab.
2. Select the failed test case.
3. Click **Show Test Case Details** on the top right corner.

    The Test Case's Log then appears.
4. Click on **Image**.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/screenshots-videos/log-image.png" height=330>

You can also use the captured screenshots for visual testing with TestOps Vision. [Learn more](https://forum.katalon.com/t/update-with-katalon-studio-7-7-early-release-of-katalon-testops-visual-testing-image-comparison/45557).

## Deactivate screenshots

To turn off the default settings, do as follows:

* For version **7.8 onwards**:

Go to **Project** > **Settings** > **Execution**. In the displayed **During-Execution Options** panel, uncheck **Take Screenshot when execution failed** and click **Apply and Close**.

* For versions **before 7.8**:

Go to **Project** > **Settings** > **Report**. In the displayed **Report** view, uncheck **Take Screenshot when execution failed** and click **OK**.

## Configure screenshots manually

If you wish to manually set the conditions for capturing screenshots during tests, you can use the following built-in keywords for Web UI and Mobile testing:

* [[WebUI] Take Screenshot](https://docs.katalon.com/katalon-studio/docs/webui-take-screenshot.html)
* [[WebUI] Take Screenshot As Checkpoint](https://docs.katalon.com/katalon-studio/docs/webui-take-screenshot-as-checkpoint.html) (Available from 7.7)
* [[WebUI] Take Area Screenshot As Checkpoint](https://docs.katalon.com/katalon-studio/docs/webui-take-area-screenshot-as-checkpoint.html) (Available from 7.7)
* [[WebUI] Take Area Screenshot](https://docs.katalon.com/katalon-studio/docs/webui-take-area-screenshot.html) (Available from 7.7)
* [[WebUI] Take Element Screenshot As Checkpoint](https://docs.katalon.com/katalon-studio/docs/webui-take-element-screenshot-as-checkpoint.html) (Available from 7.7)
* [[WebUI] Take Element Screenshot](https://docs.katalon.com/katalon-studio/docs/webui-take-element-screenshot.html) (Available from 7.7)
* [[WebUI] Take Full Page Screenshot As Checkpoint](https://docs.katalon.com/katalon-studio/docs/webui-take-fullpage-screenshot-as-checkpoint.html) (Available from 7.7)
* [[WebUI] Take Full Page Screenshot](https://docs.katalon.com/katalon-studio/docs/webui-take-fullpage-screenshot.html) (Available from 7.7)
* [[Mobile] Take Screenshot](https://docs.katalon.com/katalon-studio/docs/mobile-take-screenshot.html)

See also:
* [Record Screen-based Videos](https://docs.katalon.com/katalon-studio/docs/record-screen-based-videos.html)
* [Record Browser-based Videos](https://docs.katalon.com/katalon-studio/docs/record-browser-based-videos.html)
