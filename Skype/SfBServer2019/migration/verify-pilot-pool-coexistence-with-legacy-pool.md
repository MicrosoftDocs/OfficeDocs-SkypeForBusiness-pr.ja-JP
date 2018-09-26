---
title: レガシ プールとの共存をパイロット プールを確認します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: レガシ プールとの共存をパイロット プールを確認するプロセスです。
ms.openlocfilehash: 717726acd3654abb2296d622afc5a4d45009430e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028692"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>レガシ プールとの共存をパイロット プールを確認します。

 **この資料に記載されて**
  
[Skype サーバー 2019 のビジネスのサービスが開始されていることを確認します。](#sectionSection0)
  
[ビジネス サーバー 2019 のコントロール パネルの Skype を開く](#sectionSection1)
  
[従来トポロジ ビルダーでトポロジを開くしようとしていません。](#sectionSection2)
  
パイロット プールを展開した後は、プールの情報を表示するのには管理ツールを使用して 2 つのプールの共存を確認する必要があります。 ビジネス サーバー 2019 のプールとプールの従来の Skype、ビジネス サーバー 2019 コントロール パネルの [トポロジ ビルダー ツールの Skype を使用する必要があります。 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Skype サーバー 2019 のビジネスのサービスが開始されていることを確認します。
<a name="sectionSection0"> </a>

1. ビジネス 2019 フロント エンド サーバーの Skype、管理 Tools\Services のアプレットに移動します。
    
2. フロント エンド サーバー上で次のサービスが実行されていることを確認します。

    - サービス エージェントのログを一元管理
    - アプリケーション共有
    - オーディオ テスト サービス
    - オーディオ/ビデオ会議
    - コール パーク
    - 会議アナウンス
    - 会議アテンダント
    - フロント エンド
    - IM 会議
    - 仲介
    - レプリカ レプリケーター エージェント
    - 応答グループ
    - Web 会議
    - XMPP 変換ゲートウェイ

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>ビジネス サーバー 2019 のコントロール パネルの Skype を開く
<a name="sectionSection1"> </a>

サーバー 2019 のビジネスを展開するため、Skype でフロント エンド サーバーから、Skype ビジネス サーバー 2019 のコントロール パネルの開き従来のプールを選択します。 ビジネス サーバー 2019 プールの Skype を開く手順を繰り返します。
  
> [!IMPORTANT]
> ビジネス サーバー 2019 の Skype は、上には、Silverlight ビジネス サーバーのコントロール パネルの Skype を使用する前にバージョン 5 に Silverlight をアップグレードしてください。 
  
このトポロジには、従来と Skype ビジネス サーバー 2019 サーバーの役割です。 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>従来トポロジ ビルダーでトポロジを開くしようとしていません。
<a name="sectionSection2"> </a>

従来トポロジ ビルダーを使用してトポロジを表示しようとすると、次のエラーが発生します。 ビジネス サーバー 2019 のトポロジ ビルダーの Skype を使用してトポロジを表示のみできます。 ビジネス サーバー 2019 の Skype と従来のインストールの両方のプールを作成するには、ビジネス サーバー 2019 のトポロジ ビルダーの Skype を使用しなければなりません。

  

