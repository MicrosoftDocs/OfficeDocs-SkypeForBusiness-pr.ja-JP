---
title: アーカイブを管理Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '概要: ユーザーのアーカイブを管理する方法についてSkype for Business Server。'
ms.openlocfilehash: d7751e8aff9bb9d1f559655671ff56655dc0f188
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630691"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>アーカイブを管理Skype for Business Server

**概要:** ドキュメントのアーカイブを管理するSkype for Business Server。
  
組織のアーカイブを展開する場合は、展開時に初期構成を指定します。 ただし、日次管理のアーカイブ サポートの実装方法を変更したり、組織の新しい要件を満たしたりする場合があります。 たとえば、組織内の特定のサイト、特定のプール、または特定のユーザーに対して異なる方法でアーカイブ サポートを設定する必要がある場合があります。 この操作は、Skype for Business Serverアーカイブ構成オプションとユーザー ポリシーを作成およびカスタマイズすることで行います。 
  
このトピックを読む前に、「アーカイブの計画」および「Skype for Business Server[](../../plan-your-deployment/archiving/archiving.md)のアーカイブを展開する」の[Skype for Business Server。](../../deploy/deploy-archiving/deploy-archiving.md)
  
> [!NOTE]
> 展開で Microsoft Exchange 統合を有効にした場合、Exchange ポリシーは、Exchange に自宅にいてメールボックスを In-Place Hold に置くユーザーに対してアーカイブを有効にするかどうかを制御します。 詳細については、「Plan [for archiving in Skype for Business Server」](../../plan-your-deployment/archiving/archiving.md)および「Configure integration with [Exchange ストレージ for Skype for Business Server」 を参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="archiving-configuration-options"></a>アーカイブ構成オプション

アーカイブ構成オプションは、次の処理を行うかどうかを指定します。
  
- アーカイブの有効化または無効化
    
- IM セッションをアーカイブする
    
- Web 会議セッションのアーカイブ
    
- アーカイブが利用できない場合のアクティビティをブロックする
    
- 統合Exchange使用する
    
- データの削除とエクスポートを設定する
    
これらのオプションは、グローバル レベル、サイト レベル、またはプール レベルで設定できます。 詳細については、「Manage [archiving options in Skype for Business Server 」 を参照してください](options.md)。
  
## <a name="archiving-policies"></a>アーカイブ ポリシー

アーカイブ ポリシーは、次のアーカイブを行うかどうかを決定します。
  
- 内部通信
    
- 外部通信
    
これらのポリシーは、グローバル、サイト、またはユーザー レベルで設定できます。 詳細については、「Manage [archiving policis in](policies.md)Skype for Business Server 」 を参照してください。
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>コントロール パネルを使用するか、コントロール パネルを使用してアーカイブをWindows PowerShell

アーカイブは、コントロール パネルを使用するか、コントロール パネルを使用してWindows PowerShell。 次の表に、アーカイブの管理に役立つコマンドレットの概要を示します。 使用可能なすべてのパラメーターを含む構文の詳細については[、「Skype for Business Server」を参照してください](../management-shell.md)。 


|**コマンドレット**|**説明**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |アーカイブ データベースに格納されているレコードをSkype for Business Serverします。  <br/> |
|Get-CsArchivingConfiguration  <br/> |組織のアーカイブ構成設定に関する情報を返します。  <br/> |
|Get-CsArchivingPolicy  <br/> |内部および外部通信に関する組織のアーカイブ ポリシーに関する情報を返します。  <br/> |
|Grant-CsArchivingPolicy  <br/> |インスタント メッセージング (IM) セッションアーカイブ ポリシーをユーザーまたはユーザーのセットに割り当てる。 これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりすることができます。  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |アーカイブ データベースからレコードを手動で削除します。  <br/> |
|New-CsArchivingConfiguration  <br/> |IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりするために使用できる、インスタント メッセージング (IM) 設定の新しいセットを作成します。  <br/> |
|New-CsArchivingPolicy  <br/> |新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。 これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) セッションの自動保存を有効または無効にし、必要に応じてアーカイブできないインスタント メッセージをブロックするために使用されるアーカイブ設定の指定したコレクションを削除します。  <br/> |
|Remove-CsArchivingPolicy  <br/> |Skype for Business Server が内部ユーザー間で行うすべての IM セッション、および内部ユーザーとフェデレーション パートナー間のすべての IM セッションを自動的に保存するかどうかを決定する、指定されたインスタント メッセージング (IM) アーカイブ ポリシーを削除します。  <br/> |
|Set-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。  <br/> |
|Set-CsArchivingPolicy  <br/> |既存のインスタント メッセージング (IM) アーカイブ ポリシーを変更します。 アーカイブ ポリシーを使用すると、内部ユーザー間で行うすべての IM セッションと会議をアーカイブできます。内部ユーザーとフェデレーション パートナーの間で行うセッションをアーカイブすることもできます。  <br/> |
|Set-CsArchivingServer  <br/> |1 つ以上のアーカイブ サーバーの新しいデータベースの場所を指定できます。  <br/> |
   

