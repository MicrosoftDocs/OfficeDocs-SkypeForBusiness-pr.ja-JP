---
title: 会議ポリシーを削除するSkype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '概要: 会議ポリシーを削除する方法については、Skype for Business Server。'
ms.openlocfilehash: 62fce625133565e7e2ec53b0a5a4e37408f7e49e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595559"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>会議ポリシーを削除するSkype for Business Server
 
**概要:** 会議ポリシーを削除する方法については、Skype for Business Server。
  
会議ポリシーは、コントロール パネルまたは管理シェルSkype for Business Server使用して削除Skype for Business Serverできます。
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用して会議Skype for Business Server削除する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. 会議ポリシーの一覧で、削除するサイトまたはユーザー ポリシーをクリックし、[編集] をクリックし、[削除] を **クリックします**。
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して会議ポリシー Skype for Business Server削除する

会議ポリシーを削除するには **、Remove-CsConferencingPolicy コマンドレットを使用** します。
  
次のコマンドは、ID RedmondConferencingPolicy を持つ電話会議ポリシーを削除します。
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

次のコマンドは、外部ユーザーが会議を記録できる会議ポリシーを削除します。
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

完全な構文とパラメーターの一覧を含む詳細については [、「Remove-CsConferencingPolicy」を参照してください](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。
