---
title: Skype for Business Server で会議の構成設定を削除する
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '概要: Skype for Business Server で会議の構成設定を削除する方法について説明します。'
ms.openlocfilehash: 418ce7418be5a09658626491121dd2e2b3542110
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828184"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で会議の構成設定を削除する
 
**概要:** Skype for Business Server で会議の構成設定を削除する方法について説明します。
  
会議の構成設定は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して削除できます。
  
サイトまたはユーザーの構成は削除できますが、グローバル構成を削除することはできません。 グローバル構成を削除しようとすると、自動的に既定値にリセットされます。
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して会議の構成設定を削除する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。
    
4. 会議の構成の一覧で、削除するサイトまたはプールの構成をクリックし、[編集]をクリックして、[削除] をクリック **します**。
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議の構成設定を削除する

会議の設定を削除するには **、Remove-CsMeetingConfiguration コマンドレットを使用** します。
  
次のコマンドは、Redmond サイトに適用されている会議の構成設定を削除します。
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

次のコマンドは、サイト スコープに適用されている会議の構成設定をすべて削除します。
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

パラメーターの完全な一覧を含む詳細については [、「Remove-CsMeetingConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。
  

