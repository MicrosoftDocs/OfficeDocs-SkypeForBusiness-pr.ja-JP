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
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119506"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server での会議ポリシーの削除
 
**概要:** Skype for Business Server で会議ポリシーを削除する方法について説明します。
  
会議ポリシーは、Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して削除できます。
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して会議ポリシーを削除する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. 会議ポリシーの一覧で、削除するサイトまたはユーザー ポリシーをクリックし、[編集] をクリックし、[削除] を **クリックします**。
    
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

完全な構文とパラメーターの一覧を含む詳細については [、「Remove-CsConferencingPolicy」を参照してください](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。
