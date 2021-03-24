---
title: メディアの品質とネットワーク接続性のパフォーマンス
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: このトピックでは、Skype for Business Online サービスのネットワーク パフォーマンス要件のセットと、ネットワーク接続の評価に基づいて、ネットワークと Skype for Business Online の間の接続にインターネットまたは ExpressRoute を使用する方法を選択する方法について説明します。 Microsoft 365 または Office 365 への専用接続用に Azure ExpressRoute を展開する場合は、このドキュメントでは、さまざまな Skype for Business Online 展開シナリオで ExpressRoute 接続を計画する方法のガイダンスも提供します。
ms.openlocfilehash: 4ac879c1e2e7b625a45f5d5f399d7438d038595f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100713"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス

このトピックでは、Skype for Business Online サービスのネットワーク パフォーマンス要件のセットと、ネットワーク接続の評価に基づいて、ネットワークと Skype for Business Online の間の接続にインターネットまたは ExpressRoute を使用する方法を選択する方法について説明します。 Microsoft 365 または Office 365 への専用接続用に Azure ExpressRoute を展開する場合は、このドキュメントでは、さまざまな Skype for Business Online 展開シナリオで ExpressRoute 接続を計画する方法のガイダンスも提供します。
  
IP 上Real-Timeメディア (オーディオ、ビデオ、アプリケーション共有) の品質は、エンドツーエンドネットワーク接続の品質に大きく影響されます。 Skype for Business Online メディアの最適な品質を得るために、会社のネットワークと Skype for Business Online 間の接続が高品質であることを確認することが重要です。 これを達成するためには、内部ネットワークとクラウド接続を、接続全体にわたって Skype for Business Online のピーク時のトラフィック量を処理するネットワークのキャパシティに基づいて設定することが最善の方法になります。
  
Azure ExpressRoute は、Skype for Business Online を含む Microsoft 365 Office 365 サービスの要件ではない。 ただし、Azure ExpressRoute は利用可能な展開オプションの 1 つであり、Microsoft 365 または Office 365 への接続が Skype for Business ネットワーク パフォーマンス要件を満たしていることを確認し、Skype for Business Online の最適なメディア品質エクスペリエンスを確保するのに役立ちます。
  
> [!TIP]
> このトピックでは、ネットワーク パフォーマンスの全体的なガイダンスを提供しますが、ネットワーク評価の完全なガイダンスは、このドキュメントの対象外です。 徹底的で完全なネットワーク評価の一環として、ネットワーク パフォーマンスの測定に役立つ Skype for Business Online パートナーのリストを見つけるには [、Skype for Business パートナー](http://partnersolutions.skypeforbusiness.com/)ソリューションを参照してください。 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Skype for Business Online へのネットワーク接続要件

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Skype for Business Online のメディア品質に影響する要因

Skype for Business Online Real-Time メディア (オーディオ、ビデオ、アプリケーション共有) の品質には、使用されるデバイス、環境、ネットワーク接続など、さまざまな要因があります。 
  
#### <a name="devices"></a>デバイス

Real-Time メディア セッションでは、ヘッドセットや Web カメラなど、すべての参加者が使用するメディアキャプチャデバイスとレンダリング デバイスは、オーディオとビデオの全体的な品質に大きな影響を与えます。 品質の低いデバイスや、デバイス ドライバが間違っているデバイスでは、全体的にオーディオの音質が下がり、ビデオの画質が下がります。 一方、認定デバイスまたは高品質なデバイスは、エコー キャンセル、ノイズ フィルタリング、ビデオ解像度、遅延低減に役立ちます。
  
認定されたオーディオ/ビデオ メディア デバイスは必要ありませんが、最適なメディアエクスペリエンスを実現するには Skype for Business の認定デバイスを強くお勧めします。 Skype for Business 認定デバイスの一覧については、「Skype for Business の電話と [デバイス」を参照してください](../../SfbPartnerCertification/certification/devices-ip-phones.md)。 **Skype for** [Business](/microsoftteams/turning-on-and-using-call-quality-dashboard)管理センターにある Skype for Business Online 通話品質ダッシュボードを使用して、使用されているデバイスが正しく動作し、オーディオとビデオのメディア品質を監視することができます。
  
> [!TIP]
> **最適な Skype for Business メディア品質エクスペリエンスを実現するには、認定デバイスが必要です**。
  
Real-Time メディアが流れるすべてのメディア デバイス、Skype for Business クライアント、Skype for Business サーバーでは、ある程度の遅延が発生する点に注意してください。 ネットワーク遅延と共に遅延を処理するデバイスとソフトウェアは、エンド 間の全体的な遅延とエンド ユーザーのエクスペリエンスに大きな影響を与え、影響を与えます。
  
#### <a name="environment"></a>環境

ユーザーが会議を行い、オーディオ デバイスとビデオ デバイスを使用する環境と周辺領域は、オーディオとビデオの品質のもう 1 つの要因です。ノイズのある環境から通話しているユーザーのオーディオは、エコーがかかり、こもっていて、不明瞭です。暗くて照明が不十分な環境にいるユーザーは、ビデオで明るくクリアな画質を実現することができません。会議室の設定で、マイクとビデオ デバイスの場所は、参加者が受信する音声と画像の品質に直接影響します。
  
ユーザーのオーディオとビデオのエクスペリエンスをより明確に表示するには、Skype for Business アプリの[ツール] の [オーディオ デバイス] または [ビデオ デバイス] を使用して、使用しているデバイスを変更し、設定をカスタマイズします。  >    >   

#### <a name="network"></a>ネットワーク

IP ネットワーク上の Real-Timeメディアの品質は、ネットワーク接続の品質 、特に次の数によって大きく影響されます。
  
- **待機時間** これは、ネットワーク上のポイント A からポイント B に IP パケットを取得するのにかかる時間です。 このネットワーク伝達遅延は、さまざまなルーターの間の追加のオーバーヘッドを含めて、2 つのポイントの間の物理的な距離と光速度に関連しています。 遅延は、一方通行またはラウンドトリップ時間 (RTT) として測定されます。
    
- **パケット損失** これは、多くの場合、特定の時間内に失われるパケットの割合として定義されます。 パケット損失は、オーディオの品質に直接影響を与えます。ほとんど影響を及ぼすことのない小規模のパケット損失から、音声が完全に途切れる原因となる連続したバースト損失まで存在します。
    
- **パケット間到着ジッターまたは単なるジッター** これは、連続するパケット間の遅延の平均変化です。 Skype for Business を含むほとんどの最新の VoIP ソフトウェアは、バッファリングを通じて一部のレベルのジッターに適応できます。 これは、参加者がジッターの影響に気付くほど、ジッターがバッファリングを超える場合に限定されます。
    
> [!NOTE]
>  ジッターのバッファー処理により、エンドツーエンドの遅延が増加します。
  
多くの同時 Skype for Business Online Real-Time メディア セッションと、他の Microsoft 365 または Office 365 サービスおよび他のビジネス アプリケーションによって生成されたその他のネットワーク トラフィックを使用して、ネットワークの混雑を回避し、優れたメディア Real-Time メディア (オーディオ、ビデオ、アプリケーション共有) の品質を確保するには、ネットワークを Skype for Business Online サービスに接続するネットワーク パス全体で十分な帯域幅を確保する必要があります。 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>混雑したネットワーク間でのサービス品質 (QoS) の実装

さらに、ネットワーク全体のトラフィックの混雑はメディアの品質に大きく影響します。 音声とビデオのパケットがネットワークを高速に移動し、混雑したネットワーク内の他のネットワーク トラフィックよりも優先順位を付けするには、サービスの品質 (QoS) を使用して、オーディオおよびビデオ通信に最適なエンド ユーザー エクスペリエンスを提供できます。
  
QoS は、音声またはビデオ データを運ぶネットワーク パケットに高い優先度を割り当てる方法を提供します。 これらのパケットに高い優先度を割り当てると、音声およびビデオ通信は、ファイル転送、Web ブラウズ、データベースのバックアップなどのネットワーク セッションよりも、ネットワーク上を高速かつ少ない中断で移動する可能性が高くなります。 これは、既定でファイル転送またはデータベースのバックアップに使用されるネットワーク パケットに優先度として "ベスト ベスト の労力" が割り当てられていないためであり、ネットワークの混雑には大きな影響はありません。 メディア (オーディオ、ビデオ、アプリケーション共有) パケットに高い優先度を割り当てずに、それらを "ベスト 労力" として割り当てたままにした場合、その他のすべてのネットワーク トラフィックと共に処理されます。 ネットワークの混雑の量によっては、最終的に全体的なオーディオとビデオの品質エクスペリエンスが低下する可能性があります。
  
ネットワーク内のネットワークの混雑が影響を受けずにいく場合は、ネットワークに QoS を実装することを強くお勧めします。 ただし、これが最大の影響を及ぼすには、すべてのネットワーク エンドポイントが QoS をサポートする必要があります。つまり、すべてのエンドポイントが QoS マーキングとパケット優先順位付けを尊重する必要があります。 Skype for Business Online サービスは、Microsoft ネットワーク内での QoS マーキングと優先順位付けに対応します。 ただし、会社のネットワークから Microsoft ネットワークにインターネットのようなパブリック接続を通してルーティングされるトラフィックでは、QoS マーキングやパケット優先順位付けは保持されません。 [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)を使用したネットワークから Microsoft 365 または Office 365 へのプライベート接続は、QoS マーキングとパケット優先順位付けを保持する展開ソリューションを提供し、エンド ユーザーの全体的なオーディオとビデオの品質を向上します。
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Skype for Business Online に接続するためのネットワーク パフォーマンス要件
<a name="bkNetworkPerf"> </a>

Skype for Business Real-Timeメディアは、さまざまなデバイス、クライアント アプリ、サーバー ソフトウェア、さまざまなネットワークを通過します。 メディアのエンド Real-Timeは、すべてのコンポーネントとネットワーク セグメントで発生する遅延の合計量です。 エンドツーエンド ネットワーク接続の品質は、品質が最も悪いネットワーク セグメントによって決まります。 このセグメントは、このネットワーク トラフィックのボトルネックとして機能します。
  
次の図は、Skype for Business の 1 人の参加者から別の参加者への電話会議での一方向の音声フローを示しています。
  
![ExpressRoute コール フロー。](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
この会議シナリオでは、メディア パスは次のネットワーク セグメントで構成されます。
  
1. **ユーザー 1 から Microsoft ネットワークのエッジへの接続** これには通常、WiFi やイーサネットなどのネットワーク接続、ユーザー 1 からインターネット出口ポイント (ネットワーク エッジ デバイス) への WAN 接続、ネットワーク エッジから Microsoft ネットワーク エッジへのインターネット接続が含まれます。
    
2. **Microsoft ネットワーク内の接続** これは、Microsoft Edge から Skype for Business Online データ センターの間で、A/V 会議サーバーが使用されます。
    
3. **Microsoft Network 内の接続** これは、Skype for Business Online データ センターと Microsoft ネットワーク エッジの間にあります。
    
4. **Microsoft ネットワーク エッジからユーザー 2 への接続** これには、ネットワーク エッジから Microsoft ネットワーク エッジへのインターネット接続、ユーザー 2 からインターネット出口ポイント (ネットワーク エッジ) への WAN 接続、WiFi やイーサネットなどのネットワーク接続が含まれます。
    
次の図は、Skype for Business Online PSTN 通話のコンポーネントとネットワーク セグメントの内訳を示しています。
  
![ExpressRoute PSTN Carrier Call Flow。](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
PSTN 通話のシナリオでは、メディア パスは次のネットワーク セグメントと交差します。
  
1. **Skype for Business クライアントの呼び出し元から Microsoft ネットワークの端への接続** これには通常、WiFi やイーサネットなどのネットワーク接続、Skype for Business クライアントの呼び出し元からインターネット出口ポイント (ネットワーク エッジ デバイス) への WAN 接続、ネットワーク エッジから Microsoft ネットワーク エッジへのインターネット接続が含まれます。
    
2. **Microsoft ネットワーク内の接続** これは、Microsoft Edge から Skype for Business Online データ センターの間で、仲介サーバーが使用されます。
    
3. **Microsoft Network 内の接続** これは、Skype for Business Online データ センターと Microsoft ネットワーク エッジの間にあります。
    
4. **Microsoft ネットワークと PSTN サービス プロバイダー パートナー間の接続** これは、Microsoft ネットワークの外部にある Skype for Business クライアントから PSTN 通話を発信するために存在する接続です。
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Skype for Business クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件
<a name="bkSfBClienttoEdge"></a>

Skype for Business のメディア品質を最適化するには、会社のネットワークから Microsoft ネットワーク エッジへの接続に対して、次のネットワーク パフォーマンス指標のターゲットまたはしきい値が必要です。 ネットワークのこのセグメントには内部ネットワークが含まれます。これには、すべての WiFi およびイーサネット接続、WAN 接続を経由する会社のサイト間トラフィック (Multiprotocol Label Switching (MPLS) など) と、Microsoft ネットワーク エッジへのインターネットまたは ExpressRoute パートナー接続が含まれます。
  
> [!CAUTION]
> **会社のネットワーク上の Skype for Business クライアントから Microsoft 365 または Office 365 サービスへの接続は、以下のネットワーク パフォーマンス要件としきい値を満たしている必要があります。**
  
|||
|:-----|:-----|
|**測定基準** <br/> |**Target** <br/> |
|遅延 (一方向)  <br/> |< 50 ミリ秒  <br/> |
|遅延 (RTT または往復時間)  <br/> |< 100 ミリ秒  <br/> |
|バースト パケット損失  <br/> |< 任意の 200 ミリ秒間隔で 10%  <br/> |
|パケット損失  <br/> |< 任意の 15 秒間隔で 1%  <br/> |
|パケット到着間ジッター  <br/> |< 15 秒間隔で 30 ミリ秒  <br/> |
|パケットの並べ替え  <br/> |< 順序が適切でないパケットが 0.05%  <br/> |
   
 **その他のパフォーマンス ターゲット要件:**
  
- Microsoft ネットワークには、世界中に 160 を超える Edge の場所があります。 これらのエッジ サイトを通じて、世界中の主要なインターネット サービス プロバイダー (ISP) と取り組んでいます。 遅延メトリック ターゲットは、会社のサイトと Microsoft Edges が同じ大陸上にあることを前提とします。
    
- 会社のサイトまたは Microsoft ネットワーク エッジ接続へのサイトには、最初のホップ ネットワーク アクセス (WiFi または別のワイヤレス テクノロジ) が含まれます。 
    
- ネットワーク パフォーマンス ターゲットは、適切な帯域幅やサービスの品質の計画を前提とします。 つまり、ネットワーク接続がピーク時の負荷の下にある場合Real-Timeメディア トラフィックの Skype for Business に直接適用されます。
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>ネットワーク エッジから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件
<a name="bkYourNetworkEdge"> </a>

ネットワーク エッジと Microsoft ネットワーク エッジ間の接続に必要なネットワーク パフォーマンス ターゲットまたはしきい値を次に示します。 ネットワークのこのセグメントは、お客様の内部ネットワークまたは WAN を除外し、インターネットまたは ExpressRoute パートナー ネットワーク経由で送信されるネットワーク トラフィックをテストする際のガイダンスとして使用され、ExpressRoute プロバイダーとパフォーマンス サービス レベルアグリーメント (SLA) を交渉する際にも使用できます。
  
> [!CAUTION]
> **会社のネットワーク エッジから Microsoft ネットワーク エッジへの接続は、以下のネットワーク パフォーマンス要件としきい値を満たしている必要があります。**
  
|||
|:-----|:-----|
|**測定基準** <br/> |**Target** <br/> |
|遅延 (一方向)  <br/> |< 30 ミリ秒  <br/> |
|遅延 (RTT)  <br/> |< 60 ミリ秒  <br/> |
|バースト パケット損失  <br/> |<200 ミリ秒間隔で 1% を計算する  <br/> |
|パケット損失  <br/> |< 任意の 15 秒間隔で 0.1%  <br/> |
|パケット到着間ジッター  <br/> |< 任意の 15 秒間隔で 15 ミリ秒  <br/> |
|パケットの並べ替え  <br/> |< 順序が適切でないパケットが 0.01%  <br/> |
   
 **その他のパフォーマンス ターゲット要件:**
  
- パフォーマンス ターゲットを使用するには、会社のネットワーク エッジと最も近い Microsoft ネットワーク エッジの間の接続が同じ大陸上に必要です。
    
- ネットワーク パフォーマンス ターゲットは、適切な帯域幅やサービスの品質の計画を前提とします。 これは、ネットワーク接続の負荷がピークに達Real-Time、Skype for Business メディア トラフィックにも適用されます。 適切な帯域幅と QoS 計画については、Skype for Business Online の ExpressRoute と [QoS を参照してください](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)。
    
## <a name="measuring-network-performance"></a>ネットワーク パフォーマンスの測定
<a name="bkNetworkPerf"> </a>

会社のネットワーク サイトからネットワーク エッジへの実際のネットワーク パフォーマンス (特に遅延やパケット損失) を測定するには、Ping などのツールを使用して、Microsoft Edge とデータ センター サイトから実行されている一連の Skype for Business メディア リレー サービスに対してテストできます。 

>[!NOTE]
> ping (ICMP) によるネットワーク パフォーマンスの測定は有効ではありません。 このため、以下で公開される anycast IP は、2020 年 1 月から ICMP 要求への応答を停止します。 ネットワークのパフォーマンスを効果的に測定するために、Microsoft は [Network Assesment Tool を推奨します](https://www.microsoft.com/download/details.aspx?id=53885)。
  
Microsoft ネットワークへのインターネット接続をテストする場合は、Skype for Business メディア リレーの次の VIP に対してテストをお勧めします。 *Anycast VIP* は、テストの場所に最も近い Microsoft ネットワーク エッジ サイト内のメディア リレーの IP アドレスに解決されます。
  
||||
|:-----|:-----|:-----|
|**IP アドレス** <br/> |**Type** <br/> |**場所** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide Anycast IP  <br/> |
   
 **ここでは、ネットワーク パフォーマンスを評価するために従う必要がある、いくつかの高レベルの推奨事項を示します。**
  
- 内部ネットワークと、Microsoft 365 または Office 365 への接続を評価する必要があります。
    
- すべてのネットワークのデータを長時間評価して収集する必要があります。 すべての営業日と時間の使用パターンを確認するために、ネットワーク パフォーマンスのテストを最低 1 週間実行することをお勧めします。 これにより、ピーク時間が表示されます。
    
- ネットワーク パフォーマンス測定の複数のサンプルを取る必要があります。 データを収集している期間全体を通して、会社のサイトから 10 分ごとに測定することをお勧めします。 Skype for Business Online のネットワーク パフォーマンス要件を比較するには、このサンプル データ セットから 90 パーセント目の測定値を取得します。 
    
- ネットワークのパフォーマンスを継続的に評価する必要があります。 ネットワーク使用率は、使用パターンの変更、大量の帯域幅を使用する新しいエンタープライズ ベースのアプリケーション、組織または物理的な会社の場所の変更により、時間の長い間変化します。 これらのネットワーク パフォーマンス要件とターゲット/しきい値に対してネットワーク パフォーマンスを継続的に監視し、適時に調整を行い、最適なメディア品質をReal-Timeすることが重要です。 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Azure VM を使用したネットワーク パフォーマンスの測定
<a name="bkNetworkPerf"> </a>

Microsoft ネットワーク エッジ サイトに対してテストする代わりに、Microsoft Azure クラウドのサービスのテストセットアップを活用する Skype for Business のお客様やパートナーからのネットワーク評価ソリューションがあります。 これらのソリューションでは、ネットワーク評価ツールは、Azure クラウドでサービスとして設定されたカスタム エンドポイントに対して遅延、パケット損失、ジッターをテストします。 その結果、テスト ネットワーク トラフィックは、ネットワーク エッジとネットワーク評価サービスをホストする Azure データ センター間の Microsoft ネットワーク内の接続である、1 つの追加のネットワーク セグメントを通過します。
  
Azure でホストされるテスト サービスに基づくネットワーク評価ソリューションの場合。 国または地域内でネットワーク評価を実行することをお勧めします。 たとえば、米国東部の顧客サイトの場合、評価は、Azure の米国東部のデータ センター地域でホストされているテスト サービス インスタンスに対して実行する必要があります。 
  
Azure サービスベースのネットワーク評価セットアップの遅延 (RTT) ターゲットを以下に示します。 一方通行の遅延ターゲットは、対応する RTT ターゲットの半分です。 パケット損失とジッターの目標は、Skype Media Relay ベースのテストで定義されている目標と同じままです。
  
|||||
|:-----|:-----|:-----|:-----|
|**顧客地域** <br/> |**Azure 地域** <br/> |**ネットワーク エッジ - Azure ラウンドトリップ時間 (RTT)** <br/> |**サイト - Azure ラウンドトリップ時間 (RTT)** <br/> |
|米国中  <br/> |米国中  <br/> |99  <br/> |139  <br/> |
|米国東部  <br/> |米国東部  <br/> |86  <br/> |126  <br/> |
|米国中北部  <br/> |米国中北部  <br/> |97  <br/> |137  <br/> |
|米国中南部  <br/> |米国中南部  <br/> |94  <br/> |134  <br/> |
|米国西部  <br/> |米国西部  <br/> |94  <br/> |134  <br/> |
|米国ハワイ  <br/> |米国西部  <br/> |116  <br/> |156  <br/> |
|カナダ中央  <br/> |カナダ中央  <br/> |138  <br/> |178  <br/> |
|カナダ東部  <br/> |カナダ東部  <br/> |131  <br/> |171  <br/> |
|北ヨーロッパ  <br/> |北ヨーロッパ  <br/> |99  <br/> |139  <br/> |
|西ヨーロッパ  <br/> |西ヨーロッパ  <br/> |95  <br/> |135  <br/> |
|東アジア  <br/> |東アジア  <br/> |118  <br/> |158  <br/> |
|東南アジア  <br/> |東南アジア  <br/> |97  <br/> |137  <br/> |
|日本東部  <br/> |日本東部  <br/> |111  <br/> |151  <br/> |
|日本西部  <br/> |日本西部  <br/> |118  <br/> |158  <br/> |
|ブラジル南部  <br/> |ブラジル南部  <br/> |70  <br/> |110  <br/> |
|オーストラリア東部  <br/> |オーストラリア東部  <br/> |124  <br/> |164  <br/> |
|オーストラリア南東部  <br/> |オーストラリア南東部  <br/> |124  <br/> |164  <br/> |
|インド中部  <br/> |インド中部  <br/> |103  <br/> |143  <br/> |
|インド南部  <br/> |インド南部  <br/> |103  <br/> |143  <br/> |
|インド西部  <br/> |インド西部  <br/> |103  <br/> |143  <br/> |
|中国東部  <br/> |中国東部  <br/> |120  <br/> |160  <br/> |
|中国北部  <br/> |中国北部  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>メディア品質と ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute for Microsoft 365 または Office 365 は、Microsoft 365 または Office 365 に接続するための専用のネットワーク接続です。 ネットワーク トラフィックが受け取るパスを制御する機能がユーザーに提供されます。 不明なキャリア、プロバイダー、ISP によってデータが運び出されるインターネット上で発生する予測不能なルーティングについて心配する必要はなくなりました。 ExpressRoute を介して送信されるネットワーク トラフィックは、ExpressRoute パートナーのネットワークを介して Microsoft のネットワークに直接送信されます。 これにより、お客様は Microsoft 365 または Office 365 を専用の接続で独自のオフサイト データ センターにあるかのように扱えます。
  
Azure ExpressRoute は、すべての Microsoft 365 および Office 365 ライセンス製品で利用できます。 ただし、グローバル ルーティングを有効にするには、Microsoft 365 および Office 365 に Azure ExpressRoute Premium アドオンが必要です。 ExpressRoute を実装しているシート数が 500 以上のお客様は、必要な *ExpressRoute Premium アドオン* を追加料金で利用できます。
  
### <a name="is-expressroute-required-for-good-media-quality"></a>メディア品質を向上するために ExpressRoute は必要ですか?

Azure ExpressRoute は、Skype for Business Online の最適なメディア品質を取得するための要件ではありません。 ただし、クラウド接続が Skype for Business ネットワーク パフォーマンス ターゲットまたはしきい値を満たした場合に役立つ展開オプションの 1 つになります。
  
Microsoft 365 と Office 365 は、インターネットを使用する高パフォーマンスでセキュリティで保護されたサービスです。 セキュリティとパフォーマンスを継続的に改善するために、新しいセキュリティ機能と地域のエッジ ノードに引き続き投資しています。 Azure ExpressRoute は、Skype for Business Online を含む Microsoft 365 Office 365 サービスの要件ではない。 Azure ExpressRoute は利用可能な展開オプションの 1 つであり、Microsoft 365 または Office 365 への接続が Skype for Business ネットワーク パフォーマンス要件を満たしていることを確認し、Skype for Business Online の最適なメディア品質エクスペリエンスを確保するのに役立ちます。
  
Skype for Business Online メディア品質の場合、会社のサイトと Microsoft ネットワーク エッジ間の接続が [、Skype for Business](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件のパフォーマンス ターゲットを満たしていることを重要です。また、ネットワーク エッジと Microsoft ネットワーク エッジ間の接続が、ネットワーク エッジから Microsoft ネットワーク [エッジ](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)へのネットワーク パフォーマンス要件のパフォーマンス ターゲットを満たしていることを重要です。  
  
また、内部ネットワークやクラウド接続容量を含む会社の物理的なネットワーク接続が、ピーク時のメディア トラフィック量に対応することが重要です。 Azure ExpressRoute は、Skype for Business Online クラウド接続がこれらのパフォーマンス要件を満たしていることを確認するのに役立つさまざまな方法の 1 つです。
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>音声品質 SLA には ExpressRoute は必要ですか?

いいえ、Skype for Business Online の音声品質 SLA には ExpressRoute は必要ありません。 [Skype for Business Online 音声](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)品質 SLA は、ユーザーが任意の種類の VoIP または PSTN 通話を行う正しいライセンスとサブスクリプション内で Skype for Business Online 音声サービス ユーザーが発信した対象通話に適用されます。 音声品質 SLA には、次のすべての条件に対処する必要があります。
  
- Microsoft 認定 IP 電話からの通話。
    
- 有線イーサネット接続。
    
- Microsoft ネットワークの問題による音声品質の問題。
    
> [!NOTE]
> 音声品質 SLA は、ExpressRoute パートナーや他のネットワークを含む Microsoft 以外のネットワークの問題によって低い通話品質が発生する通話を除外します。 
  
### <a name="internet-or-azure-expressroute"></a>インターネットまたは Azure ExpressRoute の場合

Skype for Business Online へのネットワーク接続オプションを決定する前に、Skype [for Business Online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)に接続するためのネットワーク パフォーマンス要件で説明されているネットワーク パフォーマンス要件に基づいて、ネットワークと現在のインターネット接続を評価する必要があります。
  
現在のインターネット接続経由のネットワーク パフォーマンスがピーク時に十分な容量で設定され、サイトから Microsoft ネットワーク エッジ、ネットワーク エッジから Microsoft ネットワーク エッジまでのネットワーク パフォーマンス要件を満たしている場合は、引き続き既存のインターネット接続を使用して Skype for Business Online に接続できます。
  
ネットワーク パフォーマンス要件が満たされない会社サイトの場合は、まず既存のネットワーク サービス プロバイダーと一緒に作業して、全体的なネットワーク パフォーマンスを向上することを強く推奨します。 ただし、それでも満たされない場合は、Azure ExpressRoute を使用すると、Skype for Business Online クラウド接続がネットワーク パフォーマンス要件を満たすのに役立ちます。
  
Azure ExpressRoute には、次のような追加の利点があります。
  
- ネットワークと Microsoft ネットワーク間の接続の可用性に関するサービス レベルアグリーメント (SLA)。 ExpressRoute では、99.9% の可用性 SLA が保証されています。
    
- Microsoft 365 および Office 365 サービスに必要な帯域幅の計画と保証。 これを実現するには、ExpressRoute を使用して Microsoft 365、Office 365、または Skype for Business トラフィックのみを送信し、その他すべてのインターネット トラフィックがネットワークの他のインターネット出口/出口ポイントを通過します。
    
- ExpressRoute は、ネットワークと Microsoft ネットワーク間の DSCP QoS マーキングを保持するように設計されています。
    
ExpressRoute QoS と容量計画の詳細については、Skype for Business Online の ExpressRoute と [QoS を参照してください](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)。
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Skype for Business Online 専用の Azure ExpressRoute をセットアップできますか?

はい、会社のネットワークから Skype for Business Online にのみ優れたネットワーク接続を確保するように Azure ExpressRoute を設定できます。 これにより、ユーザーに最適な Real-Time メディア品質が提供されますが、引き続きインターネットを通して他の Microsoft 365 または Office 365 サービスに接続できます。
  
ボーダー ゲートウェイ プロトコル (BGP) は、インターネット上のネットワーク トラフィックをルーティングするために使用される、インターネット上のルーティング プロトコルです。 これは、インターネット全体で検出されたルーティング システム (AS) 間でルーティング情報を交換するように設計されています。 BGP コミュニティの値は、着信ルートまたは送信ルートに適用できる属性タグです。 BGP コミュニティは多くの場合、地理、サービスの種類、その他の条件に基づいて、特定の宛先に到達するために使用する送信リンクを受信 AS に通知するために使用されます。
  
BGP コミュニティのサポートにより、Microsoft はプレフィックスとルーティングに、所属するサービスに基づいて適切な BGP コミュニティ値でタグ付けします。 Microsoft は、パブリック ピアリングと Microsoft ピアリングを通じてアドバタイズされるプレフィックスに、プレフィックスがホストされている領域を示す適切な BGP コミュニティ値でタグ付けします。 最適なルーティングを提供するには、コミュニティの値を使用して適切なルーティングの決定を行います。 Skype for Business Online BGP コミュニティ値を使用して、Skype for Business Online の ExpressRoute 接続のみをセットアップできます。 詳細については [、ExpressRoute ルーティング要件を参照してください](/azure/expressroute/expressroute-routing)。
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Skype for Business Online の ExpressRoute 接続シナリオ
<a name="bkNetworkPerf"> </a>

上記の推奨事項に基づいて ExpressRoute を使用することを決定した場合は、取得する必要がある ExpressRoute 接続の場所と数に関する推奨事項を以下に示します。
  
### <a name="online-only-deployment---single-site"></a>オンライン専用展開 - 1 つのサイト

すべてのユーザーが Skype for Business Online サービスを使用し、オフィスが 1 つの物理的な場所を中心に配置されている場合、Azure ExpressRoute を展開する場合は、会社のサイト間の 1 つの ExpressRoute 接続を最も近い [ExpressRoute](/azure/expressroute/expressroute-locations)ピアリングの場所に設定する必要があります。
  
次の図は、この種類の展開の例を示しています。 この例では、Contoso は FL 州インランドに位置する大学です。 Contoso には 10,000 人の教職員と学生がいます。 その場所から Microsoft エッジ サイトへのインターネット テストでは、クラスのピーク時にパケット損失が 5% を超えました。 特に Skype for Business Online Real-Time トラフィックの Microsoft 365 または Office 365 のネットワーク混雑を回避するために、帯域幅が過剰にプロビジョニングされた ExpressRoute を使用して、Microsoft 365 または Office 365 への専用接続を取得することを決定しました。 アトランタ、GA MeetMe サイトの ExpressRoute を介して Microsoft クラウドに接続します。
  
![ExpressRoute の単一サイト。](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>オンラインのみ展開 - 同じ大陸上の複数のサイト

会社が同じ地域または大陸にある複数のオフィスの Skype for Business Online サービスを使用している場合、Azure ExpressRoute を実装することを選択した場合は、メイン サイトを ExpressRoute 経由で接続し、必要に応じて、推奨されるネットワーク パフォーマンス ターゲットを満たしていない他の場所に ExpressRoute ピアリングを追加することを推奨します。
  
次の例では、Contoso は、本社はニューヨークにあるが、米国内に他のオフィスがある米国の旅行サービス会社です。 オフィスは、MPLS を使用して Microsoft 365 または Office 365 に接続する WAN を介して相互に接続されます。 最初に、ニュージャージー州ホーボーケンにあるインターネット ルーターからニューヨーク MeetMe サイトへの ExpressRoute 接続をセットアップしました。 
  
このセットアップにより、ほとんどのサイトから Microsoft ネットワーク (ニューヨーク エッジ サイト) へのネットワーク トラフィックは [、Skype for Business](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件で説明されている Skype for Business クライアント接続ネットワーク パフォーマンス ターゲットを満たします。 ただし、Contoso の西海岸のオフィスからニューヨークへの間の遅延は、一方通行で 50ms を超える遅延です。 また、ホノルルは Contoso の 2 番目に大きなオフィスで、ホノルルからニューヨークへの遅延は一方通行で 80ms を超える。 これらのオフィスのユーザーに優れたメディア品質を確保するために、Contoso は、San Valley サイトと Silicon Valley ExpressRoute MeetMe サイトの間に西海岸の ExpressRoute 接続を追加することを決定しました。
  
![同じ大陸上の Express Router Multi-site。](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>オンラインのみ展開 - 異なる大陸上の複数のサイト

すべてのユーザーが Skype for Business Online サービスを使用している場合、オフィスが複数の大陸にわたって複数の物理的な場所にある場合、Azure ExpressRoute を展開する場合は、各大陸のメイン サイトから最も近い ExpressRoute ピアリング場所までの大陸ごとに少なくとも 1 つの [ExpressRoute](/azure/expressroute/expressroute-locations)接続を設定する必要があります。 コストとメリットに応じて、ネットワーク パフォーマンス ターゲットが満たされないサイトから追加の ExpressRoute 接続を展開することができます。
  
次の例では、Contoso は、北米とヨーロッパの主要都市にオフィスを持つ大企業の法律事務所です。 Contoso は、インターネット接続と内部ネットワーク パフォーマンス評価に基づいて、北米に 2 つの ExpressRoute 接続を展開し、ヨーロッパのすべてのオフィスに 1 つの ExpressRoute 回線を展開することを決定しました。
  
![複数のサイトと大陸を含む ExpressRoute。](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>ハイブリッド展開

オンプレミスの Lync または Skype for Business の展開を使用し、ハイブリッドの Skype for Business Online 統合を実装する場合は、Azure ExpressRoute を展開する場合は、オンプレミスの Lync または Skype for Business Edge サイトごとに少なくとも 1 つの ExpressRoute 接続と、オフィスがある大陸ごとに少なくとも 1 つの ExpressRoute 接続が必要です。 コストとメリットに応じて、大陸ごとに、ネットワーク パフォーマンス ターゲットが満たされていないオフィスから追加の ExpressRoute 接続を展開することができます。
  
オンプレミスの Skype for Business 展開がある場合は、エッジ サーバーの計画と展開ガイド [に従う必要があります](../../SfbServer/plan-your-deployment/edge-server-deployments/edge-server-deployments.md)。 特に、エッジ サーバーはネットワークの外部からアクセスできる必要があります。 これは通常、Routable パブリック IP アドレスをエッジ サーバーに割り当てるか、ネットワーク アドレス変換 (NAT) を使用して行います。
  
次の例では、Contoso には既存のオンプレミスの Skype for Business エンタープライズ VoIPがあります。 オンプレミス ユーザーを Microsoft 365 または Office 365 オンライン サービスに移行する必要がある。 また、すべてのオンプレミスユーザーとオンライン ユーザーに既存の PSTN インフラストラクチャを引き続き使用できるよう、ハイブリッド展開を使用することを決定しました。 Contoso のオンプレミス データ センターと Skype for Business エッジ サーバーはシカゴにあります。 展開のために、Contoso はシカゴのデータ センターとシカゴ ExpressRoute との間に 1 つの ExpressRoute 接続を設定することを決定しました。 また、ホノルル オフィスのサービスを向上するために、西海岸の ExpressRoute 接続も追加しました。
  
![ExpressRoute ハイブリッド。](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Cloud Connector Edition を使用したオンライン展開

Skype for Business Online Cloud Connector Edition は、オンプレミスの PSTN 接続を実装する一連のパッケージ化された仮想マシン (VM) で構成されるハイブリッド製品です。 仮想化された環境に最低限の Skype for Business Server トポロジを展開すると、既存のオンプレミス PSTN 音声インフラストラクチャを介して固定電話と携帯電話で通話を送受信できます。
  
Azure ExpressRoute と Cloud Connector Edition を展開する場合は、各大陸のメイン サイトから最も近い [ExpressRoute](/azure/expressroute/expressroute-locations)ピアリング場所までの大陸ごとに少なくとも 1 つの Express Route 接続を設定することをお勧めします。 コストとメリットに応じて、大陸ごとに、ネットワーク パフォーマンス ターゲットが満たされていないサイトから追加の ExpressRoute 接続を展開することができます。
  
オンプレミスの Skype for Business 展開がある場合は、Skype for Business Cloud Connector エディションの計画 [ガイドに従う必要があります](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md)。 具体的には、Access Edge サービスと A/V Edge サービスには、パブリック IP アドレスが割り当て、Microsoft 365 または Office 365 データ センターにアクセスできる必要があります。
  
次の例では、Contoso はヨーロッパのいくつかの主要な国と都市にプレゼンスを持つヨーロッパの会計事務所です。 すべての共同作業のニーズに合って Skype for Business Online にサインアップする際に、物理的な場所を持つ国ごとに Cloud Connector を導入し、PSTN インフラストラクチャと既に存在するキャリア契約を引き続き使用することを決定しました。 すべてのサイトと Microsoft ネットワーク エッジからのテストに基づいて、ロンドンの 1 つの ExpressRoute 接続が [、Skype for Business](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件で説明されている Skype for Business クライアント接続ネットワーク パフォーマンス ターゲットを満たすのに役立つと判断しました。
  
![ExpressRoute Cloud Connector One。](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
次に、Contoso の別の展開オプションを示します。 このケースでは、Cloud Connector が展開されている各サイトで ExpressRoute 接続を設定することを決定しました。 
  
![ExpressRoute Cloud Connector 2。](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>関連項目

[Skype for Business Online の ExpressRoute および QoS](expressroute-and-qos-in-skype-for-business-online.md)

  
