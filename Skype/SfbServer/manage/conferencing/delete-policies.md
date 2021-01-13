---
title: Skype for Business Server での会議ポリシーの削除
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '概要: Skype for Business Server で会議ポリシーを削除する方法について説明します。'
ms.openlocfilehash: eedb0b3676f0cc046e6096dca2cb1ec5ced5d6ec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828197"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server で会議ポリシーを削除する
 
**概要:** Skype for Business Server で会議ポリシーを削除する方法について説明します。
  
会議ポリシーは、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して削除できます。
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して会議ポリシーを削除する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. 電話会議ポリシーの一覧で、削除するサイトポリシーまたはユーザー ポリシーをクリックし、[編集]をクリックして、[削除] をクリック **します**。
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議ポリシーを削除する

会議ポリシーを削除するには **、Remove-CsConferencingPolicy コマンドレットを使用** します。
  
次のコマンドは、ID RedmondConferencingPolicy を持つ電話会議ポリシーを削除します。
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

次のコマンドは、外部ユーザーが会議を記録できる会議ポリシーを削除します。
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

完全な構文やパラメーターの一覧など、詳細については [、「Remove-CsConferencingPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。
  

