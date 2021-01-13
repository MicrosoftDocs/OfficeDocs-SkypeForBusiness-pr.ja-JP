---
title: Skype for Business Server でアーカイブ ポリシーを管理する
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
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: '概要: Skype for Business Server のアーカイブ用のユーザー ポリシーを管理する方法について説明します。'
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828552"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Skype for Business Server でアーカイブ ポリシーを管理する

**概要:** Skype for Business Server のアーカイブのユーザー ポリシーを管理する方法について説明します。
  
アーカイブ ポリシーは、最初はアーカイブを展開するときに設定しますが、展開後に構成を変更、追加、および削除できます。 アーカイブ ポリシーは、次の情報をアーカイブするかどうかを決定します。 
  
- 内部通信
    
- 外部通信
    
アーカイブ ポリシーは、グローバル レベル、サイト レベル、またはユーザー レベルで設定できます。
  
> [!NOTE]
> 展開で Microsoft Exchange 統合を有効にした場合、Exchange ポリシーは、Exchange にホームを置き、メールボックスが In-Place Hold に設定されているユーザーに対してアーカイブを有効にするかどうかを制御します。 詳細については [、「Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business Server 」を [参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ ポリシーを管理する

次のように、コントロール パネルを使用してアーカイブ ポリシーを管理できます。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、[アーカイブ ポリシー **] をクリックします。**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>アーカイブ ポリシーを使用してアーカイブ ポリシーをWindows PowerShell

アーカイブ ポリシーは、次の表にWindows PowerShellコマンドレットを使用して構成することもできます。 使用可能なすべてのパラメーターを含む構文の詳細については [、「Skype for Business Server Management Shell」を参照してください](../management-shell.md)。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |組織のインスタント メッセージング (IM) セッションのアーカイブ ポリシーに関する情報を戻します。  <br/> |
|Grant-CsArchivingPolicy  <br/> |インスタント メッセージング (IM) セッション アーカイブ ポリシーをユーザーまたはユーザーのセットに割り当てる。 これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりすることができます。  <br/> |
|New-CsArchivingPolicy  <br/> |新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。 これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。  <br/> |
|Remove-CsArchivingPolicy  <br/> |指定したインスタント メッセージング (IM) アーカイブ ポリシーを削除します。このアーカイブ ポリシーは、Skype for Business Server が内部ユーザー間で行うすべての IM セッション、および内部ユーザーとフェデレーション パートナーとの間で行うすべての IM セッションを自動的に保存するかどうかを決定します。  <br/> |
|Set-CsArchivingPolicy  <br/> |既存のインスタント メッセージング (IM) アーカイブ ポリシーを変更します。 アーカイブ ポリシーを使用すると、内部ユーザー間で行うすべての IM セッションと会議をアーカイブできます。内部ユーザーとフェデレーション パートナーの間で行うセッションをアーカイブすることもできます。  <br/> |
   

