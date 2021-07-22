---
title: "Test Fixtures and Test Listeners (Test Hooks)"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/fixtures-listeners.html
redirect_from:
    - "/x/E4C9/"
    - "/katalon-studio/docs/setupteardown-for-test-suite-and-test-case.html"
    - "/x/7zhO/"
    - "/katalon-studio/docs/test-listeners-test-hooks/"
    - "/katalon-studio/docs/test-listeners-test-hooks.html"
description:
---

## SetUp() and TearDown() for Test Suite and Test Case

Automation testers usually want to specify prerequisite and clean-up configurations for their test cases. With the prerequisite configuration, the test engine must take specific actions before starting test execution. For clean-up configuration, the test engine must carry out some actions after the test execution finishes.

Every test suite from your projects now has been equipped to run either **SetUp** or **TearDown** methods, which are groups of your own defined test steps before or after executing a Test Suite. This feature is another useful extension besides [Test Listeners](/katalon-studio/docs/test-listeners-test-hooks.html) to extend your current testing flow as much as possible.

In **Test Suite** interface, the **Script** tab generates sample **SetUp** and **TearDown** methods to be used.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/setupteardown-for-test-suite-and-test-case/image2018-1-8-163A253A42.png" alt="script tab interface" width=100%>

To not get confused with [setUp and tearDown](/display/Documentation/Define+method#Definemethod-SetUp()andTearDown()inManualview), the following workflow can be used to better visualize how Katalon Studio execute test automation projects with/ without setUp and tearDown methods.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/test-listeners-test-hooks/image2018-9-27-123A333A20.png" alt="test execution lifecycle" width=70%>

**Supported methods**

<table><thead><tr><th>Method</th><th>Description</th><th>Trigger Condition</th><th>Common Usages</th></tr></thead><tbody><tr><td>setUp</td><td>Setup test suite environment</td><td>Before executed test suites</td><td><ul><li>Prepare a testing environment</li><li>Call required test cases for the executed test suite</li></ul></td></tr><tr><td>setUpTestCase</td><td>Run before each test case starts</td><td>Before executed test cases</td></tr><tr><td>tearDown</td><td>Clean test suites environment</td><td>After executed test suites</td><td><ul><li>Clean-up testing environment</li><li>Call TearDown test cases for the executed test suite</li></ul></td></tr><tr><td>tearDownTestCase</td><td>Run after each test case ends</td><td>After executed test cases</td></tr></tbody></table>

### Enable SetUp and TearDown
### Activate related method

By default, the **SetUp** and **TearDown** methods are not triggered even if they match with provided trigger condition above. To activate related methods, you need to set **skipped value** from **true** to **false**.

### Methods consideration

* Execution progress from these methods still has execution logs as usual, and they will be stored in execution logs files of Katalon Studio.
* You can't see setUp and tearDown executed reports from generated Test Suite report. You can only see **setUpTestCase** and **tearDownTestCase** in generated Test Suite report.
* Test Listeners will always be triggered first if you define both Test Listeners and activate Setup/ Teardown methods simultaneously.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/setupteardown-for-test-suite-and-test-case/Screen-Shot-2018-01-05-at-14.24.23.png" alt="sample before test suite" width=70%>

### In Manual view

<table><thead><tr><th>Method</th><th>Description</th><th>Common Usage</th></tr></thead><tbody><tr><td>Set Up</td><td>This method is always called <strong>first</strong> prior to executing the main test steps.<br><br></td><td><p>Prepare testing environment such as:</p><ul><li>Starting new browser with clean cookies</li><li>Creating temporary &amp; proxy databases, directories</li><li>Starting a server process</li><li>...</li></ul></td></tr><tr><td>Tear Down If Failed</td><td>This method will be called after executing all steps of the test case, <strong>and</strong> one of those steps has <strong>Failed</strong> status.</td><td><p>Clean-up testing environment such as:</p><ul><li>Closing browsers</li><li>Disclosing opened connections to database or server</li><li>...</li></ul><p>&nbsp;</p></td></tr><tr><td>Tear Down If Passed</td><td>This method will be called after executing all steps of the test case <strong>and</strong> all of those steps have <strong>Pass</strong> status.</td></tr><tr><td>Tear Down If Error</td><td>This method will be called after executing all the test case steps <strong>and</strong> one of those steps has <strong>Error</strong> status.</td></tr><tr><td>Tear Down</td><td>This method will be called <strong>finally</strong>.</td></tr></tbody></table>

> The SetUp()/ TearDown() methods will have **Error** status if any issue occurs during their execution. The only exception to this is when **AssertionError** Class is used, or the methods are skipped.

### In Script view

You can declare a method as `setup()` or `teardown()` method using the appropriated annotation above it:

```groovy
@com.kms.katalon.core.annotation.SetUp
@com.kms.katalon.core.annotation.TearDown
@com.kms.katalon.core.annotation.TearDownIfFailed
@com.kms.katalon.core.annotation.TearDownIfPassed
@com.kms.katalon.core.annotation.TearDownIfError
```

For example:

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/define-method/image2017-2-28-153A103A1.png" alt="define method" width=70%>

## Test Listeners (Test Hooks)

**Test Listeners** are test steps created based on your own criterion. Therefore, it's a useful and flexible way to help you extend your current testing flows. When matching the condition, you can execute Test Listeners. To start with Test Listeners, follow the guide below.

### Create new Test Listeners

Test Listeners are the same as other test artifacts. You can perform all basic operations such as **create, copy/cut, rename or delete** with Test Listeners. This section focus on how to **create** new Test Listeners. In the Tests Explorer pane, you can find Test Listeners location. To create new Test Listener:

1. In **Tests Explorer**, right-click on **Test Listeners**. Select **New > New Test Listener**.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/test-listeners-test-hooks/image2017-12-5-103A353A3.png" alt="create new test listener" width=100%>

2. The **New Test Listener** dialog appears with 4 options as below: 

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/test-listeners-test-hooks/image2017-12-5-103A353A38.png" alt="Test Listeners options" width=100%>

| Generate sample Before Test Case method | A sample listener will be generated before every test case starts. |
| --- | --- |
| Generate sample After Test Case method | A sample listener will be generated after every test case ends. |
| Generate sample Before Test Suite method | A sample listener will be generated before every test suite starts. |
| Generate sample After Test Suite method | A sample listener will be generated after every test suite ends. |

You can select one or multiple options, then click **OK**. Once finished, Katalon Studio generates a sample template accordingly:

Expand source

```groovy
class NewTestListener {
	/**
	 * Executes before every test case starts.
	 * @param testCaseContext related information of the executed test case.
	 */
	@BeforeTestCase
	def sampleBeforeTestCase(TestCaseContext testCaseContext) {
		println testCaseContext.getTestCaseId()
		println testCaseContext.getTestCaseVariables()
	}

	/**
	 * Executes after every test case ends.
	 * @param testCaseContext related information of the executed test case.
	 */
	@AfterTestCase
	def sampleAfterTestCase(TestCaseContext testCaseContext) {
		println testCaseContext.getTestCaseId()
		println testCaseContext.getTestCaseStatus()
	}

	/**
	 * Executes before every test suite starts.
	 * @param testSuiteContext: related information of the executed test suite.
	 */
	@BeforeTestSuite
	def sampleBeforeTestSuite(TestSuiteContext testSuiteContext) {
		println testSuiteContext.getTestSuiteId()
	}
	/**
	 * Executes after every test suite ends.
	 * @param testSuiteContext: related information of the executed test suite.
	 */
	@AfterTestSuite
	def sampleAfterTestSuite(TestSuiteContext testSuiteContext) {
		println testSuiteContext.getTestSuiteId()
	}
}
```

As you can see from the code above, a sample generated template has already added necessary annotations, libraries and supported functions to help you extend your current testing flows to a higher level.

> * There is no limit on Test Listeners. Users can create as many as preferred.
> * If you have more than one Test Listener class, the classes themselves are instantiated in Katalon storage in alphabetical order. Only then are the individual listener methods executed **top-down**.
> * Execution status of any steps within Test Listers will not affect the **overall status** of the executed test case (e.g.: if you have a FAILED output in any of your Test Listeners, but the final status of the executed test case is PASSED, then the test case's status will be PASSED).

### Example

Define multiple environments as different Global Variables by using Test Listeners. See [Global Variables and Execution Profile](https://docs.katalon.com/katalon-studio/docs/execution-profile-v54.html#create-a-profile) for more infomation.

Before test case execution, change the environment variable to the preferred environment by following the example below:

```groovy
/**
 * Executes before every test case starts.
 * @param testCaseContext related information of the executed test case.
 */

@BeforeTestCase
def sampleBeforeTestCase(TestCaseContext testCaseContext) {
    if (GlobalVariable.gl_Environment == 'Local') {
        GlobalVariable.gl_Url = 'localhost'
    } else if (GlobalVariable.gl_Environment == 'Staging') {
        GlobalVariable.gl_Url = 'staging'
    }
}
```
