---
title: "Integration with Azure DevOps Test Plans"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/azure-devops-test-plans.html
redirect_from:
    - "/katalon-studio/docs/azure-devops-integration.html"

description: 
---

From version 8.0.0 onwards, Katalon Studio can be natively integrated with Azure DevOps (ADO) - Test Plans. This integration will help you:

1. Easily map Test Cases in ADO to automated Test Cases in Katalon Studio to know which Test Cases are automated.

2. Automatically send Test Execution logs and reports from Katalon Studio to Test Run in ADO to get the test status and have sufficient materials for debugging.

**Requirements**

* Katalon Studio version 8.0.0.
* An active Katalon Studio Enterprise license.
* Set up Azure DevOps.

### Enable the Integration and Authenticate with Azure DevOps Organization

You need to enable ADO integration and authenticate your ADO to retrieve and map test artifacts between two systems and submit test results to ADO. Do as follows:

In Katalon Studio, go to **Project > Settings > Integrations > Azure DevOps**:

1. Select **Enable Intergration** to enable **Authentication** section for editting.

2. Enter the required credentials for **Authentication**. Your credentials are encrypted by default for security.

    - **Server URL**: `https://dev.azure.com/{yourorganization}`
    - **Personal Access Token**: your [Personal Access Token](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=preview-page). We recommend you to create a Personal Access Token with full-access [scopes](https://docs.microsoft.com/en-us/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#scopes).

3. Select **Encrypt authentication data** for security assurance.

4. Click **Connect** to verify whether Azure DevOps is connected successfully.

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/azure-devops-intergration/authentication.png" width=100%>

### Configure the Integration

After successfully authenticating with ADO, you can select an ADO project among those you have access to in the drop-down list of **Project**.

To configure the integration, do as follows:

1. Select a Project for submitting the test run.

    - Select a fetched project in the **Project** drop-down list.

        > Click **Fetch Project** to fetch the latest projects list.

    - The **Test Artifacts Mapping** and **Submission Option** fieldsets are expanded automatically. You can customize the settings in each section. 

        <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/azure-devops-intergration/expand-both.png" width=100%>
        
2. Conduct Test Artifacts Mapping.

    - In the **Execution Status Mapping**, map **Katalon Studio's status** with **Azure DevOps's status** to match the test results in Katalon Studio with the test outcomes in ADO.

        <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/azure-devops-intergration/status-mapping.png" width=70%>

    - In the **Test Configuration Mapping**, map the **Execution OS/Device** and **Execution Browser/App** configured to run the test in Katalon Studio with the **Test Configurations in Azure DevOps**. 

        <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/azure-devops-intergration/test-configuration-mapping.png" width=100%>
    
        Depending on **what OS and platform** using to execute the test, Katalon Studio will get the corresponding **Azure Test Configuration** and use it as a filter for its configured test points for the test run submission.

        You can also **Add** or **Remove** item(s) to customize the settings.

        > **What is Test Configuration?**
        >
        > **A Test Configuration is a combination of configuration variable values**. Your configuration variables could be, for example, operating system, browser, CPU type, database. A configuration might be "Windows 8 + 32-bit CPU" or "Windows 10 + 64-bit CPU." [Learn more](https://docs.microsoft.com/en-us/azure/devops/test/test-different-configurations?view=azure-devops).

        > **What is Test Point?**
        > 
        > **A test point is a unique combination of a test case, test suite, configuration, and tester**. Test cases by themselves are not executable. When you add a test case to a test suite, test point(s) are generated. [Learn more](https://docs.microsoft.com/en-us/azure/devops/test/new-test-plans-page?view=azure-devops#execute-tab).

3. Configure Submission Options.

    - Select a fetched test plan in the drop-down list, the test run is submitted to ADO automatically.

	    > Click **Fetch Test Plans** to fetch the latest test plans list.

	- Enter the required **Test Run name**. 

		If you want to specify the **Build Definition ID** for test run submitted from Katalon Studio to ADO, enter the **Build Definition ID**. During runtime, Katalon Studio uses this definition ID to get the latest build and pass it to the submitted test run on ADO.

    - Decide when and what to submit test results.

    	If you want to submit test results for ADO test case ID when there are multiple test points returned, select **Submit test results for multiple test points with the same test case ID**.

	    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/azure-devops/integration/submission-options-release-definition-id-new-UI.png" width=80%>

4. Click **Apply and Close** to save your settings.

### Map test cases between Katalon Studio and Azure DevOps 

**In Katalon Studio:**

1. Double-click on a Test Case to open the test case view.
2. Select **Integrations** tab > specify the Test Cases ID(s) of ADO (to map to more than one ID, separate them by a comma).
3. Click **Verify** to check whether the test case id exists in ADO for mapping the test case(s) > **Save**.

    <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/azure-devops-intergration/map-ks-test-case-with-ado.png" width=70%>

### Submit test run and test results after execution

> Ensure that you have already taken the stated steps.

When the execution finishes, the test run is created, and test results are uploaded automatically to ADO in the format specified as below:

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/azure-devops-intergration/result-on-ado.png" width=100%>

### View test run details on test plans

From version 8.1.0 onwards, Katalon uses Release definition ID to get the latest Release and its environment when an execution finishes. It then passes them to the submitted test run.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/azure-devops/integration/view-test-run-detail-on-test-plan.png" width=80%>

### Dynamically changing test run’s information in CLI

You can change the test plan ID, test run name, and build definition ID, release definition ID of a test run by using the following command-line.

> Notes:
>
> Release Definition ID is available from version 8.1.0 onwards.

**Requirements**

* An active Katalon Runtime Engine license.
* Katalon Runtime Engine version 8.0.0.

<table data-number-column=“false” data-layout=“default” data-autosize=“false” data-pm-slice=“1 1 []“>
	<tbody>
		<tr>
			<th data-colwidth=“254”>
				<p>Katalonc Command-line Option</p>
			</th>
			<th data-colwidth=“253">
				<p>Description</p>
			</th>
			<th data-colwidth=“253”>
				<p>Mandatory?</p>
			</th>
		</tr>
		<tr>
			<td data-colwidth=“254">
				<p>-adoPlanId=&lt;testplan id&gt;</p>
			</td>
			<td data-colwidth=“253”>
				<p>Id of the test plan used for submitting test run(s).</p>
			</td>
			<td data-colwidth=“253">
				<p>N</p>
			</td>
		</tr>
		<tr>
			<td data-colwidth=“254”>
				<p>-adoTestRunName=“text”</p>
			</td>
			<td data-colwidth=“253”>
				<p>Create test run(s) on ADO with the specified name.</p>
			</td>
			<td data-colwidth=“253">
				<p>N</p>
			</td>
		</tr>
		<tr>
			<td data-colwidth=“254”>
				<p>--info -adoDefinitionID=&lt;DefinitionID&gt;</p>
			</td>
			<td data-colwidth=“253">
				<p>Get the latest completed Build Definition ID of the specified Definition ID and pass it to Test Run properties on ADO.</p>
			</td>
			<td data-colwidth=“253”>
				<p>N</p>
			</td>
		</tr>
		<tr>
			<td data-colwidth=“254">
				<p>--info -<span data-renderer-mark=“true”>adoReleaseDefID</span>=&lt;DefinitionID&gt;</p>
			</td>
			<td data-colwidth=“253">&nbsp;Based on the specified Definition ID, get the latest Release ID and its stage and pass them to Test Run properties on ADO.</td>
			<td data-colwidth=“253”>N&nbsp;</td>
		</tr>
	</tbody>
</table>

### Troubleshoot common issues

<table>
    <thead>
        <tr>
            <th>Error</th>
            <th>Solution</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Cannot create Test Results for Azure DevOps Test Case ID= due to multiple Test Points returned.</td>
            <td>Please check Test Points with Id = ; or allow sending Test Results anyway in Project Settings.</td>
        </tr>
    </tbody>
</table>
