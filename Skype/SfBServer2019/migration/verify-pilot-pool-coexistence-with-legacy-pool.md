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
ms.localizationpriority: medium
description: 従来のプールとのパイロット プールの共存を確認するプロセス。
ms.openlocfilehash: 5d2e6adad0f3297260137df0abcd082b750f0345
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606816"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>パイロット プールとレガシ プールの共存の確認

 **この記事の内容**
  
[2019 Skype for Business Serverが開始されたのを確認する](#sectionSection0)
  
[2019 Skype for Business Server パネルを開く](#sectionSection1)
  
[従来のトポロジ ビルダーでトポロジを開かない](#sectionSection2)
  
パイロット プールを展開した後、プール情報を表示するための管理ツールを使用して、2 つのプールの共存を確認する必要があります。 2019 Skype for Business Serverおよびレガシ プールの場合は、Skype for Business Server 2019 コントロール パネルおよびトポロジ ビルダー ツールを使用する必要があります。 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>2019 Skype for Business Serverが開始されたのを確認する
<a name="sectionSection0"> </a>

1. 2019 Skype for Business Server 2019 フロントエンド サーバーから、[管理ツール\サービス] アプレットに移動します。
    
2. 次のサービスがフロントエンド サーバーで実行されていることを確認します。

    - 集中ログ サービス エージェント
    - アプリケーション共有
    - オーディオ テスト サービス
    - 音声ビデオ会議
    - コール パーク
    - 会議アナウンス
    - 会議アテンダント
    - フロントエンド
    - IM 会議
    - 仲介
    - レプリカ レプリケーター エージェント
    - 応答グループ
    - Web 会議
    - XMPP 翻訳ゲートウェイ

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>2019 Skype for Business Server パネルを開く
<a name="sectionSection1"> </a>

Skype for Business Server 2019 年 2019 年の展開のフロント エンド サーバーから、Skype for Business Server 2019 コントロール パネルを開き、レガシ プールを選択します。 手順を繰り返して、2019 Skype for Business Serverを開きます。
  
> [!IMPORTANT]
> 2019 Skype for Business Serverでは、コントロール パネルを使用する前に Silverlight を Silverlight バージョン 5 にアップグレードSkype for Business Serverがあります。 
  
このトポロジには、従来の役割と 2019 Skype for Business Server役割が含まれています。 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>従来のトポロジ ビルダーでトポロジを開かない
<a name="sectionSection2"> </a>

トポロジは、2019 年のトポロジ ビルダー Skype for Business Serverのみ表示できます。 2019 Skype for Business Server 2019 トポロジ ビルダーを使用して、2019 年と従来のインストールSkype for Business Server両方のプールを作成する必要があります。

  

