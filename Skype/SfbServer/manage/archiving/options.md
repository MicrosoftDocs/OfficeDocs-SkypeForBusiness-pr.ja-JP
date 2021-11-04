---
title: アーカイブ オプションを管理Skype for Business Server
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '概要: アーカイブ オプションを構成する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 4ab0f64db30638b29367f113acc342077b84b113
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747311"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>アーカイブ オプションを管理Skype for Business Server

**概要:** ドキュメントのアーカイブ オプションを構成する方法Skype for Business Server。
  
最初は展開時にアーカイブを構成しますが、展開後に構成を変更、追加、および削除できます。 アーカイブ オプションは、次の処理を行うかどうかを決定します。 
  
- アーカイブの有効化または無効化
    
- IM セッションをアーカイブする
    
- Web 会議セッションのアーカイブ
    
- アーカイブが利用できない場合のアクティビティをブロックする
    
- 統合Exchange使用する
    
- データの削除とエクスポートを設定する
    
構成オプションは、次のレベルで指定できます。
  
- 展開時に既定で作成されるグローバル レベルの構成Skype for Business Server
    
- 特定のサイトに対するアーカイブの実装方法を指定するオプションのサイト レベル構成
    
- 特定のプールに対するアーカイブの実装方法を指定するオプションのプール レベル構成
    
サイト構成またはプール構成を削除できますが、グローバル構成を削除することはできません。 グローバル構成を削除すると、自動的に既定値にリセットされます。 アーカイブ構成の実装方法とアーカイブ構成の階層の詳細については、「Plan for archiving in Skype for Business Server」[を参照してください](../../plan-your-deployment/archiving/archiving.md)。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ オプションを構成する

次のようにコントロール パネルを使用して、アーカイブ オプションを構成できます。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで、[アーカイブ構成] **をクリックします**。
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>サーバーを使用してアーカイブ オプションを構成Windows PowerShell

次の表に示す Windows PowerShellコマンドレットを使用して、アーカイブ オプションを構成することもできます。 使用可能なすべてのパラメーターを含む構文の詳細については[、「Skype for Business Server」を参照してください](../management-shell.md)。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |組織のアーカイブ構成設定に関する情報を返します。  <br/> |
|New-CsArchivingConfiguration  <br/> |IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりするために使用できる、インスタント メッセージング (IM) 設定の新しいセットを作成します。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) セッションの自動保存を有効または無効にし、必要に応じてアーカイブできないインスタント メッセージをブロックするために使用されるアーカイブ設定の指定したコレクションを削除します。  <br/> |
|Set-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。  <br/> |
