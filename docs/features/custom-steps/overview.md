---
title: Overview
page_title: Overview
description: "Custom steps in the Step Builder in Test Studio. Steps, which can be added only manually from the Step Buidler"
position: 0
---

# Add a Custom Step from Step Builder #

The Recording Surface can help build a wide range of automation and verification quickly and without having to resort to manual configuration. However, there are some steps that need to be added manually.

The Step Builder on project level can also be used to build steps against already recorded elements in the <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a>.

1.&nbsp; Click the **Step Builder** tab in the lower right corner.

2.&nbsp; The **Step Builder** pane appears. Now select an element from the Elements Explorer to see the suggested action and verification steps for it.

3.&nbsp; Select the action, verification or general step you want to create and click **Add Step** button.

<table id="no-table">
	<tr>
		<td>![TS][3] <br><br>**Standalone version**</td>
		<td>![VS][4] <br><br>**Visual Studio plugin**</td>
	</tr>
<table>

## Web ##

<table id="no-table">
	<tr>
		<td>![TS][5] <br><br>**Standalone version**</td>
		<td>![VS][6] <br><br>**VS plugin**</td>
	</tr>
<table>

## WPF ##

<table id="no-table">
	<tr>
		<td>![TS][7] <br><br>**Standalone version**</td>
		<td>![VS][6] <br><br>**VS plugin**</td>
	</tr>
<table>

1. [Test as Step](/features/custom-steps/test-as-step) - run an existing test as a single step.
1. [Navigate To](/features/custom-steps/navigate-to) - navigate to an url step.
1. [Coded Step](/features/custom-steps/script-step) - add a coded step and open the code editor.
1. [Execution Delay](/features/custom-steps/execution-delay) - pause the test for a specified amount of time.
1. [Maximize Browser](/features/custom-steps/maximize-browser) - maximize, minimize or restore the active browser (Change Window State for WPF).
1. [Clear Browser Cache](/features/custom-steps/clear-browser-cache) - clears all cookies, temp files or history from the active browser depending on the user's choice. 
1. [Refresh Browser](/features/custom-steps/browser-refresh) - refresh the active browser.
1. [Capture Browser](/features/custom-steps/capture) - take a screenshot of only the browser or the 
1. [Comment](/features/custom-steps/comment) - display a text comment as a single test step and in the test log.
entire desktop.
1. [Wait For URL](/features/custom-steps/wait-for-url) - suspend the test until the specified URL is loaded into the browser address bar.
1. [Check for JS Errors](/features/custom-steps/check-js-errors) - verify if there are any JS errors on page 
1. [Comment](/features/custom-steps/comment) - a comment as a step in the test
1. [Custom Annotation](/features/custom-steps/custom-annotation) - add a note to display when running "Quick Execution" with Annotation turned on.
1. [Inspection Point](/features/custom-steps/inspection-point) - pause the test and display the DOM Explorer.
1. [Manual Step](/features/custom-steps/manual-step) - display a dialog box to enter directions for a manual step.
1. [Change Window State](/features/custom-steps/change-window-state) - alter the state of the **WPF** application window. 

[3]: /img/features/custom-steps/overview/fig3.png
[4]: /img/features/custom-steps/overview/fig4.png
[5]: /img/features/custom-steps/overview/fig5.png
[6]: /img/features/custom-steps/overview/fig6.png
[7]: /img/features/custom-steps/overview/fig7.png
