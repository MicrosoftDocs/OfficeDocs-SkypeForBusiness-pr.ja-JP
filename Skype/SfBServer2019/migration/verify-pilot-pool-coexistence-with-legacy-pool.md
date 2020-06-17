---
title: パイロット プールとレガシ プールの共存の確認
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: パイロットプールとレガシプールの共存を確認するプロセス。
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751659"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>パイロット プールとレガシ プールの共存の確認

 **この記事の内容**
  
[Skype for Business Server 2019 サービスが開始されていることを確認する](#sectionSection0)
  
[Skype for Business Server 2019 コントロールパネルを開く](#sectionSection1)
  
[従来のトポロジビルダーでトポロジを開かないようにします。](#sectionSection2)
  
パイロット プールを展開した後、プール情報を表示するための管理ツールを使用して、2 つのプールの共存を確認する必要があります。 Skype for Business Server 2019 プールおよび従来のプールの場合は、Skype for Business Server 2019 コントロールパネルおよびトポロジビルダーのツールを使用する必要があります。 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Skype for Business Server 2019 サービスが開始されていることを確認する
<a name="sectionSection0"> </a>

1. Skype for Business Server 2019 フロントエンドサーバーから、管理ツール \ サービスアプレットに移動します。
    
2. 次のサービスがフロントエンド サーバーで実行されていることを確認します。

    - 集中ログサービスエージェント
    - アプリケーション共有
    - オーディオテストサービス
    - 音声ビデオ会議
    - コール パーク
    - 会議アナウンス
    - 会議アテンダント
    - フロントエンド
    - IM 会議
    - 仲介
    - レプリカレプリケーターエージェント
    - 応答グループ
    - Web 会議
    - XMPP 変換ゲートウェイ

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Skype for Business Server 2019 コントロールパネルを開く
<a name="sectionSection1"> </a>

Skype for business Server 2019 展開のフロントエンドサーバーから、[Skype for Business Server 2019 コントロールパネル] を開き、従来のプールを選択します。 手順を繰り返して、Skype for Business Server 2019 プールを開きます。
  
> [!IMPORTANT]
> Skype for business Server 2019 では、Skype for Business Server コントロールパネルを使用する前に silverlight バージョン5にアップグレードする必要があります。 
  
このトポロジには、レガシおよび Skype for Business Server 2019 のサーバーの役割が含まれるようになりました。 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>従来のトポロジビルダーでトポロジを開かないようにします。
<a name="sectionSection2"> </a>

このトポロジは、Skype for Business Server 2019 トポロジビルダーを使用してのみ表示できます。 Skype for business server 2019 トポロジビルダーを使用して、Skype for business Server 2019 と従来のインストールの両方のプールを作成する必要があります。

  

