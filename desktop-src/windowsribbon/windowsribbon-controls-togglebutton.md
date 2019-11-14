---
title: Toggle Button
description: The Toggle Button when clicked provides input to an application. The control represents a mutually exclusive toggle state.
ms.assetid: 290052b7-0528-41c5-b6f4-958cc42d502b
ms.topic: article
ms.date: 05/31/2018
---

# Toggle Button

The Toggle Button when clicked provides input to an application. The control represents a mutually exclusive toggle state.

-   [Details](#details)
-   [Toggle Button Properties](#toggle-button-properties)
-   [Related topics](#related-topics)

## Details

The following screen shot illustrates the Ribbon Toggle Button.

![screen shot of a togglebutton control in the microsoft paint ribbon.](images/controls/togglebutton.png)

## Toggle Button Properties

The Ribbon framework defines a collection of [property keys](windowsribbon-reference-properties.md) for the Toggle Button control.

Typically, a Toggle Button property is updated in the ribbon UI by invalidating the Command associated with the control through a call to the [**IUIFramework::InvalidateUICommand**](https://docs.microsoft.com/windows/desktop/api/uiribbon/nf-uiribbon-iuiframework-invalidateuicommand) method. The invalidation event is handled, and the property updates defined, by the [**IUICommandHandler::UpdateProperty**](https://docs.microsoft.com/windows/desktop/api/uiribbon/nf-uiribbon-iuicommandhandler-updateproperty) callback method.

The [**IUICommandHandler::UpdateProperty**](https://docs.microsoft.com/windows/desktop/api/uiribbon/nf-uiribbon-iuicommandhandler-updateproperty) callback method is not executed, and the application queried for an updated property value, until the property is required by the framework. For example, when a tab is activated and a control revealed in the ribbon UI, or when a tooltip is displayed.

> [!Note]  
> In some cases, a property can be retrieved through the [**IUIFramework::GetUICommandProperty**](https://docs.microsoft.com/windows/desktop/api/uiribbon/nf-uiribbon-iuiframework-getuicommandproperty) method and set with the [**IUIFramework::SetUICommandProperty**](https://docs.microsoft.com/windows/desktop/api/uiribbon/nf-uiribbon-iuiframework-setuicommandproperty) method.

 

The following table lists the property keys that are associated with the Toggle Button control.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Property Key</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="windowsribbon-reference-properties-uipkey-booleanvalue">UI_PKEY_BooleanValue</a></td>
<td>Supports <a href="https://docs.microsoft.com/windows/desktop/api/uiribbon/nf-uiribbon-iuiframework-getuicommandproperty"><strong>IUIFramework::GetUICommandProperty</strong></a> and <a href="https://docs.microsoft.com/windows/desktop/api/uiribbon/nf-uiribbon-iuiframework-setuicommandproperty"><strong>IUIFramework::SetUICommandProperty</strong></a>.
<blockquote>
[!Note]<br />
If the Command associated with the control is invalidated through a call to <a href="https://docs.microsoft.com/windows/desktop/api/uiribbon/nf-uiribbon-iuiframework-invalidateuicommand"><strong>IUIFramework::InvalidateUICommand</strong></a>, the framework queries this property when <code>UI_INVALIDATIONS_VALUE</code> is passed as the value of <em>flags</em>.
</blockquote>
<br/></td>
</tr>
<tr class="even">
<td><a href="windowsribbon-reference-properties-uipkey-enabled">UI_PKEY_Enabled</a></td>
<td>Supports <a href="https://docs.microsoft.com/windows/desktop/api/uiribbon/nf-uiribbon-iuiframework-getuicommandproperty"><strong>IUIFramework::GetUICommandProperty</strong></a> and <a href="https://docs.microsoft.com/windows/desktop/api/uiribbon/nf-uiribbon-iuiframework-setuicommandproperty"><strong>IUIFramework::SetUICommandProperty</strong></a>.</td>
</tr>
<tr class="odd">
<td><a href="windowsribbon-reference-properties-uipkey-keytip">UI_PKEY_Keytip</a></td>
<td>Can only be updated through invalidation.</td>
</tr>
<tr class="even">
<td><a href="windowsribbon-reference-properties-uipkey-label">UI_PKEY_Label</a></td>
<td>Can only be updated through invalidation.</td>
</tr>
<tr class="odd">
<td><a href="windowsribbon-reference-properties-uipkey-labeldescription">UI_PKEY_LabelDescription</a></td>
<td>Can only be updated through invalidation.</td>
</tr>
<tr class="even">
<td><a href="windowsribbon-reference-properties-uipkey-largehighcontrastimage">UI_PKEY_LargeHighContrastImage</a></td>
<td>Can only be updated through invalidation.</td>
</tr>
<tr class="odd">
<td><a href="windowsribbon-reference-properties-uipkey-largeimage">UI_PKEY_LargeImage</a></td>
<td>Can only be updated through invalidation.</td>
</tr>
<tr class="even">
<td><a href="windowsribbon-reference-properties-uipkey-smallhighcontrastimage">UI_PKEY_SmallHighContrastImage</a></td>
<td>Can only be updated through invalidation.</td>
</tr>
<tr class="odd">
<td><a href="windowsribbon-reference-properties-uipkey-smallimage">UI_PKEY_SmallImage</a></td>
<td>Can only be updated through invalidation.</td>
</tr>
<tr class="even">
<td><a href="windowsribbon-reference-properties-uipkey-tooltipdescription">UI_PKEY_TooltipDescription</a></td>
<td>Can only be updated through invalidation.</td>
</tr>
<tr class="odd">
<td><a href="windowsribbon-reference-properties-uipkey-tooltiptitle">UI_PKEY_TooltipTitle</a></td>
<td>Can only be updated through invalidation.</td>
</tr>
</tbody>
</table>



 

## Related topics

<dl> <dt>

[Windows Ribbon Framework Control Library](windowsribbon-controls-entry.md)
</dt> <dt>

[**ToggleButton markup element**](windowsribbon-element-togglebutton.md)
</dt> </dl>

 

 





