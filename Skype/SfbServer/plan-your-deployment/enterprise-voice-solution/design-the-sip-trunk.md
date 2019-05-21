---
title: Skype for Business Server での E9-1 の SIP トランクの設計
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Skype for Business Server Enterprise Voice で SIP トランクプロバイダーを使用する E9 展開用の SIP トランクトポロジを計画します。
ms.openlocfilehash: 1d3b55fd6bb61fbf83f1a2294c96503b816f9c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276979"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Skype for Business Server での E9-1 の SIP トランクの設計
 
Skype for Business Server Enterprise Voice で SIP トランクプロバイダーを使用する E9 展開用の SIP トランクトポロジを計画します。
  
Skype for Business Server は、SIP trunks を使用して、緊急通話を E9 サービスプロバイダに接続します。 E9-1-1 用の緊急サービス SIP トランクは、1 つの中央サイト、複数の中央サイト、または各ブランチ サイトにセットアップできます。 ただし、発信者のサイトと緊急対応の SIP トランクをホストしているサイトとの間の WAN リンクが利用できない場合は、接続されていないサイトのユーザーによって発信される電話には、ユーザーの音声ポリシーに、通話をルーティングするための特別な電話の使用状況レコードが必要になります。[ローカル公衆交換電話網 (PSTN) ゲートウェイからの ECRC] を選びます。 通話受付管理で同時通話数制限が有効な場合も同様です。
  
Skype for Business Server 環境で SIP トランクを実装するには、次の2つの方法があります。
  
- 外部向けのパブリックルーティングインターフェイスを使用して、SIP トランクプロバイダーと通信するマルチホーム仲介サーバーを使います。
    
- オンプレミスセッションボーダーコントローラー (SBC) を使って、仲介サーバーと SIP トランクプロバイダーのサービス間に安全な境界点を指定します。
    
後者の方法を選択した場合は、選択する SBC の型とモデルが認定済みであり、SIP INVITE の一部としてプレゼンス情報データ フォーマット位置オブジェクト (PIDF-LO) 場所データの通過がサポートされていることを確認します。 サポートされてない場合、緊急サービスのサービス プロバイダーに到着した通話から場所情報が除去されます。 認定された SBCs の詳細については、「 [Microsoft Lync 用に認定](https://go.microsoft.com/fwlink/p/?LinkId=248425)されたインフラストラクチャ」および[「Skype For Business のテレフォニーインフラストラクチャ](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)」を参照してください。 
  
E9-1-1 サービス プロバイダーは、冗長性を確保するために SBC のペアへのアクセスを提供します。 仲介サーバートポロジと通話ルーティング構成について、いくつかの決定を行う必要があります。 たとえば、2 つの SBC を同等のピアとして扱い、SBC 間の通話にラウンドロビン ルーティングを使用するのか、または一方の SBC をプライマリ、もう一方をセカンダリとして指定するのかを決定します。
  
Skype for Business Server での SIP トランクの展開の詳細については、「 [skype For Business server の sip トランク](sip-trunking.md)」を参照してください。 E9-1-1 用 SIP トランクの展開方法を決定する際に次の質問が役立ちます。
  
 **SIP トランクの展開に、専用接続を使用するか、それとも共有のインターネット接続を使用するか。**
  
> 緊急電話は常につながることが重要です。専用線で接続すれば、ネットワーク上の他のトラフィックによって回線が専有されることがなくなり、サービス品質 (QoS) も実装できます。パブリック インターネット経由で緊急サービスのサービス プロバイダーに接続し、緊急電話の機密性を保証する必要がある場合は、IPsec 暗号化が必要です。 
    
 **E9 展開は、耐障害性のために設計されていますか?**
  
> これは緊急時向けのソリューションなので、回復性が重要です。 プライマリおよびセカンダリの仲介サーバーと SIP trunks を、ディザスタートレラントな場所に展開します。 サポート対象のユーザーに最も近いプライマリ仲介サーバーを展開し、セカンダリ仲介サーバー (別の地理的な場所にある) 経由でフェールオーバー通話をルーティングすることをお勧めします。 
    
 **ブランチ オフィスごとに個別に SIP トランクを展開するかどうか。**
  
> Skype for Business Server には、回復可能なデータネットワークが存在する場合、各ブランチに SIP トランクを展開する場合、または停止中にローカルゲートウェイへの呼び出しをプッシュする場合など、支店での音声回復性を処理するためのいくつかの戦略が用意されています。 詳細については、「 [Skype For Business Server の SIP トランキング](sip-trunking.md)」を参照してください。
    
 **通話受付管理 (CAC) を有効にするかどうか。**
  
> Skype for Business Server では、通常の通話とは異なる方法で緊急通話を処理することはできません。 そのため、帯域幅管理や通話受付管理 (CAC) が E9-1-1 の構成に悪影響を与える場合があります。 CAC が有効になっており、緊急電話がルーティングされているリンク上に構成された制限数を超過した場合は、緊急電話がブロックされたり、ローカル PSTN ゲートウェイにルーティングされたりします。 前述のように、このような通話には場所データが含まれていないので、ECRC に手動でルーティングする必要があります。
    

