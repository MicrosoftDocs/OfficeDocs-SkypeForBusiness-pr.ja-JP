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
description: '概要: Skype for Business Server でアーカイブ ポリシーをユーザーに割り当てる方法について学習します。'
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817767"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Skype for Business Server のユーザーにアーカイブ ポリシーを適用する

**概要:** Skype for Business Server でアーカイブ ポリシーをユーザーに割り当てる方法について学習します。
  
Skype for Business Server にホームのユーザーのアーカイブ用に 1 つ以上のユーザー ポリシーを作成した場合は、該当するポリシーをそれらのユーザーまたはユーザー グループに適用することで、特定のユーザーのアーカイブ サポートを実装できます。 たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合、そのポリシーを少なくとも 1 つのユーザーまたはユーザー グループに適用して、ユーザーの Skype for Business Server 通信のアーカイブをサポートできます。
  
> [!NOTE]
> 展開で Microsoft Exchange 統合を有効にした場合、Exchange In-Place 保留ポリシーは、Exchange にホームを置き、メールボックスを In-Place 保留にするユーザーに対してアーカイブを有効にするかどうかを制御します。 詳細については [、「Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business Server 」を [参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>コントロール パネルを使用してユーザー ポリシーを適用する

コントロール パネルを使用してユーザー ポリシーを適用するには:
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。 
    
4. 検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
5. [Lync **Server ユーザーの** 編集] の **[アーカイブ** ポリシー] で、適用するアーカイブ ユーザー ポリシーを選択します。
    
    > [!NOTE]
    > この **\<Automatic\>** 設定では、既定のサーバー インストール設定が適用されます。 これらの設定はサーバーによって自動的に適用されます。
  
6. [**確定**] をクリックします。
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>ユーザー ポリシーを使用してユーザー ポリシーをWindows PowerShell

**Grant-CsArchivingPolicy** コマンドレットを使用してWindows PowerShellポリシーを適用することもできます。
  
次のコマンドは、ユーザー単位のアーカイブ ポリシーである RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

このコマンドは、ユーザー単位のアーカイブ ポリシー RedmondArchivingPolicy を、レジストラー プールにホームのアカウントを持つすべてのユーザーに割り当atl-cs-001.contoso.com。 このコマンドで使用される Filter パラメーターの詳細については [、Get-CsUser コマンドレット](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) のドキュメントを参照してください。
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

次のコマンドは、Ken Myer に以前割り当てられたユーザーごとのアーカイブ ポリシーを削除します。 ユーザーごとのポリシーを削除すると、Ken Myer は、グローバル ポリシーまたは存在する場合はローカル サイト ポリシーを使用して自動的に管理されます。 サイト ポリシーの方がグローバル ポリシーより優先されます。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

詳細については [、Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) コマンドレットのドキュメントを参照してください。
  

