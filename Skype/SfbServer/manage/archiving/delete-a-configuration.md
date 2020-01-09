---
title: Skype for Business Server でアーカイブ構成を削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: '概要: Skype for Business Server でアーカイブ構成を削除する方法について説明します。'
ms.openlocfilehash: 22da9464a4bb6b17c6d4b9aa63ad8990a9152c38
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992374"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Skype for Business Server でアーカイブ構成を削除する

**概要:** Skype for Business Server でアーカイブ構成を削除する方法について説明します。
  
サイト構成やプール構成は削除できますが、グローバル構成は削除できません。グローバル構成を削除すると、グローバル構成は自動的に既定値にリセットされます。
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ構成を削除する

コントロール パネルを使用してアーカイブ構成を削除するには、次の手順を実行します
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成のリストで、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
    > [!NOTE]
    > グローバル構成をクリックすることもできますが、グローバル構成を既定値にリセットする場合にのみこのオプションを選択します。 
  
5. [**確定**] をクリックします。
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Windows PowerShell を使用してアーカイブ構成を削除する

**CsArchivingConfiguration**コマンドレットを使用して、アーカイブ構成を削除することもできます。
  
たとえば、以下のコマンドを実行すると、Redmond サイトに適用されているアーカイブ構成設定が削除されます。サイト スコープで構成されているポリシーを削除すると、以前にサイト ポリシーによって管理されていたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

次のコマンドを実行すると、サービス スコープに適用されているすべてのアーカイブ構成設定が削除されます。
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

次のコマンドを実行すると、Exchange のアーカイブが無効になっているすべてのアーカイブ構成設定が削除されます。
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

また、**Remove-CsArchivingConfiguration** コマンドレットを使用してグローバル設定を既定値にリセットすることもできます。 たとえば、グローバル レベルで IM セッションのアーカイブを有効にしている場合、次のコマンドを実行すると、値が既定値の "None" にリセットされ、グローバル レベルでのアーカイブが無効になります。
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

詳細については、 [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)コマンドレットのヘルプトピックを参照してください。
