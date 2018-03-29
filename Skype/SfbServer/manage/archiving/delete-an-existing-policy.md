---
title: Skype for Business Server 2015 での既存のアーカイブ ポリシーの削除
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: '概要: は、Skype のビジネス サーバー 2015 のアーカイブ ポリシーを削除する方法を説明します。'
ms.openlocfilehash: aeb640cc832bffbded4765e5b6cc931a17365215
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での既存のアーカイブ ポリシーの削除

**の概要:**ビジネス サーバー 2015 の Skype は、アーカイブ ・ ポリシーを削除する方法について説明します。
  
ユーザー ポリシーやサイト ポリシーは削除できますが、グローバル ポリシーは削除できません。 グローバル ポリシーを削除する場合 Skype ビジネス サーバーに自動的にポリシーをリセットする既定値にします。
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>コントロール パネルを使用してポリシーを削除する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
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

詳細については、[削除 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。