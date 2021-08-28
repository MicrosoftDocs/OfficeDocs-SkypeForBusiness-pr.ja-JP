---
title: アーカイブ構成を削除Skype for Business Server
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: '概要: アーカイブ構成を削除する方法については、Skype for Business Server。'
ms.openlocfilehash: 046bd2c1fc5e54189ac038bdf769a711b3c9a774
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621143"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>アーカイブ構成を削除Skype for Business Server

**概要:** アーカイブ構成を削除する方法については、Skype for Business Server。
  
サイト構成またはプール構成を削除できますが、グローバル構成を削除することはできません。 グローバル構成を削除すると、自動的に既定値にリセットされます。
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ構成を削除する

コントロール パネルを使用してアーカイブ構成を削除するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成のリストで、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
    > [!NOTE]
    > グローバル構成をクリックすることもできますが、グローバル構成を既定値にリセットする場合にのみ、このオプションを選択します。 
  
5. [**確定**] をクリックします。
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>サーバーを使用してアーカイブ構成を削除Windows PowerShell

**Remove-CsArchivingConfiguration** コマンドレットを使用してアーカイブ構成を削除することもできます。
  
たとえば、次のコマンドは、Redmond サイトに適用されるアーカイブ構成設定を削除します。 サイト スコープで構成されたポリシーが削除された場合、サイト ポリシーによって以前に管理されたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

次のコマンドは、サービス スコープに適用されるアーカイブ構成設定をすべて削除します。
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

次のコマンドは、アーカイブが無効になっているアーカイブ構成Exchange削除します。
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

**Remove-CsArchivingConfiguration** コマンドレットを使用して、グローバル設定を既定値にリセットすることもできます。 たとえば、グローバル レベルで IM セッションアーカイブを有効にしたとします。次のコマンドは、値を既定値の None にリセットし、グローバル レベルでのアーカイブを無効にします。
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

詳細については [、Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。