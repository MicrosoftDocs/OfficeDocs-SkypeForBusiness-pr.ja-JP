---
title: Skype for Business Server でアーカイブ構成を削除する
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: '概要: Skype for Business Server でアーカイブ構成を削除する方法について説明します。'
ms.openlocfilehash: a9d24a17ec769f5686502beb325e021c8b0f39c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817627"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Skype for Business Server でアーカイブ構成を削除する

**概要:** Skype for Business Server でアーカイブ構成を削除する方法について説明します。
  
サイト構成またはプール構成は削除できますが、グローバル構成を削除することはできません。 グローバル構成を削除すると、自動的に既定値にリセットされます。
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ構成を削除する

コントロール パネルを使用してアーカイブ構成を削除するには:
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成のリストで、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
    > [!NOTE]
    > グローバル構成をクリックすることもできますが、グローバル構成を既定値にリセットする場合にのみ、このオプションを選択します。 
  
5. [**確定**] をクリックします。
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>アーカイブ構成を使用して削除Windows PowerShell

**Remove-CsArchivingConfiguration** コマンドレットを使用してアーカイブ構成を削除することもできます。
  
たとえば、次のコマンドを実行すると、Redmond サイトに適用されているアーカイブ構成設定が削除されます。 サイト スコープで構成されたポリシーを削除すると、以前にサイト ポリシーによって管理されたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

次のコマンドは、サービス スコープに適用されているアーカイブ構成設定を削除します。
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

次のコマンドは、Exchange アーカイブが無効になっているすべてのアーカイブ構成設定を削除します。
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

**Remove-CsArchivingConfiguration** コマンドレットを使用して、グローバル設定を既定値にリセットすることもできます。 たとえば、IM セッションのアーカイブをグローバル レベルで有効にしたとします。次のコマンドを実行すると、値が既定値の None にリセットされ、グローバル レベルでのアーカイブが無効になります。
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

詳細については [、Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
