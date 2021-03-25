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
ms.openlocfilehash: 8685b3263b9e3b6f98bc94e190ac9dd8207348df
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112693"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Skype for Business Server で E9-1-1 の SIP トランクを設計する
 
Skype for Business Server エンタープライズ VoIP で、SIP トランキング プロバイダーを使用する E9-1-1 展開の SIP トランキング トポロジを計画します。
  
Skype for Business Server では、SIP トランクを使用して緊急通話を E9-1-1 サービス プロバイダーに接続します。 E9-1-1 用の緊急サービス SIP トランクは、1 つのセントラル サイト、複数のセントラル サイト、または各ブランチ サイトにセットアップできます。 ただし、発信者のサイトと緊急サービス SIP トランクをホストするサイトとの間の WAN リンクが使用できない場合、切断されたサイトでユーザーが発信した通話には、ローカル公衆交換電話網 (PSTN) ゲートウェイを介して ECRC に通話をルーティングするユーザーの音声ポリシー内の特別な電話使用レコードが必要になります。 通話受付管理で同時通話数制限が有効な場合も同様です。
  
Skype for Business Server 環境で SIP トランクを実装するには、次の 2 つの方法があります。
  
- SIP トランク プロバイダーと通信するには、外部向きのパブリックルーティング インターフェイスを使用するマルチホーム仲介サーバーを使用します。
    
- オンプレミスのセッション ボーダー コントローラー (SBC) を使用して、仲介サーバーと SIP トランク プロバイダーのサービスとの間に安全な境界ポイントを提供します。
    
後者の方法を選択した場合は、選択する SBC の型とモデルが認定済みであり、SIP INVITE の一部としてプレゼンス情報データ フォーマット位置オブジェクト (PIDF-LO) 場所データの通過がサポートされていることを確認します。 サポートされてない場合、緊急サービスのサービス プロバイダーに到着した通話から場所情報が除去されます。 認定 SPC の詳細については   [、「Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) のインフラストラクチャ認定」および「Skype for Business のテレフォニー [インフラストラクチャ」を参照してください](../../../SfbPartnerCertification/certification/infra-gateways.md)。 
  
E9-1-1 サービス プロバイダーは、冗長性を確保するために SBC のペアへのアクセスを提供します。 仲介サーバーのトポロジと通話ルーティングの構成に関して、いくつかの決定を行う必要があります。 たとえば、2 つの SBC を同等のピアとして扱い、SBC 間の通話にラウンドロビン ルーティングを使用するのか、または一方の SBC をプライマリ、もう一方をセカンダリとして指定するのかを決定します。
  
Skype for Business Server での SIP トランクの展開の詳細については、「Skype for Business Server での [SIP トランキング」を参照してください](sip-trunking.md)。 E9-1-1 用 SIP トランクの展開方法を決定する際に次の質問が役立ちます。
  
 **SIP トランクの展開に、専用接続を使用するか、それとも共有のインターネット接続を使用するか。**
  
> 緊急電話は常につながることが重要です。専用線で接続すれば、ネットワーク上の他のトラフィックによって回線が専有されることがなくなり、サービス品質 (QoS) も実装できます。パブリック インターネット経由で緊急サービスのサービス プロバイダーに接続し、緊急電話の機密性を保証する必要がある場合は、IPsec 暗号化が必要です。 
    
 **E9-1-1 の展開は障害耐性を目的として設計されていますか?**
  
> これは緊急時向けのソリューションなので、回復性が重要です。 障害対応の場所にプライマリおよびセカンダリ仲介サーバーと SIP トランクを展開します。 プライマリ 仲介サーバーをサポートしているユーザーに最も近い場所に展開し、フェールオーバー 呼び出しをセカンダリ 仲介サーバー (別の地理的な場所にある) 経由でルーティングすると良い考えです。 
    
 **ブランチ オフィスごとに個別に SIP トランクを展開するかどうか。**
  
> Skype for Business Server には、回復力のあるデータ ネットワークの構築、各ブランチでの SIP トランクの展開、停止中のローカル ゲートウェイへの呼び出しのプッシュなど、ブランチ オフィスでの音声復元を処理するためのいくつかの戦略が用意されています。 詳細については、「Skype for Business Server での SIP ト [ランキング」を参照してください](sip-trunking.md)。
    
 **通話受付管理 (CAC) を有効にするかどうか。**
  
> Skype for Business Server は、通常の呼び出しとは異なる方法で緊急通話を処理しません。 そのため、帯域幅管理や通話受付管理 (CAC) が E9-1-1 の構成に悪影響を与える場合があります。 CAC が有効になっており、緊急電話がルーティングされているリンク上に構成された制限数を超過した場合は、緊急電話がブロックされたり、ローカル PSTN ゲートウェイにルーティングされたりします。 前述のように、このような通話には場所データが含まれていないので、ECRC に手動でルーティングする必要があります。
