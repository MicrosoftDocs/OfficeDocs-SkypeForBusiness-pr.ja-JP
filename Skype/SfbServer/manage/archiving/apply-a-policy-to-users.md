---
title: Skype for Business Server のユーザーにアーカイブ ポリシーを適用する
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '概要: Skype for Business Server のユーザーにアーカイブ ポリシーを割り当てる方法について学習します。'
ms.openlocfilehash: 1fce0dbd0cc7b0595dcf3cd91baeba9ed364e28a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095491"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Skype for Business Server のユーザーにアーカイブ ポリシーを適用する

**概要:** Skype for Business Server のユーザーにアーカイブ ポリシーを割り当てる方法について学習します。
  
Skype for Business Server に保存されているユーザーのアーカイブ用に 1 つ以上のユーザー ポリシーを作成した場合は、該当するポリシーをそれらのユーザーまたはユーザー グループに適用することで、特定のユーザーのアーカイブ サポートを実装できます。 たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合、それを少なくとも 1 つのユーザーまたはユーザー グループに適用して、ユーザーの Skype for Business Server 通信のアーカイブをサポートできます。
  
> [!NOTE]
> 展開に対して Microsoft Exchange 統合を有効にした場合、Exchange In-Place Hold ポリシーは、Exchange にホームを持ち、メールボックスを In-Place ホールドに置くユーザーに対してアーカイブを有効にするかどうかを制御します。 詳細については [、「Plan for archiving in Skype for Business Server」および「Configure](../../plan-your-deployment/archiving/archiving.md) integration with Exchange storage [for Skype for Business Server」を参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>コントロール パネルを使用してユーザー ポリシーを適用する

コントロール パネルを使用してユーザー ポリシーを適用するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。 
    
4. 検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
5. [**アーカイブ ポリシー] の [Lync Server ユーザー** の編集] で、適用するアーカイブ ユーザー ポリシーを選択します。
    
    > [!NOTE]
    > この **\<Automatic\>** 設定は、既定のサーバー インストール設定を適用します。 これらの設定はサーバーによって自動的に適用されます。
  
6. [**確定**] をクリックします。
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>ユーザー ポリシーを使用してユーザー ポリシーを適用Windows PowerShell

**Grant-CsArchivingPolicy** コマンドレットを使用してWindows PowerShellポリシーを適用することもできます。
  
次のコマンドは、ユーザー単位のアーカイブ ポリシーである RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

このコマンドは、ユーザーごとのアーカイブ ポリシー RedmondArchivingPolicy をレジストラー プール にアカウントを持つすべてのユーザーに割り当 atl-cs-001.contoso.com。 このコマンドで使用される Filter パラメーターの詳細については [、Get-CsUser コマンドレットのドキュメントを](/powershell/module/skype/get-csuser?view=skype-ps) 参照してください。
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

次のコマンドは、Ken Myer に以前割り当てられたユーザーごとのアーカイブ ポリシーを削除します。 ユーザーごとのポリシーが削除されると、Ken Myer はグローバル ポリシーを使用するか、存在する場合はローカル サイト ポリシーを使用して自動的に管理されます。 サイト ポリシーの方がグローバル ポリシーより優先されます。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

詳細については [、Grant-CsArchivingPolicy コマンドレットのドキュメントを](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) 参照してください。
