---
title: "Record Browser-based Videos"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/record-browser-based-videos.html
redirect_from:
- "/katalon-studio/docs/screenshots-videos.html"

---

You can record and watch videos to see what went wrong with failed tests.  
> Notes
> * You can only record videos for Web UI testing.

Katalon Studio version **7.8 onwards** supports [screen-based recording](katalon-studio/docs/record-screen-based-videos.html) and browser-based recording. Screen-based recording allows you to see tests run in a local machine while browser-based recording enables you to see tests run in console mode.

> **Requirements:**
 >
 > * An active Katalon Studio Enterprise license.
 > * Katalon Studio version 7.8 onwards.

You can use browser-based recording feature to:  

* **Record video of browser window only** (even if it's hidden behind another window).
 * **Record video of Headless browser**.

    Headless Browser is a way to run browsers in a headless environment, popularly used for test automation and browser testing in CI/CD pipeline when you don't need a visible GUI. You can learn more about Headless Browser Execution in this [manual](https://docs.katalon.com/katalon-studio/docs/headless-browsers-execution.html).
* **Record videos of multiple browsers simultaneously** (for instance, parallel execution of Test Suite Collection).

> Notes:
 > * This feature is available for Chrome, Microsoft Edge (Chromium-based), and [Headless Chrome](https://developers.google.com/web/updates/2017/04/headless-chrome). 
> * This feature supports Test Suite and Test Suite Collection execution.

To use browser-based recording feature, you need to enable it in Katalon Studio and install a third-party library (FFmpeg) for video encoding.

## Enable Browser-based Recorder in Katalon Studio

1. Go to **Project** > **Settings** > **Execution** to open the Execution view.
2. In the **During Execution Options** panel, enable Video Recorder by checking **Record Video during execution**.
   > The Browser-based Video  Recorder function only records failed test cases by default.
3. Set a window size of 1500x1000 for the browser you record in Project Settings.
* Go to **Project** > **Settings** > **Desired Capabilities** > **Web UI**. Select **Chrome** or **Chrome Headless** or **Edge Chromium**.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/screenshots-videos/browser-size.png">

   > Learn more about how to set [Desired Capabilities for Web UI](https://docs.katalon.com/katalon-studio/docs/introduction-to-desired-capabilities.html#chromechrome-headless)
4. Click **Apply and Close**.

## Install FFmpeg library

Choose your operating system to install the FFmpeg library as follows:

### For Windows

1. Go to the [FFmpeg download web page](https://ffmpeg.org/download.html).
2. Download the package which is appropriate for your operating system.
3. Add the path to the FFmpeg executable file to your PATH environment variable.
4. Reactivate Katalon Studio for this installation to take effect.

Click [here](http://blog.gregzaal.com/how-to-install-ffmpeg-on-windows/) for detailed instructions.

### For macOS

* Install FFmpeg via Homebrew with `$ brew install ffmpeg`,

   OR
* Install it manually:
1. Go to the [FFmpeg download web page](https://ffmpeg.org/download.html).
2. Download the package which is appropriate for your operating system.
3. Add the path to the `.../ffmpeg/bin` folder to the `/etc/paths` file.

Click [here](https://avpres.net/FFmpeg/install_Apple.html) for detailed instructions.

### For Linux

* Use the following command: `sudo apt-get install ffmpeg`,

   OR
* Install it manually:
1. Go to the [FFmpeg download web page](https://ffmpeg.org/download.html).
2. Download the package which is appropriate for your operating system.
3. Add the path to the `.../ffmpeg/bin` folder to the `/etc/environment` file.

Click [here](https://linuxize.com/post/how-to-install-ffmpeg-on-ubuntu-18-04/) for detailed instructions.

### For Docker Image

Katalon Docker Image could be used as a container to execute Katalon Studio tests and write reports to the host's file system.

Currently, Katalon Docker Image doesn’t include FFmpeg library. You can build your own image by following these steps:
1. Create a docker image file with this content:

   ```groovy
   FROM katalonstudio/katalon
   RUN apt-get -y update
   RUN apt-get install -y ffmpeg
   ```

2. Build your own image. Eg:

   ```groovy
   docker build -t mybuild .
   ```

3. Run your docker with Katalon script. Eg:

   ```groovy
   docker run -t --rm -v "$(pwd)":/tmp/project mybuild katalonc.sh -projectPath=/tmp/project - 
   browserType="Chrome" -retry=0 -statusDelay=15 -testSuitePath="Test Suites/TS_RegressionTest"

## View recorded videos

 After running the test suite, navigate to the **Result** tab. You can see a list of test cases. A recorded video is attached to each test case accordingly.

Click on the *Play* icon in the **Video** column to play the video.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/video-capturing/image2017-8-25-153A353A13.png" width=100%>

Each test step in a video has a description embedded like a subtitle.
