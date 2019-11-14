---
Description: These topics describe the documents and printing features of Windows that enable applications to save, view, and print.
ms.assetid: 20e56af6-9598-4d6a-a2bf-454cef8a3368
title: Documents and Printing
ms.topic: reference
ms.date: 05/31/2018
---

# Documents and Printing

These topics describe the documents and printing features of Windows that enable applications to save, view, and print.

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
<td><a href="https://docs.microsoft.com/windows/desktop/printdocs/what-s-new-for-printing-in-windows-vnext">What's New for Printing</a><br/></td>
<td>Windows 8 supports <a href="https://docs.microsoft.com/previous-versions/windows/apps/hh465225(v=win.10)">printing for Windows Store apps using JavaScript and HTML</a> and <a href="https://docs.microsoft.com/previous-versions/windows/apps/hh465196(v=win.10)">printing for Windows Store apps using C#/VB/C++ and XAML</a>.<br/> Windows 8 also includes a new COM-based API that provides full support for Open XPS and access to portions of the new printer drivers that Windows 8 supports. For more information about the new API, see <a href="https://docs.microsoft.com/windows/desktop/printdocs/tailored-app-printing-api">Print Document Package API</a>.<br/> The Windows Print Driver Inbox Program makes sure that Windows 8 includes support for a high percentage of the popular printers.<br/></td>
</tr>
<tr class="even">
<td><a href="https://docs.microsoft.com/windows/desktop/printdocs/jobbindalldocuments">XPS Documents</a><br/></td>
<td>Information about the XPS Document API an XPS Digital Signatures.<br/>
<ul>
<li><a href="https://docs.microsoft.com/previous-versions/windows/desktop/dd316976(v=vs.85)">XPS Document API</a><br/> The XPS Document API is a native Windows API that supports the XPS OM. The XPS Document API was introduced in Windows 7 and can be used in user-mode programs and XPSDrv printer drivers.<br/></li>
<li><a href="https://docs.microsoft.com/previous-versions/windows/desktop/ff819108(v=vs.85)">XPS Digital Signature API</a><br/> XPS Digital Signatures enable document signing, verification of the signer's identity, and indication of whether an XPS document has changed since it was signed.<br/></li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="printdocs-printing">Printing</a><br/></td>
<td>Information about the printing features supported by Windows. These features include:<br/>
<ul>
<li><a href="https://docs.microsoft.com/windows/desktop/printdocs/tailored-app-printing-api">Print Document Package API</a><br/> Provides apps with an interface that allows the management of the <strong>PrintDocument</strong> package.<br/></li>
<li><a href="print-spooler-api">Print Spooler API</a><br/> Provides an interface to the print spooler so that applications can manage printers and print jobs.<br/></li>
<li><a href="print-ticket-api">Print Ticket API</a><br/> Provides applications with functions to manage and convert print tickets.<br/></li>
<li><a href="gdi-printing">GDI Print API</a><br/> Provides applications with a device-independent printing interface. <br/></li>
<li><p><a href="xps-printing">XPS Print API</a><br/> Provides an interface to the print spooler that applications can use to send XPS documents to a printer.</p>
<blockquote>
[!Note]<br />
The XPS Print API is not supported and may be altered or unavailable in the future. Client applications should use the <a href="https://docs.microsoft.com/windows/desktop/printdocs/tailored-app-printing-api">Print Document Package API</a> instead.
</blockquote>
<p><br/> <br/></p></li>
</ul></td>
</tr>
<tr class="even">
<td><a href="https://docs.microsoft.com/windows/desktop/printdocs/printschema">Print Schema</a><br/></td>
<td>The Print Schema and related technologies describe a printer's features and specify the printing preferences of a document to printers and viewing applications. The <a href="https://go.microsoft.com/?linkid=7141496">Print Schema Specification</a> is a downloadable document that contains information about the Print Schema and how to use it in documents and printing. The online information that is found in this section is provided for your information only and might not accurately reflect the current version of the <a href="https://go.microsoft.com/?linkid=7141496">Print Schema Specification</a>.<br/> Refer to the <a href="https://go.microsoft.com/?linkid=7141496">Print Schema Specification</a> for the most current design information.<br/></td>
</tr>
</tbody>
</table>



 

## Additional resources

The [Print Sample sample app](https://go.microsoft.com/fwlink/p/?linkid=242999) demonstrates how to print from a Windows Store app starting with Windows 8.

The features described in this section are for native Windows programming. To use similar features in .NET (managed) programming, see [Windows Presentation Foundation Documents](https://msdn.microsoft.com/en-us/library/ms749165(v=VS.85).aspx).

XPS documents are built on the [Packaging](https://docs.microsoft.com/previous-versions/windows/desktop/opc/packaging) API. See the Packaging API, for lower level access to the contents of an XPS document.

## Related topics

<dl> <dt>

[Bidirectional printer communications (Hardware Dev Center)](https://go.microsoft.com/fwlink/p/?LinkId=613189  )
</dt> </dl>

 

 




