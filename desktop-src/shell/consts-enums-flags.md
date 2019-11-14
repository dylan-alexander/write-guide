---
Description: This section describes the Windows Shell constants, enumerations, and flags.
title: Shell Constants, Enumerations, and Flags
ms.topic: article
ms.date: 05/31/2018
ms.assetid: 638beaa7-a065-4ab3-8eb5-286a306a8f24
api_name: 
api_type: 
api_location: 
topic_type: 
 - kbArticle

---

# Shell Constants, Enumerations, and Flags

This section describes the Windows Shell constants, enumerations, and flags.

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
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_svgio"><strong>_SVGIO</strong></a><br/></td>
<td>Used with the <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ifolderview-items"><strong>IFolderView::Items</strong></a>, <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ifolderview-itemcount"><strong>IFolderView::ItemCount</strong></a>, and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellview-getitemobject"><strong>IShellView::GetItemObject</strong></a> methods to restrict or control the items in their collections.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_svsif"><strong>_SVSIF</strong></a><br/></td>
<td>Indicates flags used by <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ifolderview"><strong>IFolderView</strong></a>, <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ifolderview2"><strong>IFolderView2</strong></a>, <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishellview"><strong>IShellView</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ishellview2"><strong>IShellView2</strong></a> to specify a type of selection to apply.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shappmgr/ne-shappmgr-_tagappactionflags"><strong>APPACTIONFLAGS</strong></a><br/></td>
<td>Specifies application management actions supported by an application publisher. These flags are bitmasks passed to <a href="/windows/desktop/api/Shappmgr/nf-shappmgr-ishellapp-getpossibleactions"><strong>IShellApp::GetPossibleActions</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shappmgr/ne-shappmgr-_tagappinfoflags"><strong>APPINFODATAFLAGS</strong></a><br/></td>
<td>Specifies application information to return from <a href="/windows/desktop/api/Shappmgr/nf-shappmgr-ishellapp-getappinfo"><strong>IShellApp::GetAppInfo</strong></a>. These flags are bitmasks used in the <a href="/windows/desktop/api/Shappmgr/ns-shappmgr-_appinfodata"><strong>dwMask</strong></a> member of the <strong>APPINFODATA</strong> structure.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl_core/ne-shobjidl_core-application_view_orientation"><strong>APPLICATION_VIEW_ORIENTATION</strong></a><br/></td>
<td>Defines the set of display orientation modes for a window (app view). Used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationdesignmodesettings2-getapplicationvieworientation"><strong>IApplicationDesignModeSettings2::GetApplicationViewOrientation</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationdesignmodesettings2-setapplicationvieworientation"><strong>IApplicationDesignModeSettings2::SetApplicationViewOrientation</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl_core/ne-shobjidl_core-application_view_size_preference"><strong>APPLICATION_VIEW_SIZE_PREFERENCE</strong></a><br/></td>
<td>Defines the set of possible general window (app view) size preferences. Used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ilaunchsourceviewsizepreference-getsourceviewsizepreference"><strong>ILaunchSourceViewSizePreference::GetSourceViewSizePreference</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ilaunchtargetviewsizepreference-gettargetviewsizepreference"><strong>ILaunchTargetViewSizePreference::GetTargetViewSizePreference</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-application_view_state"><strong>APPLICATION_VIEW_STATE</strong></a><br/></td>
<td>Indicates the current view state of a Windows Store app. Used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationdesignmodesettings-setapplicationviewstate"><strong>IApplicationDesignModeSettings::SetApplicationViewState</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationdesignmodesettings-isapplicationviewstatesupported"><strong>IApplicationDesignModeSettings::IsApplicationViewStateSupported</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shlwapi/ne-shlwapi-assocdata"><strong>ASSOCDATA</strong></a><br/></td>
<td>Used by <a href="https://docs.microsoft.com/windows/desktop/api/shlwapi/nf-shlwapi-iqueryassociations-getdata"><strong>IQueryAssociations::GetData</strong></a> to define the type of data that is to be returned.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/win32/shell/assocf_str"><strong>ASSOCF</strong></a><br/></td>
<td>Provides information to the <a href="https://docs.microsoft.com/windows/desktop/api/shlwapi/nn-shlwapi-iqueryassociations"><strong>IQueryAssociations</strong></a> interface methods.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-associationlevel"><strong>ASSOCIATIONLEVEL</strong></a><br/></td>
<td>Specifies the source of the default association for a file name extension. Used by methods of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-iapplicationassociationregistration"><strong>IApplicationAssociationRegistration</strong></a> interface.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-associationtype"><strong>ASSOCIATIONTYPE</strong></a><br/></td>
<td>Specifies the type of association for an application. Used by methods of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-iapplicationassociationregistration"><strong>IApplicationAssociationRegistration</strong></a> interface.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shlwapi/ne-shlwapi-assockey"><strong>ASSOCKEY</strong></a><br/></td>
<td>Specifies the type of key to be returned by <a href="https://docs.microsoft.com/windows/desktop/api/shlwapi/nf-shlwapi-iqueryassociations-getkey"><strong>IQueryAssociations::GetKey</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlwapi/ne-shlwapi-assocstr"><strong>ASSOCSTR</strong></a><br/></td>
<td>Used by <a href="https://docs.microsoft.com/windows/desktop/api/shlwapi/nf-shlwapi-iqueryassociations-getstring"><strong>IQueryAssociations::GetString</strong></a> to define the type of string that is to be returned.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-attachment_action"><strong>ATTACHMENT_ACTION</strong></a><br/></td>
<td>Provides a set of flags to be used with <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iattachmentexecute-prompt"><strong>IAttachmentExecute::Prompt</strong></a> to indicate the action to be performed upon user confirmation.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-attachment_prompt"><strong>ATTACHMENT_PROMPT</strong></a><br/></td>
<td>Provides a set of flags to be used with <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iattachmentexecute-prompt"><strong>IAttachmentExecute::Prompt</strong></a> to indicate the type of prompt UI to display.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ne-shlobj_core-_tagautocompletelistoptions"><strong>AUTOCOMPLETELISTOPTIONS</strong></a><br/></td>
<td>Specifies which objects are enumerated for autocompletion lists.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shldisp/ne-shldisp-_tagautocompleteoptions"><strong>AUTOCOMPLETEOPTIONS</strong></a><br/></td>
<td>Specifies values used by <a href="/windows/desktop/api/Shldisp/nf-shldisp-iautocomplete2-getoptions"><strong>IAutoComplete2::GetOptions</strong></a> and <a href="/windows/desktop/api/Shldisp/nf-shldisp-iautocomplete2-setoptions"><strong>IAutoComplete2::SetOptions</strong></a> for options surrounding autocomplete.<br/></td>
</tr>
<tr class="even">
<td><a href="str-constants"><strong>Bind Context String Keys</strong></a><br/></td>
<td>A set of string keys that are used with the <a href="https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ibindctx-registerobjectparam"><strong>IBindCtx::RegisterObjectParam</strong></a> method to specify a bind context.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shdeprecated/ne-shdeprecated-tagbnstate"><strong>BNSTATE</strong></a><br/></td>
<td>Deprecated. Used by <a href="/windows/desktop/api/Shdeprecated/nf-shdeprecated-ibrowserservice-setnavigatestate"><strong>IBrowserService::SetNavigateState</strong></a> and <a href="/windows/desktop/api/Shdeprecated/nf-shdeprecated-ibrowserservice-getnavigatestate"><strong>IBrowserService::GetNavigateState</strong></a> to specify navigation states.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl_core/ne-shobjidl_core-_browserframeoptions"><strong>BROWSERFRAMEOPTIONS</strong></a><br/></td>
<td>Used with method <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ibrowserframeoptions-getframeoptions"><strong>IBrowserFrameOptions::GetFrameOptions</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-categoryinfo_flags"><strong>CATEGORYINFO_FLAGS</strong></a><br/></td>
<td>Provides a set of flags for use with the <a href="/windows/desktop/api/shobjidl_core/ns-shobjidl_core-category_info"><strong>CATEGORY_INFO</strong></a> structure.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-catsort_flags"><strong>CATSORT_FLAGS</strong></a><br/></td>
<td>Specifies methods for sorting category data.<br/></td>
</tr>
<tr class="odd">
<td><a href="https://docs.microsoft.com/previous-versions/windows/desktop/legacy/bb762483(v=vs.85)"><strong>CDCONTROLSTATE</strong></a><br/></td>
<td>Specifies the values that indicate whether a control is visible and enabled. Used by members of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ifiledialogcustomize"><strong>IFileDialogCustomize</strong></a> interface.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-cm_enum_flags"><strong>CM_ENUM_FLAGS</strong></a><br/></td>
<td>Used by members of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-icolumnmanager"><strong>IColumnManager</strong></a> interface to specify which set of columns are being requested, either all or only those currently visible.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-cm_mask"><strong>CM_MASK</strong></a><br/></td>
<td>Indicates which values in the <a href="/windows/desktop/api/shobjidl_core/ns-shobjidl_core-cm_columninfo"><strong>CM_COLUMNINFO</strong></a> structure should be set during calls to <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-icolumnmanager-setcolumninfo"><strong>IColumnManager::SetColumnInfo</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-cm_set_width_value"><strong>CM_SET_WIDTH_VALUE</strong></a><br/></td>
<td>Specifies width values in pixels and includes special support for default and autosize. Used by members of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-icolumnmanager"><strong>IColumnManager</strong></a> interface through the <a href="/windows/desktop/api/shobjidl_core/ns-shobjidl_core-cm_columninfo"><strong>CM_COLUMNINFO</strong></a> structure.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-cm_state"><strong>CM_STATE</strong></a><br/></td>
<td>Specifies column state values. Used by members of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-icolumnmanager"><strong>IColumnManager</strong></a> interface through the <a href="/windows/desktop/api/shobjidl_core/ns-shobjidl_core-cm_columninfo"><strong>CM_COLUMNINFO</strong></a> structure.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/CredentialProvider/ne-credentialprovider-credential_provider_account_options"><strong>CREDENTIAL_PROVIDER_ACCOUNT_OPTIONS</strong></a><br/></td>
<td>Indicates the type of credential that a credential provider should return to associate with the &quot;Other user&quot; tile. Used by <a href="/windows/desktop/api/CredentialProvider/nf-credentialprovider-icredentialprovideruserarray-getaccountoptions"><strong>ICredentialProviderUserArray_GetAccountOptions</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/CredentialProvider/ne-credentialprovider-credential_provider_credential_field_options"><strong>CREDENTIAL_PROVIDER_CREDENTIAL_FIELD_OPTIONS</strong></a><br/></td>
<td>Provides customization options for a single field in a logon or credential UI.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Credentialprovider/ne-credentialprovider-_credential_provider_field_interactive_state"><strong>CREDENTIAL_PROVIDER_FIELD_INTERACTIVE_STATE</strong></a><br/></td>
<td>Describes the state of a field and how it a user can interact with it. Fields can be displayed by a credential provider in a variety of different interactive states.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Credentialprovider/ne-credentialprovider-_credential_provider_field_state"><strong>CREDENTIAL_PROVIDER_FIELD_STATE</strong></a><br/></td>
<td>Specifies the state of a single field in the Credential UI.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Credentialprovider/ne-credentialprovider-_credential_provider_field_type"><strong>CREDENTIAL_PROVIDER_FIELD_TYPE</strong></a><br/></td>
<td>Specifies a type of credential field. Used by <a href="/windows/desktop/api/Credentialprovider/ns-credentialprovider-_credential_provider_field_descriptor"><strong>CREDENTIAL_PROVIDER_FIELD_DESCRIPTOR</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Credentialprovider/ne-credentialprovider-_credential_provider_get_serialization_response"><strong>CREDENTIAL_PROVIDER_GET_SERIALIZATION_RESPONSE</strong></a><br/></td>
<td>Describes the response when a credential provider attempts to serialize credentials.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Credentialprovider/ne-credentialprovider-_credential_provider_status_icon"><strong>CREDENTIAL_PROVIDER_STATUS_ICON</strong></a><br/></td>
<td>Indicates which status icon should be displayed.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Credentialprovider/ne-credentialprovider-_credential_provider_usage_scenario"><strong>CREDENTIAL_PROVIDER_USAGE_SCENARIO</strong></a><br/></td>
<td>Declares the scenarios in which a credential provider is supported. A credential provider usage scenario (CPUS) enables the credential provider to provide distinct enumeration behavior and UI field setup across scenarios.<br/></td>
</tr>
<tr class="even">
<td><a href="csidl"><strong>CSIDL</strong></a><br/></td>
<td><blockquote>
<p>[!Note]As of Windows Vista, these values have been replaced by <a href="knownfolderid"><strong>KNOWNFOLDERID</strong></a> values. See that topic for a list of the new constants and their corresponding CSIDL values. For convenience, corresponding <strong>KNOWNFOLDERID</strong> values are also noted here for each CSIDL value.</p>
<p>The CSIDL system is supported under Windows Vista for compatibility reasons. However, new development should use <a href="knownfolderid"><strong>KNOWNFOLDERID</strong></a> values rather than CSIDL values.<br/></p>
</blockquote>
<br/> CSIDL (constant special item ID list) values provide a unique system-independent way to identify special folders used frequently by applications, but which may not have the same name or location on any given system. For example, the system folder may be &quot;C:\Windows&quot; on one system and &quot;C:\Winnt&quot; on another. These constants are defined in Shlobj.h.<br/></td>
</tr>
<tr class="odd">
<td><a href="ctf"><strong>CTF Flags</strong></a><br/></td>
<td>Flags that control the calling function's behavior. Used by <a href="/windows/desktop/api/Shlwapi/nf-shlwapi-shcreatethread"><strong>SHCreateThread</strong></a> and <a href="/windows/desktop/api/Shlwapi/nf-shlwapi-shcreatethreadwithhandle"><strong>SHCreateThreadWithHandle</strong></a>. In those functions, these values are defined as being of type SHCT_FLAGS.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-dataobj_get_item_flags"><strong>DATAOBJ_GET_ITEM_FLAGS</strong></a><br/></td>
<td>Values used by the <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-shgetitemfromdataobject"><strong>SHGetItemFromDataObject</strong></a> function to specify options concerning the processing of the source object.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-tagdeskbandcid"><strong>DBID Command Flags</strong></a><br/></td>
<td>These command IDs can be sent to the band object's container with <a href="https://docs.microsoft.com/windows/desktop/api/docobj/nf-docobj-iolecommandtarget-exec"><strong>IOleCommandTarget::Exec</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-def_share_id"><strong>DEF_SHARE_ID</strong></a><br/></td>
<td>Values that specify the folder being acted on by methods of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-isharingconfigurationmanager"><strong>ISharingConfigurationManager</strong></a> interface.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-defaultsavefoldertype"><strong>DEFAULTSAVEFOLDERTYPE</strong></a><br/></td>
<td>Specifies the default save location.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-default_folder_menu_restrictions"><strong>DEFAULT_FOLDER_MENU_RESTRICTIONS</strong></a><br/></td>

</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-desktop_wallpaper_position"><strong>DESKTOP_WALLPAPER_POSITION</strong></a><br/></td>
<td>Specifies how the desktop wallpaper should be displayed.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shtypes/ne-shtypes-device_scale_factor"><strong>DEVICE_SCALE_FACTOR</strong></a><br/></td>
<td>Indicates a spoofed device scale factor, as a percent. Used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationdesignmodesettings-setapplicationviewstate"><strong>IApplicationDesignModeSettings::SetApplicationViewState</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationdesignmodesettings-isapplicationviewstatesupported"><strong>IApplicationDesignModeSettings::IsApplicationViewStateSupported</strong></a><br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/ShellScalingAPI/ne-shellscalingapi-display_device_type"><strong>DISPLAY_DEVICE_TYPE</strong></a><br/></td>
<td>Indicates whether the device is a primary or immersive type of display.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ne-shlobj_core-dropimagetype"><strong>DROPIMAGETYPE</strong></a><br/></td>
<td>Values used with the <a href="/windows/desktop/api/shlobj_core/ns-shlobj_core-dropdescription"><strong>DROPDESCRIPTION</strong></a> structure to specify the drop image.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_expcmdstate"><strong>EXPCMDSTATE</strong></a><br/></td>
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_expcmdstate"><strong>EXPCMDSTATE</strong></a> values represent the command state of a Shell item.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-explorer_browser_fill_flags"><strong>EXPLORER_BROWSER_FILL_FLAGS</strong></a><br/></td>
<td>These flags are used with <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iexplorerbrowser-fillfromobject"><strong>IExplorerBrowser::FillFromObject</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-explorer_browser_options"><strong>EXPLORER_BROWSER_OPTIONS</strong></a><br/></td>
<td>These flags are used with <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iexplorerbrowser-getoptions"><strong>IExplorerBrowser::GetOptions</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iexplorerbrowser-setoptions"><strong>IExplorerBrowser::SetOptions</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_explorerpanestate"><strong>EXPLORERPANESTATE</strong></a><br/></td>
<td>Indicate flags used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iexplorerpanevisibility-getpanestate"><strong>IExplorerPaneVisibility::GetPaneState</strong></a> to get the current state of the given Windows Explorer pane.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-fdap"><strong>FDAP</strong></a><br/></td>
<td>Specifies list placement.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-fde_overwrite_response"><strong>FDE_OVERWRITE_RESPONSE</strong></a><br/></td>
<td>Specifies the values used by the <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ifiledialogevents-onoverwrite"><strong>IFileDialogEvents::OnOverwrite</strong></a> method to indicate an application's response to an overwrite request during a save operation using the common file dialog.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-fde_shareviolation_response"><strong>FDE_SHAREVIOLATION_RESPONSE</strong></a><br/></td>
<td>Specifies the values used by the <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ifiledialogevents-onshareviolation"><strong>IFileDialogEvents::OnShareViolation</strong></a> method to indicate an application's response to a sharing violation that occurs when a file is opened or saved.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-fffp_mode"><strong>FFFP_MODE</strong></a><br/></td>
<td>Describes match criteria. Used by methods of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-iknownfoldermanager"><strong>IKnownFolderManager</strong></a> interface.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-file_usage_type"><strong>FILE_USAGE_TYPE</strong></a><br/></td>
<td>Constants used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ifileisinuse-getusage"><strong>IFileIsInUse::GetUsage</strong></a> to indicate how a file in use is being used.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_fileopendialogoptions"><strong>FILEOPENDIALOGOPTIONS</strong></a><br/></td>
<td>Defines the set of options available to an Open or Save dialog.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlwapi/ne-shlwapi-filetypeattributeflags"><strong>FILETYPEATTRIBUTEFLAGS</strong></a><br/></td>
<td>Indicates <a href="/windows/desktop/api/Shlwapi/ne-shlwapi-filetypeattributeflags"><strong>FILETYPEATTRIBUTEFLAGS</strong></a> constants that are used in the EditFlags value of a file association <a href="fa-progids">PROGID</a> registry key.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-folder_enum_mode"><strong>FOLDER_ENUM_MODE</strong></a><br/></td>
<td>Used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iobjectwithfolderenummode-getmode"><strong>IObjectWithFolderEnumMode::GetMode</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iobjectwithfolderenummode-setmode"><strong>IObjectWithFolderEnumMode::SetMode</strong></a> methods to get and set the display modes for the folders.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-folderflags"><strong>FOLDERFLAGS</strong></a><br/></td>
<td>A set of flags that specify folder view options. The flags are independent of each other and can be used in any combination.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-folderlogicalviewmode"><strong>FOLDERLOGICALVIEWMODE</strong></a><br/></td>
<td>Used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ifolderviewsettings-getviewmode"><strong>IFolderViewSettings::GetViewMode</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-isearchfolderitemfactory-setfolderlogicalviewmode"><strong>ISearchFolderItemFactory::SetFolderLogicalViewMode</strong></a> to describe the view mode.<br/></td>
</tr>
<tr class="odd">
<td><a href="foldertypeid"><strong>FOLDERTYPEID</strong></a><br/></td>
<td>The <a href="foldertypeid"><strong>FOLDERTYPEID</strong></a> values represent a view template applied to a folder, usually based on its intended use and contents.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-folderviewmode"><strong>FOLDERVIEWMODE</strong></a><br/></td>
<td>Specifies the folder view type.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl/ne-shobjidl-folderviewoptions"><strong>FOLDERVIEWOPTIONS</strong></a><br/></td>
<td>Used by methods of the <a href="/windows/desktop/api/Shobjidl/nn-shobjidl-ifolderviewoptions"><strong>IFolderViewOptions</strong></a> interface to activate Windows Vista options not supported by default in Windows 7 and later systems as well as deactivating new Windows 7 options.<br/></td>
</tr>
<tr class="even">
<td><a href="iactivedesktop-flags"><strong>IActiveDesktop Flags</strong></a><br/></td>
<td>This section describes the flags used by <a href="https://docs.microsoft.com/windows/desktop/api/shlobj_core/nn-shlobj_core-iactivedesktop"><strong>IActiveDesktop</strong></a> interface methods.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ne-shlobj_core-tagieshortcutflags"><strong>IESHORTCUTFLAGS</strong></a><br/></td>
<td>Specifies how a shortcut should be handled by the browser.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-kf_category"><strong>KF_CATEGORY</strong></a><br/></td>
<td>Value that represent a category by which a folder registered with the Known Folder system can be classified.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_kf_definition_flags"><strong>KF_DEFINITION_FLAGS</strong></a><br/></td>
<td>Flags that specify certain known folder behaviors. Used with the <a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-knownfolder_definition"><strong>KNOWNFOLDER_DEFINITION</strong></a> structure.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_kf_redirect_flags"><strong>KF_REDIRECT_FLAGS</strong></a><br/></td>
<td>Flags used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iknownfoldermanager-redirect"><strong>IKnownFolderManager::Redirect</strong></a> to specify details of a known folder redirection such as permissions and ownership for the redirected folder.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_kf_redirection_capabilities"><strong>KF_REDIRECTION_CAPABILITIES</strong></a><br/></td>
<td>Flags that specify the current redirection capabilities of a known folder. Used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iknownfolder-getredirectioncapabilities"><strong>IKnownFolder::GetRedirectionCapabilities</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ne-shlobj_core-known_folder_flag"><strong>KNOWN_FOLDER_FLAG</strong></a><br/></td>
<td>Specify special retrieval options for known folders. These values supersede <a href="csidl"><strong>CSIDL</strong></a> values, which have parallel meanings.<br/></td>
</tr>
<tr class="odd">
<td><a href="knownfolderid"><strong>KNOWNFOLDERID</strong></a><br/></td>
<td>The <a href="knownfolderid"><strong>KNOWNFOLDERID</strong></a> constants represent GUIDs that identify standard folders registered with the system as <a href="known-folders">Known Folders</a>. These folders are installed with Windows Vista and later operating systems, and a computer will have only folders appropriate to it installed. For descriptions of these folders, see <a href="csidl"><strong>CSIDL</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-libraryfolderfilter"><strong>LIBRARYFOLDERFILTER</strong></a><br/></td>
<td>Defines options for filtering folder items. <br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-librarymanagedialogoptions"><strong>LIBRARYMANAGEDIALOGOPTIONS</strong></a><br/></td>
<td>Used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-shshowmanagelibraryui"><strong>SHShowManageLibraryUI</strong></a> to define options for handling a name collision when saving a library.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-libraryoptionflags"><strong>LIBRARYOPTIONFLAGS</strong></a><br/></td>
<td>Specifies the library options.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-librarysaveflags"><strong>LIBRARYSAVEFLAGS</strong></a><br/></td>
<td>Specifies the options for handling a name collision when saving a library. <br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Intshcut/ne-intshcut-mimeassociationdialog_in_flags"><strong>MIMEASSOCIATIONDIALOG_IN_FLAGS</strong></a><br/></td>
<td>Used with the <a href="/windows/desktop/api/Intshcut/nf-intshcut-mimeassociationdialoga"><strong>MIMEAssociationDialog</strong></a> function to determine how it executes.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-monitor_app_visibility"><strong>MONITOR_APP_VISIBILITY</strong></a><br/></td>
<td>Specifies whether a display is showing desktop windows instead of Windows Store apps.<br/></td>
</tr>
<tr class="even">
<td><a href="mp-popupflags"><strong>MP_POPUPFLAGS constants</strong></a><br/></td>
<td>Represent options available when displaying a pop-up menu.<br/></td>
</tr>
<tr class="odd">
<td><a href="net-string"><strong>NET_STRING</strong></a><br/></td>
<td>Represent network address types. Use one or more (as a bitwise combination) of the following constants to create a network address mask to use with the macro <a href="/windows/desktop/api/Shellapi/nf-shellapi-netaddr_setallowtype"><strong>NetAddr_SetAllowType</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-nstcfoldercapabilities"><strong>NSTCFOLDERCAPABILITIES</strong></a><br/></td>
<td>Specifies the state of a tree item. These values are used by methods of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-inamespacetreecontrolfoldercapabilities"><strong>INameSpaceTreeControlFolderCapabilities</strong></a> interface.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_nstcitemstate"><strong>NSTCITEMSTATE</strong></a><br/></td>
<td>Specifies the state of a tree item. These values are used by methods of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-inamespacetreecontrol"><strong>INameSpaceTreeControl</strong></a> interface.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_nstcstyle"><strong>NSTCSTYLE</strong></a><br/></td>
<td>Describes the characteristics of a given namespace tree control.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl/ne-shobjidl-nstcstyle2"><strong>NSTCSTYLE2</strong></a><br/></td>
<td>Used by methods of the <a href="/windows/desktop/api/Shobjidl/nn-shobjidl-inamespacetreecontrol2"><strong>INameSpaceTreeControl2</strong></a> to specify extended display styles in a Shell namespace treeview.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-nwmf"><strong>NWMF</strong></a><br/></td>
<td>Flags used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-inewwindowmanager-evaluatenewwindow"><strong>INewWindowManager::EvaluateNewWindow</strong></a>. These values are factors in the decision of whether to display a pop-up window.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-package_execution_state"><strong>PACKAGE_EXECUTION_STATE</strong></a><br/></td>

</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shtypes/ne-shtypes-tagperceived"><strong>PERCEIVED</strong></a><br/></td>
<td>Specifies a file's perceived type. This set of constants is used in the <a href="/windows/desktop/api/Shlwapi/nf-shlwapi-assocgetperceivedtype"><strong>AssocGetPerceivedType</strong></a> function.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shappmgr/ne-shappmgr-_tagpublishedappinfoflags"><strong>PUBAPPINFOFLAGS</strong></a><br/></td>
<td>Specifies which members in the <a href="/windows/desktop/api/Shappmgr/ns-shappmgr-_pubappinfo"><strong>PUBAPPINFO</strong></a> structure are valid. These flags are bitmasks set in the <strong>dwMask</strong> member and passed to <a href="/windows/desktop/api/Shappmgr/nf-shappmgr-ipublishedapp-getpublishedappinfo"><strong>IPublishedApp::GetPublishedAppInfo</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shellapi/ne-shellapi-query_user_notification_state"><strong>QUERY_USER_NOTIFICATION_STATE</strong></a><br/></td>
<td>Specifies the state of the machine for the current user in relation to the propriety of sending a notification. Used by <a href="/windows/desktop/api/Shellapi/nf-shellapi-shqueryusernotificationstate"><strong>SHQueryUserNotificationState</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="hkey-type"><strong>Registry Data Types</strong></a><br/></td>
<td>These data types can be used to specify the type of a registry value.<br/></td>
</tr>
<tr class="even">
<td><a href="regsam"><strong>REGSAM</strong></a><br/></td>
<td>A data type used for specifying the security access attributes in the registry.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ne-shlobj_core-restrictions"><strong>RESTRICTIONS</strong></a><br/></td>
<td>These flags are used with the <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shrestricted"><strong>SHRestricted</strong></a> function. <strong>SHRestricted</strong> is used to determine whether a specified administrator policy is in effect. In many cases, applications need to modify certain behaviors in order to comply with the policies enacted by system administrators.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/ShellScalingAPI/ne-shellscalingapi-scale_change_flags"><strong>SCALE_CHANGE_FLAGS</strong></a><br/></td>
<td>Flags that are used to indicate the scaling change that occured.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shlobj_core/ne-shlobj_core-scnrt_status"><strong>SCNRT_STATUS</strong></a><br/></td>
<td>Indicates whether to enable or disable Async Register and Deregister for <a href="/windows/desktop/api/Shlobj/nf-shlobj-shchangenotifyregisterthread"><strong>SHChangeNotifyRegisterThread</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shlwapi/ne-shlwapi-tagsfbs_flags"><strong>SFBS_FLAGS</strong></a><br/></td>
<td>Specifies how the <a href="/windows/desktop/api/Shlwapi/nf-shlwapi-strformatbytesizeex"><strong>StrFormatByteSizeEx</strong></a> function should handle rounding of undisplayed digits.<br/></td>
</tr>
<tr class="odd">
<td><a href="sfgao"><strong>SFGAO</strong></a><br/></td>
<td>Attributes that can be retrieved on an item (file or folder) or set of items.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ne-shlobj_core-shard"><strong>SHARD</strong></a><br/></td>
<td>Indicates the interpretation of the data passed by <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shaddtorecentdocs"><strong>SHAddToRecentDocs</strong></a> in its <em>pv</em> parameter to identify the item whose usage statistics are being tracked.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-share_role"><strong>SHARE_ROLE</strong></a><br/></td>
<td>Specifies the access permissions assigned to the <strong>Users</strong> or <strong>Public</strong> folder. Used in <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-isharingconfigurationmanager-createshare"><strong>CreateShare</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-isharingconfigurationmanager-getsharepermissions"><strong>GetSharePermissions</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shtypes/ne-shtypes-tagshcolstate"><strong>SHCOLSTATE</strong></a><br/></td>
<td>Describes how a property should be treated. These values are defined in Shtypes.h.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf"><strong>SHCONTF</strong></a><br/></td>
<td>Determines the types of items included in an enumeration. These values are used with the <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects"><strong>IShellFolder::EnumObjects</strong></a> method.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shlobj_core/ne-shlobj_core-shell_link_data_flags"><strong>SHELL_LINK_DATA_FLAGS</strong></a><br/></td>
<td>Specifies option settings. Used with <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishelllinkdatalist-getflags"><strong>IShellLinkDataList::GetFlags</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishelllinkdatalist-setflags"><strong>IShellLinkDataList::SetFlags</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/ShellScalingApi/ne-shellscalingapi-shell_ui_component"><strong>SHELL_UI_COMPONENT</strong></a><br/></td>
<td>Identifies the type of UI component that is needed in the shell.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shldisp/ne-shldisp-shellfolderviewoptions"><strong>ShellFolderViewOptions</strong></a><br/></td>
<td>Specifies the view options returned by the <a href="shellfolderview-viewoptions"><strong>ViewOptions</strong></a> property.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shldisp/ne-shldisp-shellspecialfolderconstants"><strong>ShellSpecialFolderConstants</strong></a><br/></td>
<td>Specifies unique, system-independent values that identify special folders. These folders are frequently used by applications but which may not have the same name or location on any given system. For example, the system folder can be &quot;C:\Windows&quot; on one system and &quot;C:\Winnt&quot; on another.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/ExDisp/ne-exdisp-shellwindowfindwindowoptions"><strong>ShellWindowFindWindowOptions</strong></a><br/></td>
<td>Specifies options for finding window in the Shell windows collection. <br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Exdisp/ne-exdisp-shellwindowtypeconstants"><strong>ShellWindowTypeConstants</strong></a><br/></td>
<td>Specifies types of Shell windows.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shgdnf"><strong>SHGDNF</strong></a><br/></td>
<td>Defines the values used with the <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-getdisplaynameof"><strong>IShellFolder::GetDisplayNameOf</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-setnameof"><strong>IShellFolder::SetNameOf</strong></a> methods to specify the type of file or folder names used by those methods. <br/>
<blockquote>
[!Note]<br />
Prior to Windows 7, these values were packaged as the SHGNO enumeration.
</blockquote>
<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlwapi/ne-shlwapi-shglobalcounter"><strong>SHGLOBALCOUNTER</strong></a><br/></td>
<td>Identifiers for various global counters, or shared variables. Each global counter can be incremented or decremented using <a href="/windows/desktop/api/Shlwapi/nf-shlwapi-shglobalcounterincrement"><strong>SHGlobalCounterIncrement</strong></a> and <a href="/windows/desktop/api/Shlwapi/nf-shlwapi-shglobalcounterdecrement"><strong>SHGlobalCounterDecrement</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shlwapi/ne-shlwapi-shregdel_flags"><strong>SHREGDEL_FLAGS</strong></a><br/></td>
<td>Provides a set of values that indicate from which base key an item will be deleted.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlwapi/ne-shlwapi-shregenum_flags"><strong>SHREGENUM_FLAGS</strong></a><br/></td>
<td>Provides a set of values that indicate the base key that will be used for an enumeration.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shellapi/ne-shellapi-shstockiconid"><strong>SHSTOCKICONID</strong></a><br/></td>
<td>Used by <a href="/windows/desktop/api/Shellapi/nf-shellapi-shgetstockiconinfo"><strong>SHGetStockIconInfo</strong></a> to identify which stock system icon to retrieve.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_sichintf"><strong>SICHINTF</strong></a><br/></td>
<td>Used to determine how to compare two Shell items. <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellitem-compare"><strong>IShellItem::Compare</strong></a> uses this enumerated type.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_sigdn"><strong>SIGDN</strong></a><br/></td>
<td>Requests the form of an item's display name to retrieve through <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellitem-getdisplayname"><strong>IShellItem::GetDisplayName</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-shgetnamefromidlist"><strong>SHGetNameFromIDList</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_spaction"><strong>SPACTION</strong></a><br/></td>
<td>Describes an action being performed that requires progress to be shown to the user using an <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-iactionprogress"><strong>IActionProgress</strong></a> interface.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_spbeginf"><strong>SPBEGINF</strong></a><br/></td>
<td>Used by <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iactionprogress-begin"><strong>IActionProgress::Begin</strong></a>, these constants specify certain UI operations that are to be enabled or disabled.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_sptext"><strong>SPTEXT</strong></a><br/></td>
<td>Specifies the type of descriptive text being provided to an <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-iactionprogress"><strong>IActionProgress</strong></a> interface.<br/></td>
</tr>
<tr class="even">
<td><a href="srrf"><strong>SRRF</strong></a><br/></td>
<td>Flags that restrict the data to be set or returned.<br/></td>
</tr>
<tr class="odd">
<td><a href="ssf-constants"><strong>SSF Constants</strong></a><br/></td>
<td>Used by the <a href="/windows/desktop/api/shlobj_core/nf-shlobj_core-shgetsetsettings"><strong>SHGetSetSettings</strong></a> function to specify which members of its <a href="https://docs.microsoft.com/windows/desktop/api/shlobj_core/ns-shlobj_core-shellstatea"><strong>SHELLSTATE</strong></a> structure should be set or retrived.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-stpflag"><strong>STPFLAG</strong></a><br/></td>
<td>Used by the <a href="/windows/desktop/api/shobjidl_core/nf-shobjidl_core-itaskbarlist4-settabproperties"><strong>ITaskbarList4::SetTabProperties</strong></a> method to specify tab properties.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-svuia_status"><strong>SVUIA_STATUS</strong></a><br/></td>
<td>Used with the <a href="/windows/desktop/api/Shdeprecated/nf-shdeprecated-ibrowserservice2-_uiactivateview"><strong>IBrowserService2::_UIActivateView</strong></a> method to set the state of a browser view.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_cancel_request"><strong>SYNCMGR_CANCEL_REQUEST</strong></a><br/></td>
<td>Describes a request by the user to cancel a synchronization.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_conflict_item_type"><strong>SYNCMGR_CONFLICT_ITEM_TYPE</strong></a><br/></td>
<td>Describes conflict item type.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_control_flags"><strong>SYNCMGR_CONTROL_FLAGS</strong></a><br/></td>
<td>Specifies how an operation requested on certain methods of <a href="/windows/desktop/api/Syncmgr/nn-syncmgr-isyncmgrcontrol"><strong>ISyncMgrControl</strong></a> should be performed.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_event_flags"><strong>SYNCMGR_EVENT_FLAGS</strong></a><br/></td>
<td>Specifies flags for a synchronization event.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_event_level"><strong>SYNCMGR_EVENT_LEVEL</strong></a><br/></td>
<td>Specifies the type of event being reported to Sync Center.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_handler_capabilities"><strong>SYNCMGR_HANDLER_CAPABILITIES</strong></a><br/></td>
<td>Specifies the capabilities of a handler regarding the actions that can be performed against it.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_handler_policies"><strong>SYNCMGR_HANDLER_POLICIES</strong></a><br/></td>
<td>Enumerates policies specified by a sync handler that deviate from the default policy.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_handler_type"><strong>SYNCMGR_HANDLER_TYPE</strong></a><br/></td>
<td>Specifies the type of a handler. Used by <a href="/windows/desktop/api/Syncmgr/nf-syncmgr-isyncmgrhandlerinfo-gettype"><strong>ISyncMgrHandlerInfo::GetType</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_item_capabilities"><strong>SYNCMGR_ITEM_CAPABILITIES</strong></a><br/></td>
<td>Specifies the actions that can be performed against an item.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_item_policies"><strong>SYNCMGR_ITEM_POLICIES</strong></a><br/></td>
<td>Specifies an item's policies to control how they can be enabled or disabled by group policy.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_presenter_choice"><strong>SYNCMGR_PRESENTER_CHOICE</strong></a><br/></td>
<td>Describes what choice a user makes about a sync manager conflict resolution. Used by <a href="/windows/desktop/api/Syncmgr/nn-syncmgr-isyncmgrconflictpresenter"><strong>ISyncMgrConflictPresenter</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_presenter_next_step"><strong>SYNCMGR_PRESENTER_NEXT_STEP</strong></a><br/></td>
<td>Describes the next step that is to occur in sync manager conflict resolution. Used by <a href="/windows/desktop/api/Syncmgr/nn-syncmgr-isyncmgrconflictpresenter"><strong>ISyncMgrConflictPresenter</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_progress_status"><strong>SYNCMGR_PROGRESS_STATUS</strong></a><br/></td>
<td>Specifies the current progress status of a synchronization process. Used by <a href="/windows/desktop/api/Syncmgr/nf-syncmgr-isyncmgrsynccallback-reportprogress"><strong>ISyncMgrSyncCallback::ReportProgress</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_resolution_abilities"><strong>SYNCMGR_RESOLUTION_ABILITIES</strong></a><br/></td>
<td>Indicates abilities and the conflict resolution activity to follow. Used with <a href="/windows/desktop/api/Syncmgr/nf-syncmgr-isyncmgrresolutionhandler-queryabilities"><strong>ISyncMgrResolutionHandler::QueryAbilities</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_resolution_feedback"><strong>SYNCMGR_RESOLUTION_FEEDBACK</strong></a><br/></td>
<td>Describes Sync Manager resolution feedback. Used by <a href="/windows/desktop/api/Syncmgr/nn-syncmgr-isyncmgrresolutionhandler"><strong>ISyncMgrResolutionHandler</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Syncmgr/ne-syncmgr-syncmgr_sync_control_flags"><strong>SYNCMGR_SYNC_CONTROL_FLAGS</strong></a><br/></td>
<td>Indicates flags used by <a href="/windows/desktop/api/Syncmgr/nf-syncmgr-isyncmgrcontrol-starthandlersync"><strong>ISyncMgrControl::StartHandlerSync</strong></a> and <a href="/windows/desktop/api/Syncmgr/nf-syncmgr-isyncmgrcontrol-startitemsync"><strong>ISyncMgrControl::StartItemSync</strong></a>.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgrflag"><strong>SYNCMGRFLAG</strong></a><br/></td>
<td>The <a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgrflag"><strong>SYNCMGRFLAG</strong></a> enumeration values are used in the <a href="/windows/desktop/api/Mobsync/nf-mobsync-isyncmgrsynchronize-initialize"><strong>ISyncMgrSynchronize::Initialize</strong></a> method to indicate how the synchronization event was initiated.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgrhandlerflags"><strong>SYNCMGRHANDLERFLAGS</strong></a><br/></td>
<td>Used in the <a href="/windows/desktop/api/Mobsync/ns-mobsync-_tagsyncmgrhandlerinfo"><strong>SYNCMGRHANDLERINFO</strong></a> structure as flags that apply to the current handler.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgrinvokeflags"><strong>SYNCMGRINVOKEFLAGS</strong></a><br/></td>
<td>The <a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgrinvokeflags"><strong>SYNCMGRINVOKEFLAGS</strong></a> enumeration value specifies how the Sync Manager is to be invoked in the <a href="/windows/desktop/api/Mobsync/nf-mobsync-isyncmgrsynchronizeinvoke-updateitems"><strong>ISyncMgrSynchronizeInvoke::UpdateItems</strong></a> method.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgritemflags"><strong>SYNCMGRITEMFLAGS</strong></a><br/></td>
<td>Specifies information for the current item in the <a href="/windows/desktop/api/Mobsync/ns-mobsync-_tagsyncmgritem"><strong>SYNCMGRITEM</strong></a> structure.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgrloglevel"><strong>SYNCMGRLOGLEVEL</strong></a><br/></td>
<td>The <a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgrloglevel"><strong>SYNCMGRLOGLEVEL</strong></a> enumeration values specify an error level for use in the <a href="/windows/desktop/api/Mobsync/nf-mobsync-isyncmgrsynchronizecallback-logerror"><strong>ISyncMgrSynchronizeCallback::LogError</strong></a> method.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgrregisterflags"><strong>SYNCMGRREGISTERFLAGS</strong></a><br/></td>
<td>The <a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgrregisterflags"><strong>SYNCMGRREGISTERFLAGS</strong></a> enumeration values are used in methods of the <a href="/windows/desktop/api/Mobsync/nn-mobsync-isyncmgrregister"><strong>ISyncMgrRegister</strong></a> interface to identify events for which the handler is registered to be notified.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Mobsync/ne-mobsync-_tagsyncmgrstatus"><strong>SYNCMGRSTATUS</strong></a><br/></td>
<td>Used in the <a href="/windows/desktop/api/Mobsync/nf-mobsync-isyncmgrsynchronize-setitemstatus"><strong>ISyncMgrSynchronize::SetItemStatus</strong></a> method to specify the updated status for the item.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-thumbbuttonflags"><strong>THUMBBUTTONFLAGS</strong></a><br/></td>
<td>Used by <a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-thumbbutton"><strong>THUMBBUTTON</strong></a> to control specific states and behaviors of the button.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-thumbbuttonmask"><strong>THUMBBUTTONMASK</strong></a><br/></td>
<td>Used by the <a href="/windows/desktop/api/Shobjidl_core/ns-shobjidl_core-thumbbutton"><strong>THUMBBUTTON</strong></a> structure to specify which members of that structure contain valid data.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/thumbnailstreamcache/ne-thumbnailstreamcache-thumbnailstreamcacheoptions"><strong>ThumbnailStreamCacheOptions</strong></a><br/></td>
<td>Defines the cache options used by the <a href="/windows/desktop/api/thumbnailstreamcache/nn-thumbnailstreamcache-ithumbnailstreamcache"><strong>IThumbnailStreamCache</strong></a> interface.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_transfer_source_flags"><strong>TRANSFER_SOURCE_FLAGS</strong></a><br/></td>
<td>Used by methods of the <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-itransfersource"><strong>ITransferSource</strong></a> and <a href="/windows/desktop/api/shobjidl_core/nn-shobjidl_core-itransferdestination"><strong>ITransferDestination</strong></a> interfaces to control their file operations.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Intshcut/ne-intshcut-translateurl_in_flags"><strong>TRANSLATEURL_IN_FLAGS</strong></a><br/></td>
<td>The <a href="/windows/desktop/api/Intshcut/ne-intshcut-translateurl_in_flags"><strong>TRANSLATEURL_IN_FLAGS</strong></a> enumerated values are used with the <a href="/windows/desktop/api/Intshcut/nf-intshcut-translateurla"><strong>TranslateURL</strong></a> function to determine how it will execute.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl/ne-shobjidl-undock_reason"><strong>UNDOCK_REASON</strong></a><br/></td>
<td>Values that indicate the reason that a docked accessibility app window has been undocked. Used by <a href="https://docs.microsoft.com/windows/desktop/api/shobjidl/nf-shobjidl-iaccessibilitydockingservicecallback-undocked"><strong>IAccessibilityDockingServiceCallback::Undocked</strong></a>.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shlwapi/ne-shlwapi-url_scheme"><strong>URL_SCHEME</strong></a><br/></td>
<td>Used to specify URL schemes.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Intshcut/ne-intshcut-urlassociationdialog_in_flags"><strong>URLASSOCIATIONDIALOG_IN_FLAGS</strong></a><br/></td>
<td>The <a href="/windows/desktop/api/Intshcut/ne-intshcut-urlassociationdialog_in_flags"><strong>URLASSOCIATIONDIALOG_IN_FLAGS</strong></a> enumerated values are used with <a href="/windows/desktop/api/Intshcut/nf-intshcut-urlassociationdialoga"><strong>URLAssociationDialog</strong></a> to determine how it executes.<br/></td>
</tr>
<tr class="odd">
<td><a href="/windows/desktop/api/Shobjidl/ne-shobjidl-vpcolorflags"><strong>VPCOLORFLAGS</strong></a><br/></td>
<td>Specifies the use of a color. Used by <a href="/windows/desktop/api/Shobjidl/nn-shobjidl-ivisualproperties"><strong>IVisualProperties</strong></a> methods.<br/></td>
</tr>
<tr class="even">
<td><a href="/windows/desktop/api/Shobjidl/ne-shobjidl-vpwatermarkflags"><strong>VPWATERMARKFLAGS</strong></a><br/></td>
<td>Specifies watermark flags. Used by <a href="/windows/desktop/api/Shobjidl/nf-shobjidl-ivisualproperties-setwatermark"><strong>IVisualProperties::SetWatermark</strong></a>.<br/></td>
</tr>
</tbody>
</table>



 

 

 




