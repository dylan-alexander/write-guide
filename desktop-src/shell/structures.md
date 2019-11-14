---
Description: This section describes the Windows Shell Structures.
title: Shell Structures
ms.topic: article
ms.date: 05/31/2018
ms.assetid: 814ae153-39b3-49ee-9da1-efe7e649c73e
api_name: 
api_type: 
api_location: 
topic_type:
- kbArticle
---

# Shell Structures

This section describes the Windows Shell Structures.

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
<td><a href="/windows/desktop/api/Shlobj/ns-shlobj-tagaamenufilename"><strong>AASHELLMENUFILENAME</strong></a><br/></td>
<td>A variable-size structure that contains information about a menu file name.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shlobj/ns-shlobj-tagaashellmenuitem"><strong>AASHELLMENUITEM</strong></a><br/></td>
<td>Contains information about a menu item.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-_appbardata"><strong>APPBARDATA</strong></a><br/></td>
<td>Contains information about a system appbar message.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Appmgmt/ns-appmgmt-_appcategoryinfo"><strong>APPCATEGORYINFO</strong></a><br/></td>
<td>Provides application category information to Add/Remove Programs in Control Panel. The <a href="/windows/desktop/api/Appmgmt/ns-appmgmt-_appcategoryinfolist"><strong>APPCATEGORYINFOLIST</strong></a> structure is used create a complete list of categories for an application publisher.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Appmgmt/ns-appmgmt-_appcategoryinfolist"><strong>APPCATEGORYINFOLIST</strong></a><br/></td>
<td>Provides a list of supported application categories from an application publisher to Add/Remove Programs in Control Panel. <br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shappmgr/ns-shappmgr-_appinfodata"><strong>APPINFODATA</strong></a><br/></td>
<td>Provides information about a published application to the Add/Remove Programs Control Panel utility.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-associationelement"><strong>ASSOCIATIONELEMENT</strong></a><br/></td>
<td>Defines information used by <a href="/windows/desktop/api/Shellapi/nf-shellapi-assoccreateforclasses"><strong>AssocCreateForClasses</strong></a> to retrieve an <a href="https://docs.microsoft.com/windows/desktop/api/shlwapi/nn-shlwapi-iqueryassociations"><strong>IQueryAssociations</strong></a> interface for a given file association.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shlobj/ns-shlobj-bandinfosfb"><strong>BANDINFOSFB</strong></a><br/></td>
<td>Contains information about a folder band. This structure is used with the <a href="https://docs.microsoft.com/windows/desktop/api/shlobj/nf-shlobj-ishellfolderband-getbandinfosfb"><strong>IShellFolderBand::GetBandInfoSFB</strong></a> and <a href="https://docs.microsoft.com/windows/desktop/api/shlobj/nf-shlobj-ishellfolderband-setbandinfosfb"><strong>IShellFolderBand::SetBandInfoSFB</strong></a> methods.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-tagbandsiteinfo"><strong>BANDSITEINFO</strong></a><br/></td>
<td>Contains information about a band site. This structure is used with the <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ibandsite-getbandsiteinfo"><strong>IBandSite::GetBandSiteInfo</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ibandsite-setbandsiteinfo"><strong>IBandSite::SetBandSiteInfo</strong></a> methods.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shdeprecated/ns-shdeprecated-basebrowserdatalh"><strong>BASEBROWSERDATA</strong></a><br/></td>
<td>Contains protected members of the base class. <a href="/windows/desktop/api/Shdeprecated/ns-shdeprecated-basebrowserdatalh"><strong>BASEBROWSERDATA</strong></a> defines the browser state and is used with <a href="/windows/desktop/api/Shdeprecated/nf-shdeprecated-ibrowserservice2-getbasebrowserdata"><strong>IBrowserService2::GetBaseBrowserData</strong></a> and <a href="/windows/desktop/api/Shdeprecated/nf-shdeprecated-ibrowserservice2-putbasebrowserdata"><strong>IBrowserService2::PutBaseBrowserData</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/cc136564(v=vs.85)"><strong>BORDERWIDTHS</strong></a><br/></td>
<td>Defines the coordinates of the upper-left and lower-right corners of a border rectangle.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_browseinfoa"><strong>BROWSEINFO</strong></a><br/></td>
<td>Contains parameters for the <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shbrowseforfoldera"><strong>SHBrowseForFolder</strong></a> function and receives information about the folder selected by the user.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ns-shobjidl_core-category_info"><strong>CATEGORY_INFO</strong></a><br/></td>
<td>Contains category information. A component category is a group of logically-related Component Object Model (COM) classes that share a common category identifier (CATID).<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_ida"><strong>CIDA</strong></a><br/></td>
<td>Used with the <a href="clipboard">CFSTR_SHELLIDLIST</a> clipboard format to transfer the pointer to an item identifier list (PIDL) of one or more Shell namespace objects.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ns-shobjidl_core-cm_columninfo"><strong>CM_COLUMNINFO</strong></a><br/></td>
<td>Defines column information. Used by members of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-icolumnmanager"><strong>IColumnManager</strong></a> interface.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-_cminvokecommandinfo"><strong>CMINVOKECOMMANDINFO</strong></a><br/></td>
<td>Contains information needed by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-icontextmenu-invokecommand"><strong>IContextMenu::InvokeCommand</strong></a> to invoke a shortcut menu command.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-_cminvokecommandinfoex"><strong>CMINVOKECOMMANDINFOEX</strong></a><br/></td>
<td>Contains extended information about a shortcut menu command. This structure is an extended version of <a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-_cminvokecommandinfo"><strong>CMINVOKECOMMANDINFO</strong></a> that allows the use of Unicode values.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shtypes/ns-shtypes-_comdlg_filterspec"><strong>COMDLG_FILTERSPEC</strong></a><br/></td>
<td>Used generically to filter elements.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_tagcomponent"><strong>COMPONENT</strong></a><br/></td>
<td>Used by Windows 2000 to hold information about a component. This structure replaces the <a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_tagie4component"><strong>IE4COMPONENT</strong></a> structure.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_tagcomponentsopt"><strong>COMPONENTSOPT</strong></a><br/></td>
<td>Contains the desktop item options.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_tagcomppos"><strong>COMPPOS</strong></a><br/></td>
<td>Holds information about a component's position and size.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_tagcompstateinfo"><strong>COMPSTATEINFO</strong></a><br/></td>
<td>Used by Windows 2000 to hold information about a component's state.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Syncmgr/ns-syncmgr-confirm_conflict_item"><strong>CONFIRM_CONFLICT_ITEM</strong></a><br/></td>
<td>Defines conflict item structure.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Syncmgr/ns-syncmgr-confirm_conflict_result_info"><strong>CONFIRM_CONFLICT_RESULT_INFO</strong></a><br/></td>
<td>Defines conflict result information structure.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Cpl/ns-cpl-tagcplinfo"><strong>CPLINFO</strong></a><br/></td>
<td>Contains resource information and an application-defined value for a dialog box supported by a Control Panel application. The <a href="https://docs.microsoft.com/windows/desktop/api/cpl/nc-cpl-applet_proc"><strong>CPlApplet</strong></a> function of the Control Panel application returns this information to the Control Panel in response to a <a href="cpl-inquire"><strong>CPL_INQUIRE</strong></a> message.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Credentialprovider/ns-credentialprovider-_credential_provider_credential_serialization"><strong>CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION</strong></a><br/></td>
<td>Contains details about a credential.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Credentialprovider/ns-credentialprovider-_credential_provider_field_descriptor"><strong>CREDENTIAL_PROVIDER_FIELD_DESCRIPTOR</strong></a><br/></td>
<td>Describes a single field in a credential. For example, a string or a user image.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_csfv"><strong>CSFV</strong></a><br/></td>
<td>Used with the <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shcreateshellfolderviewex"><strong>SHCreateShellFolderViewEx</strong></a> function.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-tagdatablockheader"><strong>DATABLOCK_HEADER</strong></a><br/></td>
<td>Serves as the header for some of the extra data structures used by <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishelllinkdatalist"><strong>IShellLinkDataList</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-defcontextmenu"><strong>DEFCONTEXTMENU</strong></a><br/></td>
<td>Contains context menu information used by <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shcreatedefaultcontextmenu"><strong>SHCreateDefaultContextMenu</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ns-shobjidl_core-delegateitemid"><strong>DELEGATEITEMID</strong></a><br/></td>
<td>Used by delegate folders in place of a standard <a href="/windows/desktop/api/Shtypes/ns-shtypes-_itemidlist"><strong>ITEMIDLIST</strong></a> structure.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_detailsinfo"><strong>DETAILSINFO</strong></a><br/></td>
<td>Contains detail information for a Shell folder item. Used with the <a href="sfvm-getdetailsof"><strong>SFVM_GETDETAILSOF</strong></a> notification.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-dfmics"><strong>DFMICS</strong></a><br/></td>
<td>Contains additional arguments used by <a href="dfm-invokecommandex"><strong>DFM_INVOKECOMMANDEX</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shlwapi/ns-shlwapi-_dllversioninfo"><strong>DLLVERSIONINFO</strong></a><br/></td>
<td>Receives DLL-specific version information. It is used with the <a href="/windows/desktop/api/Shlwapi/nc-shlwapi-dllgetversionproc"><strong>DllGetVersion</strong></a> function. <br/>
<blockquote>
[!Note]<br />
In place of this structure, you can use the <a href="/windows/desktop/api/Shlwapi/ns-shlwapi-_dllversioninfo2"><strong>DLLVERSIONINFO2</strong></a> structure.
</blockquote>
<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlwapi/ns-shlwapi-_dllversioninfo2"><strong>DLLVERSIONINFO2</strong></a><br/></td>
<td>Receives DLL-specific version information. It is used with the <a href="/windows/desktop/api/Shlwapi/nc-shlwapi-dllgetversionproc"><strong>DllGetVersion</strong></a> function.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-dropdescription"><strong>DROPDESCRIPTION</strong></a><br/></td>
<td>Describes the image and accompanying text for a drop object.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_dropfiles"><strong>DROPFILES</strong></a><br/></td>
<td>Defines the <a href="clipboard">CF_HDROP</a> clipboard format. The data that follows is a double null-terminated list of file names.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-exp_darwin_link"><strong>EXP_DARWIN_LINK</strong></a><br/></td>
<td>Holds an extra data block used by <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishelllinkdatalist"><strong>IShellLinkDataList</strong></a>. It holds the link's Windows Installer ID.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-exp_propertystorage"><strong>EXP_PROPERTYSTORAGE</strong></a><br/></td>
<td>Stores information about the Shell link state. This structure is used for extra data sections that are tagged with EXP_PROPERTYSTORAGE_SIG.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-exp_special_folder"><strong>EXP_SPECIAL_FOLDER</strong></a><br/></td>
<td>Holds an extra data block used by <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishelllinkdatalist"><strong>IShellLinkDataList</strong></a>. It holds special folder information.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-exp_sz_link"><strong>EXP_SZ_LINK</strong></a><br/></td>
<td>Holds an extra data block used by <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishelllinkdatalist"><strong>IShellLinkDataList</strong></a>. It holds expandable environment strings for the icon or target.<br/></td>
</tr>
<tr class="even">
<td><a href="ext-button"><strong>EXT_BUTTON</strong></a><br/></td>
<td>Contains information about a button that a File Manager extension DLL is adding to the toolbar of File Manager.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ns-shobjidl_core-extrasearch"><strong>EXTRASEARCH</strong></a><br/></td>
<td>Used by an <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ienumextrasearch"><strong>IEnumExtraSearch</strong></a> enumerator object to return information on the search objects supported by a Shell Folder object.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-file_attributes_array"><strong>FILE_ATTRIBUTES_ARRAY</strong></a><br/></td>
<td>Contains the clipboard format definition for CFSTR_FILE_ATTRIBUTES_ARRAY.<br/></td>
</tr>
<tr class="odd">
<td><a href="https://docs.microsoft.com/windows/desktop/api/shlobj_core/ns-shlobj_core-filedescriptora"><strong>FILEDESCRIPTOR</strong></a><br/></td>
<td>Describes the properties of a file that is being copied by means of the clipboard during a Microsoft ActiveX <a href="dragdrop">drag-and-drop</a> operation.<br/></td>
</tr>
<tr class="even">
<td><a href="https://docs.microsoft.com/windows/desktop/api/shlobj_core/ns-shlobj_core-filegroupdescriptora"><strong>FILEGROUPDESCRIPTOR</strong></a><br/></td>
<td>Defines the CF_FILEGROUPDESCRIPTOR clipboard format.<br/></td>
</tr>
<tr class="odd">
<td><a href="fms-getdriveinfo"><strong>FMS_GETDRIVEINFO</strong></a><br/></td>
<td>Contains information about the drive selected in the active File Manager window (the directory window or the Search Results window).<br/></td>
</tr>
<tr class="even">
<td><a href="fms-getfilesel"><strong>FMS_GETFILESEL</strong></a><br/></td>
<td>Contains information about a selected file in the active File Manager window (the directory window or the Search Results window).<br/></td>
</tr>
<tr class="odd">
<td><a href="fms-helpstring"><strong>FMS_HELPSTRING</strong></a><br/></td>
<td>Contains information that File Manager uses to add a Help string for a menu or toolbar command item.<br/></td>
</tr>
<tr class="even">
<td><a href="fms-load"><strong>FMS_LOAD</strong></a><br/></td>
<td>Contains information that File Manager uses to add a custom menu provided by a File Manager extension DLL. The structure also provides a delta value that the extension DLL can use to manipulate the custom menu after File Manager has loaded the menu.<br/></td>
</tr>
<tr class="odd">
<td><a href="fms-toolbarload"><strong>FMS_TOOLBARLOAD</strong></a><br/></td>
<td>Contains information about custom buttons to be added to the File Manager toolbar. The buttons are provided by a File Manager extension DLL.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ns-shobjidl_core-foldersettings"><strong>FOLDERSETTINGS</strong></a><br/></td>
<td>Contains folder view information.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlobj/ns-shlobj-fvshowinfo"><strong>FVSHOWINFO</strong></a><br/></td>
<td>Contains information that the file viewer uses to display a file.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Winuser/ns-winuser-taghelpinfo"><strong>HELPINFO</strong></a><br/></td>
<td>Contains information about an item for which context-sensitive Help has been requested.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Winuser/ns-winuser-taghelpwininfoa"><strong>HELPWININFO</strong></a><br/></td>
<td>Contains the size and position of either a primary or secondary Help window. An application can set this information by calling the <a href="/windows/desktop/api/Winuser/nf-winuser-winhelpa"><strong>WinHelp</strong></a> function with the HELP_SETWINPOS value.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_tagie4component"><strong>IE4COMPONENT</strong></a><br/></td>
<td>Used by Microsoft Internet Explorer 4.0 and Microsoft Internet Explorer 4.01 to hold information about a component. With Windows 2000, it is replaced by the <a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_tagcomponent"><strong>COMPONENT</strong></a> structure.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shtypes/ns-shtypes-_itemidlist"><strong>ITEMIDLIST</strong></a><br/></td>
<td>Contains a list of item identifiers.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_itemspacing"><strong>ITEMSPACING</strong></a><br/></td>
<td>Stores the dimensions of the two possible sizes of icon spacing that are available for display: small and large. Used by <a href="https://docs.microsoft.com/windows/desktop/api/shlobj_core/nf-shlobj_core-ishellfolderview-getitemspacing"><strong>IShellFolderView::GetItemSpacing</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-knownfolder_definition"><strong>KNOWNFOLDER_DEFINITION</strong></a><br/></td>
<td>Defines the specifics of a known folder.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/dimm/ns-dimm-__midl___midl_itf_dimm_0000_0000_0003"><strong>LOGFONT</strong></a><br/></td>
<td>Defines the attributes of a font.<br/></td>
</tr>
<tr class="odd">
<td><a href="mruinfo"><strong>MRUINFO</strong></a><br/></td>
<td>Contains information that defines a new most recently used (MRU) list. Used by <a href="createmrulist"><strong>CreateMRUListW</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Winuser/ns-winuser-tagmultikeyhelpa"><strong>MULTIKEYHELP</strong></a><br/></td>
<td>Specifies a keyword to search for and the keyword table to be searched by Windows Help.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-tagnc_address"><strong>NC_ADDRESS</strong></a><br/></td>
<td>Contains information that describes a network address.<br/></td>
</tr>
<tr class="even">
<td><a href="https://docs.microsoft.com/windows/desktop/shell/hkey-type"><strong>NET_ADDRESS_INFO</strong></a><br/></td>
<td>Describes a network address.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Cpl/ns-cpl-tagnewcplinfoa"><strong>NEWCPLINFO</strong></a><br/></td>
<td>Contains resource information and an application-defined value for a dialog box supported by a Control Panel application.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-_notifyicondataa"><strong>NOTIFYICONDATA</strong></a><br/></td>
<td>Contains information that the system needs to display notifications in the notification area. Used by <a href="/windows/desktop/api/Shellapi/nf-shellapi-shell_notifyicona"><strong>Shell_NotifyIcon</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-_notifyiconidentifier"><strong>NOTIFYICONIDENTIFIER</strong></a><br/></td>
<td>Contains information used by <a href="/windows/desktop/api/Shellapi/nf-shellapi-shell_notifyicongetrect"><strong>Shell_NotifyIconGetRect</strong></a> to identify the icon for which to retrieve the bounding rectangle.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_nresarray"><strong>NRESARRAY</strong></a><br/></td>
<td>Defines the CF_NETRESOURCE clipboard format.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl/ns-shobjidl-nstccustomdraw"><strong>NSTCCUSTOMDRAW</strong></a><br/></td>
<td>Custom draw structure used by <a href="/windows/desktop/api/Shobjidl/nn-shobjidl-inamespacetreecontrolcustomdraw"><strong>INameSpaceTreeControlCustomDraw</strong></a> methods.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-nt_console_props"><strong>NT_CONSOLE_PROPS</strong></a><br/></td>
<td>Holds an extra data block used by <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishelllinkdatalist"><strong>IShellLinkDataList</strong></a>. It holds console properties.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-nt_fe_console_props"><strong>NT_FE_CONSOLE_PROPS</strong></a><br/></td>
<td>Holds an extra data block used by <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishelllinkdatalist"><strong>IShellLinkDataList</strong></a>. It holds the console's code page.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-_open_printer_props_infoa"><strong>OPEN_PRINTER_PROPS_INFO</strong></a><br/></td>
<td>Identifies a particular property sheet in a printer's property pages and whether that property sheet should be modal. Optionally used with the <a href="/windows/desktop/api/Shellapi/nf-shellapi-shinvokeprintercommanda"><strong>SHInvokePrinterCommand</strong></a> function.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_openasinfo"><strong>OPENASINFO</strong></a><br/></td>
<td>Stores information for the <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shopenwithdialog"><strong>SHOpenWithDialog</strong></a> function.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl/ns-shobjidl-_overlapped"><strong>OVERLAPPED</strong></a><br/></td>
<td>Contains information used in asynchronous (overlapped) input/output (I/O).<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlwapi/ns-shlwapi-tagparsedurla"><strong>PARSEDURL</strong></a><br/></td>
<td>Used by the <a href="/windows/desktop/api/Shlwapi/nf-shlwapi-parseurla"><strong>ParseURL</strong></a> function to return the parsed URL.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-_persist_folder_target_info"><strong>PERSIST_FOLDER_TARGET_INFO</strong></a><br/></td>
<td>Specifies a folder shortcut's target folder and its attributes. This structure is used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipersistfolder3-getfoldertargetinfo"><strong>IPersistFolder3::GetFolderTargetInfo</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipersistfolder3-initializeex"><strong>IPersistFolder3::InitializeEx</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-previewhandlerframeinfo"><strong>PREVIEWHANDLERFRAMEINFO</strong></a><br/></td>
<td>Accelerator table structure. Used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipreviewhandlerframe-getwindowcontext"><strong>IPreviewHandlerFrame::GetWindowContext</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Profinfo/ns-profinfo-_profileinfoa"><strong>PROFILEINFO</strong></a><br/></td>
<td>Contains information used when loading or unloading a user profile.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shappmgr/ns-shappmgr-_pubappinfo"><strong>PUBAPPINFO</strong></a><br/></td>
<td>Provides information about a published application from an application publisher to <strong>Add/Remove Programs</strong> in Control Panel.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_qcminfo"><strong>QCMINFO</strong></a><br/></td>
<td>Contains information for merging menu items into Windows Explorer menus.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlwapi/ns-shlwapi-qitab"><strong>QITAB</strong></a><br/></td>
<td>Used by the <a href="/windows/desktop/api/Shlwapi/nf-shlwapi-qisearch"><strong>QISearch</strong></a> function to describe a single interface.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Propidl/ns-propidl-tagserializedpropertyvalue"><strong>SERIALIZEDPROPERTYVALUE</strong></a><br/></td>
<td>A range of memory of arbitrary type that represents a serialized <a href="https://docs.microsoft.com/windows/win32/api/propidl/ns-propidl-propvariant"><strong>PROPVARIANT</strong></a> structure. Programs should not inspect the contents of a <a href="/windows/desktop/api/Propidl/ns-propidl-tagserializedpropertyvalue"><strong>SERIALIZEDPROPERTYVALUE</strong></a>; instead, they should manipulate it with the <a href="https://docs.microsoft.com/windows/desktop/api/propvarutil/nf-propvarutil-stgserializepropvariant"><strong>StgSerializePropVariant</strong></a> and <a href="https://docs.microsoft.com/windows/desktop/api/propvarutil/nf-propvarutil-stgdeserializepropvariant"><strong>StgDeserializePropVariant</strong></a> functions.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_sfv_create"><strong>SFV_CREATE</strong></a><br/></td>
<td>This structure is used with the <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shcreateshellfolderview"><strong>SHCreateShellFolderView</strong></a> function.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shlobj/ns-shlobj-_sfv_setitempos"><strong>SFV_SETITEMPOS</strong></a><br/></td>
<td>Stores position information for an item. Used with message <a href="sfvm-setitempos"><strong>SFVM_SETITEMPOS</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_sfvm_helptopic_data"><strong>SFVM_HELPTOPIC_DATA</strong></a><br/></td>
<td>Contains the name of an HTML Help file and a topic in that file. Used with the <a href="sfvm-gethelptopic"><strong>SFVM_GETHELPTOPIC</strong></a> notification. This structure requires Unicode strings.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_sfvm_proppage_data"><strong>SFVM_PROPPAGE_DATA</strong></a><br/></td>
<td>Contains the details of a page to be added to an object's <strong>Properties</strong> sheet.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-shardappidinfo"><strong>SHARDAPPIDINFO</strong></a><br/></td>
<td>Contains data used by <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shaddtorecentdocs"><strong>SHAddToRecentDocs</strong></a> to identify both an item—in this case as an <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishellitem"><strong>IShellItem</strong></a>—and the process that it is associated with.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-shardappidinfoidlist"><strong>SHARDAPPIDINFOIDLIST</strong></a><br/></td>
<td>Contains data used by <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shaddtorecentdocs"><strong>SHAddToRecentDocs</strong></a> to identify both an item—in this case by an absolute PIDL—and the process that it is associated with.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-shardappidinfolink"><strong>SHARDAPPIDINFOLINK</strong></a><br/></td>
<td>Contains data used by <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shaddtorecentdocs"><strong>SHAddToRecentDocs</strong></a> to identify both an item, in this case through an <a href="/windows/desktop/api/Shobjidl_core/nn-shobjidl_core-ishelllinka"><strong>IShellLink</strong></a>, and the process that it is associated with.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_shchangenotifyentry"><strong>SHChangeNotifyEntry</strong></a><br/></td>
<td>Contains and receives information for change notifications. This structure is used with the <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shchangenotifyregister"><strong>SHChangeNotifyRegister</strong></a> function and the <a href="sfvm-queryfsnotify"><strong>SFVM_QUERYFSNOTIFY</strong></a> notification.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlobj/ns-shlobj-shcolumndata"><strong>SHCOLUMNDATA</strong></a><br/></td>
<td>Contains information that identifies a particular file. It is used by <a href="https://docs.microsoft.com/windows/desktop/api/shlobj/nf-shlobj-icolumnprovider-getitemdata"><strong>IColumnProvider::GetItemData</strong></a> when requesting data for a particular file.<br/></td>
</tr>
<tr class="even">
<td><a href="https://docs.microsoft.com/windows/desktop/shell/objects"><strong>SHCOLUMNID</strong></a><br/></td>
<td>Specifies the FMTID/PID identifier of a column that will be displayed by the Windows Explorer Details view. <br/>
<blockquote>
[!Note]<br />
As of Windows Vista, <a href="https://docs.microsoft.com/windows/desktop/shell/objects"><strong>SHCOLUMNID</strong></a> is considered a legacy form and should not be used. In its place, use the <a href="https://docs.microsoft.com/windows/desktop/api/wtypes/ns-wtypes-propertykey"><strong>PROPERTYKEY</strong></a> structure.
</blockquote>
<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlobj/ns-shlobj-shcolumninfo"><strong>SHCOLUMNINFO</strong></a><br/></td>
<td>Contains information about the properties of a column. It is used by <a href="https://docs.microsoft.com/windows/desktop/api/shlobj/nf-shlobj-icolumnprovider-getcolumninfo"><strong>IColumnProvider::GetColumnInfo</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shlobj/ns-shlobj-shcolumninit"><strong>SHCOLUMNINIT</strong></a><br/></td>
<td>Passes initialization information to <a href="https://docs.microsoft.com/windows/desktop/api/shlobj/nf-shlobj-icolumnprovider-initialize"><strong>IColumnProvider::Initialize</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_shdescriptionid"><strong>SHDESCRIPTIONID</strong></a><br/></td>
<td>Receives item data in response to a call to <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shgetdatafromidlista"><strong>SHGetDataFromIDList</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-shdragimage"><strong>SHDRAGIMAGE</strong></a><br/></td>
<td>Contains the information needed to create a drag image.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-shell_item_resource"><strong>SHELL_ITEM_RESOURCE</strong></a><br/></td>
<td>Defines Shell item resource.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shtypes/ns-shtypes-_shelldetails"><strong>SHELLDETAILS</strong></a><br/></td>
<td>Reports detailed information on an item in a Shell folder.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-_shellexecuteinfoa"><strong>SHELLEXECUTEINFO</strong></a><br/></td>
<td>Contains information used by <a href="/windows/desktop/api/Shellapi/nf-shellapi-shellexecuteexa"><strong>ShellExecuteEx</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-shellflagstate"><strong>SHELLFLAGSTATE</strong></a><br/></td>
<td>Contains a set of flags that indicate the current Shell settings. This structure is used with the <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shgetsettings"><strong>SHGetSettings</strong></a> function.<br/></td>
</tr>
<tr class="odd">
<td><a href="https://docs.microsoft.com/windows/desktop/api/shlobj_core/ns-shlobj_core-shellstatea"><strong>SHELLSTATE</strong></a><br/></td>
<td>Contains settings for the Shell's state. This structure is used with the <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shgetsetsettings"><strong>SHGetSetSettings</strong></a> function.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-_shfileinfoa"><strong>SHFILEINFO</strong></a><br/></td>
<td>Contains information about a file object.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-_shfileopstructa"><strong>SHFILEOPSTRUCT</strong></a><br/></td>
<td>Contains information that the <a href="/windows/desktop/api/Shellapi/nf-shellapi-shfileoperationa"><strong>SHFileOperation</strong></a> function uses to perform file operations. <br/>
<blockquote>
[!Note]<br />
As of Windows Vista, the use of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ifileoperation"><strong>IFileOperation</strong></a> interface is recommended over this function.
</blockquote>
<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-shfoldercustomsettings"><strong>SHFOLDERCUSTOMSETTINGS</strong></a><br/></td>
<td>Holds custom folder settings. This structure is used with the <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shgetsetfoldercustomsettings"><strong>SHGetSetFolderCustomSettings</strong></a> function.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shtypes/ns-shtypes-_shitemid"><strong>SHITEMID</strong></a><br/></td>
<td>Defines an item identifier.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-_shnamemappinga"><strong>SHNAMEMAPPING</strong></a><br/></td>
<td>Contains the old and new path names for each file that was moved, copied, or renamed by the <a href="/windows/desktop/api/Shellapi/nf-shellapi-shfileoperationa"><strong>SHFileOperation</strong></a> function.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-_shqueryrbinfo"><strong>SHQUERYRBINFO</strong></a><br/></td>
<td>Contains the size and item count information retrieved by the <a href="/windows/desktop/api/Shellapi/nf-shellapi-shqueryrecyclebina"><strong>SHQueryRecycleBin</strong></a> function.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shellapi/ns-shellapi-_shstockiconinfo"><strong>SHSTOCKICONINFO</strong></a><br/></td>
<td>Receives information used to retrieve a stock Shell icon. This structure is used in a call <a href="/windows/desktop/api/Shellapi/nf-shellapi-shgetstockiconinfo"><strong>SHGetStockIconInfo</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shappmgr/ns-shappmgr-_tagslowappinfo"><strong>SLOWAPPINFO</strong></a><br/></td>
<td>Provides specialized application information to <strong>Add/Remove Programs</strong> in Control Panel. This structure is not applicable to published applications.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ns-shobjidl_core-shcschangenotifystruct"><strong>SMCSHCHANGENOTIFYSTRUCT</strong></a><br/></td>
<td>Contains information about change notification. It is used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellmenucallback-callbacksm"><strong>IShellMenuCallback::CallbackSM</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-tagsmdata"><strong>SMDATA</strong></a><br/></td>
<td>Contains information from a menu band.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-tagsminfo"><strong>SMINFO</strong></a><br/></td>
<td>Contains information about an item from a menu band.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Urlmon/ns-urlmon-_tagsoftdistinfo"><strong>SOFTDISTINFO</strong></a><br/></td>
<td>Contains information about a software update.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-sortcolumn"><strong>SORTCOLUMN</strong></a><br/></td>
<td>Stores information about how to sort a column that is displayed in the folder view.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shtypes/ns-shtypes-_strret"><strong>STRRET</strong></a><br/></td>
<td>Contains strings returned from the <a href="https://docs.microsoft.com/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishellfolder"><strong>IShellFolder</strong></a> interface methods.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-_sv2cvw2_params"><strong>SV2CVW2_PARAMS</strong></a><br/></td>
<td>Holds the parameters for the <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellview2-createviewwindow2"><strong>IShellView2::CreateViewWindow2</strong></a> method.<br/></td>
</tr>
<tr class="odd">
<td><a href="https://docs.microsoft.com/windows/desktop/shell/objects-cpp"><strong>SYNC_HANDLER_ITEM_INFO</strong></a><br/></td>
<td>Defines a handler for a scheduled synchronization. Used with <a href="https://docs.microsoft.com/previous-versions/windows/desktop/isync-schedule/bb774680(v=vs.85)"><strong>ISyncSchedule::AddItem</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Syncmgr/ns-syncmgr-syncmgr_conflict_id_info"><strong>SYNCMGR_CONFLICT_ID_INFO</strong></a><br/></td>
<td>Describes conflict ID information structure.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Mobsync/ns-mobsync-_tagsyncmgrhandlerinfo"><strong>SYNCMGRHANDLERINFO</strong></a><br/></td>
<td>Provides information about the handler for use in the <a href="/windows/desktop/api/Mobsync/nf-mobsync-isyncmgrsynchronize-gethandlerinfo"><strong>ISyncMgrSynchronize::GetHandlerInfo</strong></a> method.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Mobsync/ns-mobsync-_tagsyncmgritem"><strong>SYNCMGRITEM</strong></a><br/></td>
<td>Provides information about items being enumerated by the <a href="/windows/desktop/api/mobsync/nn-mobsync-isyncmgrenumitems"><strong>ISyncMgrEnumItems</strong></a> interface.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Mobsync/ns-mobsync-_tagsyncmgrlogerrorinfo"><strong>SYNCMGRLOGERRORINFO</strong></a><br/></td>
<td>Provides error information for use in the <a href="/windows/desktop/api/Mobsync/nf-mobsync-isyncmgrsynchronizecallback-logerror"><strong>ISyncMgrSynchronizeCallback::LogError</strong></a> method.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Mobsync/ns-mobsync-_tagsyncmgrprogressitem"><strong>SYNCMGRPROGRESSITEM</strong></a><br/></td>
<td>Provides status information while a synchronization is in progress. This structure is used with the <a href="/windows/desktop/api/Mobsync/nf-mobsync-isyncmgrsynchronizecallback-progress"><strong>ISyncMgrSynchronizeCallback::Progress</strong></a> method and corresponds to a single synchronization item.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlobj/ns-shlobj-_tbinfo"><strong>TBINFO</strong></a><br/></td>
<td>Used with the <a href="sfvm-getbuttoninfo"><strong>SFVM_GETBUTTONINFO</strong></a> notification to specify the number of buttons to add to the toolbar, as well as how they're added.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-thumbbutton"><strong>THUMBBUTTON</strong></a><br/></td>
<td>Used by methods of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-itaskbarlist3"><strong>ITaskbarList3</strong></a> interface to define buttons used in a toolbar embedded in a window's thumbnail representation.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-_tagwallpaperopt"><strong>WALLPAPEROPT</strong></a><br/></td>
<td>Contains the wallpaper display options. Used with members of the <a href="https://docs.microsoft.com/windows/desktop/api/shlobj_core/nn-shlobj_core-iactivedesktop"><strong>IActiveDesktop</strong></a> interface.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Tlogstg/ns-tlogstg-_windowdata"><strong>WINDOWDATA</strong></a><br/></td>
<td>Stores window data.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Thumbcache/ne-thumbcache-wts_contextflags"><strong>WTS_CONTEXTFLAGS</strong></a><br/></td>
<td>Specifies the context of a thumbnail extraction. Used by <a href="/windows/desktop/api/Thumbcache/nf-thumbcache-ithumbnailsettings-setcontext"><strong>IThumbnailSettings::SetContext</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Thumbcache/ne-thumbcache-wts_flags"><strong>WTS_FLAGS</strong></a><br/></td>
<td>Values used by <a href="/windows/desktop/api/Thumbcache/nf-thumbcache-ithumbnailcache-getthumbnail"><strong>IThumbnailCache::GetThumbnail</strong></a> to specify options for the extraction and display of the thumbnail image.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Thumbcache/ns-thumbcache-wts_thumbnailid"><strong>WTS_THUMBNAILID</strong></a><br/></td>
<td>Contains a unique identifier for a thumbnail in the system thumbnail cache.<br/></td>
</tr>
</tbody>
</table>



 

 

 




