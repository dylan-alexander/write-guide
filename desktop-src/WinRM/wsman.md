---
title: WSMan object (WSManDisp.h)
description: Provides methods and properties used to create a session, represented by a Session object.
ms.assetid: 45895a4e-b7de-4469-ae78-6d1d3f9d6145
ms.tgt_platform: multiple
keywords:
- WSMan object Windows Remote Management
- WSMan object Windows Remote Management , described
topic_type:
- apiref
api_name:
- WSMan
api_location:
- WSMAuto.dll
api_type:
- COM
ms.topic: reference
ms.date: 05/31/2018
---

# WSMan object

Provides methods and properties used to create a session, represented by a [**Session**](session.md) object. Any Windows Remote Management operations require creation of a [**Session**](session.md) that connects to a remote computer, [*base management controller*](windows-remote-management-glossary.md) (BMC), or the local computer. Operations include getting, writing, enumerating data, or invoking methods.

## Members

The **WSMan** object has these types of members:

-   [Methods](#methods)
-   [Properties](#properties)

### Methods

The **WSMan** object has these methods.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: left;">Method</th>
<th style="text-align: left;">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-createconnectionoptions"><strong>CreateConnectionOptions</strong></a></td>
<td style="text-align: left;">Creates a <a href="connectionoptions"><strong>ConnectionOptions</strong></a> object that specifies the user name and password used when creating a remote session.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-createresourcelocator"><strong>CreateResourceLocator</strong></a></td>
<td style="text-align: left;">Creates a <a href="resourcelocator"><strong>ResourceLocator</strong></a> object that can specify:<br/>
<ul>
<li>The complete path to a <a href="windows-remote-management-glossary"><em>resource</em></a> or a single piece of data.</li>
<li>A <a href="windows-remote-management-glossary"><em>selector</em></a> for a specific instance of a resource.</li>
<li>An <a href="windows-remote-management-glossary"><em>option</em></a> that supplies additional data to the resource provider.</li>
</ul></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-createsession"><strong>CreateSession</strong></a></td>
<td style="text-align: left;">Creates a <a href="session"><strong>Session</strong></a> object that can then be used for subsequent network operations.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-enumerationflaghierarchydeep"><strong>WSMan.EnumerationFlagHierarchyDeep</strong></a></td>
<td style="text-align: left;">Returns the value of the enumeration flag <strong>EnumerationFlagHierarchyDeep</strong> for use in the <em>flags</em> parameter of <a href="session-enumerate"><strong>Session.Enumerate</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-enumerationflaghierarchydeepbasepropsonly"><strong>WSMan.EnumerationFlagHierarchyDeepBasePropsOnly</strong></a></td>
<td style="text-align: left;">Returns the value of the enumeration flag <strong>EnumerationFlagHierarchyDeepBasePropsOnly</strong> for use in the <em>flags</em> parameter of <a href="session-enumerate"><strong>Session.Enumerate</strong></a>.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-enumerationflaghierarchyshallow"><strong>WSMan.EnumerationFlagHierarchyShallow</strong></a></td>
<td style="text-align: left;">Returns the value of the enumeration flag <strong>EnumerationFlagHierarchyShallow</strong> for use in the <em>flags</em> parameter of <a href="session-enumerate"><strong>Session.Enumerate</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-enumerationflagnonxmltext"><strong>WSMan.EnumerationFlagNonXmlText</strong></a></td>
<td style="text-align: left;">Returns the value of the enumeration constant <strong>WSManFlagNonXmlText</strong> for use in the <em>flags</em> parameter of the <a href="session-enumerate"><strong>Session.Enumerate</strong></a> method.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-enumerationflagreturnepr"><strong>WSMan.EnumerationFlagReturnEPR</strong></a></td>
<td style="text-align: left;">Returns the value of the enumeration flag <strong>EnumerationFlagReturnEPR</strong> for use in the <em>flags</em> parameter of <a href="session-enumerate"><strong>Session.Enumerate</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-enumerationflagreturnobject"><strong>WSMan.EnumerationFlagReturnObject</strong></a></td>
<td style="text-align: left;">Returns the value of the enumeration flag <strong>EnumerationFlagReturnObject</strong> for use in the <em>flags</em> parameter of <a href="session-enumerate"><strong>Session.Enumerate</strong></a>.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-enumerationflagreturnobjectandepr"><strong>WSMan.EnumerationFlagReturnObjectAndEPR</strong></a></td>
<td style="text-align: left;">Returns the value of the enumeration flag <strong>EnumerationFlagReturnObjectAndEPR</strong> for use in the <em>flags</em> parameter of <a href="session-enumerate"><strong>Session.Enumerate</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-geterrormessage"><strong>WSMan.GetErrorMessage</strong></a></td>
<td style="text-align: left;">Returns a formatted string containing the text of an error number.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-sessionflagcredusernamepassword"><strong>WSMan.SessionFlagCredUsernamePassword</strong></a></td>
<td style="text-align: left;">Returns the value of the authentication flag <strong>WSManFlagCredUsernamePassword</strong> for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-sessionflagenablespnserverport"><strong>WSMan.SessionFlagEnableSPNServerPort</strong></a></td>
<td style="text-align: left;">Returns the value of the authentication flag <strong>WSManFlagEnableSPNServerPort</strong> for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-sessionflagnoencryption"><strong>WSMan.SessionFlagNoEncryption</strong></a></td>
<td style="text-align: left;">Returns the value of the authentication flag <strong>WSManFlagNoEncryption</strong> for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-sessionflagskipcacheck"><strong>WSMan.SessionFlagSkipCACheck</strong></a></td>
<td style="text-align: left;">Returns the value of the <strong>WSManFlagSkipCACheck</strong> authentication flag for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-sessionflagskipcncheck"><strong>WSMan.SessionFlagSkipCNCheck</strong></a></td>
<td style="text-align: left;">Returns the value of the authentication flag <strong>WSManFlagSkipCNCheck</strong> for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-sessionflagusebasic"><strong>WSMan.SessionFlagUseBasic</strong></a></td>
<td style="text-align: left;">Returns the value of the authentication flag <strong>WSManFlagUseBasic</strong> for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-sessionflagusedigest"><strong>WSMan.SessionFlagUseDigest</strong></a></td>
<td style="text-align: left;">Returns the value of the authentication flag <strong>WSManFlagUseDigest</strong> for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-sessionflagusekerberos"><strong>WSMan.SessionFlagUseKerberos</strong></a></td>
<td style="text-align: left;">Returns the value of the authentication flag <strong>WSManFlagUseKerberos</strong> for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-sessionflagusenegotiate"><strong>WSMan.SessionFlagUseNegotiate</strong></a></td>
<td style="text-align: left;">Returns the value of the authentication flag <strong>WSManFlagUseNegotiate</strong> for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><a href="wsman-sessionflagusenoauthentication"><strong>WSMan.SessionFlagUseNoAuthentication</strong></a></td>
<td style="text-align: left;">Returns the value of the authentication flag <strong>WSManFlagUseNoAuthentication</strong> for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><a href="wsman-sessionflagutf8"><strong>WSMan.SessionFlagUTF8</strong></a></td>
<td style="text-align: left;">Returns the value of the authentication flag <strong>WSManFlagUTF8</strong> for use in the <em>flags</em> parameter of <a href="wsman-createsession"><strong>WSMan.CreateSession</strong></a>.<br/></td>
</tr>
</tbody>
</table>



 

### Properties

The **WSMan** object has these properties.



| Property                                            | Access type          | Description                                                                   |
|:----------------------------------------------------|:---------------------|:------------------------------------------------------------------------------|
| [**CommandLine**](wsman-commandline.md)<br/> | Read-only<br/> | Gets the unprocessed command line for the current hosting process.<br/> |
| [**Error**](wsman-error.md)<br/>             | Read-only<br/> | Gets error information.<br/>                                            |



 

## Remarks

The **WSMan** object corresponds to the [**IWSMan**](/windows/desktop/api/WSManDisp/nn-wsmandisp-iwsman) and [**IWSManEx**](/windows/desktop/api/WSManDisp/nn-wsmandisp-iwsmanex) interfaces. **WSMan** is the only object that can be created directly using [CreateObject](https://docs.microsoft.com/previous-versions//xzysf6hc(v=vs.85)).

## Examples

The following code example shows how to instantiate a **WSMan** object.


```VB
Dim objWsman
Dim Session, Resource 
Set objWsman = CreateObject( "WSMAN.Automation" )
Set Session = objWsman.CreateSession
strResource = "https://schemas.microsoft.com/wbem/wsman/1/wmi/Root/CIMv2/Win32_OperatingSystem"
```



## Requirements



|                                     |                                                                                          |
|-------------------------------------|------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                 |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                           |
| Header<br/>                   | <dl> <dt>WSManDisp.h</dt> </dl>   |
| IDL<br/>                      | <dl> <dt>WSManDisp.idl</dt> </dl> |
| Library<br/>                  | <dl> <dt>WSManDisp.tlb</dt> </dl> |
| DLL<br/>                      | <dl> <dt>WSMAuto.dll</dt> </dl>   |



## See also

<dl> <dt>

[WinRM Scripting API](winrm-scripting-api.md)
</dt> <dt>

[About Windows Remote Management](about-windows-remote-management.md)
</dt> <dt>

[Using Windows Remote Management](using-windows-remote-management.md)
</dt> <dt>

[Scripting in Windows Remote Management](scripting-in-windows-remote-management.md)
</dt> <dt>

[Obtaining Data from the Local Computer](obtaining-data-from-the-local-computer.md)
</dt> <dt>

[Obtaining Data from a Remote Computer](obtaining-data-from-a-remote-computer.md)
</dt> </dl>

 

 





