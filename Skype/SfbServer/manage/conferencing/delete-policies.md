---
title: Skype for Business Server 2015 での電話会議ポリシーの削除
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Summary: Learn how to delete conferencing policies in Skype for Business Server 2015.'
ms.openlocfilehash: 783e2ef4c1bc0732fd93949427cea21c5ca165ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="delete-conferencing-policies-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での電話会議ポリシーの削除
 
**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.
  
You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Delete conferencing policies by using Skype for Business Server Control Panel

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Open Skype for Business Server Control Panel.
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。
    
4. 電話会議ポリシーのリストで、削除するサイト ポリシーまたはユーザー ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Delete conferencing policies by using Skype for Business Server Management Shell

電話会議ポリシーを削除するには、**Remove-CsConferencingPolicy** コマンドレットを使用します。
  
次のコマンドは、Identity が RedmondConferencingPolicy の電話会議ポリシーを削除します。
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

次のコマンドは、外部ユーザーに電話会議の記録を許可するすべての電話会議ポリシーを削除します。
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
  

