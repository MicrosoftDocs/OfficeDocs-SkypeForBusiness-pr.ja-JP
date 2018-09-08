---
title: 受付制御の展開の最終チェックリストを Skype のビジネス サーバーの呼び出し
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: ビジネス サーバーのエンタープライズ VoIP の電話受付制御 (CAC) Skype でを展開するための最終的なチェックリストです。
ms.openlocfilehash: 841a3a8d124a50142cd3644dd6f001e6019af9f3
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885477"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>受付制御の配置を呼び出す: ビジネス サーバーの Skype の最終チェックリスト
 
ビジネス サーバーのエンタープライズ VoIP の電話受付制御 (CAC) Skype でを展開するための最終的なチェックリストです。 
  
次のチェック リストを使用して、通話受付管理サービス (CAC) を展開するために必要なすべての構成タスクを完了したことを確認してください。
  
- 1 つまたは複数のエッジ サーバーを展開する場合は、ネットワーク構成の設定で、32 ビット マスクのサブネットの一覧に各外部インターフェイスの IP アドレスを追加する必要があります。 音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。
    
    > [!NOTE]
    > エッジ サーバーは CAC を実装する必要はありません。 
  
- 指定された[ビジネス サーバーの Skype で通話受付制御を有効にする](enable-call-admission-control.md)と、CAC が有効であることを確認します。
    
- すべてのセントラル サイトで CAC が有効化されていることを確認します。 これは、トポロジ ビルダーを実行できます。 警告が生成されるは、発行するとき場合は、無視*しません*。
    
- エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。 [ネットワークの領域を展開、サイトとサブネットでビジネス用の Skype](deploy-network.md)で説明したようにもすべてのサブネットがネットワーク サイトに関連付けられていることが重要です。
    
- すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。
    

