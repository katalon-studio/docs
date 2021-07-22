---
title: "Load Balancing for Local Test Environments"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-analytics/docs/load-balancing-agents.html
---

With Katalon TestOps, your tests can be executed in parallel using load-balanced configurations.

To do so, Katalon TestOps distributes Test Executions over Agents to optimize Remote Execution efficiency.

Each Agent can be configured with a unique Threshold. Test Executions can then be setup to minimize Agent idleness.

> Requirements:
>
> You have at least one active Local Test Environment. See: [Create a Local Test Environment with an Agent](https://docs.katalon.com/katalon-analytics/docs/agents.html).

## Configure an Agent's Threshold

An Agent's Threshold is the maximum number of sessions that an Agent can execute concurrently in a Local Test Environment.

You must configure the Threshold value to assign the number of jobs to an Agent.

> Notes:
>
> By default, the Threshold value of all Agents is set as **1**.

To configure an Agent's Threshold, follow these steps:

1. Sign in to [Katalon TestOps](https://testops.katalon.io/login) and go to your Project.

2. Go to **Configurations** > **Test Environments**.

    The **Test Environments** page appears.

3. Click on the Local Test Environment you want to configure the Agent's Threshold for (e.g., **My Agent**).

    The **Agent Details** page appears as below.

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-july-load-balancing/configure-agent-threshold.png" width=100% alt="agent details page">

4. Update the value in the **Threshold** section.

5. Click **Update**.

The maximum number of concurrent sessions that an Agent can execute is equal to the Threshold value you have configured.

You can check the sessions in the **Test Environments** page.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-july-load-balancing/test-environment-page-with-agents-highlight-session.png" width=100% alt="test environment page highlight assigned sessions">

## Assign an Agent to execute Test Runs

### For a new Test Plan

You can create a new Test Runs Schedule to assign an Agent for Test Executions. See: [Schedule Test Runs](https://docs.katalon.com/katalon-analytics/docs/create-plan.html).

When creating a new Test Runs Schedule, you are asked to select Test Environments.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-july-load-balancing/assign-test-environment-in-schedule-page.png" width=100% alt="test environment section in schedule test run page">

You can select an Agent here to assign it to your new Test Plan.

### For an existing Test Plan

1. Go to your Project > **Test Planning** > **Test Run Types**.

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-july-load-balancing/test-run-types-page.png" width=100% alt="test run type page">

2. Click on a Test Run (e.g., **a Verify Match exact name**).

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-july-load-balancing/a-verify-match-exact-name-page.png" width=100% alt="a verify match exact name page">

3. Click **Edit**.

    The Test Run Type page appears as below (e.g., **Test run type: a Verify Match exact name**).

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/testops-revamp-july-load-balancing/assign-test-environjment-agent.png" width=100% alt="highlight select test environment section">

4. Scroll down to the **Select Test Environment** section.

    In the **Test Environments** section, select a new Agent.
    
5. Click **Save**.

    > Notes:
    >
    > * If you want to assign multiple Test Runs to the same Agent whose Threshold you have configured, repeat step 2 to 5 for each Test Run.
    >
    > * You can assign Test Runs to multiple Agents. The most available and active Agent would then run the Test.

To check the Test Execution process, go back to the **Test Environments** page.
