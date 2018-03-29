---
title: Skype for Business Server 2015 での会議の構成設定の削除
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '概要: を削除する方法を説明する会議出席ビジネス サーバー 2015 の Skype の設定を構成します。'
ms.openlocfilehash: dec2e51dfe6ae0b9983515d849bc9fc416e9bcc4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での会議の構成設定の削除
 
**の概要:**削除する方法について説明会議出席ビジネス サーバー 2015 の Skype の設定を構成します。
  
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
  

