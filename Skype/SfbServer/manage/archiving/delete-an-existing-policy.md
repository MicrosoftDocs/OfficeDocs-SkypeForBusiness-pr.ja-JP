---
title: Skype for Business Server で既存のアーカイブポリシーを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: '概要: Skype for Business Server のアーカイブポリシーを削除する方法について説明します。'
ms.openlocfilehash: 04ea9db10a2f95ba5010471f262d58c269c173d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278413"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Skype for Business Server で既存のアーカイブポリシーを削除する

**概要:** Skype for Business Server のアーカイブポリシーを削除する方法について説明します。
  
ユーザー ポリシーやサイト ポリシーは削除できますが、グローバル ポリシーは削除できません。 グローバルポリシーを削除すると、Skype for Business Server によってポリシーが自動的に既定値にリセットされます。
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>コントロール パネルを使用してポリシーを削除する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
4. アーカイブ ポリシーのリストで、削除するユーザー ポリシーまたはサイト ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
5. [**コミット**] をクリックします。
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Windows PowerShell を使用してポリシーを削除する

**Remove-CsArchivingPolicy** コマンドレットを使用してアーカイブ ポリシーを削除することもできます。
  
たとえば、以下のコマンドを実行すると、site:Redmond という ID を持つポリシーが削除されます。サイト レベルで構成されているポリシーを削除すると、以前にサイト ポリシーによって管理されていたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

このコマンドでは、ユーザーごとのレベルに適用されているすべてのアーカイブ ポリシーを削除します。
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

このコマンドでは、内部アーカイブが無効になっているすべてのアーカイブ ポリシーを削除します。
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

詳細については、 [CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)コマンドレットのヘルプトピックを参照してください。
