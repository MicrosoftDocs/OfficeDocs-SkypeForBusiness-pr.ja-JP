---
title: '[会議の構成設定を削除する] Skype for Business Server'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '概要: 会議の構成設定を削除する方法については、Skype for Business Server。'
ms.openlocfilehash: f08869e2cb9c59dc6fb382de6568ad913c329c1a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391129"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>[会議の構成設定を削除する] Skype for Business Server
 
**概要:** 会議の構成設定を削除する方法については、Skype for Business Server。
  
会議の構成設定は、コントロール パネルを使用するかSkype for Business Server管理シェルを使用してSkype for Business Server削除できます。
  
サイトまたはユーザー構成を削除できますが、グローバル構成を削除することはできません。 グローバル構成を削除しようとすると、自動的に既定値にリセットされます。
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用して会議Skype for Business Server設定を削除する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。
    
4. 会議の構成の一覧で、削除するサイトまたはプールの構成をクリックし、[編集] をクリックして、[削除] をクリック **します**。
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して会議の構成設定Skype for Business Server削除する

会議の設定を削除するには、 **Remove-CsMeetingConfiguration コマンドレットを使用** します。
  
次のコマンドは、Redmond サイトに適用される会議構成設定を削除します。
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

次のコマンドは、サイト スコープに適用されている会議構成設定をすべて削除します。
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

パラメーターの完全な一覧を含む詳細については、「 [Remove-CsMeetingConfiguration」を参照してください](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。
