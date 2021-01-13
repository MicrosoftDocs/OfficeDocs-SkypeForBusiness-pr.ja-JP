---
title: Skype for Business Server でのアーカイブの管理
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '概要: Skype for Business Server のアーカイブを管理する方法について学習します。'
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817737"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Skype for Business Server でのアーカイブの管理

**概要:** Skype for Business Server のアーカイブを管理する方法について学習します。
  
組織のアーカイブを展開する場合は、展開時に初期構成を指定します。 ただし、日次管理のアーカイブ サポートの実装方法を変更したり、組織の新しい要件を満たしたりしたい場合があります。 たとえば、組織内の特定のサイト、特定のプール、または特定のユーザーに対して、アーカイブ サポートを異なる方法で設定する必要がある場合があります。 Skype for Business Server にホームのユーザーの場合は、アーカイブ構成オプションとユーザー ポリシーを作成およびカスタマイズすることで、これを行います。 
  
このトピックを読む前に [、「Plan for archiving in Skype for Business Server」および「Deploy](../../plan-your-deployment/archiving/archiving.md) [archiving for Skype for Business Server」](../../deploy/deploy-archiving/deploy-archiving.md)の情報を理解している必要があります。
  
> [!NOTE]
> 展開で Microsoft Exchange 統合を有効にした場合、Exchange ポリシーは、Exchange にホームを置き、メールボックスが In-Place Hold に設定されているユーザーに対してアーカイブを有効にするかどうかを制御します。 詳細については [、「Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business Server 」を [参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="archiving-configuration-options"></a>アーカイブ構成オプション

アーカイブ構成オプションでは、次の処理を行うかどうかを指定します。
  
- アーカイブの有効化または無効化
    
- IM セッションをアーカイブする
    
- Web 会議セッションをアーカイブする
    
- アーカイブが利用できない場合のアクティビティのブロック
    
- Exchange 統合の使用
    
- データの削除とエクスポートを設定する
    
これらのオプションは、グローバル レベル、サイト レベル、またはプール レベルで設定できます。 詳細については、「Skype for Business Server でのアーカイブ オプションの [管理」を参照してください](options.md)。
  
## <a name="archiving-policies"></a>アーカイブ ポリシー

アーカイブ ポリシーは、以下をアーカイブするかどうかを決定します。
  
- 内部通信
    
- 外部通信
    
これらのポリシーは、グローバル レベル、サイト レベル、またはユーザー レベルで設定できます。 詳細については [、「Skype for Business Server でのアーカイブ ポリシーの管理」を参照してください](policies.md)。
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>コントロール パネルまたはコントロール パネルを使用してアーカイブをWindows PowerShell

コントロール パネルまたはコントロール パネルを使用して、アーカイブをWindows PowerShell。 次の表に、アーカイブの管理に役立つコマンドレットの概要を示します。 使用可能なすべてのパラメーターを含む構文の詳細については [、「Skype for Business Server Management Shell」を参照してください](../management-shell.md)。 


|**コマンドレット**|**説明**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Skype for Business Server Archiving データベースに格納されているレコードをエクスポートします。  <br/> |
|Get-CsArchivingConfiguration  <br/> |組織のアーカイブ構成設定に関する情報を戻します。  <br/> |
|Get-CsArchivingPolicy  <br/> |内部通信と外部通信に関する組織のアーカイブ ポリシーに関する情報を戻します。  <br/> |
|Grant-CsArchivingPolicy  <br/> |インスタント メッセージング (IM) セッション アーカイブ ポリシーをユーザーまたはユーザーのセットに割り当てる。 これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりすることができます。  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |アーカイブ データベースからレコードを手動で削除します。  <br/> |
|New-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) 設定の新しいセットを作成します。IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりするために使用できます。  <br/> |
|New-CsArchivingPolicy  <br/> |新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。 これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをオプションでブロックしたりするために使用されるアーカイブ設定の指定されたコレクションを削除します。  <br/> |
|Remove-CsArchivingPolicy  <br/> |指定したインスタント メッセージング (IM) アーカイブ ポリシーを削除します。このポリシーは、Skype for Business Server が内部ユーザー間で行うすべての IM セッション、および内部ユーザーとフェデレーション パートナー間のすべての IM セッションを自動的に保存するかどうかを決定します。  <br/> |
|Set-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。  <br/> |
|Set-CsArchivingPolicy  <br/> |既存のインスタント メッセージング (IM) アーカイブ ポリシーを変更します。 アーカイブ ポリシーを使用すると、内部ユーザー間で行うすべての IM セッションと会議をアーカイブできます。内部ユーザーとフェデレーション パートナーの間で行うセッションをアーカイブすることもできます。  <br/> |
|Set-CsArchivingServer  <br/> |1 つ以上のアーカイブ サーバーの新しいデータベースの場所を指定できます。  <br/> |
   

