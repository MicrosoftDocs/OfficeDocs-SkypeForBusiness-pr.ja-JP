---
title: Skype のビジネス サーバー 2015 の受付制御の展開の最終チェックリストを呼び出す
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: ビジネス サーバーのエンタープライズ VoIP の電話受付制御 (CAC) Skype でを展開するための最終的なチェックリストです。
ms.openlocfilehash: beec5c03f47d8f06ec862c3e9a3609fba7b66f2c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a>通話受付管理の展開: Skype for Business Server 2015 の最終チェックリスト
 
ビジネス サーバーのエンタープライズ VoIP の電話受付制御 (CAC) Skype でを展開するための最終的なチェックリストです。 
  
次のチェック リストを使用して、通話受付管理サービス (CAC) を展開するために必要なすべての構成タスクを完了したことを確認してください。
  
- 1 つまたは複数のエッジ サーバーを展開する場合は、ネットワーク構成の設定で、32 ビット マスクのサブネットの一覧に各外部インターフェイスの IP アドレスを追加する必要があります。 音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。
    
    > [!NOTE]
    > エッジ サーバーは CAC を実装する必要はありません。 
  
- 指定された[ビジネス サーバー 2015 の Skype で通話受付制御を有効にする](enable-call-admission-control.md)と、CAC が有効であることを確認します。
    
- すべてのセントラル サイトで CAC が有効化されていることを確認します。 これは、トポロジ ビルダーを実行できます。 警告が生成されるは、発行するとき場合は、無視*しません*。
    
- エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。 [展開ネットワーク領域、サイト、およびビジネス 2015年の Skype でのサブネット](deploy-network.md)で説明したようにもすべてのサブネットがネットワーク サイトに関連付けられていることが重要です。
    
- すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。
    

