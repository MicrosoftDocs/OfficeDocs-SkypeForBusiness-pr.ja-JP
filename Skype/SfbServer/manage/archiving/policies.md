---
title: Skype for Business Server でアーカイブポリシーを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: '概要: Skype for Business Server のアーカイブのユーザーポリシーを管理する方法について説明します。'
ms.openlocfilehash: f2dca47dd7fd3095b2865ff72516b6be84144352
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818889"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Skype for Business Server でアーカイブポリシーを管理する

**概要:** Skype for Business Server のアーカイブのユーザーポリシーを管理する方法について説明します。
  
アーカイブの展開時にアーカイブポリシーを最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。 アーカイブポリシーは、アーカイブするかどうかを決定します。 
  
- 内部通信
    
- 外部通信
    
アーカイブポリシーは、グローバル、サイト、またはユーザーのレベルで設定できます。
  
> [!NOTE]
> 展開に対して Microsoft Exchange の統合を有効にしている場合、exchange のポリシーでは、Exchange を使用しているユーザーに対してアーカイブが有効になっているかどうかが制御されます。また、メールボックスはインプレースホールドに配置されています。 詳細については、「 [skype For Business server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」および「 [Skype for business Server 用の Exchange storage との統合を構成する](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)」を参照してください。 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ ポリシーを管理する

次のようにコントロール パネルを使用すると、アーカイブ ポリシーを管理することができます。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで [**アーカイブ ポリシー**] をクリックします。
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Windows PowerShell を使用してアーカイブ ポリシーを管理する

次の表に示す Windows PowerShell コマンドレットを使用してアーカイブ ポリシーを構成することもできます。 使用可能なすべてのパラメーターを含む構文の詳細については、「 [Skype For Business Server 管理シェル](../management-shell.md)」を参照してください。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |組織のインスタント メッセージング (IM) セッションのアーカイブ ポリシーに関する情報を戻します。  <br/> |
|Grant-CsArchivingPolicy  <br/> |インスタント メッセージング (IM) セッションのアーカイブ ポリシーをユーザーまたはユーザー セットに割り当てます。 これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりすることができます。  <br/> |
|New-CsArchivingPolicy  <br/> |新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。 これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。  <br/> |
|Remove-CsArchivingPolicy  <br/> |内部ユーザーとフェデレーションパートナー間のすべての im セッションが、Skype for Business Server によって自動的に保存されるかどうかを決定する、指定したインスタントメッセージング (IM) アーカイブポリシーを削除します。  <br/> |
|Set-CsArchivingPolicy  <br/> |既存のインスタントメッセージング (IM) アーカイブポリシーを変更します。 アーカイブポリシーを使用すると、内部ユーザー間で行われるすべての IM セッションと会議をアーカイブすることができます。内部ユーザーとフェデレーションパートナーの間で行われるセッションをアーカイブすることもできます。  <br/> |
   

