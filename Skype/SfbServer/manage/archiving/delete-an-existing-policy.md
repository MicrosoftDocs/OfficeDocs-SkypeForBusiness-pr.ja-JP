---
title: Skype for Business Server の既存のアーカイブ ポリシーを削除する
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: '概要: Skype for Business Server のアーカイブ ポリシーを削除する方法について学習します。'
ms.openlocfilehash: 2baad7d862b1b6739019a4459492bfb3b67e04cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095391"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Skype for Business Server の既存のアーカイブ ポリシーを削除する

**概要:** Skype for Business Server のアーカイブ ポリシーを削除する方法について学習します。
  
ユーザー ポリシーまたはサイト ポリシーは削除できますが、グローバル ポリシーは削除できます。 グローバル ポリシーを削除すると、Skype for Business Server はポリシーを既定値に自動的にリセットします。
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>コントロール パネルを使用してポリシーを削除する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
4. アーカイブ ポリシーのリストで、削除するユーザー ポリシーまたはサイト ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
5. [**確定**] をクリックします。
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>ポリシーを使用してポリシーを削除Windows PowerShell

**Remove-CsArchivingPolicy** コマンドレットを使用してアーカイブ ポリシーを削除することもできます。
  
たとえば、次のコマンドは、Identity サイト:Redmond を使用してポリシーを削除します。 サイト レベルで構成されたポリシーが削除された場合、サイト ポリシーによって以前に管理されたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

このコマンドは、ユーザー単位レベルに適用されるアーカイブ ポリシーをすべて削除します。
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

このコマンドでは、内部アーカイブが無効になっているすべてのアーカイブ ポリシーを削除します。
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

詳細については [、Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。