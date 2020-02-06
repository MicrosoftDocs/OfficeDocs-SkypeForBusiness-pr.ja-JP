---
title: Skype for Business Server の会議ポリシーを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '概要: Skype for Business Server の会議ポリシーを削除する方法について説明します。'
ms.openlocfilehash: 3fe5b8c2bb12f48cb6e904df2fe43c6c8a01e3f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818598"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server の会議ポリシーを削除する
 
**概要:** Skype for Business Server の会議ポリシーを削除する方法について説明します。
  
会議ポリシーを削除するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して会議ポリシーを削除する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。
    
4. 電話会議ポリシーのリストで、削除するサイト ポリシーまたはユーザー ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議ポリシーを削除する

電話会議ポリシーを削除するには、**Remove-CsConferencingPolicy** コマンドレットを使用します。
  
次のコマンドは、Identity が RedmondConferencingPolicy の電話会議ポリシーを削除します。
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

次のコマンドは、外部ユーザーに電話会議の記録を許可するすべての電話会議ポリシーを削除します。
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

完全な構文とパラメーターの一覧を含む詳細については、「 [Remove-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)」を参照してください。
  

