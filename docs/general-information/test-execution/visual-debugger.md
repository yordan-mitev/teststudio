---
title: Visual Debugger
page_title: Visual Debugger
description: "Test Studio Visual Debugger tools to explore why a test is failing. What is the Visual Debugger in Test Studio. How to use the Visual Debugger in Test Studio"
position: 9
---
# Visual Debugger #

During Quick Execution, press the **Pause** button on the Visual Debugger, or set a <a href="/features/test-maintenance/steps-pane" target="_blank">Breakpoint</a> ahead of time, to interrupt the test and perform Debug Options.

![Visual debugger][1]

Once the test pauses, the following Debug Options are available:

* Show the <a href="/features/elements-menu/dom-explorer" target="_blank">DOM Explorer</a> of the currently displayed page.
* Capture the currently failed state. Save a .zip file containing a snapshot of the DOM, browser image, and test log.
* Diagnose a failure directly. Only enabled on detected failures.
	* Opens the <a href="/features/verifications/advanced-verification" target="_blank">Sentence Verification Builder</a> for failed Verifications.
	* Opens the <a href="/features/elements-explorer/find-element" target="_blank">Find Element</a> dialog for Unable to locate element failures.
* View the current execution log of the test.
* Easily record any bugs in the target application during debugging.

![Debug options][2]

Resume normal execution with the **Play** button, or use the **Fast Forward** button to execute one step at a time.

## See also ##

* <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-visual-debugger" target="_blank">Using the Visual Debugger</a>

[1]: /img/general-information/test-execution/visual-debugger/fig1.png
[2]: /img/general-information/test-execution/visual-debugger/fig2.png