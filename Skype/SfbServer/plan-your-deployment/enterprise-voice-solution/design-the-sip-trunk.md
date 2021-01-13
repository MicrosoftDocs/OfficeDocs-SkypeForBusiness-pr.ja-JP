---
title: Skype for Business Server で E9-1-1 の SIP トランクを設計する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Skype for Business Server エンタープライズ VoIP で、SIP トランキング プロバイダーを使用する E9-1-1 展開の SIP トランキング トポロジを計画します。
ms.openlocfilehash: ef30d721b59f29885004ee948055a91ca8af9490
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825797"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Skype for Business Server で E9-1-1 の SIP トランクを設計する
 
Skype for Business Server エンタープライズ VoIP で、SIP トランキング プロバイダーを使用する E9-1-1 展開の SIP トランキング トポロジを計画します。
  
Skype for Business Server は SIP トランクを使用して、緊急通話を E9-1-1 サービス プロバイダーに接続します。 E9-1-1 用の緊急サービス SIP トランクは、1 つのセントラル サイト、複数のセントラル サイト、または各ブランチ サイトにセットアップできます。 ただし、発信者のサイトと緊急サービス SIP トランクをホストするサイト間の WAN リンクが使用できない場合、切断されたサイトのユーザーが発信した通話には、ローカルの公衆交換電話網 (PSTN) ゲートウェイを介して ECRC に通話をルーティングする、ユーザーの音声ポリシー内の特別な電話使用法レコードが必要です。 通話受付管理で同時通話数制限が有効な場合も同様です。
  
Skype for Business Server 環境に SIP トランクを実装するには、次の 2 つの方法があります。
  
- SIP トランク プロバイダーと通信するには、外向きの公開ルーティング インターフェイスを使用するマルチホーム仲介サーバーを使用します。
    
- オンプレミスのセッション ボーダー コントローラー (SBC) を使用して、仲介サーバーと SIP トランク プロバイダーのサービス間に安全な境界ポイントを提供します。
    
後者の方法を選択した場合は、選択する SBC の型とモデルが認定済みであり、SIP INVITE の一部としてプレゼンス情報データ フォーマット位置オブジェクト (PIDF-LO) 場所データの通過がサポートされていることを確認します。 サポートされてない場合、緊急サービスのサービス プロバイダーに到着した通話から場所情報が除去されます。 認定 SPC の詳細については   [、「Infrastructure Qualified for Microsoft Lync」](https://go.microsoft.com/fwlink/p/?LinkId=248425) および [「Telephony Infrastructure for Skype for Business」](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)を参照してください。 
  
E9-1-1 サービス プロバイダーは、冗長性を確保するために SBC のペアへのアクセスを提供します。 仲介サーバーのトポロジと通話ルーティング構成に関して、いくつかの決定を行う必要があります。 たとえば、2 つの SBC を同等のピアとして扱い、SBC 間の通話にラウンドロビン ルーティングを使用するのか、または一方の SBC をプライマリ、もう一方をセカンダリとして指定するのかを決定します。
  
Skype for Business Server での SIP トランクの展開の詳細については、「Skype for Business Server での SIP トランキング」 [を参照してください](sip-trunking.md)。 E9-1-1 用 SIP トランクの展開方法を決定する際に次の質問が役立ちます。
  
 **SIP トランクの展開に、専用接続を使用するか、それとも共有のインターネット接続を使用するか。**
  
> 緊急電話は常につながることが重要です。専用線で接続すれば、ネットワーク上の他のトラフィックによって回線が専有されることがなくなり、サービス品質 (QoS) も実装できます。パブリック インターネット経由で緊急サービスのサービス プロバイダーに接続し、緊急電話の機密性を保証する必要がある場合は、IPsec 暗号化が必要です。 
    
 **E9-1-1 展開は障害許容度を目的として設計されていますか?**
  
> これは緊急時向けのソリューションなので、回復性が重要です。 プライマリおよびセカンダリの仲介サーバーと SIP トランクを障害許容の場所に展開します。 プライマリ仲介サーバーは、サポートしているユーザーに最も近い場所に展開し、フェールオーバー呼び出しを (地理的に異なる場所にある) セカンダリ仲介サーバーを経由してルーティングする方法をお試しください。 
    
 **ブランチ オフィスごとに個別に SIP トランクを展開するかどうか。**
  
> Skype for Business Server は、ブランチ オフィスでの音声の復元に対応するためのいくつかの戦略を提供します。たとえば、回復力のあるデータ ネットワークの確保、各ブランチでの SIP トランクの展開、停止時のローカル ゲートウェイへの通話のプッシュなどです。 詳細については、Skype for Business Server の [SIP トランキングを参照してください](sip-trunking.md)。
    
 **通話受付管理 (CAC) を有効にするかどうか。**
  
> Skype for Business Server は、通常の通話と異なる方法で緊急電話を処理しません。 そのため、帯域幅管理や通話受付管理 (CAC) が E9-1-1 の構成に悪影響を与える場合があります。 CAC が有効になっており、緊急電話がルーティングされているリンク上に構成された制限数を超過した場合は、緊急電話がブロックされたり、ローカル PSTN ゲートウェイにルーティングされたりします。 前述のように、このような通話には場所データが含まれていないので、ECRC に手動でルーティングする必要があります。
    

