---
title: アーカイブ ポリシーを管理Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: '概要: ユーザー のアーカイブ用のユーザー ポリシーを管理する方法について説明Skype for Business Server。'
ms.openlocfilehash: 47c88ea294a3b8ea96f7904041a95fa6f0330816
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616583"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>アーカイブ ポリシーを管理Skype for Business Server

**概要:** ユーザー ポリシーのアーカイブを管理する方法について説明Skype for Business Server。
  
アーカイブを展開するときに最初にアーカイブ ポリシーを設定しましたが、展開後に構成を変更、追加、および削除できます。 アーカイブ ポリシーは、アーカイブするかどうかを決定します。 
  
- 内部通信
    
- 外部通信
    
アーカイブ ポリシーは、グローバル、サイト、またはユーザー レベルで設定できます。
  
> [!NOTE]
> 展開で Microsoft Exchange 統合を有効にした場合、Exchange ポリシーは、Exchange に自宅にいて、メールボックスを In-Place Hold に置くユーザーに対してアーカイブを有効にするかどうかを制御します。 詳細については、「Plan [for archiving in Skype for Business Server」](../../plan-your-deployment/archiving/archiving.md)および「Configure integration with [Exchange ストレージ for Skype for Business Server」 を参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ ポリシーを管理する

次のようにコントロール パネルを使用して、アーカイブ ポリシーを管理できます。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで、[アーカイブ ポリシー **] をクリックします。**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>アーカイブ ポリシーを使用してアーカイブ ポリシーをWindows PowerShell

次の表に示すWindows PowerShellコマンドレットを使用して、アーカイブ ポリシーを構成することもできます。 使用可能なすべてのパラメーターを含む構文の詳細については[、「Skype for Business Server」を参照してください](../management-shell.md)。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |組織のインスタント メッセージング (IM) セッションのアーカイブ ポリシーに関する情報を返します。  <br/> |
|Grant-CsArchivingPolicy  <br/> |インスタント メッセージング (IM) セッションアーカイブ ポリシーをユーザーまたはユーザーのセットに割り当てる。 これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりすることができます。  <br/> |
|New-CsArchivingPolicy  <br/> |新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。 これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。  <br/> |
|Remove-CsArchivingPolicy  <br/> |Skype for Business Server が内部ユーザー間で行うすべての IM セッション、および内部ユーザーとフェデレーション パートナー間のすべての IM セッションを自動的に保存するかどうかを決定する、指定されたインスタント メッセージング (IM) アーカイブ ポリシーを削除します。  <br/> |
|Set-CsArchivingPolicy  <br/> |既存のインスタント メッセージング (IM) アーカイブ ポリシーを変更します。 アーカイブ ポリシーを使用すると、内部ユーザー間で行うすべての IM セッションと会議をアーカイブできます。内部ユーザーとフェデレーション パートナーの間で行うセッションをアーカイブすることもできます。  <br/> |
   

