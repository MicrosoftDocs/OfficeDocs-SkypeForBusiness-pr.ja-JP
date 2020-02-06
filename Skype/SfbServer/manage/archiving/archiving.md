---
title: Skype for Business Server でアーカイブを管理する
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '概要: Skype for Business Server のアーカイブを管理する方法について説明します。'
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818999"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Skype for Business Server でアーカイブを管理する

**概要:** Skype for Business Server のアーカイブを管理する方法について説明します。
  
組織のアーカイブを展開するときは、展開時に初期構成を指定します。 ただし、日常的な管理のためのアーカイブサポートの実装方法を変更したり、組織の新しい要件を満たす必要がある場合があります。 たとえば、特定のサイト、特定のプール、または組織内の特定のユーザーに対して、アーカイブのサポートを異なる方法でセットアップすることが必要な場合があります。 Skype for Business Server を使っているユーザーは、アーカイブ構成オプションとユーザーポリシーを作成してカスタマイズすることで、この操作を行うことができます。 
  
このトピックを読む前に、「 [skype For Business server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」の情報と[Skype for business server のアーカイブの展開](../../deploy/deploy-archiving/deploy-archiving.md)について理解していることを確認してください。
  
> [!NOTE]
> 展開で Microsoft Exchange 統合が有効の場合、インプレース保持上にメールボックスがある Exchange 所属のユーザーに対してアーカイブを有効にするかどうかは、Exchange のポリシーで管理されます。 詳細については、「 [skype For Business server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」および「 [Skype for business Server 用の Exchange storage との統合を構成する](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)」を参照してください。 
  
## <a name="archiving-configuration-options"></a>構成オプションをアーカイブする

アーカイブ構成オプションでは次の事項を指定します。
  
- アーカイブの有効または無効
    
- IM セッションのアーカイブ
    
- Web 会議セッションのアーカイブ
    
- アーカイブを使用できない場合のアクティビティのブロック
    
- Exchange 統合の使用
    
- データの削除とエクスポートのセットアップ
    
これらのオプションは、グローバル レベル、サイト レベル、プール レベルで設定できます。 詳細については、「 [Skype For Business Server のアーカイブオプションを管理](options.md)する」を参照してください。
  
## <a name="archiving-policies"></a>アーカイブのポリシー

アーカイブポリシーは、次のアイテムをアーカイブするかどうかを決定します。
  
- 内部通信
    
- 外部通信
    
これらのポリシーは、グローバル レベル、サイト レベル、ユーザー レベルで設定できます。 詳細については、「 [Skype For Business Server でアーカイブポリシーを管理](policies.md)する」を参照してください。
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>コントロール パネルまたは Windows PowerShell コマンドレットを使用してアーカイブを管理する

アーカイブは、コントロール パネルまたは Windows PowerShell コマンドレットを使用して管理できます。 次の表に、アーカイブの管理に役立つ使用可能なコマンドレットの一覧を示します。 使用可能なすべてのパラメーターを含む構文の詳細については、「 [Skype For Business Server 管理シェル](../management-shell.md)」を参照してください。 


|**コマンドレット**|**説明**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Skype for Business Server アーカイブデータベースに保存されているレコードをエクスポートします。  <br/> |
|Get-CsArchivingConfiguration  <br/> |組織のアーカイブ構成設定に関する情報を戻します。  <br/> |
|Get-CsArchivingPolicy  <br/> |内部および外部通信に関する組織のアーカイブ ポリシーの情報を戻します。  <br/> |
|Grant-CsArchivingPolicy  <br/> |インスタント メッセージング (IM) セッションのアーカイブ ポリシーをユーザーまたはユーザー セットに割り当てます。 これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりできます。  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |アーカイブ データベースからレコードを手動で削除します。  <br/> |
|New-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) 設定のセットを新たに作成します。これらの設定を使用すると、IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりできます。  <br/> |
|New-CsArchivingPolicy  <br/> |新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。 これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |アーカイブ設定の指定のコレクションを削除します。アーカイブ設定は、インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをすべてブロックしたり (オプション) するときに使用されます。  <br/> |
|Remove-CsArchivingPolicy  <br/> |内部ユーザーとフェデレーションパートナー間のすべての im セッションが、Skype for Business Server によって自動的に保存されるかどうかを決定する、指定したインスタントメッセージング (IM) アーカイブポリシーを削除します。  <br/> |
|Set-CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。  <br/> |
|Set-CsArchivingPolicy  <br/> |既存のインスタントメッセージング (IM) アーカイブポリシーを変更します。 アーカイブポリシーを使用すると、内部ユーザー間で行われるすべての IM セッションと会議をアーカイブすることができます。内部ユーザーとフェデレーションパートナーの間で行われるセッションをアーカイブすることもできます。  <br/> |
|Set-CsArchivingServer  <br/> |1 つ以上のアーカイブ サーバーの新しいデータベースの場所を指定できます。  <br/> |
   

