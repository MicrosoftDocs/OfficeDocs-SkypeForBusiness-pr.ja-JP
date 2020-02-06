---
title: Skype for Business Server でアーカイブオプションを管理する
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '概要: Skype for Business Server のアーカイブオプションを構成する方法について説明します。'
ms.openlocfilehash: af5c8f90cd49f556e1e787e5f550b54da1976c45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818899"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Skype for Business Server でアーカイブオプションを管理する

**概要:** Skype for Business Server のアーカイブオプションを構成する方法について説明します。
  
アーカイブは展開時に初期構成しますが、展開後に変更、追加、削除ができます。 アーカイブ オプションでは次の事項を指定します。 
  
- アーカイブの有効または無効
    
- IM セッションのアーカイブ
    
- Web 会議セッションのアーカイブ
    
- アーカイブを使用できない場合のアクティビティのブロック
    
- Exchange 統合の使用
    
- データの削除とエクスポートのセットアップ
    
構成オプションは次のレベルで指定できます。
  
- Skype for Business Server を展開するときに既定で作成されるグローバルレベルの構成
    
- (オプション) 特定のサイトにアーカイブを実装する方法を指定するサイト レベルの構成
    
- 特定のプールに対するアーカイブの実装方法を指定するオプションのプールレベル構成
    
サイト構成やプール構成は削除できますが、グローバル構成は削除できません。 グローバル構成を削除すると、グローバル構成は自動的に既定値にリセットされます。 アーカイブ構成の実装方法とアーカイブ構成の階層について詳しくは、「 [Skype For Business Server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」をご覧ください。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ オプションを構成する

アーカイブ オプションは、コントロール パネルを使用して次の手順で構成できます。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで [**アーカイブ構成**] をクリックします。
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Windows PowerShell を使用してアーカイブ オプションを構成する

次の表に示す Windows PowerShell コマンドレットを使用してアーカイブ オプションを構成することもできます。 使用可能なすべてのパラメーターを含む構文の詳細については、「 [Skype For Business Server 管理シェル](../management-shell.md)」を参照してください。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |組織のアーカイブ構成設定に関する情報を戻します。  <br/> |
|New-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) 設定のセットを新たに作成します。これらの設定を使用すると、IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりできます。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |アーカイブ設定の指定のコレクションを削除します。アーカイブ設定は、インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをすべてブロックしたり (オプション) するときに使用されます。  <br/> |
|Set-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。  <br/> |
