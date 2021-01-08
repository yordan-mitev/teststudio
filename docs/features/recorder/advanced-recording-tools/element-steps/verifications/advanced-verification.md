---
title: Advanced Verification
page_title: Create Advanced Verifications
description: "Create Advanced Verifications in Test Studio test. Verify an element's attribute in Test Studio test"
position: 6
---
# Create Advanced Verifications

An advanced verification allows you to interactively build verification rules and validate them against a live web document or WPF application.

In order to create custom verification you need to highlight the element and choose **Build Step...** from the menu:

![Build Step][1]

In the Advanced Recording Tools select **Verifications** tab.

![Verifications][2]

Start by selecting the type verification you want to add:

- IsVisible
- Content
- Attributes
- Style
- IsEnabled
- <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/image-verification" target="_blank">Image</a>
- <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/text-from-image" target="_blank">TextFromImage</a>

![Available verifications][3]

When crafting verifications, content is dynamically built against the currently selected element. As selections are made, default values are populated according to values the element contains.
For example, choose Content as the verification type and three menu options appear. 

![Content][4]

Click on the down arrow next to each option to see a list of possible values.

<table id="no-table">
<tr>
<td>![Inner Text][5]</td>
<td>![Exact][6]</td>
</tr>
<table>

Once finished building the verification(s), click **Add Step** to add it as a step to the current test.

![Add Step][7]

The newly created verification appears in the test:

![Test Steps][8]

> **Tip**
>
> We recommend against using the Content Markup validation types. They are fragile in the face of minor page changes, and different browsers may reorder the element attributes making them unreliable. For more information please see our Automated Testing blog entry on <a href="http://blogs.telerik.com/jimholmes/posts/11-08-23/understanding-validation-content-element-types.aspx" target="_blank">**Understanding Validation Content Element Types**</a>. 

[1]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig4.png
[5]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig5.png
[6]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig6.png
[7]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig7.png
[8]: /img/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification/fig8.png
