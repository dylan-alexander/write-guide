---
title: Using Rich Edit Controls
description: This section contains topics that demonstrate how to create and use rich edit controls.
ms.assetid: 2c4717c9-3257-42d5-9c36-89b7e524e788
ms.topic: article
ms.date: 05/31/2018
---

# Using Rich Edit Controls

This section contains topics that demonstrate how to create and use rich edit controls.

## In this section



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="create-rich-edit-controls">How to Create Rich Edit Controls</a><br/></td>
<td>To create a rich edit control, call the <a href="https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-createwindowexa"><strong>CreateWindowEx</strong></a> function, specifying the rich edit window class. For Microsoft Rich Edit 4.1 (Msftedit.dll), specify MSFTEDIT_CLASS as the window class. For all previous versions, specify RICHEDIT_CLASS. For more information, see <a href="about-rich-edit-controls">Versions of Rich Edit</a>. <br/> Rich edit controls support most of the window styles used with edit controls as well as additional styles. You should specify the <a href="edit-control-styles"><strong>ES_MULTILINE</strong></a> window style if you want to allow more than one line of text in the control. For more information, see <a href="rich-edit-control-styles">Rich Edit Control Styles</a>. <br/></td>
</tr>
<tr class="even">
<td><a href="format-text-in-rich-edit-controls">How to Format Text in Rich Edit Controls</a><br/></td>
<td>An application can send messages to a rich edit control in order to format characters and paragraphs and retrieve formatting information. Paragraph formatting attributes include alignment, tabs, indents, numbering, and simple tables. For characters, you can specify font name, size, color, and effects such as bold, italic, and protected. <br/></td>
</tr>
<tr class="odd">
<td><a href="interact-with-the-current-selection">How to Interact with the Current Selection</a><br/></td>
<td>The user can select text in a rich edit control by using the mouse or the keyboard. The <em>current selection</em> is the range of selected characters, or the position of the insertion point if no characters are selected. An application can get information about the current selection, set it, determine when it changes, and show or hide the selection highlight. <br/></td>
</tr>
<tr class="even">
<td><a href="use-rich-edit-text-operations">How to Use Rich Edit Text Operations</a><br/></td>
<td>An application can send messages to retrieve or find text in a rich edit control. You can retrieve either the selected text or a specified range of text. <br/></td>
</tr>
<tr class="odd">
<td><a href="use-word-and-line-break-information">How to Use Word and Line Break Information</a><br/></td>
<td>A rich edit control calls a function called a word-break procedure to find breaks between words and to determine where it can break lines. The control uses this information when performing word-wrap operations and when processing CTRL+LEFT ARROW key and CTRL+RIGHT ARROW key combinations. An application can send messages to a rich edit control to replace the default word-break procedure, to retrieve word-break information, and to determine what line a given character falls on. <br/></td>
</tr>
<tr class="even">
<td><a href="use-rich-edit-clipboard-operations">How to Use Rich Edit Clipboard Operations</a><br/></td>
<td>An application can paste the contents of the clipboard into a rich edit control by using either the best available clipboard format or a specific clipboard format. You can also determine whether a rich edit control is capable of pasting a clipboard format. <br/></td>
</tr>
<tr class="odd">
<td><a href="use-streams">How to Use Streams</a><br/></td>
<td>You can use streams to transfer data into or out of a rich edit control. A stream is defined by an <a href="/windows/desktop/api/Richedit/ns-richedit-_editstream"><strong>EDITSTREAM</strong></a> structure, which specifies a buffer and an application-defined callback function. <br/></td>
</tr>
<tr class="even">
<td><a href="automatically-resize-rich-edit-controls">How to Automatically Resize Rich Edit Controls</a><br/></td>
<td>An application can resize a rich edit control as needed so that it is always the same size as its contents. A rich edit control supports this so-called <em>bottomless</em> functionality by sending its parent window an <a href="en-requestresize">EN_REQUESTRESIZE</a> notification code whenever the size of the control's content changes. <br/></td>
</tr>
<tr class="odd">
<td><a href="use-rich-edit-control-notification-codes">How to Use Rich Edit Control Notification Codes</a><br/></td>
<td>A rich edit control's parent window can process notification codes to monitor events that affect the control. Rich edit controls support all of the notification codes that are used with edit controls, as well as several additional ones. <br/></td>
</tr>
<tr class="even">
<td><a href="use-font-binding-in-rich-edit-controls">How to Use Font Binding in Rich Edit Controls</a><br/></td>
<td>Microsoft Rich Edit 3.0 assigns a character set to plain-text characters depending on their context. Some examples are: <br/>
<ul>
<li>Greek characters are assigned <strong>GREEK_CHARSET</strong>.</li>
<li>Hangul symbols are assigned <strong>HANGUL_CHARSET</strong>.</li>
<li>Chinese characters are assigned <strong>SHIFTJIS_CHARSET</strong> if kana characters are found nearby, or <strong>GB2312_CHARSET</strong> if no kana are found nearby.</li>
<li>Non-neutral ANSI characters are assigned <strong>ANSI_CHARSET</strong> in any event.</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="using-rich-edit-com">How to Use OLE in Rich Edit Controls</a><br/></td>
<td>This section contains information about using object linking and embedding (OLE) in rich edit controls. <br/></td>
</tr>
<tr class="even">
<td><a href="printing-rich-edit-controls">How to Print the Contents of Rich Edit Controls</a><br/></td>
<td>This section contains information about how to print the contents of rich edit controls. <br/></td>
</tr>
</tbody>
</table>



 

 

 





