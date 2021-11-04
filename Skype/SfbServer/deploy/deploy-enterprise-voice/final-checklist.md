---
title: 通話受付管理の展開の最終チェックリスト (Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 通話受付管理 (CAC) を展開するための最後のチェックリストをSkype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 11bf5a69b273f1311399090cc893bee1f4732443
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759079"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>通話受付管理の展開: 通話の最終チェックリストSkype for Business Server
 
通話受付管理 (CAC) を展開するための最後のチェックリストをSkype for Business Server エンタープライズ VoIP。 
  
次のチェックリストを使用して、通話受付管理 (CAC) を展開するために必要なすべての構成タスクが完了したと確認します。
  
- 1 つまたは複数のエッジ サーバーが展開されている場合には、32 ビット マスクのすべての外部インターフェイス IP アドレスがネットワーク構成設定のサブネット リストに追加されている必要があります。音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。
    
    > [!NOTE]
    > CAC を実装するためにエッジ サーバーは必要ありません。 
  
- [ユーザーの通話受付管理を有効にする] で指定されている CAC が有効[Skype for Business Server。](enable-call-admission-control.md)
    
- すべてのセントラル サイトで CAC が有効化されていることを確認します。 これはトポロジ ビルダーを使用して実行できます。 発行時に警告が生成された場合は  *、無視*  しない。
    
- エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。 また、「ネットワーク領域、サイト、サブネットをネットワーク サイトに展開する」で説明したように、すべてのサブネットをネットワーク サイトに[関連](deploy-network.md)付Skype for Business。
    
- すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。
    

