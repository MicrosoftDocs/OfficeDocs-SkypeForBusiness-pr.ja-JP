---
title: パイロット プールとレガシ プールの共存の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来のプールとの間でパイロットプールを共存させるプロセス。
ms.openlocfilehash: b41a1f24786fdf807f9c9c1d5854e397654fdadb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2019
ms.locfileid: "35758905"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>パイロット プールとレガシ プールの共存の確認

 **この記事の内容**
  
[Skype for Business Server 2019 サービスが開始されたことを確認する](#sectionSection0)
  
[Skype for Business Server 2019 コントロールパネルを開く](#sectionSection1)
  
[従来のトポロジビルダーでトポロジを開かないようにします。](#sectionSection2)
  
パイロットプールを展開した後、管理ツールを使用してプール情報を表示し、2つのプールの共存を確認する必要があります。 Skype for Business Server 2019 プールおよび従来のプールの場合は、Skype for Business Server 2019 コントロールパネルツールとトポロジビルダーツールを使用する必要があります。 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Skype for Business Server 2019 サービスが開始されたことを確認する
<a name="sectionSection0"> </a>

1. Skype for Business Server 2019 フロントエンドサーバーから、管理用の [サービス] アプレットに移動します。
    
2. フロントエンドサーバーで次のサービスが実行されていることを確認します。

    - 一元ログサービスエージェント
    - アプリケーション共有
    - オーディオテストサービス
    - 音声/ビデオ会議
    - コール パーク
    - 会議アナウンス
    - 会議の応答
    - フロントエンド
    - IM 会議
    - 仲介
    - レプリカレプリケーターエージェント
    - 応答グループ
    - Web 会議
    - XMPP の変換ゲートウェイ

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Skype for Business Server 2019 コントロールパネルを開く
<a name="sectionSection1"> </a>

Skype for Business Server 2019 展開のフロントエンドサーバーから、[Skype for Business Server 2019 コントロールパネル] を開いて、従来のプールを選択します。 手順を繰り返して、Skype for Business Server 2019 プールを開きます。
  
> [!IMPORTANT]
> Skype for Business Server 2019 で、Skype for Business Server コントロールパネルを使用する前に、Silverlight を Silverlight バージョン5にアップグレードする必要があります。 
  
このトポロジには、レガシーおよび Skype for Business Server 2019 サーバーの役割が含まれています。 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>従来のトポロジビルダーでトポロジを開かないようにします。
<a name="sectionSection2"> </a>

このトポロジを表示するには、Skype for Business Server 2019 Topology Builder を使用します。 Skype for business server 2019 トポロジビルダーを使用して、Skype for Business Server 2019 と従来のインストールの両方のプールを作成する必要があります。

  

