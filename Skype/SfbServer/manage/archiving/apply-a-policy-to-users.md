---
title: Skype 内のユーザーにビジネス サーバーのアーカイブ ・ ポリシーを適用します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '概要: は、Skype のユーザーにビジネス サーバーのアーカイブ ・ ポリシーを割り当てる方法について説明します。'
ms.openlocfilehash: bc54c25a710e4e1cca44fb7311a47101f31ef7df
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985617"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Skype 内のユーザーにビジネス サーバーのアーカイブ ・ ポリシーを適用します。

**の概要:** Skype 内のユーザーにビジネス サーバーのアーカイブ ・ ポリシーを割り当てる方法について説明します。
  
1 つを作成した、またはユーザーのアーカイブのための複数のユーザー ポリシーは、Skype ビジネス サーバーのホーム、それらのユーザーまたはユーザー グループに適切なポリシーを適用することによって特定のユーザーのアーカイブのサポートを実装できます。 たとえば、内部通信のアーカイブをサポートするためにポリシーを作成する場合は、ビジネス サーバー間の通信のユーザーの Skype のアーカイブをサポートするために少なくとも 1 つのユーザーまたはユーザー ・ グループに適用できます。
  
> [!NOTE]
> 場合は有効にする Microsoft Exchange の統合、展開、Exchange インプレース保持ポリシーの管理に Exchange のホーム サーバーはユーザーのアーカイブが有効になっているし、インプレース保持に自分のメールボックスを配置するかどうか。 詳細については、 [Skype のビジネス サーバーでアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)と[構成との統合 Skype ビジネス サーバー用の Exchange の記憶域](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)を参照してください。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>コントロール パネルを使用したユーザー ポリシーの適用

コントロール パネルを使用してユーザー ポリシーを適用するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックして、構成するユーザー アカウントを検索します。 
    
4. 検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
5. **アーカイブ**ポリシーでは、 **Lync Server ユーザーの編集**では、アーカイブ ユーザー ポリシーを適用するを選択します。
    
    > [!NOTE]
    > **\<自動\>** の設定は、サーバー インストールの既定の設定を適用します。 これらの設定はサーバーによって自動的に適用されます。
  
6. [**確定**] をクリックします。
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Windows PowerShell を使用してユーザー ポリシーを適用します。

**与える CsArchivingPolicy**の Windows PowerShell コマンドレットを使用してユーザー ポリシーを適用することもできます。
  
次のコマンドは、ユーザー単位のアーカイブ ポリシー RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

次のコマンドは、ユーザーごとのアーカイブ ポリシーである RedmondArchivingPolicy を、レジストラー プール atl-cs-001.contoso.com に所属するアカウントを持つすべてのユーザーに割り当てます。 詳細については、このコマンドで使用されるフィルター パラメーターは、 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)コマンドレットのドキュメントを参照してください。
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

次のコマンドは、Ken Myer に割り当てられたユーザー単位のアーカイブ ポリシーを削除します。ユーザー単位のポリシーが削除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

詳細については、[補助金 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)コマンドレットのドキュメントを参照してください。
  

