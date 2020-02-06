---
title: Skype for Business Server のユーザーにアーカイブポリシーを適用する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '概要: Skype for Business Server のユーザーにアーカイブポリシーを割り当てる方法について説明します。'
ms.openlocfilehash: 7be62aaf5b2b70108cb67a36559b242377d26117
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819009"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Skype for Business Server のユーザーにアーカイブポリシーを適用する

**概要:** Skype for Business Server のユーザーにアーカイブポリシーを割り当てる方法について説明します。
  
Skype for Business Server を使用しているユーザー用にアーカイブ用のユーザーポリシーを1つ以上作成した場合は、それらのユーザーまたはユーザーグループに適切なポリシーを適用することで、特定のユーザーのアーカイブサポートを実装できます。 たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合、ユーザーの Skype for Business Server の通信のアーカイブをサポートするために、少なくとも1人のユーザーまたはユーザーグループに適用することができます。
  
> [!NOTE]
> 展開で Microsoft Exchange の統合を有効にしている場合、Exchange のインプレースホールドポリシーは、Exchange を使用しているユーザーに対してアーカイブが有効になっているかどうかを制御します。また、メールボックスはインプレースホールドに配置されています。 詳細については、「 [skype For Business server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」および「 [Skype for business Server 用の Exchange storage との統合を構成する](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)」を参照してください。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>コントロール パネルを使用したユーザー ポリシーの適用

コントロール パネルを使用してユーザー ポリシーを適用するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックして、構成するユーザー アカウントを検索します。 
    
4. 検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
5. [**アーカイブポリシー**] の [ **Lync Server ユーザーの編集**] で、適用するアーカイブユーザーポリシーを選択します。
    
    > [!NOTE]
    > ** \<自動\> **設定では、既定のサーバーインストール設定が適用されます。 これらの設定はサーバーにより自動的に適用されます。
  
6. [**コミット**] をクリックします。
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Windows PowerShell を使用してユーザーポリシーを適用する

また、Windows PowerShell **Grant-CsArchivingPolicy**コマンドレットを使用して、ユーザーポリシーを適用することもできます。
  
次のコマンドは、ユーザー単位のアーカイブ ポリシー RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

次のコマンドは、ユーザーごとのアーカイブ ポリシーである RedmondArchivingPolicy を、レジストラー プール atl-cs-001.contoso.com に所属するアカウントを持つすべてのユーザーに割り当てます。 このコマンドで使用される Filter パラメーターの詳細については、「 [CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)コマンドレットのドキュメント」を参照してください。
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

次のコマンドは、Ken Myer に割り当てられたユーザー単位のアーカイブ ポリシーを削除します。ユーザー単位のポリシーが削除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

詳細については、「 [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)コマンドレットのドキュメント」を参照してください。
  

