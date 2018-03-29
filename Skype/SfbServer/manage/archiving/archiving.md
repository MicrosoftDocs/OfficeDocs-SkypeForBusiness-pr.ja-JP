---
title: Skype for Business Server 2015 のアーカイブの管理
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '概要: は、Skype のビジネス サーバー 2015 のアーカイブを管理する方法を説明します。'
ms.openlocfilehash: fb8359d47b1933e2575685bc532d69e6b9bb6c45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のアーカイブの管理

**の概要:**Skype ビジネス サーバー 2015 のアーカイブを管理する方法について説明します。
  
組織のアーカイブを展開するときは、初期展開時に構成を指定します。 ただし、日常的な管理のためのアーカイブのサポートを実装する方法を変更するか、組織の新しい要件を満たすために、必要な場合があります。 たとえば、アーカイブとは異なる、特定のサイト、特定のプール、または組織内の特定のユーザーのサポートを設定する必要があります。 ユーザーは、Skype のビジネス サーバーのホームのこれを行うを作成し、アーカイブの構成オプションとユーザーのポリシーをカスタマイズします。 
  
このトピックを参照する前に、[ビジネス サーバー 2015 の Skype でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)し、[展開のビジネス サーバー 2015 の Skype のアーカイブ](../../deploy/deploy-archiving/deploy-archiving.md)内の情報に精通していることを確認します。
  
> [!NOTE]
> 展開で Microsoft Exchange 統合が有効の場合、インプレース保持上にメールボックスがある Exchange 所属のユーザーに対してアーカイブを有効にするかどうかは、Exchange のポリシーで管理されます。 詳細については、[ビジネス サーバー 2015 の Skype でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)と[構成との統合ビジネス サーバー 2015 の Skype の Exchange の記憶域](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)を参照してください。 
  
## <a name="archiving-configuration-options"></a>構成オプションをアーカイブする

アーカイブ構成オプションでは次の事項を指定します。
  
- アーカイブの有効または無効
    
- IM セッションのアーカイブ
    
- Web 会議セッションのアーカイブ
    
- アーカイブを使用できない場合のアクティビティのブロック
    
- Exchange 統合の使用
    
- データの削除とエクスポートのセットアップ
    
これらのオプションは、グローバル レベル、サイト レベル、プール レベルで設定できます。 詳細については、[ビジネス サーバー 2015 の Skype での管理アーカイブ ・ オプション](options.md)を参照してください。
  
## <a name="archiving-policies"></a>アーカイブのポリシー

アーカイブ ・ ポリシーは、次にアーカイブするかどうかを決定します。
  
- 内部通信
    
- 外部通信
    
これらのポリシーは、グローバル レベル、サイト レベル、ユーザー レベルで設定できます。 詳細については、 [Skype のビジネス サーバー 2015 のアーカイブ ・ ポリシーの管理](policies.md)を参照してください。
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>コントロール パネルまたは Windows PowerShell コマンドレットを使用してアーカイブを管理する

アーカイブは、コントロール パネルまたは Windows PowerShell コマンドレットを使用して管理できます。 次の表に、アーカイブの管理に役立つ使用可能なコマンドレットの一覧を示します。 などのすべての利用可能なパラメーターの構文の詳細については、 [Skype ビジネス サーバー 2015 管理シェルに](../management-shell.md)を参照してください。 


|**コマンドレット**|**説明**|
|:-----|:-----|
|.Eml という  <br/> |Skype のビジネス ・ サーバのアーカイブ データベースに格納されているレコードをエクスポートします。  <br/> |
|Get CsArchivingConfiguration  <br/> |組織のアーカイブ構成設定に関する情報を戻します。  <br/> |
|Get CsArchivingPolicy  <br/> |内部および外部通信に関する組織のアーカイブ ポリシーの情報を戻します。  <br/> |
|許可 CsArchivingPolicy  <br/> |インスタント メッセージング (IM) セッションのアーカイブ ポリシーをユーザーまたはユーザー セットに割り当てます。 これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりできます。  <br/> |
|呼び出す CsArchivingDatabasePurge  <br/> |アーカイブ データベースからレコードを手動で削除します。  <br/> |
|CsArchivingConfiguration で新しい  <br/> |インスタント メッセージング (IM) 設定のセットを新たに作成します。これらの設定を使用すると、IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりできます。  <br/> |
|新しい-CsArchivingPolicy  <br/> |新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。 これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。  <br/> |
|削除 CsArchivingConfiguration  <br/> |アーカイブ設定の指定のコレクションを削除します。アーカイブ設定は、インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをすべてブロックしたり (オプション) するときに使用されます。  <br/> |
|削除 CsArchivingPolicy  <br/> |指定したインスタント メッセージング (IM) アーカイブ ビジネス サーバーの Skype の内部ユーザー、および内部ユーザーとフェデレーション パートナーとの間のすべての IM セッションの間で行われるすべての IM セッションが自動的に保存するかどうかを決定するポリシーを削除します。  <br/> |
|セット CsArchivingConfiguration  <br/> |インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。  <br/> |
|セット CsArchivingPolicy  <br/> |既存インスタント メッセージング (IM) アーカイブ ポリシーを変更します。 アーカイブ ポリシーは、すべての IM セッションおよび内部ユーザー間で行われる会議をアーカイブする機能を提供します。内部ユーザーとフェデレーション パートナーの間で行われるセッションをアーカイブすることもできます。  <br/> |
|セット CsArchivingServer  <br/> |1 つ以上のアーカイブ サーバーの新しいデータベースの場所を指定できます。  <br/> |
   

