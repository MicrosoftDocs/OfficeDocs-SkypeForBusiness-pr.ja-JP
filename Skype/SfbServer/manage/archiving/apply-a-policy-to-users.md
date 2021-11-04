---
title: アーカイブ ポリシーをユーザーに適用Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '概要: アーカイブ ポリシーをユーザーに割り当てる方法についてSkype for Business Server。'
ms.openlocfilehash: 343afcca74947f4a9e40830775c2149adcbc58af
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765565"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>アーカイブ ポリシーをユーザーに適用Skype for Business Server

**概要:** アーカイブ ポリシーをユーザーに割り当てる方法については、Skype for Business Server。
  
Skype for Business Server に保存されているユーザーのアーカイブ用に 1 つ以上のユーザー ポリシーを作成した場合は、それらのユーザーまたはユーザー グループに適切なポリシーを適用することで、特定のユーザーのアーカイブ サポートを実装できます。 たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合は、少なくとも 1 つのユーザーまたはユーザー グループに適用して、ユーザーの Skype for Business Server 通信のアーカイブをサポートできます。
  
> [!NOTE]
> 展開で Microsoft Exchange 統合を有効にした場合、Exchange In-Place 保留ポリシーは、Exchange に自宅にいてメールボックスを In-Place 保留にしているユーザーに対してアーカイブを有効にするかどうかを制御します。 詳細については、「Plan [for archiving in Skype for Business Server」](../../plan-your-deployment/archiving/archiving.md)および「Configure integration with [Exchange ストレージ for Skype for Business Server」 を参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>コントロール パネルを使用してユーザー ポリシーを適用する

コントロール パネルを使用してユーザー ポリシーを適用するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
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
