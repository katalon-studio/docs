---
title: "Record Screen-based Videos"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/record-screen-based-videos.html
---

You can record and watch videos to see what went wrong with failed tests.  

> Notes
> * You can only record videos for Web UI testing.

Katalon Studio version **7.8 onwards** supports screen-based recording and [browser-based recording](katalon-studio/docs/record-browser-based-videos.html). Screen-based recording allows you to see tests run in a local machine while browser-based recording enables you to see tests run in console mode.

Screen-based Recorder captures and records what is happening on the computer screen when running a test. The function can be used with Chrome, Firefox, Safari, Microsoft Edge, or IE.

Screen-based Recorder is currently available for single Test Suite execution only.  To record parallel executions, you can follow these instructions instead: [Record Browser-based Videos](katalon-studio/docs/record-browser-based-videos.html).

We recommend the [K-Lite Codec](https://www.codecguide.com/download_kl.htm) to play the recorded screen-based video.

## Configure Screen-based Recorder

Follow guidelines below to record the screen:

> **If you use macOS, make sure you first enable Katalon Studio for Screen Recording.**
>
> Go to **Security & Privacy** settings > **Privacy** > **Screen Recording** > Allow Katalon Studio to do Screen Recording.

### For configuration in version 7.8 and onwards

1. Go to **Project** > **Settings** > **Execution** to open the **Execution** view.
2. In the **During-Execution Options** panel, enable Video Recorder by checking **Record Video during execution**.
   
   By default, **Browser-based Recorder** for **failed Test Cases only** is selected.

3. Select **Screen Recorder** and specify Video settings based on your preferences. 

   We recommend AVI (`.avi`) format and low quality to save disk space. The higher the video quality is, the bigger the file size is.

* **Video format**: AVI (`.avi`) or MOV (`.mov`)
* **Video quality**: Low; Medium or High
4. Click **Apply and Close**.

**<details><summary>For configuration in versions before 7.8</summary>**

1. After creating a test suite in Katalon Studio, go to **Project** > **Settings** > **Report** to open the **Report** view.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/video-capturing/image2017-8-25-143A243A12.png" width=100%>

2. Check **Enable Video Recorder during execution** option. 

   By default, Katalon Studio only captures **Failed** test cases. However, you can decide to either capture the **Passed** or **Failed** test cases, or both.  

     <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/video-capturing/image2017-8-25-153A43A45.png" width=100%>
  
3. Specify Video settings based on your preferences.

   We recommend AVI (`.avi`) format and low quality to save disk space. The higher the video quality is, the bigger the file size is.

* **Video format**: AVI (`.avi`) or MOV (`.mov`)
* **Video quality**: Low; Medium or High
4. Click **OK**

 </details>

## View recorded videos

After running the test suite, navigate to the **Result** tab. You can see a list of test cases. A recorded video is attached to each test case accordingly.

Click on the *Play* icon in the **Video** column to play the video.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/video-capturing/image2017-8-25-153A353A13.png" width=100%>

Each test step in a video has a description embedded like a subtitle.
