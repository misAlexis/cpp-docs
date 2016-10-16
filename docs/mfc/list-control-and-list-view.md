---
title: "List Control and List View"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListView class, and CListCtrl"
  - "views, list and list control"
  - "CListCtrl class, and CListView"
  - "list views"
  - "list controls, List view"
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: 9
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# List Control and List View
For convenience, MFC encapsulates the list control in two ways. You can use list controls:  
  
-   Directly, by embedding a [CListCtrl](../mfcref/clistctrl-class.md) object in a dialog class.  
  
-   Indirectly, by using class [CListView](../mfcref/clistview-class.md).  
  
 `CListView` makes it easy to integrate a list control with the MFC document/view architecture, encapsulating the control much as [CEditView](../mfcref/ceditview-class.md) encapsulates an edit control: the control fills the entire surface area of an MFC view. (The view *is* the control, cast to `CListView`.)  
  
 A `CListView` object inherits from [CCtrlView](../mfcref/cctrlview-class.md) and its base classes and adds a member function to retrieve the underlying list control. Use view members to work with the view as a view. Use the [GetListCtrl](../Topic/CListView::GetListCtrl.md) member function to gain access to the list control's member functions. Use these members to:  
  
-   Add, delete, or manipulate "items" in the list.  
  
-   Set or get list control attributes.  
  
 To obtain a reference to the `CListCtrl` underlying a `CListView`, call `GetListCtrl` from your list view class:  
  
 [!code[NVC_MFCListView#4](../atl/codesnippet/CPP/list-control-and-list-view_1.cpp)]  
  
 This topic describes both ways to use the list control.  
  
## See Also  
 [Using CListCtrl](../mfc/using-clistctrl.md)   
 [Controls](../mfc/controls--mfc-.md)