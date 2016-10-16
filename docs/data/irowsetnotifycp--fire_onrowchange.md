---
title: "IRowsetNotifyCP::Fire_OnRowChange"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IRowsetNotifyCP.Fire_OnRowChange"
  - "ATL.IRowsetNotifyCP.Fire_OnRowChange"
  - "Fire_OnRowChange"
  - "ATL::IRowsetNotifyCP::Fire_OnRowChange"
  - "IRowsetNotifyCP::Fire_OnRowChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fire_OnRowChange method"
ms.assetid: 6f9beed6-7a69-4c92-936f-422e98f3de5c
caps.latest.revision: 8
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
# IRowsetNotifyCP::Fire_OnRowChange
Broadcasts an [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) event to all listeners on the connection point **IID_IRowsetNotify** to notify consumers of a change affecting the rows.  
  
## Syntax  
  
```  
  
      HRESULT Fire_OnRowChange(  
   IRowset* pRowset,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny   
);  
```  
  
#### Parameters  
 See [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) in the *OLE DB Programmer's Reference*.  
  
## Requirements  
 **Header:** atldb.h  
  
## See Also  
 [IRowsetNotifyCP Class](../data/irowsetnotifycp-class.md)