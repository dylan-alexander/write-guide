---
title: Tree-View Control Window Styles (CommCtrl.h)
description: This section lists window styles used when creating tree-view controls.
ms.assetid: d0a1ad6d-1bda-4b65-b97a-b389d6e6d7a6
topic_type:
- apiref
api_name:
- TVS_CHECKBOXES
- TVS_DISABLEDRAGDROP
- TVS_EDITLABELS
- TVS_FULLROWSELECT
- TVS_HASBUTTONS
- TVS_HASLINES
- TVS_INFOTIP
- TVS_LINESATROOT
- TVS_NOHSCROLL
- TVS_NONEVENHEIGHT
- TVS_NOSCROLL
- TVS_NOTOOLTIPS
- TVS_RTLREADING
- TVS_SHOWSELALWAYS
- TVS_SINGLEEXPAND
- TVS_TRACKSELECT
api_location:
- CommCtrl.h
api_type:
- HeaderDef
ms.topic: reference
ms.date: 05/31/2018
---

# Tree-View Control Window Styles

This section lists window styles used when creating tree-view controls.



| Constant                                                                                                                                                                        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="TVS_CHECKBOXES"></span><span id="tvs_checkboxes"></span><dl> <dt>**TVS\_CHECKBOXES**</dt> </dl>                | [Version 4.70](common-control-versions.md). Enables check boxes for items in a tree-view control. A check box is displayed only if an image is associated with the item. When set to this style, the control effectively uses [**DrawFrameControl**](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-drawframecontrol) to create and set a state image list containing two images. State image 1 is the unchecked box and state image 2 is the checked box. Setting the state image to zero removes the check box altogether. For more information, see [Working with state image indexes](tree-view-controls.md).<br/> [Version 5.80](common-control-versions.md). Displays a check box even if no image is associated with the item.<br/> Once a tree-view control is created with this style, the style cannot be removed. Instead, you must destroy the control and create a new one in its place. Destroying the tree-view control does not destroy the check box state image list. You must destroy it explicitly. Get the handle to the state image list by sending the tree-view control a [**TVM\_GETIMAGELIST**](tvm-getimagelist.md) message. Then destroy the image list with [**ImageList\_Destroy**](/windows/desktop/api/Commctrl/nf-commctrl-imagelist_destroy).<br/> If you want to use this style, you must set the TVS\_CHECKBOXES style with [**SetWindowLong**](https://docs.microsoft.com/windows/desktop/api/winuser/nf-winuser-setwindowlonga) after you create the treeview control, and before you populate the tree. Otherwise, the checkboxes might appear unchecked, depending on timing issues.<br/> |
| <span id="TVS_DISABLEDRAGDROP"></span><span id="tvs_disabledragdrop"></span><dl> <dt>**TVS\_DISABLEDRAGDROP**</dt> </dl> | Prevents the tree-view control from sending [TVN\_BEGINDRAG](tvn-begindrag.md) notification codes. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| <span id="TVS_EDITLABELS"></span><span id="tvs_editlabels"></span><dl> <dt>**TVS\_EDITLABELS**</dt> </dl>                | Allows the user to edit the labels of tree-view items. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| <span id="TVS_FULLROWSELECT"></span><span id="tvs_fullrowselect"></span><dl> <dt>**TVS\_FULLROWSELECT**</dt> </dl>       | [Version 4.71](common-control-versions.md). Enables full-row selection in the tree view. The entire row of the selected item is highlighted, and clicking anywhere on an item's row causes it to be selected. This style cannot be used in conjunction with the **TVS\_HASLINES** style. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| <span id="TVS_HASBUTTONS"></span><span id="tvs_hasbuttons"></span><dl> <dt>**TVS\_HASBUTTONS**</dt> </dl>                | Displays plus (+) and minus (-) buttons next to parent items. The user clicks the buttons to expand or collapse a parent item's list of child items. To include buttons with items at the root of the tree view, TVS\_LINESATROOT must also be specified. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| <span id="TVS_HASLINES"></span><span id="tvs_haslines"></span><dl> <dt>**TVS\_HASLINES**</dt> </dl>                      | Uses lines to show the hierarchy of items. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <span id="TVS_INFOTIP"></span><span id="tvs_infotip"></span><dl> <dt>**TVS\_INFOTIP**</dt> </dl>                         | [Version 4.71](common-control-versions.md). Obtains tooltip information by sending the [TVN\_GETINFOTIP](tvn-getinfotip.md) notification. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| <span id="TVS_LINESATROOT"></span><span id="tvs_linesatroot"></span><dl> <dt>**TVS\_LINESATROOT**</dt> </dl>             | Uses lines to link items at the root of the tree-view control. This value is ignored if TVS\_HASLINES is not also specified. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| <span id="TVS_NOHSCROLL"></span><span id="tvs_nohscroll"></span><dl> <dt>**TVS\_NOHSCROLL**</dt> </dl>                   | [Version 5.80](common-control-versions.md). Disables horizontal scrolling in the control. The control will not display any horizontal scroll bars. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| <span id="TVS_NONEVENHEIGHT"></span><span id="tvs_nonevenheight"></span><dl> <dt>**TVS\_NONEVENHEIGHT**</dt> </dl>       | [Version 4.71](common-control-versions.md) Sets the height of the items to an odd height with the [**TVM\_SETITEMHEIGHT**](tvm-setitemheight.md) message. By default, the height of items must be an even value. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| <span id="TVS_NOSCROLL"></span><span id="tvs_noscroll"></span><dl> <dt>**TVS\_NOSCROLL**</dt> </dl>                      | [Version 4.71](common-control-versions.md). Disables both horizontal and vertical scrolling in the control. The control will not display any scroll bars. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <span id="TVS_NOTOOLTIPS"></span><span id="tvs_notooltips"></span><dl> <dt>**TVS\_NOTOOLTIPS**</dt> </dl>                | [Version 4.70](common-control-versions.md). Disables tooltips. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <span id="TVS_RTLREADING"></span><span id="tvs_rtlreading"></span><dl> <dt>**TVS\_RTLREADING**</dt> </dl>                | [Version 4.70](common-control-versions.md). Causes text to be displayed from right-to-left (RTL). Usually, windows display text left-to-right (LTR). Windows can be *mirrored* to display languages such as Hebrew or Arabic that read RTL. Typically, tree-view text is displayed in the same direction as the text in its parent window. If TVS\_RTLREADING is set, tree-view text reads in the opposite direction from the text in the parent window. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| <span id="TVS_SHOWSELALWAYS"></span><span id="tvs_showselalways"></span><dl> <dt>**TVS\_SHOWSELALWAYS**</dt> </dl>       | Causes a selected item to remain selected when the tree-view control loses focus. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| <span id="TVS_SINGLEEXPAND"></span><span id="tvs_singleexpand"></span><dl> <dt>**TVS\_SINGLEEXPAND**</dt> </dl>          | [Version 4.71](common-control-versions.md). Causes the item being selected to expand and the item being unselected to collapse upon selection in the tree view. If the mouse is used to single-click the selected item and that item is closed, it will be expanded. If the user holds down the CTRL key while selecting an item, the item being unselected will not be collapsed. <br/> [Version 5.80](common-control-versions.md). Causes the item being selected to expand and the item being unselected to collapse upon selection in the tree view. If the user holds down the CTRL key while selecting an item, the item being unselected will not be collapsed.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| <span id="TVS_TRACKSELECT"></span><span id="tvs_trackselect"></span><dl> <dt>**TVS\_TRACKSELECT**</dt> </dl>             | [Version 4.70](common-control-versions.md). Enables hot tracking in a tree-view control. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |



## Requirements



|                   |                                                                                       |
|-------------------|---------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>CommCtrl.h</dt> </dl> |



 

 




