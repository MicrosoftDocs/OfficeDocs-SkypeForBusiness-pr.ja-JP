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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: このトピックでは、Microsoft Teams サービスのネットワーク パフォーマンス要件のセットと、ネットワーク接続の評価に基づいて、ネットワークと Microsoft Teams の間の接続にインターネットまたは ExpressRoute を使用する方法について説明します。 Microsoft 365 または Office 365 への専用接続用に Azure ExpressRoute をデプロイすることを決定した場合、このドキュメントでは、さまざまな Microsoft Teams デプロイ シナリオで ExpressRoute 接続を計画する方法に関するガイダンスも提供します。
ms.openlocfilehash: 3699e225f69deda5fd69b2308dc50337a1d0b228
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618243"
---
# <a name="media-quality-and-network-connectivity-performance-in-microsoft-teams"></a>メディア品質とネットワーク接続のパフォーマンス (Microsoft Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

このトピックでは、Microsoft Teams サービスのネットワーク パフォーマンス要件のセットと、ネットワーク接続の評価に基づいて、ネットワークと Microsoft Teams の間の接続にインターネットまたは ExpressRoute を使用する方法について説明します。 Microsoft 365 または Office 365 への専用接続用に Azure ExpressRoute をデプロイすることを決定した場合、このドキュメントでは、さまざまな Microsoft Teams デプロイ シナリオで ExpressRoute 接続を計画する方法に関するガイダンスも提供します。
  
IP を使用Real-Timeメディア (オーディオ、ビデオ、アプリケーション共有) の品質は、エンドツーエンドネットワーク接続の品質の影響を大きく受け取っています。 最適なMicrosoft Teamsメディア品質を実現するには、会社のネットワークとネットワークの間に高品質の接続が確立Microsoft Teams。 これを実現する最善の方法は、ネットワークの容量に基づいて内部ネットワークとクラウド接続を設定し、すべての接続で Microsoft Teams のピーク トラフィック量に対応する方法です。
  
Azure ExpressRoute は、サービスを含むMicrosoft 365サービスOffice 365要件Microsoft Teams。 ただし、Azure ExpressRoute は、Microsoft 365 または Office 365 への接続が Microsoft Teams ネットワーク パフォーマンス要件を満たしていることを確認し、Microsoft Teams メディア品質エクスペリエンスを最適にするためのデプロイ オプションの 1 つです。
  
> [!TIP]
> このトピックでは全体的なネットワーク パフォーマンス ガイダンスを提供しますが、ネットワーク評価の完全なガイダンスは、このドキュメントの範囲を外しています。 完全なネットワーク評価の一環Microsoft Teamsネットワーク パフォーマンス測定を支援するパートナーの一覧については、パートナー ソリューションに関するページをSkype for Business[してください](http://partnersolutions.skypeforbusiness.com/)。 
  
## <a name="network-connectivity-requirements-to-microsoft-teams"></a>ネットワーク接続の要件をMicrosoft Teams

### <a name="factors-that-impact-microsoft-teams-media-quality"></a>メディア品質に影響Microsoft Teams要因

使用されるデバイス、環境、ネットワーク接続を含む Microsoft Teams Real-Time メディア (オーディオ、ビデオ、アプリケーション共有) の品質に影響するさまざまな要因があります。 
  
#### <a name="devices"></a>デバイス

Real-Time メディア セッションでは、ヘッドセットや Web カメラなどのすべての参加者が使用するメディア キャプチャおよびレンダリング デバイスは、オーディオとビデオの全体的な品質に大きな影響を与えます。 品質の低いデバイスや、デバイス ドライバが間違っているデバイスでは、全体的にオーディオの音質が下がり、ビデオの画質が下がります。 認定デバイスまたは高品質デバイスは、エコーキャンセル、ノイズ フィルタリング、ビデオ解像度、待機時間の短縮に役立ちます。
  
認定されたオーディオ およびビデオ メディア デバイスは必要ありませんが、最適なメディア エクスペリエンスを実現するために、Microsoft Teams認定デバイスを強くお勧めします。 認定デバイスの一覧については、「Microsoft Teamsとデバイス」[を参照Skype for Business。](../../SfbPartnerCertification/certification/devices-ip-phones.md) Microsoft Teams **Skype for Business** 管理センター [にある](/microsoftteams/turning-on-and-using-call-quality-dashboard)[通話品質ダッシュボード] を使用して、使用されているデバイスが正しく動作し、オーディオおよびビデオ メディア品質を監視できます。
  
> [!TIP]
> **最も最適なメディア品質エクスペリエンスを実現するにはSkype for Businessデバイスが必要です**。
  
メディア デバイス、Microsoft Teams クライアント、および Skype for Business サーバー (Real-Time メディア フロー) には、ある程度の待機時間が発生する点に注意してください。 デバイスとソフトウェアの処理待ち時間とネットワーク待ち時間は、エンド to エンドの全体的な待機時間とエンド ユーザーのエクスペリエンスに大きな影響を与え、それに貢献します。
  
#### <a name="environment"></a>環境

ユーザーが会議を行い、オーディオ デバイスやビデオ デバイスを使用している環境とその周辺領域は、オーディオとビデオの品質のもう 1 つの大きな要因です。 ノイズの多い環境から呼び出すユーザーは、エコー、こもり、不明瞭な音声を受け取ります。 暗くて照明が不十分な環境にいるユーザーは、ビデオで明るくクリアな画質を実現することができません。 会議室の設定で、マイクとビデオ デバイスの場所は、参加者が受信する音声と画像の品質に直接影響します。
  
ユーザーのオーディオとビデオのエクスペリエンスのより明確な画像を取得するには、Skype for Business アプリのツールオプション オーディオ デバイスまたはビデオ デバイスを使用して、使用されているデバイスに変更を加え、設定をカスタマイズします。  >    >   

#### <a name="network"></a>ネットワーク

IP ネットワーク上のReal-Timeの品質は、ネットワーク接続の品質の影響を受け、特に以下の量によって大きく影響されます。
  
- **待機時間** これは、ネットワーク上のポイント A からポイント B への IP パケットの取得にかかる時間です。 このネットワーク伝達遅延は、2 つのポイント間の物理的な距離と光の速度に関連付けられます。これには、その間のさまざまなルーターによって余分に発生するオーバーヘッドが含まれています。 待機時間は、一方通行時間またはラウンドトリップ時間 (RTT) として測定されます。
    
- **パケット損失** これは、多くの場合、特定の時間内に失われたパケットの割合として定義されます。 パケット損失は、オーディオの品質に直接影響を与えます。ほとんど影響を及ぼすことのない小規模のパケット損失から、音声が完全に途切れる原因となる連続したバースト損失まで存在します。
    
- **パケット間到着ジッターまたは単なるジッター** これは、連続するパケット間の遅延の平均変化です。 データを含む最新の VoIP ソフトウェアMicrosoft Teamsバッファリングを通じて一部のレベルのジッターに適応できます。 これは、参加者がジッターの影響に気付くほど、ジッターがバッファリングを超える場合に限定されます。
    
> [!NOTE]
>  ジッターのバッファー処理により、エンドツーエンドの待ち時間が増加します。
  
多くの同時 Microsoft Teams Real-Time メディア セッションや、他の Microsoft 365 または Office 365 サービスや他のビジネス アプリケーションによって生成されるその他のネットワーク トラフィックでは、ネットワークの輻輳を回避し、優れたメディア Real-Time メディア (オーディオ、ビデオ、アプリケーション共有) の品質を確保するために、ネットワークを Microsoft Teams サービスに接続するネットワーク パス全体で十分な帯域幅を確保する必要があります。 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>混雑したネットワーク間でのサービス品質 (QoS) の実装

さらに、ネットワーク全体のトラフィックの輻輳はメディアの品質に大きく影響します。 音声パケットとビデオ パケットがネットワークを速く移動し、混雑したネットワーク内の他のネットワーク トラフィックよりも優先順位を付けるために、サービス品質 (QoS) を使用して、オーディオおよびビデオ通信に最適なエンド ユーザー エクスペリエンスを提供できます。
  
QoS は、音声またはビデオ データを転送しているネットワーク パケットに優先順位を高く割り当てる方法を提供します。 これらのパケットに優先順位を高く割り当てると、オーディオおよびビデオ通信は、ファイル転送、Web ブラウズ、データベース バックアップなどのネットワーク セッションよりも、ネットワーク上を移動する速度が速く、中断が少ない可能性があります。 これは、既定でファイル転送またはデータベース バックアップに使用されるネットワーク パケットには優先度として "ベスト ベスト インベスト" が割り当て、ネットワークの輻輳は大きな影響を及ぼすためです。 メディア (オーディオ、ビデオ、アプリケーション共有) パケットに優先順位を高く割り当てずに、それらを "ベスト 努力" として割り当てたままにした場合、そのパケットも他のすべてのネットワーク トラフィックと共に処理されます。 ネットワークの輻輳の量によっては、ユーザーの全体的なオーディオおよびビデオ品質のエクスペリエンスが低下する可能性があります。
  
ネットワーク内のネットワーク輻輳が影響を受けずにいけずに、ネットワークに QoS を実装することを強くお勧めします。 ただし、これが最大の影響を及ぼすには、すべてのネットワーク エンドポイントが QoS をサポートする必要があります。つまり、すべてのエンドポイントが QoS マーキングとパケット優先順位付けを尊重する必要があります。 Microsoft Teamsサービスは、Microsoft ネットワーク内での QoS マーキングと優先順位付けに対応します。 ただし、会社のネットワークから Microsoft ネットワークへのインターネットのようなパブリック接続を通してルーティングされるトラフィックでは、QoS マーキングとパケット優先順位付けは保持されません。 [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)を使用したネットワークから Microsoft 365 または Office 365 へのプライベート接続では、QoS マーキングとパケット優先順位を保持するデプロイ ソリューションが提供され、エンド ユーザーの全体的なオーディオとビデオの品質が向上します。
  
## <a name="network-performance-requirements-to-connect-to-microsoft-teams"></a>ネットワーク に接続するためのネットワーク パフォーマンス要件Microsoft Teams
<a name="bkNetworkPerf"> </a>

Skype for Business Real-Timeメディアは、さまざまなデバイス、クライアント アプリ、サーバー ソフトウェア、さまざまなネットワークを経由して移動します。 各メディアのエンド Real-Timeは、すべてのコンポーネントとネットワーク セグメントで発生する待機時間の合計量です。 エンドツーエンド ネットワーク接続の品質は、品質が最も悪いネットワーク セグメントによって決まります。 このセグメントは、このネットワーク トラフィックのボトルネックとして機能します。
  
次の図は、ある参加者から別の参加者への会議の一方向Microsoft Teamsを示しています。
  
![ExpressRoute 通話Flow。](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
この会議シナリオでは、メディア パスは次のネットワーク セグメントで構成されます。
  
1. **ユーザー 1 から Microsoft ネットワークのエッジへの接続** これには通常、WiFi やイーサネットなどのネットワーク接続、ユーザー 1 からインターネット出口ポイント (ネットワーク エッジ デバイス) への WAN 接続、ネットワーク エッジから Microsoft ネットワーク エッジへのインターネット接続が含まれます。
    
2. **Microsoft ネットワーク内の接続** これは、A/V Microsoft Edge Microsoft Teams使用されるデータ センターへの接続の間です。
    
3. **Microsoft Network 内の接続** これは、データ センター Microsoft Teams Microsoft ネットワーク エッジの間です。
    
4. **Microsoft ネットワーク エッジからユーザー 2 への接続** これには、ネットワーク エッジから Microsoft ネットワーク エッジへのインターネット接続、ユーザー 2 からインターネット出口ポイント (ネットワーク エッジ) への WAN 接続、WiFi やイーサネットなどのネットワーク接続が含まれます。
    
次の図は、PSTN 通話のコンポーネントとネットワーク セグメントMicrosoft Teams示しています。
  
![ExpressRoute PSTN 通信事業者の通話Flow。](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
PSTN 通話シナリオでは、メディア パスは次のネットワーク セグメントをまたがっています。
  
1. **クライアントの呼びSkype for Businessから Microsoft ネットワークのエッジへの接続** 通常、これには、WiFi やイーサネットなどのネットワーク接続、Skype for Business クライアント呼び出し元からインターネット出口ポイント (ネットワーク エッジ デバイス)への WAN 接続、ネットワーク エッジから Microsoft ネットワーク エッジへのインターネット接続が含まれます。
    
2. **Microsoft ネットワーク内の接続** これは、仲介サーバー Microsoft Edge使用Microsoft Teamsデータ センターへの接続の間です。
    
3. **Microsoft Network 内の接続** これは、データ センター Microsoft Teams Microsoft ネットワーク エッジの間です。
    
4. **Microsoft Network と PSTN サービス プロバイダー パートナー間の接続** これは、Microsoft ネットワークの外部にあるクライアントから PSTN Skype for Business発信するために存在する接続です。
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>クライアントから Microsoft ネットワーク エッジSkype for Businessネットワーク パフォーマンス要件
<a name="bkSfBClienttoEdge"></a>

最適なSkype for Businessメディア品質を実現するには、会社のネットワークから Microsoft ネットワーク Edge への接続に対して、次のネットワーク パフォーマンス メトリックのターゲットまたはしきい値が必要です。 ネットワークのこのセグメントには、内部ネットワークが含まれます。これには、すべての WiFi およびイーサネット接続、WAN 接続経由の会社のサイト間トラフィック (Multiprotocol Label Switching (MPLS) など) と、Microsoft ネットワーク Edge へのインターネットまたは ExpressRoute パートナー接続が含まれます。
  
> [!CAUTION]
> **会社のネットワーク上Skype for Businessクライアントと Microsoft 365 または Office 365 サービス間の接続は、以下のネットワーク パフォーマンス要件としきい値を満たしている必要があります。**

|**測定基準** <br/> |**Target** <br/> |
|:-----|:-----|
|遅延 (一方向)  <br/> |< 50 ミリ秒  <br/> |
|遅延 (RTT または往復時間)  <br/> |< 100 ミリ秒  <br/> |
|バースト パケット損失  <br/> |< 任意の 200 ミリ秒間隔で 10%  <br/> |
|パケット損失  <br/> |< 任意の 15 秒間隔で 1%  <br/> |
|パケット到着間ジッター  <br/> |< 15 秒間隔で 30 ミリ秒  <br/> |
|パケットの並べ替え  <br/> |< 順序が適切でないパケットが 0.05%  <br/> |
   
 **その他のパフォーマンス ターゲット要件:**
  
- Microsoft ネットワークには、世界中に 160 を超える Edge の場所があります。 これらのエッジ サイトを通じて、世界中の主要なインターネット サービス プロバイダー (ISP) と取り組んでいます。 待機時間メトリック ターゲットは、会社のサイトまたはサイトと Microsoft Edges が同じ大陸上にあることを前提とします。
    
- 会社のサイトまたは Microsoft ネットワーク エッジ接続へのサイトには、最初のホップ ネットワーク アクセスが含まれます。このアクセスには、WiFi または別のワイヤレス テクノロジを使用できます。 
    
- ネットワーク パフォーマンス ターゲットは、適切な帯域幅やサービス品質の計画を前提とします。 つまり、ネットワーク接続の負荷がピーク時Skype for Business Real-Timeメディア トラフィックに直接適用されます。
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>ネットワーク エッジから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件
<a name="bkYourNetworkEdge"> </a>

ネットワーク エッジと Microsoft ネットワーク エッジ間の接続に必要なネットワーク パフォーマンスのターゲットまたはしきい値を次に示します。 ネットワークのこのセグメントは、顧客の内部ネットワークまたは WAN を除外し、インターネット経由または ExpressRoute パートナー ネットワーク経由で送信されるネットワーク トラフィックをテストする際のガイダンスとして意図され、ExpressRoute プロバイダーとパフォーマンス サービス レベル アグリーメント (SLA) をネゴシエートするときにも使用できます。
  
> [!CAUTION]
> **会社のネットワーク Edge から Microsoft ネットワーク エッジへの接続は、以下のネットワーク パフォーマンス要件としきい値を満たしている必要があります。**

|**測定基準** <br/> |**Target** <br/> |
|:-----|:-----|
|遅延 (一方向)  <br/> |< 30 ミリ秒  <br/> |
|遅延 (RTT)  <br/> |< 60 ミリ秒  <br/> |
|バースト パケット損失  <br/> |<200 ミリ秒間隔で 1% を超える  <br/> |
|パケット損失  <br/> |< 任意の 15 秒間隔で 0.1%  <br/> |
|パケット到着間ジッター  <br/> |< 任意の 15 秒間隔で 15 ミリ秒  <br/> |
|パケットの並べ替え  <br/> |< 順序が適切でないパケットが 0.01%  <br/> |
   
 **その他のパフォーマンス ターゲット要件:**
  
- パフォーマンス ターゲットでは、会社のネットワーク エッジとその最も近い Microsoft ネットワーク エッジの間の接続が同じ大陸上に必要です。
    
- ネットワーク パフォーマンス ターゲットは、適切な帯域幅やサービス品質の計画を前提とします。 これは、ネットワーク接続Skype for Business Real-Time負荷がピークに達した場合のメディア トラフィックにも適用されます。 適切な帯域幅と QoS の計画については、 の ExpressRoute と[QoS に関するページMicrosoft Teams。](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>ネットワーク パフォーマンスの測定
<a name="bkNetworkPerf"> </a>

会社のネットワーク サイトからネットワーク エッジへの実際のネットワーク パフォーマンス (特に待機時間とパケット損失) を測定するには、ping などのツールを使用し、Microsoft Edge サイトとデータ センター サイトから実行されている一連の Skype for Business メディア リレー サービスに対してテストできます。 

>[!NOTE]
> ping (ICMP) によるネットワーク パフォーマンスの測定は有効ではありません。 このため、以下で公開されている anycast IP は、2020 年 1 月から ICMP 要求への応答を停止します。 ネットワークパフォーマンスを効果的に測定するために、Microsoft では [Network Assesment Tool をお勧めします](https://www.microsoft.com/download/details.aspx?id=53885)。
  
Microsoft ネットワークへのインターネット接続をテストするには、メディア リレーの次の VIP に対してテストSkype for Business勧めします。 *Anycast VIP は*、テストの場所に最も近い Microsoft ネットワーク エッジ サイト内の Media Relay の IP アドレスに解決されます。
  

|**IP アドレス** <br/> |**Type** <br/> |**場所** <br/>|
|:-----|:-----|:-----|
|13.107.8.2  <br/> |VIP  <br/> |World Wide Anycast IP  <br/> |
   
 **ネットワーク パフォーマンスを評価するために従う推奨事項の一部を次に示します。**
  
- 内部ネットワークと、ネットワークまたはネットワークへの接続Microsoft 365評価Office 365。
    
- すべてのネットワークのデータを長時間評価して収集する必要があります。 すべての営業日と時間の使用パターンを確認できるよう、ネットワーク パフォーマンスのテストを少なくとも 1 週間実行することをお勧めします。 これにより、ピーク時間が表示されます。
    
- ネットワーク パフォーマンス測定の複数のサンプルを使用する必要があります。 データを収集する期間中は、会社のサイトから 10 分ごとに測定することをお勧めします。 ネットワーク パフォーマンス要件Microsoft Teams比較するには、このサンプル データ セットから 90 パーセントの測定値を取得します。 
    
- ネットワークのパフォーマンスを継続的に評価する必要があります。 ネットワーク使用率は、使用パターンの変更、大量の帯域幅を使用する新しいエンタープライズ ベースのアプリケーション、組織または物理的な会社の場所の変更により、時間の長い間変化します。 これらのネットワーク パフォーマンス要件とターゲット/しきい値に対してネットワーク パフォーマンスを継続的に監視し、最適なメディア品質を確保するために適時に調整Real-Time重要です。 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Azure VM を使用したネットワーク パフォーマンスの測定
<a name="bkNetworkPerf"> </a>

Microsoft ネットワーク Edge サイトに対してテストする代わりに、Skype for Business のお客様とパートナーから、Microsoft Azure クラウドのサービスのテスト セットアップを使用するネットワーク評価ソリューションがあります。 これらのソリューションでは、ネットワーク評価ツールは、Azure クラウドでサービスとして設定されたカスタム エンドポイントに対して待機時間、パケット損失、ジッターをテストします。 その結果、テスト ネットワーク トラフィックは、ネットワーク エッジとネットワーク評価サービスをホストする Azure データ センター間の Microsoft ネットワーク内の接続である、もう 1 つのネットワーク セグメントを通過します。
  
Azure でホストされているテスト サービスに基づくネットワーク評価ソリューションの場合。 国または地域内でネットワーク評価を実行することをお勧めします。 たとえば、米国東部の顧客サイトの場合、評価は、Azure の米国東部データ センター リージョンでホストされているテスト サービス インスタンスに対して実行する必要があります。 
  
Azure サービス ベースのネットワーク評価セットアップの待機時間 (RTT) ターゲットを次に示します。 一方通行の待機時間ターゲットは、対応する RTT ターゲットの半分です。 パケット損失とジッターの目標は、Media Relay ベースのテストで定義Skypeと同じです。
  


|**顧客リージョン** <br/> |**Azure リージョン** <br/> |**ネットワーク エッジ - Azure ラウンドトリップ時間 (RTT)** <br/> |**サイト - Azure ラウンドトリップ時間 (RTT)** <br/> |
|:-----|:-----|:-----|:-----|
|米国中部  <br/> |米国中部  <br/> |99  <br/> |139  <br/> |
|米国東部  <br/> |米国東部  <br/> |86  <br/> |126  <br/> |
|米国中北部  <br/> |米国中北部  <br/> |97  <br/> |137  <br/> |
|米国中南部  <br/> |米国中南部  <br/> |94  <br/> |134  <br/> |
|米国西部  <br/> |米国西部  <br/> |94  <br/> |134  <br/> |
|米国ハワイ  <br/> |米国西部  <br/> |116  <br/> |156  <br/> |
|カナダ中部  <br/> |カナダ中部  <br/> |138  <br/> |178  <br/> |
|カナダ東部  <br/> |カナダ東部  <br/> |131  <br/> |171  <br/> |
|北ヨーロッパ  <br/> |北ヨーロッパ  <br/> |99  <br/> |139  <br/> |
|西ヨーロッパ  <br/> |西ヨーロッパ  <br/> |95  <br/> |135  <br/> |
|東アジア  <br/> |東アジア  <br/> |118  <br/> |158  <br/> |
|東南アジア  <br/> |東南アジア  <br/> |97  <br/> |137  <br/> |
|東日本  <br/> |東日本  <br/> |111  <br/> |151  <br/> |
|西日本  <br/> |西日本  <br/> |118  <br/> |158  <br/> |
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

Azure ExpressRoute for Microsoft 365 または Office 365 は、ユーザーまたはユーザーに接続するための専用Microsoft 365ネットワークOffice 365。 お客様は、ネットワーク トラフィックが受け取るパスを制御できます。 不明な通信事業者、プロバイダー、および ISP によってデータが運び出されるインターネット上で発生する予測不可能なルーティングについて心配する必要はなくなりました。 ExpressRoute を介して送信されるネットワーク トラフィックは、ExpressRoute パートナーのネットワークを介して Microsoft のネットワークに直接送信されます。 これにより、お客様はMicrosoft 365またはOffice 365専用の接続を持つ独自のオフサイト データ センターにある場合と同様に処理できます。
  
Azure ExpressRoute は、すべてのライセンス サービスMicrosoft 365およびOffice 365で利用できます。 ただし、グローバル ルーティングを有効プレミアムを有効にするには、Microsoft 365 Azure ExpressRoute Office 365アドオンが必要です。 ExpressRoute を実装している 500 以上のシートをお持ちのお客様は、追加費用プレミアム必要な *ExpressRoute* サービスを利用できます。
  
### <a name="is-expressroute-required-for-good-media-quality"></a>優れたメディア品質を実現するには ExpressRoute が必要ですか?

Azure ExpressRoute は、メディア品質を最適化するためのMicrosoft Teamsではありません。 ただし、クラウド接続がネットワーク パフォーマンスの目標またはしきい値を満たSkype for Businessオプションの 1 つになります。
  
Microsoft 365とOffice 365、インターネットを使用する高パフォーマンスでセキュリティで保護されたサービスです。 セキュリティとパフォーマンスを継続的に向上させるために、新しいセキュリティ機能と地域のエッジ ノードに投資し続けます。 Azure ExpressRoute は、サービスを含むMicrosoft 365サービスOffice 365要件Microsoft Teams。 Azure ExpressRoute は、Microsoft 365 または Office 365 への接続が Skype for Business のネットワーク パフォーマンス要件を満たしていることを確認し、Microsoft Teams メディア品質エクスペリエンスを最適にするためのデプロイ オプションの 1 つです。
  
Microsoft Teams メディア品質の場合、会社のサイトと Microsoft ネットワーク エッジ間の接続が[、Skype for Business](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件のパフォーマンス 目標を満たしていることを重要です。また、ネットワーク エッジと Microsoft ネットワーク エッジ間の接続が、ネットワーク エッジから[Microsoft](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)ネットワーク エッジへのネットワーク パフォーマンス要件のパフォーマンス ターゲットを満たしていることを確認します。  
  
また、内部ネットワークやクラウド接続容量を含む会社の物理ネットワーク接続が、メディア トラフィックのピーク量に対応することが重要です。 Azure ExpressRoute は、クラウド接続がこれらのパフォーマンス要件のすべてMicrosoft Teamsを確実に満たすのに役立つさまざまな方法の 1 つです。
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute は音声品質 SLA に必要ですか?

いいえ。ExpressRoute は、音声品質 SLA Microsoft Teams必要ありません。 [Microsoft Teams音声](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)品質 SLA は、そのユーザーが任意の種類の VoIP または PSTN 通話を行える適切なライセンスとサブスクリプション内の任意の Microsoft Teams ボイス サービス ユーザーによって発信された対象通話に適用されます。 音声品質 SLA には、次のすべての条件に対処する必要があります。
  
- Microsoft 認定 IP Phone からの呼び出し。
    
- 有線イーサネット接続。
    
- Microsoft Network の問題による音声品質の問題。
    
> [!NOTE]
> 音声品質 SLA は、低い通話品質が、ExpressRoute パートナーや他のネットワークを含む Microsoft 以外のネットワークの問題によって引き起こされた通話を除外します。 
  
### <a name="internet-or-azure-expressroute"></a>インターネットまたは Azure ExpressRoute

Microsoft Teams へのネットワーク接続オプションを決定する前に、Microsoft Teams に接続するためのネットワーク パフォーマンス要件に関するページで説明されているネットワーク パフォーマンス要件に基づいて、ネットワークと現在のインターネット接続を評価[するMicrosoft Teams。](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)
  
現在のインターネット接続上のネットワーク パフォーマンスがピーク時に十分な容量に設定され、サイトから Microsoft ネットワーク エッジ、およびネットワーク エッジから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件を満たしている場合は、既存のインターネット接続を使用して Microsoft Teams に接続できます。
  
ネットワーク パフォーマンス要件が満たされていない企業サイトの場合は、まず既存のネットワーク サービス プロバイダーと一緒に作業し、全体的なネットワーク パフォーマンスを向上することを強く推奨します。 ただし、まだ満たされていない場合は、Azure ExpressRoute を使用すると、Microsoft Teams クラウド接続がネットワーク パフォーマンス要件を満たすのに役立ちます。
  
Azure ExpressRoute には、次の追加の利点があります。
  
- ネットワークと Microsoft ネットワーク間の接続の可用性に関するサービス レベル アグリーメント (SLA)。 ExpressRoute の可用性 SLA は 99.9% という保証があります。
    
- サービスを使用するために必要な、計画Microsoft 365帯域幅Office 365。 これを実現するには、ExpressRoute を使用して Microsoft 365、Office 365、または Skype for Business トラフィックのみを送信し、その他のすべてのインターネット トラフィックがネットワークの他のインターネットエグレス/イングレス ポイントを経由します。
    
- ExpressRoute は、ネットワークと Microsoft ネットワーク間の DSCP QoS マーキングを保持するように設計されています。
    
ExpressRoute QoS と容量計画の詳細については、「ExpressRoute と QoS in [Microsoft Teams」を参照してください](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)。
  
### <a name="can-i-set-up-azure-expressroute-for-microsoft-teams-only"></a>Azure ExpressRoute を設定できるのはMicrosoft Teamsですか?

はい。Azure ExpressRoute を設定して、会社のネットワークからのネットワーク接続が優れている場合にのみ接続Microsoft Teams。 これにより、ユーザーに最適なReal-Timeメディア品質が提供されますが、インターネットを使用して他の Microsoft 365 または Office 365 サービスに接続し続けできます。
  
Border Gateway Protocol (BGP) は、インターネット上のネットワーク トラフィックをインターネットにルーティングするために使用される、インターネット上のルーティング プロトコルです。 これは、インターネット上で検出された自律システム (AS) 間でルーティング情報を交換するように設計されています。 BGP コミュニティの値は、着信ルートまたは送信ルートに適用できる属性タグです。 BGP コミュニティは、多くの場合、地理的、サービスの種類、その他の条件に基づいて特定の宛先に到達するために使用する送信リンクを受信 AS に通知するために使用されます。
  
BGP コミュニティのサポートにより、Microsoft はプレフィックスとルートに、属するサービスに基づいて適切な BGP コミュニティ値でタグ付けします。 Microsoft は、パブリック ピアリングと Microsoft ピアリングを通じてアドバタイズされたプレフィックスに、プレフィックスがホストされているリージョンを示す適切な BGP コミュニティ値でタグ付けします。 コミュニティの値に依存して、最適なルーティングを提供するために適切なルーティングの決定を行います。 BGP コミュニティ値の Microsoft Teamsを使用して、ゲートウェイの ExpressRoute 接続のみを設定Microsoft Teams。 詳細については [、「ExpressRoute のルーティング要件」を参照してください](/azure/expressroute/expressroute-routing)。
  
## <a name="expressroute-connectivity-scenarios-for-microsoft-teams"></a>ExpressRoute 接続のシナリオ (Microsoft Teams
<a name="bkNetworkPerf"> </a>

上記の推奨事項に基づいて ExpressRoute を使用することを決定した場合は、取得する必要がある ExpressRoute 接続の場所と数に関する推奨事項を次に示します。
  
### <a name="online-only-deployment---single-site"></a>オンラインのみ展開 - 単一サイト

すべてのユーザーが Microsoft Teams サービスを使用し、オフィスが 1 つの物理的な場所を中心に配置され、Azure ExpressRoute をデプロイする場合は、会社サイト間の ExpressRoute 接続を最も近い ExpressRoute ピアリングの場所に設定する[必要があります](/azure/expressroute/expressroute-locations)。
  
次の図は、この種類のデプロイの例を示しています。 この例では、Contoso はフロリダ州オーランドにある大学です。 Contoso には 10,000 人の教職員と学生がいます。 その場所からサイトへのインターネット テストMicrosoft Edgeクラス時間のピーク時にパケット損失が 5% を超えました。 特に Microsoft Teams Real-Time トラフィックに対する Microsoft 365 または Office 365 のネットワーク輻輳を回避するために、ExpressRoute と過剰にプロビジョニングされた帯域幅を使用して Microsoft 365 または Office 365 への専用接続を取得することを決定しました。 GA MeetMe サイトのアトランタにある ExpressRoute を介して Microsoft クラウドに接続します。
  
![ExpressRoute シングル サイト。](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>オンラインのみ展開 - 同じ大陸上の複数のサイト

会社が同じ地域または大陸の複数のオフィスから Microsoft Teams サービスを使用している場合、Azure ExpressRoute を実装することを選択した場合は、ExpressRoute を介してメイン サイトを接続し、必要に応じて、推奨されるネットワーク パフォーマンス ターゲットを満たしていない他の場所に ExpressRoute ピアリングを追加することを推奨します。
  
次の例では、Contoso はニューヨークに本社を置き、米国全体に他のオフィスを持つ米国旅行サービス会社です。 オフィスは、MPLS を使用してネットワークまたはネットワークに接続する WAN Microsoft 365接続Office 365。 最初に、ニュージャージー州ホボーケンのインターネット ルーターからニューヨーク MeetMe サイトへの ExpressRoute 接続を設定しました。 
  
この設定により、ほとんどのサイトから Microsoft Network (New York Edge サイト) へのネットワーク トラフィックは[、「Skype for Business](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件」で説明されている Skype for Business クライアント接続ネットワーク パフォーマンス ターゲットを満たします。 ただし、Contoso の西海岸オフィスからニューヨークへの間の待ち時間は、50 ミリ秒を超える場合があります。 さらに、Contoso の 2 番目に大きなオフィスである、80 ミリ秒を超える待機時間は、一方通行で 80 ミリ秒を超える、Contoso のオフィスです。 これらのオフィスのユーザーに優れたメディア品質を確保するために、Contoso は、San Jose サイトとシリコン バレー ExpressRoute MeetMe サイトの間に西海岸 ExpressRoute 接続を追加することを決定しました。
  
![同じ大陸の Express Router マルチサイト。](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>オンラインのみ展開 - 異なる大陸の複数のサイト

すべてのユーザーが Microsoft Teams サービスを使用している場合、オフィスが複数の大陸にわたって複数の物理的な場所にある場合は、Azure ExpressRoute をデプロイする場合は、各大陸のメイン サイト間の各大陸の ExpressRoute 接続を、最も近い[ExpressRoute](/azure/expressroute/expressroute-locations)ピアリングの場所に設定する必要があります。 コストとメリットに応じて、ネットワーク パフォーマンス ターゲットが満たされていないサイトから追加の ExpressRoute 接続をデプロイすることができます。
  
次の例では、Contoso は、北米とヨーロッパの主要都市にオフィスを持つ大規模な企業の法律事務所です。 Contoso は、インターネット接続と内部ネットワーク パフォーマンス評価に基づいて、北米に 2 つの ExpressRoute 接続をデプロイし、ヨーロッパのすべてのオフィスに 1 つの ExpressRoute 回線をデプロイすることを決定しました。
  
![複数のサイトと大陸を含む ExpressRoute。](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>ハイブリッドデプロイ

オンプレミスの Lync または Microsoft Teams デプロイを使用し、ハイブリッド Microsoft Teams 統合を実装する場合は、Azure ExpressRoute をデプロイする場合は、オンプレミスの Lync または Microsoft Teams Edge サイトごとに少なくとも 1 つの ExpressRoute 接続と、オフィスがある大陸ごとに少なくとも 1 つの ExpressRoute 接続が必要です。 コストとメリットに応じて、大陸ごとに、ネットワーク パフォーマンス ターゲットが満たされていないオフィスから追加の ExpressRoute 接続をデプロイすることができます。
  
オンプレミスのデプロイを使用しているMicrosoft Teams、Edge Server Planning and Deployment Guide に従[う必要があります](../../SfbServer/plan-your-deployment/edge-server-deployments/edge-server-deployments.md)。 具体的には、ネットワークの外部から Edge サーバーに到達できる必要があります。 これは通常、Routable パブリック IP アドレスを Edge サーバーに割り当てるか、ネットワーク アドレス変換 (NAT) を使用して実現されます。
  
次の例では、Contoso は既存のオンプレミスのデプロイMicrosoft Teams エンタープライズ VoIPしています。 オンプレミスのユーザーをオンライン サービスに移行Microsoft 365またはOffice 365する必要があります。 また、すべてのオンプレミスユーザーとオンライン ユーザーに対して既存の PSTN インフラストラクチャを引き続き使用できるよう、ハイブリッド展開を使用することを決定しました。 Contoso のオンプレミス データ センターと Skype for Business エッジ サーバーはシカゴにあります。 Contoso はデプロイのために、シカゴのデータ センターとシカゴ ExpressRoute の間に 1 つの ExpressRoute 接続を設定することを決定しました。 また、西海岸の ExpressRoute 接続を追加して、より良いサービスを提供しています。
  
![ExpressRoute ハイブリッド。](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Cloud Connector Edition を使用したオンライン デプロイ

Skype for Business クラウド コネクタ エディションは、オンプレミスの PSTN 接続を実装するパッケージ化された仮想マシン (VM) のセットで構成されるハイブリッド サービスです。 仮想化された環境に最小限の Skype for Business Server トポロジをデプロイすることで、既存のオンプレミス PSTN 音声インフラストラクチャを介して固定電話と携帯電話で通話を送受信できます。
  
Azure ExpressRoute と Cloud Connector Edition をデプロイする場合は、各大陸のメイン サイト間の大陸ごとに少なくとも 1 つの ExpressRoute 接続を、最も近い ExpressRoute ピアリングの場所に設定することをお [勧めします](/azure/expressroute/expressroute-locations)。 コストとメリットに応じて、大陸ごとに、ネットワーク パフォーマンス ターゲットが満たされていないサイトから追加の ExpressRoute 接続をデプロイできます。
  
オンプレミスのデプロイを使用している場合Microsoft Teams計画ガイドに従って、次の手順[を実行Skype for Business クラウド コネクタ エディション。](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md) 具体的には、Access Edge サービスと A/V Edge サービスにパブリック IP アドレスを割り当て、データ センター Microsoft 365アクセスOffice 365必要があります。
  
次の例では、Contoso はヨーロッパのいくつかの主要な国と都市にプレゼンスを持つヨーロッパの会計会社です。 すべてのコラボレーション ニーズに合った Microsoft Teams にサインアップするときに、既に存在する PSTN インフラストラクチャと通信事業者の契約を引き続き使用するために、物理的な場所を持つ国ごとにクラウド コネクタを設定することを決定しました。 すべてのサイトと Microsoft ネットワーク エッジからのテストに基づいて、ロンドンの 1 つの ExpressRoute 接続が[、「Skype for Business](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)クライアントから Microsoft ネットワーク エッジへのネットワーク パフォーマンス要件」で説明されている Microsoft Teams クライアント接続ネットワーク パフォーマンス ターゲットを満たすのに役立つと判断しました。
  
![ExpressRoute Cloud Connector One。](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Contoso のもう 1 つのデプロイ オプションを次に示します。 この場合、クラウド コネクタがデプロイされている各サイトで ExpressRoute 接続を設定することを決定しました。 
  
![ExpressRoute クラウド コネクタ 2。](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>関連トピック

[Skype for Business Online の ExpressRoute および QoS](expressroute-and-qos-in-skype-for-business-online.md)

  
