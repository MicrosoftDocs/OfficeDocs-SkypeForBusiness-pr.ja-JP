---
title: 削除 Skype ビジネス サーバーの構成設定を満たす
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '概要: を削除する方法を学習する Skype ビジネス サーバーの構成設定に対応します。'
ms.openlocfilehash: 47cde99751c90b71a52b70a0bde9aaf15acf0154
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222759"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>削除 Skype ビジネス サーバーの構成設定を満たす
 
**の概要:** 削除する方法を学習 Skype ビジネス サーバーの構成設定に対応します。
  
削除することができます Skype ビジネス サーバーのコントロール パネルを使用するか、Skype ビジネス サーバー管理シェルを使用して会議の構成設定。
  
サイト構成やユーザー構成は削除できますが、グローバル構成は削除できません。グローバル構成を削除しようとすると、グローバル構成は自動的に既定値にリセットされます。
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>削除ビジネス サーバーのコントロール パネルの Skype を使用して、会議の構成設定

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。
    
4. 会議構成の一覧で、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>削除ビジネス サーバー管理シェルの Skype を使用して、会議の構成設定

会議の構成設定を削除するには、**Remove-CsMeetingConfiguration** コマンドレットを使用します。
  
次のコマンドを実行すると、Redmond サイトに適用されていた会議の構成設定が削除されます。
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

次のコマンドは、サイト スコープに適用された会議構成設定をすべて削除します。
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

パラメーターの完全な一覧を含む詳細については、[削除 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)を参照してください。
  

