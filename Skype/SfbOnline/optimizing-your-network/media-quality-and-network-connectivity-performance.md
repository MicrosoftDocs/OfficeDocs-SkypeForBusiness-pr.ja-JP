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
description: このトピックでは、Skype for Business Online サービスのネットワークパフォーマンス要件のセットと、ネットワークと Skype for Business Online との間の接続にインターネットまたは ExpressRoute を使用する方法を定義する方法について説明します。ネットワークの評価に基づいています。対する. Office 365 への専用接続用に Azure ExpressRoute を展開することにした場合、このドキュメントでは、さまざまな Skype for Business Online の展開シナリオで ExpressRoute 接続を計画する方法のガイダンスについて説明します。
ms.openlocfilehash: 2d9192f4dfb27de97527ff584c0ab0a204e20cca
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693072"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス

このトピックでは、Skype for Business Online サービスのネットワークパフォーマンス要件のセットと、ネットワークと Skype for Business Online との間の接続にインターネットまたは ExpressRoute を使用する方法を定義する方法について説明します。ネットワークの評価に基づいています。対する. Office 365 への専用接続用に Azure ExpressRoute を展開することにした場合、このドキュメントでは、さまざまな Skype for Business Online の展開シナリオで ExpressRoute 接続を計画する方法のガイダンスについて説明します。
  
IP 経由のリアルタイムメディア (オーディオ、ビデオ、およびアプリケーション共有) の品質は、エンドツーエンドのネットワーク接続の品質に大きく影響します。 Skype for Business Online メディアの最適な品質を得るために、会社のネットワークと Skype for Business Online 間の接続が高品質であることを確認することが重要です。 これを達成するためには、内部ネットワークとクラウド接続を、接続全体にわたって Skype for Business Online のピーク時のトラフィック量を処理するネットワークのキャパシティに基づいて設定することが最善の方法になります。
  
Azure ExpressRoute は、Skype for Business Online などの Office 365 サービスの要件ではありません。 ただし、Azure ExpressRoute は、Office 365 への接続が Skype for Business ネットワークのパフォーマンス要件を満たし、最適な Skype for Business Online メディアを確実に満たすために使用できる展開オプションの1つです。音質が向上します。
  
> [!TIP]
> このトピックでは、全体的なネットワークパフォーマンスガイダンスについて説明していますが、ネットワークの評価に関する包括的なガイダンスは、このドキュメントの範囲外です。 綿密かつ完全なネットワーク評価の一環として、ネットワークパフォーマンスの測定に役立つ Skype for Business Online パートナーの一覧を見つけるには、 [skype For Business パートナーソリューション](http://partnersolutions.skypeforbusiness.com/)にアクセスしてください。 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Skype for Business Online へのネットワーク接続要件

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Skype for Business Online メディアの品質に影響する要因

Skype for Business Online のリアルタイムメディア (オーディオ、ビデオ、およびアプリケーション共有) には、使用されているデバイス、環境、ネットワーク接続など、さまざまな要因があります。 
  
#### <a name="devices"></a>デバイス

リアルタイムのメディアセッションでは、ヘッドセットや Web カメラなどすべての参加者によって使用されるメディアのキャプチャとレンダリングデバイスは、全体的な音声とビデオの品質に大きな影響を与えます。 品質の低いデバイスや、デバイス ドライバが間違っているデバイスでは、全体的にオーディオの音質が下がり、ビデオの画質が下がります。 一方、認定デバイスまたは高品質なデバイスは、エコー キャンセル、ノイズ フィルタリング、ビデオ解像度、遅延低減に役立ちます。
  
認定されたオーディオおよびビデオメディアデバイスは必須ではありませんが、最適なメディアエクスペリエンスを実現するために Skype for Business で認定されているデバイスを強くお勧めします。 すべての Skype for Business 認定デバイスの一覧については、「Skype for business[の電話とデバイス](https://technet.microsoft.com/office/dn947482)」を参照してください。 Skype for business**管理センター**にある[Skype For Business Online 通話品質ダッシュボード](/microsoftteams/turning-on-and-using-call-quality-dashboard)を使用して、使用中のデバイスが正常に動作していることを確認し、オーディオとビデオのメディアの品質を監視することができます。
  
> [!TIP]
> **Skype For business で最適なメディア品質を得るには、認定デバイスが必要**です。
  
リアルタイムメディアを使用するメディアデバイス、Skype for business クライアント、および Skype for Business サーバーは、一定の時間がかかることを覚えておくことが重要です。 デバイスとソフトウェアの処理待ち時間は、ネットワーク待ち時間と共に、エンドツーエンドの全体的な待ち時間とエンドユーザーエクスペリエンスに大きく影響します。
  
#### <a name="environment"></a>環境

ユーザーが会議を行い、オーディオ デバイスとビデオ デバイスを使用する環境と周辺領域は、オーディオとビデオの品質のもう 1 つの要因です。ノイズのある環境から通話しているユーザーのオーディオは、エコーがかかり、こもっていて、不明瞭です。暗くて照明が不十分な環境にいるユーザーは、ビデオで明るくクリアな画質を実現することができません。会議室の設定で、マイクとビデオ デバイスの場所は、参加者が受信する音声と画像の品質に直接影響します。
  
ユーザーの音声とビデオのエクスペリエンスをより明確にするために、Skype for business アプリの [**ツール** > **]** > の [**オーディオデバイス**] または [**ビデオデバイス**] を使って、使用中のデバイスに変更を加え、その設定をカスタマイズします。

#### <a name="network"></a>ネットワーク

IP ネットワーク上のリアルタイムメディアの品質は、ネットワーク接続の品質に大きな影響を与えますが、特に次の量によって影響を受けます。
  
- **待機時間**これは、IP パケットがネットワーク上のポイント A からポイント B に到達するまでにかかる時間です。 このネットワーク伝播遅延は、さまざまなルーターの間の追加のオーバーヘッドを含めて、2つのポイントとライトの速度の間の物理的な距離に関連しています。 待ち時間は、一方向またはラウンドトリップ時間 (RTT) として測定されます。
    
- **パケット損失**これは、多くの場合、特定の時間帯に消失したパケットの割合として定義されます。 パケット損失は、オーディオの品質に直接影響を与えます。これは、完全に失われた小さいパケットによって、完全なオーディオのカットアウトを引き起こすバックツーバックのバースト損失になります。
    
- **パケット間の着信のジッターまたは単なるジッター**これは、連続するパケット間の遅延の平均変更です。 Skype for Business などの最新の VoIP ソフトウェアは、バッファー処理によって一定レベルのジッターに対応できます。 これは、ジッタがジッターの効果に気付くというバッファリングを超える場合に限られます。
    
> [!NOTE]
>  ジッタのバッファリングにより、エンドツーエンドの待ち時間が増加します。
  
Skype for Business Online のリアルタイムメディアセッション、および他の Office 365 サービスやその他のビジネスアプリケーションによって生成されるその他のネットワークトラフィックによって、ネットワークパス全体に十分な帯域幅があることを確認します。ネットワークの輻輳を回避し、優れたメディアリアルタイムメディア (オーディオ、ビデオ、およびアプリケーション共有) の品質を確保するために、ネットワークを Skype for Business Online サービスに接続することが重要です。 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>混雑したネットワーク全体でサービスの品質 (QoS) を実装する

また、ネットワーク全体のトラフィック渋滞は、メディアの品質に大きく影響します。 オーディオおよびビデオのパケットがネットワークをより迅速に移動できるようにし、輻輳ネットワーク内の他のネットワークトラフィックに優先順位を付けるには、QoS (Quality of Service) を使って、音声とビデオの通信に最適なエンドユーザーエクスペリエンスを提供することができます。
  
QoS は、オーディオデータまたはビデオデータを伝送するネットワークパケットに優先順位を割り当てるための手段を提供します。 これらのパケットに高い優先順位を割り当てることによって、音声とビデオの通信は、ファイル転送、web 閲覧、データベースバックアップなどのネットワークセッションよりも、ネットワークを介して高速かつ中断される可能性が高くなります。 これは、ファイル転送に使用されるネットワークパケット、または既定ではデータベースのバックアップに、優先度とネットワークの輻輳としては大きな影響を与えないためです。 メディア (オーディオ、ビデオ、およびアプリケーションの共有) パケットに優先度を割り当てずに、"ベストエフォート" として割り当てたままにすると、その他のすべてのネットワークトラフィックと共にそれらも処理されます。 ネットワーク輻輳の量によっては、ユーザーのために全体的な音質とビデオ品質のエクスペリエンスが低下する可能性があります。
  
ネットワーク内のネットワークの輻輳が影響を受けることがないように、QoS をネットワークに実装することを強くお勧めします。 ただし、このような影響を最大にするために、すべてのネットワークエンドポイントは QoS をサポートしている必要があります。つまり、すべてのエンドポイントが QoS マーキングとパケットの優先順位を遵守する必要があります。 Skype for Business Online サービスは、Microsoft ネットワーク内での QoS マーキングと優先順位付けを受け入れます。 ただし、社内ネットワークから Microsoft ネットワークへのインターネットなどのパブリック接続を経由してルーティングされるトラフィックは、QoS マーキングとパケットの優先順位を維持しません。 [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)を使用したネットワークから Office 365 へのプライベート接続は、エンドユーザーの全体的な音声とビデオの品質を向上させるために、QoS マーキングとパケットの優先順位を維持する展開ソリューションを提供します。
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Skype for Business Online に接続するためのネットワークパフォーマンス要件
<a name="bkNetworkPerf"> </a>

Skype for Business のリアルタイムメディアは、さまざまなデバイス、クライアントアプリ、サーバーソフトウェア、および異なるネットワーク間で転送されます。 リアルタイムメディアのエンドツーエンドの待機時間は、すべてのコンポーネントとネットワークセグメントにわたって導入される待機時間の合計です。 エンドツーエンドのネットワーク接続の品質は、最も品質の低いネットワークセグメントによって決まります。 このセグメントは、このネットワークトラフィックのボトルネックとして機能します。
  
次の図は、1つの Skype for Business の参加者から別の会議への一方向のオーディオフローを示しています。
  
![ExpressRoute のコールフロー。](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
この会議シナリオでは、メディアパスは次のネットワークセグメントで構成されています。
  
1. **ユーザー1から Microsoft ネットワークの端への接続**通常、WiFi またはイーサネットなどのネットワーク接続、ユーザー1からインターネット出口ポイント (ネットワークエッジデバイス) への WAN 接続、ネットワークエッジから Microsoft ネットワークエッジへのインターネット接続などが含まれます。
    
2. **Microsoft ネットワーク内の接続**これは、Microsoft Edge と Skype for Business Online データセンター間で、A/V 会議サーバーが使われています。
    
3. **Microsoft ネットワーク内の接続**これは、Skype for Business Online データセンターと Microsoft ネットワークエッジの間にあります。
    
4. **Microsoft ネットワークエッジからユーザー2への接続**これには、ネットワークエッジから Microsoft ネットワークエッジへのインターネット接続、ユーザー2からインターネット出口ポイント (ネットワークエッジ) への WAN 接続、WiFi またはイーサネットなどのネットワーク接続が含まれます。
    
次の図は、Skype for Business Online PSTN 通話のコンポーネントとネットワークセグメントの内訳を示しています。
  
![ExpressRoute PSTN キャリアのコールフロー。](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
PSTN 通話のシナリオでは、メディアパスは以下のネットワークセグメントを横断します。
  
1. **Skype For business クライアントの発信者から Microsoft ネットワークの端への接続**これには通常、WiFi またはイーサネットなどのネットワーク接続、Skype for Business クライアントの発信者からインターネット出口ポイント (ネットワークエッジデバイス) への WAN 接続、ネットワークエッジから Microsoft ネットワークエッジへのインターネット接続などが含まれます。
    
2. **Microsoft ネットワーク内の接続**これは、Microsoft Edge と Skype for Business Online データセンターの間で、仲介サーバーが使用されます。
    
3. **Microsoft ネットワーク内の接続**これは、Skype for Business Online データセンターと Microsoft ネットワークエッジの間にあります。
    
4. **Microsoft ネットワークと PSTN サービスプロバイダパートナーとの接続**これは、Microsoft ネットワークの外部にある Skype for Business クライアントから PSTN 通話を発信するために存在する接続です。
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Skype for Business クライアントから Microsoft ネットワークエッジへのネットワークパフォーマンス要件
<a name="bkSfBClienttoEdge"></a>

Skype for Business の最適なメディア品質を得るため、会社のネットワークから Microsoft ネットワークエッジへの接続には、次のネットワークパフォーマンスメトリックのターゲットまたはしきい値が必要です。 ネットワークのこのセグメントには内部ネットワークが含まれています。これには、すべての WiFi とイーサネット接続、WAN 接続経由の会社のサイト間トラフィック (マルチプロトコルラベル切り替え (MPLS)、インターネットまたは ExpressRoute パートナーなど) が含まれます。Microsoft ネットワークエッジへの接続。
  
> [!CAUTION]
> **会社のネットワーク上の Skype for Business クライアントと Office 365 サービス間の接続は、以下のネットワークパフォーマンス要件としきい値を満たす必要があります。**
  
|||
|:-----|:-----|
|**指標** <br/> |**Target** <br/> |
|遅延 (一方向)  <br/> |< 50 ミリ秒  <br/> |
|遅延 (RTT または往復時間)  <br/> |< 100 ミリ秒  <br/> |
|バースト パケット損失  <br/> |< 任意の 200 ミリ秒間隔で 10%  <br/> |
|パケット損失  <br/> |< 任意の 15 秒間隔で 1%  <br/> |
|パケット到着間ジッター  <br/> |< 15 秒間隔で 30 ミリ秒  <br/> |
|パケットの並べ替え  <br/> |< 順序が適切でないパケットが 0.05%  <br/> |
   
 **その他のパフォーマンスターゲット要件:**
  
- Microsoft ネットワークでは、世界中に160を超えるエッジの場所があります。 このエッジサイトを通じて世界各地の主要インターネットサービスプロバイダ (Isp) と協力しています。 潜在期間の指標の目標は、会社のサイトまたはサイトを想定しており、Microsoft の端が同じ大陸にあることを前提としています。
    
- 会社のサイトまたは Microsoft ネットワークエッジ接続には、WiFi または別のワイヤレステクノロジとして使用できる最初のホップネットワークアクセスが含まれます。 
    
- ネットワークパフォーマンスターゲットは、適切な帯域幅とサービス品質の計画を前提としています。 つまり、これは、ネットワーク接続がピーク負荷の下にあるときに、Skype for Business のリアルタイムメディアトラフィックに直接適用されます。
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>ネットワークエッジから Microsoft ネットワークエッジへのネットワークパフォーマンス要件
<a name="bkYourNetworkEdge"> </a>

ネットワークエッジと Microsoft ネットワークエッジ間の接続に必要なネットワークパフォーマンスのターゲットまたはしきい値を次に示します。 このセグメントには、お客様の内部ネットワークまたは WAN が含まれていません。また、インターネット経由で送信されたネットワークトラフィックをテストするとき、または ExpressRoute パートナーネットワーク経由で送信されるネットワークトラフィックをテストする際のガイダンスとして、パフォーマンスをネゴシエートするときにも使うことができます。ExpressRoute プロバイダーとのサービスレベル契約 (SLA)。
  
> [!CAUTION]
> **会社のネットワークエッジと Microsoft ネットワークエッジ間の接続は、以下のネットワークパフォーマンス要件としきい値を満たす必要があります。**
  
|||
|:-----|:-----|
|**指標** <br/> |**Target** <br/> |
|遅延 (一方向)  <br/> |< 30 ミリ秒  <br/> |
|待機時間 (RTT)  <br/> |< 60 ミリ秒  <br/> |
|バースト パケット損失  <br/> |200ミリ秒間隔で 1% <  <br/> |
|パケット損失  <br/> |< 任意の 15 秒間隔で 0.1%  <br/> |
|パケット到着間ジッター  <br/> |< 任意の 15 秒間隔で 15 ミリ秒  <br/> |
|パケットの並べ替え  <br/> |< 順序が適切でないパケットが 0.01%  <br/> |
   
 **その他のパフォーマンスターゲット要件:**
  
- パフォーマンスターゲットでは、会社のいずれかのネットワークエッジと、それに最も近い Microsoft ネットワークエッジ間の接続が同じ大陸にあることが必要です。
    
- ネットワークパフォーマンスターゲットは、適切な帯域幅とサービス品質の計画を前提としています。 これは、ネットワーク接続がピーク負荷の下にある場合の、Skype for Business のリアルタイムメディアトラフィックにも適用されます。 適切な帯域幅と QoS の計画については、「 [Skype For Business Online の ExpressRoute および qos」](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)を参照してください。
    
## <a name="measuring-network-performance"></a>ネットワークパフォーマンスの測定
<a name="bkNetworkPerf"> </a>

実際のネットワークのパフォーマンスを測定するには (特に、会社のネットワークサイトからネットワークの端まで)、ping などのツールを使用して、Microsoft Edge とデータから実行されている一連の Skype for Business メディアリレーサービスをテストすることができます。センターサイト。 

>[!NOTE]
> Ping (ICMP) を使ったネットワークパフォーマンスの測定は有効ではありません。 そのため、以下のエニーキャスト IP 公開は、2020年1月以降の ICMP 要求への応答を停止します。 ネットワークのパフォーマンスを効果的に測定するには、 [Network Assesment ツール](https://www.microsoft.com/download/details.aspx?id=53885)をお勧めします。
  
Microsoft ネットワークへのインターネット接続をテストするには、Skype for Business メディアリレーの次の Vip に対してテストすることをお勧めします。 *エニーキャスト VIP*は、テストの場所に最も近い Microsoft ネットワークエッジサイトのメディアリレーの IP アドレスに解決されます。
  
||||
|:-----|:-----|:-----|
|**IP アドレス** <br/> |**種類** <br/> |**場所** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide エニーキャスト IP  <br/> |
   
 **ネットワークパフォーマンスの評価については、次の高レベルの推奨事項を参照してください。**
  
- 内部ネットワークと Office 365 への接続を評価する必要があります。
    
- すべてのネットワークのデータを長期間にわたって評価して収集する必要があります。 少なくとも1週間のネットワークパフォーマンスのテストを実施することをお勧めします。そのため、すべての営業日と時間の使用状況パターンを確認できます。 ピーク時間が表示されます。
    
- ネットワークパフォーマンスの測定の複数のサンプルを実行する必要があります。 データを収集している間、会社のサイトから10分ごとに測定を行うことをお勧めします。 Skype for Business Online のネットワークパフォーマンス要件を比較するには、このサンプルデータセットから90th タイルの測定値を取得します。 
    
- ネットワークのパフォーマンスを継続的に評価する必要があります。 ネットワーク使用率は、使用パターンの変更、大量の帯域幅を使用する新しいエンタープライズベースのアプリケーション、組織または物理的な会社の場所への変更などによって、時間の経過と共に変化します。 これらのネットワークパフォーマンス要件とターゲット/しきい値に基づいてネットワークのパフォーマンスを継続的に監視し、最適なリアルタイムのメディア品質を確保するためにタイムリーに調整を行うことが重要です。 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Azure Vm を使ったネットワークパフォーマンスの測定
<a name="bkNetworkPerf"> </a>

Microsoft ネットワークエッジサイトに対するテストの代わりに、Skype for Business のお客様とパートナーが提供するネットワーク評価ソリューションを利用して、Microsoft Azure cloud でのサービスのセットアップのテストを活用してください。 これらのソリューションでは、ネットワーク評価ツールは、Azure cloud でサービスとしてセットアップされたカスタムエンドポイントに対して、待機時間、パケット損失、ジッタをテストします。 このため、テストネットワークトラフィックは、ネットワーク評価サービスをホストするネットワークエッジと Azure データセンター間の Microsoft ネットワーク内の接続という、1つの追加のネットワークセグメントを経由して転送されます。
  
Azure でホストされているテストサービスに基づくネットワーク評価ソリューション。 国または地域内でネットワーク評価を実施することをお勧めします。 たとえば、米国東部の顧客サイトの場合、評価は、Azure の east US データセンター地域でホストされているテストサービスインスタンスに対して実行する必要があります。 
  
以下は、Azure サービスベースのネットワーク評価のセットアップの待機時間 (RTT) のターゲットです。 一方向の待ち時間のターゲットは、対応する RTT ターゲットの半分になります。 パケット損失とジッタの目標は、Skype メディアリレーベースのテスト用に定義されたものと同じままです。
  
|||||
|:-----|:-----|:-----|:-----|
|**顧客の地域** <br/> |**Azure の地域** <br/> |**ネットワークエッジ-Azure 間のラウンドトリップ時間 (RTT)** <br/> |**サイト-Azure のラウンドトリップ時間 (RTT)** <br/> |
|米国中央部  <br/> |米国中央部  <br/> |99  <br/> |139  <br/> |
|米国東部  <br/> |米国東部  <br/> |86  <br/> |126  <br/> |
|北中央アメリカ  <br/> |北中央アメリカ  <br/> |97  <br/> |137  <br/> |
|南部中央アメリカ  <br/> |南部中央アメリカ  <br/> |94  <br/> |134  <br/> |
|米国西部  <br/> |米国西部  <br/> |94  <br/> |134  <br/> |
|米国ハワイ  <br/> |米国西部  <br/> |116  <br/> |156  <br/> |
|カナダ中部  <br/> |カナダ中部  <br/> |138  <br/> |178  <br/> |
|カナダ東部  <br/> |カナダ東部  <br/> |131  <br/> |171  <br/> |
|北ヨーロッパ  <br/> |北ヨーロッパ  <br/> |99  <br/> |139  <br/> |
|西ヨーロッパ  <br/> |西ヨーロッパ  <br/> |95  <br/> |135  <br/> |
|東アジア  <br/> |東アジア  <br/> |118  <br/> |158  <br/> |
|東南アジア  <br/> |東南アジア  <br/> |97  <br/> |137  <br/> |
|日本東部  <br/> |日本東部  <br/> |111  <br/> |151  <br/> |
|西西部  <br/> |西西部  <br/> |118  <br/> |158  <br/> |
|ブラジル南部  <br/> |ブラジル南部  <br/> |70  <br/> |110  <br/> |
|オーストラリア東部  <br/> |オーストラリア東部  <br/> |124  <br/> |164  <br/> |
|オーストラリア南東  <br/> |オーストラリア南東  <br/> |124  <br/> |164  <br/> |
|インド中部  <br/> |インド中部  <br/> |103  <br/> |143  <br/> |
|インド南部  <br/> |インド南部  <br/> |103  <br/> |143  <br/> |
|インド西部  <br/> |インド西部  <br/> |103  <br/> |143  <br/> |
|中国東部  <br/> |中国東部  <br/> |120  <br/> |160  <br/> |
|中国北部  <br/> |中国北部  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>メディアの品質と ExpressRoute
<a name="bkNetworkPerf"> </a>

Office 365 用 Azure ExpressRoute は、Office 365 に接続するための専用ネットワーク接続です。 Office 365 ネットワークトラフィックにかかるパスを管理する機能をユーザーに提供します。 インターネット上では、未知の配送業者、プロバイダー、および Isp によってデータが伝送される予期しないルーティングについて心配する必要はありません。 ExpressRoute 経由で送信されるネットワークトラフィックは、ExpressRoute パートナーのネットワークを介して Microsoft のネットワークに直接送信されます。 これにより、ユーザーは、専用の接続を備えた独自のオフサイトデータセンターにあるかのように Office 365 を扱うことができます。
  
Azure ExpressRoute は、すべての Office 365 ライセンスサービスで利用できます。 ただし、Office 365 でグローバルルーティングを有効にするには、Azure ExpressRoute Premium アドオンが必要です。 Office 365 では、ExpressRoute を実装している少なくとも500座席をお持ちのお客様は、必要な*Expressroute Premium アドオン*を追加料金なしで入手できます。
  
### <a name="is-expressroute-required-for-good-media-quality"></a>適切なメディア品質を使用するには ExpressRoute が必要ですか?

Azure ExpressRoute は、最適な Skype for Business Online メディア品質を得るための要件ではありません。 ただし、クラウド接続が Skype for Business ネットワークパフォーマンスのターゲットまたはしきい値を満たすようにするために役立つ展開オプションの1つです。
  
Office 365 は、インターネットを使用する高パフォーマンスで安全なサービスです。 セキュリティとパフォーマンスを継続的に向上させるために、新しいセキュリティ機能と地域の Edge ノードへの投資を継続しています。 Azure ExpressRoute は、Skype for Business Online などの Office 365 サービスの要件ではありません。 Azure ExpressRoute は、Office 365 への接続が Skype for Business ネットワークパフォーマンス要件を満たしていることを確認し、最適な Skype for Business Online メディア品質を確保するために使用できる展開オプションの1つです。実感.
  
Skype for Business Online のメディアの品質を向上させるには、会社のサイトと Microsoft ネットワークエッジ間の接続が、ネットワークパフォーマンス要件のネットワークのパフォーマンスに関するパフォーマンスの目標を[ネットワークエッジから microsoft ネットワークエッジに](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)までとしていることが[重要となっ](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)ています。  
  
また、社内ネットワークやクラウドの接続性など、ピークメディアトラフィックのボリュームを含む、会社の物理ネットワーク接続も重要です。 Azure ExpressRoute は、お客様が Skype for Business Online クラウド接続をすべて満たしているかどうかを確認するためのさまざまな方法の1つです。
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute は音声品質 SLA に必要ですか?

いいえ。 Skype for Business Online の音声品質 SLA では、ExpressRoute は必要ありません。 [Skype For Business online の音声品質の SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)は、ユーザーがどのような種類の VoIP または PSTN 通話を行うことができるように、適切なライセンスとサブスクリプションで Skype For business online ボイスサービスユーザーが配置した有効な通話に適用されます。 音声品質の SLA には、次のすべての条件に対応する必要があります。
  
- Microsoft 認定 IP 電話からの通話。
    
- 有線イーサネット接続。
    
- Microsoft ネットワークの問題が原因で発生する音声品質の問題。
    
> [!NOTE]
> 音声品質 SLA では、ExpressRoute パートナーやその他のネットワークを含む Microsoft 以外のネットワークの問題によって通話品質の低下が発生している通話は除外されます。 
  
### <a name="internet-or-azure-expressroute"></a>インターネットまたは Azure ExpressRoute?

Skype for Business Online へのネットワーク接続オプションを決定する前に、お客様は、ネットワークパフォーマンス要件に基づいて、「 [skype For Business online に接続する](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)」に記載されているネットワークパフォーマンス要件に基づいて、ネットワークと現在のインターネット接続を評価する必要があります。
  
現在のインターネット接続のネットワークパフォーマンスが、ピーク時に十分な容量に設定されていて、サイトから Microsoft ネットワークエッジに、またはネットワークエッジから Microsoft ネットワークエッジへのネットワークパフォーマンス要件を満たしている場合、引き続き既存のインターネット接続を使用して、Skype for Business Online に接続します。
  
ネットワークパフォーマンス要件が満たされていない企業サイトの場合、最初に既存のネットワークサービスプロバイダーと連携して、全体的なネットワークのパフォーマンスを向上させることを強くお勧めします。 ただし、まだ満たされていない場合は、Azure ExpressRoute を使用することで、ネットワークのパフォーマンス要件を満たすために Skype for Business Online クラウド接続を確実に行うことができます。
  
Azure ExpressRoute には、次のような追加の利点があります。
  
- ネットワークと Microsoft ネットワーク間の接続が利用可能かどうかを、サービスレベル契約 (SLA) で確認します。 ExpressRoute には、保証された可用性の SLA 99.9% があります。
    
- Office 365 サービスに必要な計画と保証された帯域幅。 これを実現するには、Office 365 トラフィックまたは Skype for Business トラフィックのみを ExpressRoute を使って送信し、その他のすべてのインターネットトラフィックを、ネットワークの他のインターネット出口や入口ポイントを経由して送信します。
    
- ExpressRoute は、ネットワークと Microsoft ネットワーク間の DSCP QoS マーキングを保持するように設計されています。
    
ExpressRoute の QoS とキャパシティの計画の詳細については、「 [Skype For Business Online の expressroute と QoS」](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)を参照してください。
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Skype for Business Online 専用に Azure ExpressRoute を設定できますか?

はい、会社のネットワークから Skype for Business Online のみに優れたネットワーク接続を実現するように Azure ExpressRoute を設定することができます。 これにより、ユーザーに最適なリアルタイムのメディア品質が提供されますが、インターネット経由で他の Office 365 サービスへの接続を続けることができます。
  
境界ゲートウェイプロトコル (BGP) は、インターネット上でネットワークトラフィックをルーティングするために使用されるインターネット上のルーティングプロトコルです。 インターネット上で検出された自律システム間でルーティング情報を交換することを目的としています。 BGP コミュニティの値は、入力ルートまたは送信ルートに適用できる属性タグです。 BGP コミュニティは、多くの場合、地理、サービスの種類、またはその他の条件に基づいて、特定の宛先に到達するために使用する送信リンクを受信に通知するために使われます。
  
BGP コミュニティがサポートされている場合、Microsoft は、プレフィックスとルートに属しているサービスに基づいて適切な BGP コミュニティ値をタグ付けします。 Microsoft では、公開ピアリングと Microsoft ピアによってアドバタイズされたプレフィックスに、プレフィックスがホストされている地域を示す適切な BGP コミュニティ値でタグ付けされます。 コミュニティの値に依存して、最適なルーティングを提供するために適切なルーティング決定を行うことができます。 Skype for Business Online の BGP コミュニティの値を使用して、Skype for Business Online の ExpressRoute 接続のみをセットアップすることができます。 詳細については、「 [ExpressRoute ルーティング要件](https://azure.microsoft.com/documentation/articles/expressroute-routing/)」を参照してください。
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Skype for Business Online の ExpressRoute 接続シナリオ
<a name="bkNetworkPerf"> </a>

上記の推奨事項に基づいて ExpressRoute を使用することにした場合は、次の推奨事項をお勧めします。
  
### <a name="online-only-deployment---single-site"></a>オンラインのみの展開-単一サイト

すべてのユーザーが Skype for Business Online サービスを使用していて、オフィスが1つの物理的な場所を中心としていて、Azure ExpressRoute を展開する場合は、会社のサイトと最も近い[expressroute のピアリング場所](https://azure.microsoft.com/documentation/articles/expressroute-locations/)の間に単一の expressroute 接続を設定する必要があります。
  
次の図は、この種類の展開の例を示しています。 この例では、Contoso は FL オーランドである大学です。 Contoso には1万教職員のメンバーと学生がいます。 自分の場所から Microsoft edge サイトへのインターネットテストは、最大のクラス時間に5% を超えるパケット損失を示しました。 ユーザーは、特に Skype for Business Online のリアルタイムトラフィックについて、office 365 のネットワーク輻輳を回避できるように、帯域幅を超えて、ExpressRoute を使用して、Office 365 への専用接続を取得することにしました。 これらのユーザーは、アトランタの GA MeetMe サイトで、ExpressRoute 経由で Microsoft cloud に接続します。
  
![ExpressRoute 単一サイト。](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>オンラインのみの展開-同じ大陸上の複数のサイト

会社が同じ地域または大陸の複数のオフィスから Skype for Business Online サービスを使用していて、Azure ExpressRoute を実装することを選んだ場合は、ExpressRoute 経由でメインサイトを接続し、必要に応じて追加することをお勧めします。推奨されるネットワークパフォーマンスターゲットを満たしていない他の場所の ExpressRoute ピアリング。
  
次の例では、Contoso は米国旅行サービス会社であり、米国内には他の支社があります。 オフィスは、Office 365 への接続に MPLS を使用する WAN 経由で接続されています。 最初は、Hoboken のインターネットルータから ExpressRoute 接続を設定して、ニューヨーク MeetMe サイトに追加しています。 
  
この設定では、ほとんどのサイトから Microsoft ネットワーク (ニューヨークエッジサイト) へのネットワークトラフィックは、「 [skype For business クライアントから microsoft ネットワークエッジへのネットワークパフォーマンス要件](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)」で説明されている Skype for business クライアント接続ネットワークパフォーマンスターゲットを満たすことができます。 ただし、ニューヨークの西海岸オフィス間の遅延は、1方向以上50ミリ秒を超えています。 さらに、ホノルルは Contoso の第2の最大のオフィスであり、ホノルルからニューヨークまでの待ち時間は80ms の1方向を超えています。 これらのオフィスのユーザーにとって良好なメディア品質を確保するために、Contoso は、お客様のサンノゼサイトとシリコンバレー ExpressRoute MeetMe サイトとの間に west coast ExpressRoute 接続を追加することを決定しました。
  
![同じ大陸上の高速ルーターの複数サイト。](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>オンラインのみの展開-複数のサイトに異なる大陸で対応

すべてのユーザーが Skype for Business Online サービスを使用していて、オフィスが複数の大陸の複数の物理的な場所にいる場合は、Azure ExpressRoute を展開することにした場合、各大陸のメインサイト間の少なくとも1つの ExpressRoute 接続を設定して、最も近い[expressroute ピアリングの場所](https://azure.microsoft.com/documentation/articles/expressroute-locations/)にする必要があります。 コスト対利益に応じて、ネットワークパフォーマンスターゲットが満たされないサイトから追加の ExpressRoute 接続を展開することを選択できます。
  
次の例では、Contoso は北米およびヨーロッパの主要都市にオフィスがある大企業法律事務所です。 Contoso は、インターネット接続と内部ネットワークパフォーマンスの評価に基づいて、北アメリカに2つの ExpressRoute 接続を展開し、すべてのヨーロッパ支社に1つの ExpressRoute 回線を導入することを決定しました。
  
![複数のサイトや大陸での ExpressRoute。](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>ハイブリッド展開

オンプレミスの Lync または Skype for Business の展開を使用して、ハイブリッド Skype for Business Online 統合を実装することを選んだ場合、Azure ExpressRoute の展開を決定する場合は、それぞれに少なくとも1つの ExpressRoute 接続が必要です。オンプレミスの Lync または Skype for Business Edge サイトと、オフィスがある大陸ごとに少なくとも1つの ExpressRoute 接続。 各大陸のコストと利点に応じて、ネットワークパフォーマンスのターゲットが満たされていないオフィスから追加の ExpressRoute 接続を展開することを選択できます。
  
オンプレミスの Skype for Business をお持ちの場合は、 [Edge Server の計画と展開ガイド](https://technet.microsoft.com/library/mt346417.aspx)に従う必要があります。 特に、エッジサーバーはネットワークの外部から到達可能である必要があります。 通常、これを実現するには、ルーティング可能なパブリック IP アドレスをエッジサーバーに割り当てるか、ネットワークアドレス変換 (NAT) を使用します。
  
次の例では、Contoso には既存のオンプレミス Skype for Business のエンタープライズボイス展開があります。 オンプレミスユーザーを Office 365 オンラインサービスに移行する必要があります。 また、ハイブリッド展開を使用して、すべてのオンプレミスおよびオンラインのユーザーに対して既存の PSTN インフラストラクチャを引き続き使用できるようにしました。 Contoso のオンプレミスデータセンターと Skype for Business Edge サーバーはシカゴにあります。 Contoso は、展開のために、シカゴのデータセンターとシカゴの ExpressRoute との間に1つの ExpressRoute 接続を設定することを決定しました。 また、ホノルル支社をさらに充実させるために、西海岸 ExpressRoute 接続も追加しました。
  
![ExpressRoute ハイブリッド。](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Cloud Connector エディションを使用したオンライン展開

Skype for Business Online Cloud Connector エディションは、オンプレミスの PSTN 接続を実装する一連のパッケージ仮想マシン (Vm) で構成されるハイブリッドサービスです。 仮想化された環境に Skype for Business Server の最小トポロジを展開することで、既存のオンプレミス PSTN 音声インフラストラクチャを介して、固定電話と携帯電話で通話を送受信できるようになります。
  
Azure ExpressRoute および Cloud Connector エディションを展開する場合は、各大陸のメインサイト間の少なくとも1つの Express Route 接続を、各大陸の主要サイト間で設定することをお勧め[します。](https://azure.microsoft.com/documentation/articles/expressroute-locations/) 各大陸のコストと利点に応じて、ネットワークパフォーマンスのターゲットが満たされていないサイトから追加の ExpressRoute 接続を展開することを選択できます。
  
オンプレミスの Skype for business の展開を使用している場合は、 [skype For Business Cloud Connector Edition の計画ガイド](https://technet.microsoft.com/library/mt605227.aspx)に従う必要があります。 特に、アクセスエッジサービスと A/V Edge サービスには、Office 365 データセンターからのパブリック IP アドレスとアクセス可能なアクセス許可が割り当てられている必要があります。
  
次の例では、Contoso はヨーロッパのいくつかの国と都市に存在するヨーロッパ会計会社です。 Skype for Business Online に対して、共同作業のニーズに合わせてサインアップすると、その国ごとにクラウドコネクタを配置して、既に存在する PSTN インフラストラクチャとキャリア契約を引き続き使用することにしました。 すべてのサイトと Microsoft ネットワークエッジからのテストに基づいて、London の1つの ExpressRoute 接続が、「 [skype For business クライアントから Microsoft ネットワークエッジへのネットワークパフォーマンス要件](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)」で説明されている Skype for business クライアント接続のネットワークパフォーマンス目標を満たしていることを確認しました。
  
![ExpressRoute Cloud Connector One。](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Contoso の別の展開オプションを以下に示します。 この場合、クラウドコネクタが展開されている各サイトで ExpressRoute 接続を設定することにしました。 
  
![ExpressRoute Cloud Connector 2。](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>関連トピック

[Skype for Business Online の ExpressRoute および QoS](expressroute-and-qos-in-skype-for-business-online.md)

  
 
