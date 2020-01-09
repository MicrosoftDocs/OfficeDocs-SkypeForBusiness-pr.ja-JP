---
title: Skype for Business Server で会議の構成設定を削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '概要: Skype for Business Server で会議の構成設定を削除する方法について説明します。'
ms.openlocfilehash: cbf63ba635077dd61599d4bc84a740906b662a6c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991862"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で会議の構成設定を削除する
 
**概要:** Skype for Business Server の会議の構成設定を削除する方法について説明します。
  
会議の設定を削除するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
サイト構成やユーザー構成は削除できますが、グローバル構成は削除できません。グローバル構成を削除しようとすると、グローバル構成は自動的に既定値にリセットされます。
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して会議の設定を削除する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。
    
4. 会議構成の一覧で、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議の構成設定を削除する

会議の構成設定を削除するには、**Remove-CsMeetingConfiguration** コマンドレットを使用します。
  
次のコマンドを実行すると、Redmond サイトに適用されていた会議の構成設定が削除されます。
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

次のコマンドは、サイト スコープに適用された会議構成設定をすべて削除します。
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

パラメーターの完全な一覧など、詳細については、「 [Cs会議の構成](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)」を参照してください。
  

