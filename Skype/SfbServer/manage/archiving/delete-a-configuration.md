---
title: Skype for Business Server のアーカイブ構成を削除する
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
ms.openlocfilehash: 43913485ce18660b6c7fa7ce747ceeaaebd49923
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095411"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Skype for Business Server のアーカイブ構成を削除する

**概要:** Skype for Business Server でアーカイブ構成を削除する方法について説明します。
  
サイト構成またはプール構成を削除できますが、グローバル構成を削除することはできません。 グローバル構成を削除すると、自動的に既定値にリセットされます。
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ構成を削除する

コントロール パネルを使用してアーカイブ構成を削除するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
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

次のコマンドは、Exchange アーカイブが無効になっているすべてのアーカイブ構成設定を削除します。
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

**Remove-CsArchivingConfiguration** コマンドレットを使用して、グローバル設定を既定値にリセットすることもできます。 たとえば、グローバル レベルで IM セッションアーカイブを有効にしたとします。次のコマンドは、値を既定値の None にリセットし、グローバル レベルでのアーカイブを無効にします。
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

詳細については [、Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。