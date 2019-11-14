---
Description: Functions for setting and retrieving an objects security descriptor.
ms.assetid: 22bf0d6b-3ec6-4c28-ace4-49e48714f4bf
title: Low-level Security Descriptor Functions
ms.topic: article
ms.date: 05/31/2018
---

# Low-level Security Descriptor Functions

There are several pairs of low-level functions for setting and retrieving an object's [*security descriptor*](https://docs.microsoft.com/windows/desktop/SecGloss/s-gly). Each of these pairs works only with a limited set of Windows objects. For example, one pair works with file objects and another works with registry keys. The following table shows the low-level functions to use with the different types of securable objects.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Object type</th>
<th>Low-level functions</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><a href="https://docs.microsoft.com/windows/desktop/FileIO/file-security-and-access-rights">Files</a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/FileIO/file-security-and-access-rights">Directories</a></li>
<li>Mailslots</li>
<li><a href="https://docs.microsoft.com/windows/desktop/ipc/named-pipe-security-and-access-rights">Named pipes</a></li>
</ul></td>
<td>Use the <a href="/windows/desktop/api/Winbase/nf-winbase-getfilesecuritya"><strong>GetFileSecurity</strong></a> and <a href="/windows/desktop/api/Winbase/nf-winbase-setfilesecuritya"><strong>SetFileSecurity</strong></a> functions. These functions use character strings to identify the securable object, instead of using handles.</td>
</tr>
<tr class="even">
<td><ul>
<li><a href="https://docs.microsoft.com/windows/desktop/ProcThread/process-security-and-access-rights">Processes</a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/ProcThread/thread-security-and-access-rights">Threads</a></li>
<li><a href="access-rights-for-access-token-objects">Access tokens</a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/Memory/file-mapping-security-and-access-rights">File-mapping objects</a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/Sync/synchronization-object-security-and-access-rights">Semaphores</a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/Sync/synchronization-object-security-and-access-rights">Events</a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/Sync/synchronization-object-security-and-access-rights">Mutexes</a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/Sync/synchronization-object-security-and-access-rights">Waitable timers</a></li>
</ul></td>
<td>Use the <a href="https://docs.microsoft.com/windows/desktop/api/securitybaseapi/nf-securitybaseapi-getkernelobjectsecurity"><strong>GetKernelObjectSecurity</strong></a> and <a href="https://docs.microsoft.com/windows/desktop/api/securitybaseapi/nf-securitybaseapi-setkernelobjectsecurity"><strong>SetKernelObjectSecurity</strong></a> functions.</td>
</tr>
<tr class="odd">
<td><ul>
<li><a href="https://docs.microsoft.com/windows/desktop/winstation/window-station-security-and-access-rights">Window stations</a></li>
<li><a href="https://docs.microsoft.com/windows/desktop/winstation/desktop-security-and-access-rights">Desktops</a></li>
</ul></td>
<td>Use the <a href="/windows/desktop/api/Winuser/nf-winuser-getuserobjectsecurity"><strong>GetUserObjectSecurity</strong></a> and <a href="/windows/desktop/api/Winuser/nf-winuser-setuserobjectsecurity"><strong>SetUserObjectSecurity</strong></a> functions.</td>
</tr>
<tr class="even">
<td><ul>
<li><a href="https://docs.microsoft.com/windows/desktop/SysInfo/registry-key-security-and-access-rights">Registry keys</a></li>
</ul></td>
<td>Use the <a href="/windows/desktop/api/Winreg/nf-winreg-reggetkeysecurity"><strong>RegGetKeySecurity</strong></a> and <a href="/windows/desktop/api/Winreg/nf-winreg-regsetkeysecurity"><strong>RegSetKeySecurity</strong></a> functions.</td>
</tr>
<tr class="odd">
<td><ul>
<li><a href="https://docs.microsoft.com/windows/desktop/Services/service-security-and-access-rights">Windows service objects</a></li>
</ul></td>
<td>Use the <a href="/windows/desktop/api/Winsvc/nf-winsvc-queryserviceobjectsecurity"><strong>QueryServiceObjectSecurity</strong></a> and <a href="/windows/desktop/api/Winsvc/nf-winsvc-setserviceobjectsecurity"><strong>SetServiceObjectSecurity</strong></a> functions.</td>
</tr>
<tr class="even">
<td><ul>
<li>Printer objects</li>
</ul></td>
<td>Use the <a href="https://docs.microsoft.com/windows/desktop/printdocs/printer-info-2"><strong>PRINTER_INFO_2</strong></a> structure with the <a href="https://docs.microsoft.com/windows/desktop/printdocs/getprinter"><strong>GetPrinter</strong></a> and <a href="https://docs.microsoft.com/windows/desktop/printdocs/setprinter"><strong>SetPrinter</strong></a> functions.</td>
</tr>
<tr class="odd">
<td><ul>
<li><a href="https://docs.microsoft.com/windows/desktop/NetMgmt/security-requirements-for-the-network-management-functions">Network shares</a></li>
</ul></td>
<td>Use level 502 with the <a href="https://docs.microsoft.com/windows/desktop/api/lmshare/nf-lmshare-netsharegetinfo"><strong>NetShareGetInfo</strong></a> and <a href="https://docs.microsoft.com/windows/desktop/api/lmshare/nf-lmshare-netsharesetinfo"><strong>NetShareSetInfo</strong></a> functions.</td>
</tr>
<tr class="even">
<td><ul>
<li><a href="acl-based-access-control">Private objects (objects private to the creating application)</a></li>
</ul></td>
<td>Use the <a href="https://docs.microsoft.com/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurity"><strong>CreatePrivateObjectSecurity</strong></a>, <a href="https://docs.microsoft.com/windows/desktop/api/securitybaseapi/nf-securitybaseapi-destroyprivateobjectsecurity"><strong>DestroyPrivateObjectSecurity</strong></a>, <a href="https://docs.microsoft.com/windows/desktop/api/securitybaseapi/nf-securitybaseapi-getprivateobjectsecurity"><strong>GetPrivateObjectSecurity</strong></a> and <a href="https://docs.microsoft.com/windows/desktop/api/securitybaseapi/nf-securitybaseapi-setprivateobjectsecurity"><strong>SetPrivateObjectSecurity</strong></a> functions.</td>
</tr>
</tbody>
</table>



 

 

 



