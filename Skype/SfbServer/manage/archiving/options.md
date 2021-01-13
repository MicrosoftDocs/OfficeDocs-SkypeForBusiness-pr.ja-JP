---
title: Skype for Business Server でアーカイブ オプションを管理する
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '概要: Skype for Business Server のアーカイブ オプションを構成する方法について説明します。'
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817537"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Skype for Business Server でアーカイブ オプションを管理する

**概要:** Skype for Business Server のアーカイブ オプションを構成する方法について説明します。
  
最初は展開時にアーカイブを構成しますが、展開後に構成を変更、追加、および削除できます。 アーカイブ オプションは、次の処理を行うかどうかを決定します。 
  
- アーカイブの有効化または無効化
    
- IM セッションをアーカイブする
    
- Web 会議セッションをアーカイブする
    
- アーカイブが利用できない場合のアクティビティのブロック
    
- Exchange 統合の使用
    
- データの削除とエクスポートを設定する
    
構成オプションは、次のレベルで指定できます。
  
- Skype for Business Server を展開するときに既定で作成されるグローバル レベルの構成
    
- 特定のサイトに対するアーカイブの実装方法を指定するオプションのサイト レベルの構成
    
- 特定のプールに対するアーカイブの実装方法を指定するオプションのプール レベルの構成
    
サイト構成またはプール構成は削除できますが、グローバル構成を削除することはできません。 グローバル構成を削除すると、自動的に既定値にリセットされます。 アーカイブ構成の実装方法とアーカイブ構成の階層の詳細については [、「Plan for archiving in Skype for Business Server」](../../plan-your-deployment/archiving/archiving.md)を参照してください。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ オプションを構成する

次のように、コントロール パネルを使用してアーカイブ オプションを構成できます。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、[アーカイブ構成] **をクリックします**。
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>アーカイブ オプションを構成するには、次のWindows PowerShell

次の表に示すコマンドレットWindows PowerShell使用して、アーカイブ オプションを構成することもできます。 使用可能なすべてのパラメーターを含む構文の詳細については [、「Skype for Business Server Management Shell」を参照してください](../management-shell.md)。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |組織のアーカイブ構成設定に関する情報を戻します。  <br/> |
|New-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) 設定の新しいセットを作成します。IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりするために使用できます。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをオプションでブロックしたりするために使用されるアーカイブ設定の指定されたコレクションを削除します。  <br/> |
|Set-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。  <br/> |
