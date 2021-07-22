---
title: "Schedule Test Runs"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-analytics/docs/create-plan.html 
redirect_from:
    - "/katalon-analytics/docs/view-ci-plans/"
description: 
---

> Requirements:
>
> * You have created a [Local Test Environment with Agent](https://docs.katalon.com/katalon-analytics/docs/agents.html), or you have already created a different Test Environment (Docker, Kubernetes, etc.).
>
> * You have created a [Script Repository](https://docs.katalon.com/katalon-analytics/docs/code-repo.html).

## Schedule Test Runs

Follow these steps:

1. Go to your Project and select the **Test Planning** tab.

    The **Test Runs** page appears as below.

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-june-schedule-test-runs/schedule-test-run-button.png" width=100% alt="test run page">

    > Notes:
    >
    > If you have not scheduled any Test Run yet, the calendar view on the **Test Runs** page is empty.

2. Click on the **Schedule Test Run** button.

    The **Schedule Test Run** page appears as below.

     <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-june-schedule-test-runs/schedule-test-run-page-fill-in-1.png" width=100% alt="schedule test run page 1">

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-june-schedule-test-runs/schedule-test-run-page-fill-in-2.png" width=100% alt="schedule test run page 2">

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-june-schedule-test-runs/schedule-test-run-page-fill-in-3.png" width=100% alt="schedule test run page 3">

    Fill in all the required information and click **Create**.
    
You have created a new schedule for your Test Runs.

After creating the schedule, Katalon TestOps automatically directs you to the **Test Run Types** page.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-june-schedule-test-runs/test-run-type-page.png" width=100% alt="test run types page">

The **Test Run Types** page shows you a collection of Test Runs with the same configurations (Test Environment, Trigger, Script Repository).

## View Test Run Types in Katalon Studio

> Requirements:
>
> * Katalon Studio version 7.9.1 onwards.
> * [Katalon Studio Integration](https://docs.katalon.com/katalon-studio/docs/katalon-analytics-beta-integration.html).

Follow these steps:

1. Open Katalon Studio and your Project.

2. Go to **TestOps** > **Test Run Types** on the **Tests Explorer** sidebar.

    You then can view a summary of Test Run Types that have been configured in TestOps.

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-june-schedule-test-runs/navigate-to-test-run-type-in-studio.png" width=100% alt="find test run types in studio">

3. Click on one of the names to view Test Runs details in Katalon TestOps (e.g., **a Verify Match exact name(git)**).

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-june-schedule-test-runs/detail-of-test-run-type-on-testops.png" width=100% alt="test run details on testops">
    
Next step: [Execute Test Runs](https://docs.katalon.com/katalon-analytics/docs/kt-scheduler.html).
