---
title: Skype for Business Server 2015 での通話受付管理の計画
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Learn about call admission control, which can prevent calls from taking place if they would have poor media quality, in Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 69dc2bd15b5ca8866ce38d96bfaf5cab2f878728
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での通話受付管理の計画
 
Learn about call admission control, which can prevent calls from taking place if they would have poor media quality, in Skype for Business Server Enterprise Voice.
  
テレフォニー、ビデオ、およびアプリケーション共有などの IP ベースのアプリケーションでは、通常、エンタープライズのネットワークで使用可能な帯域幅が LAN 環境内での制限因子とみなされることはありませんが、サイトを相互接続する WAN リンクではネットワーク帯域幅が制限される可能性があります。 
  
ネットワーク トラフィックによって 1 つの WAN リンクが過剰に予約されると、輻輳を解決するため、キュー、バッファー、およびパケット ドロップなどの最新のメカニズムが使用されます。一般に、余分なトラフィックはネットワークの輻輳が緩和されるまで遅延され、必要であれば、そのトラフィックはドロップされます。そのような状況にある従来のデータ トラフィックの場合、受信側のクライアントは回復できます。ただし、統合コミュニケーションなどのリアルタイム トラフィックの場合は、ネットワークの輻輳をこの方法で解決することはできません。これは、統合コミュニケーションのトラフィックが遅延とパケット損失両方の影響を受けやすいからです。WAN で輻輳が発生すると、ユーザーの QoE (Quality of Experience) が低下します。輻輳状態のリアルタイム トラフィックの場合は、低品質での接続を提供するよりも、通話を拒否する方が適切です。
  
通話受付管理 (CAC) では、リアルタイム セッションを許容品質で確立するのに十分なネットワーク帯域幅があるかどうかを判断します。 In Skype for Business Server, CAC controls real-time traffic only for audio and video, but it does not affect data traffic. 既定の WAN パスで必要な帯域幅が確保されていない場合、CAC はインターネット パスまたは公衆交換電話網 (PSTN) を利用した通話のルーティングを試みることができます。 
  
ここでは、通話受付管理機能と CAC の計画方法を説明します。
  
> [!NOTE]
> Skype for Business Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass. For an overview of planning information that is common to all three of these features, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server 2015](network-settings-for-advanced-features.md). 
  
The CAC design in Skype for Business Server offers four main attributes:
  
- 展開と管理が簡単であり、特別に構成されたルーターなど、追加の機器は不要です。
    
- 移動ユーザーや複数の Multiple Point of Presence など、ユニファイド コミュニケーションの重要なユース ケースに対処します。CAC ポリシーは、ユーザーが所属する場所ではなく、エンドポイントが配置されている場所に基づいて適用されます。
    
- 音声通話に加えて、ビデオ通話や音声ビデオ会議セッションなどの、他のトラフィックにも適用できます。
    
- 各種のネットワーク トポロジを柔軟に表示できます。 
    
新しい音声セッションまたはビデオ セッションが WAN リンクに設定されている帯域幅制限を超えた場合、セッションはブロックされるか、(電話での通話のみ) PSTN に再ルーティングされます。
  
CAC では、音声とビデオのリアルタイムのトラフィックのみ制御します。データ トラフィックは制御しません。
  
Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool. CAC settings are automatically propagated to all Skype for Business Server Front End Servers in your network.
  
CAC ポリシーのために失敗した通話では、通話を再ルーティングする優先順位は次のようになります。
  
1. インターネット
    
2. PSTN
    
3. ボイス メール
    
通話詳細記録 (CDR) では、PSTN またはボイス メールに再ルーティングされた通話に関する情報を収集します。 CDR では、インターネットは 2 番目のオプションではなく代替パスとして扱われるため、インターネットに再ルーティングされた通話に関する情報は収集されません。 
  
> [!NOTE]
> ボイス メール デポジットは、帯域幅制限のために拒否されることはありません。 
  
帯域幅ポリシー サービスは、CSV (コンマ区切り値) 形式で 2 種類のログ ファイルを生成します。[**チェックの失敗**] ログ ファイルには、帯域幅要求が拒否されたときの情報が収集されます。 [**リンクの使用率**] ログ ファイルには、ネットワーク トポロジのスナップショットと WAN リンクの帯域幅使用率が収集されます。これらの両方のログ ファイルは、使用率に基づいて CAC ポリシーを細かく調整するのに役立ちます。
  
## <a name="call-admission-control-considerations"></a>通話受付管理に関する考慮事項

The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site. Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites. The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool. The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds. If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again. This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service. Therefore there is the possibility of bandwidth oversubscription of your links during this period 
  
The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools. The Bandwidth Policy Service cannot failover from one Front End pool to another. Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.
  
### <a name="network-considerations"></a>ネットワークに関する考慮事項

Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Skype for Business Server, this restriction is not enforced at the network router (layer 2 and 3). CAC では、CAC ポリシーによって音声とビデオに予約されている帯域幅を含め、データ アプリケーションによって WAN リンク上の全体的なネットワーク帯域幅が使用されないようにすることはできません。 ネットワーク上の必要な帯域幅を保護するために、Differentiated Services (DiffServ) などのサービスの品質 (QoS) プロトコルを展開できます。 そのため、定義する CAC 帯域幅ポリシーと展開する QoS 設定を調整することをお勧めします。
  
### <a name="media-and-signaling-paths-over-vpn"></a>VPN 経由のメディア パスと信号パス

企業が VPN 経由のメディアをサポートする場合、メディア ストリームと信号ストリームの両方が VPN を通過するのか、または両方がインターネット経由でルーティングされるのかを確認します。 既定では、メディア ストリームと信号ストリームは VPN トンネルを通過します。
  
### <a name="call-admission-control-of-outside-users"></a>外部ユーザーの通話受付管理

Call admission control is not enforced beyond the limits of the Skype for Business Server 2015 organization. CAC cannot be applied to the media traffic traversing the Internet, which is not managed by Skype for Business Server 2015. CAC checks will be performed on the portion of the call that flows through the enterprise network if the called endpoint belongs to the organization, and the Edge Server has been added to the network configuration, as described in [Call admission control deployment: final checklist for Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/final-checklist.md). フェデレーション ユーザーまたは PC ユーザーなど、呼び出しのエンドポイントが組織に所属していない場合は、帯域幅ポリシーの確認が実行されず、発信通話では CAC 制限が無視されます。
  
### <a name="call-admission-control-of-pstn-connections"></a>PSTN 接続の通話受付管理

Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk. Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media. It has two connection sides: a side that is connected to Skype for Business Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks. For details about PSTN connections, see [Plan for PSTN connectivity in Skype for Business Server 2015](pstn-connectivity-0.md).
  
CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled. If media bypass is enabled, the media traffic doesn't traverse the Mediation Server but instead flows directly between the Skype for Business client and the gateway. この場合、CAC は不要です。 For details, see [Plan for media bypass in Skype for Business 2015](media-bypass.md).
  
次の図は、メディア バイパスが有効な場合と有効でない場合について、PSTN 接続に CAC がどのように適用されるのかを示しています。
  
**Call admission control enforcement on connections to the PSTN**

![音声 CAC メディア バイパス接続の適用](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)
  
## <a name="defining-your-requirements-for-call-admission-control"></a>組織の通話受付管理サービス要件の定義

通話受付管理 (CAC) を計画するには、エンタープライズ ネットワーク トポロジに関する詳細な情報が必要です。通話受付管理ポリシーの計画を容易にするために、次の手順を実行します。
  
1. Identify the hubs/backbones (called network regions) within your enterprise network.
    
2. Identify the offices or locations (called network sites) within each network region.
    
3. ネットワーク地域の各ペア間のネットワーク ルートを決定します。
    
4. 各 WAN リンクの帯域幅制限を決定します。
    
    > [!NOTE]
    > Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic. When a WAN link is described as "bandwidth-constrained," the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link. 
  
5. 各ネットワーク サイトに割り当てる IP サブネットを特定します。
    
To explain these concepts, we'll use the example network topology shown in the following figure.
  
**Example topology for call admission control**

![Litware Inc. のネットワーク トポロジの例](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)
  
> [!NOTE]
> すべてのネットワーク サイトはネットワーク地域に関連付けられています。たとえば、ポートランド、リノ、およびアルバカーキは北アメリカ地域に含まれています。この図には、帯域幅制限があり、CAC ポリシーが適用されている WAN リンクのみが示されています。シカゴ、ニューヨーク、デトロイトの各ネットワーク サイトは北アメリカ地域の楕円内に示されています。これらは帯域幅が制限されていないので、CAC ポリシーが不要であるためです。 
  
このトポロジ例の各コンポーネントについて、以下のセクションで説明します。 For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering requirements for call admission control in Skype for Business Server 2015](example-gathering-requirements.md).
  
### <a name="identify-network-regions"></a>ネットワーク地域の特定

ネットワーク地域とは、ネットワーク バックボーンまたはネットワーク ハブを示します。
  
ネットワークのバックボーンまたはハブは、ネットワークのさまざまな部分を相互接続するコンピューター ネットワーク インフラストラクチャの一部で、異なる LAN またはサブネット間で情報を交換するためのパスを提供します。バックボーンは、小さな地域から地理的に広範囲な地域までさまざまなネットワークを結合できます。通常、バックボーンの処理能力はバックボーンに接続するネットワークの処理能力よりも高くなっています。
  
このトポロジ例には、北アメリカ、EMEA、APAC の 3 つのネットワーク地域があります。ネットワーク地域には、一連のネットワーク サイト (このトピックで後述するネットワーク サイトの定義を参照) が含まれます。ネットワーク運用チームと連携してネットワーク地域を特定します。
  
### <a name="associating-a-central-site-with-each-network-region"></a>中央サイトと各ネットワーク地域の関連付け

CAC requires that a Skype for Business Server central site is defined for each network region. 中央サイトは、そのネットワーク地域内の他のすべてのサイトへの最適なネットワーク接続と最高帯域幅に基づいて選択されます。 前のネットワーク トポロジの例には 3 つのネットワーク地域が示されており、それぞれに CAC の決定を管理する中央サイトがあります。 前の例の適切な関連付けを次の表に示します。
  
> [!NOTE]
> 中央サイトは、ネットワーク サイトに必ずしも対応しているわけではありません。 このドキュメントの例では、一部の中央サイト (シカゴ、ロンドン、北京) がネットワーク サイトと同じ名前になっています。 However, even if a central site and network site share the same name, the central site is an element of the Skype for Business Server topology, whereas the network site is a part of the overall network in which the Skype for Business Server topology resides. 
  
**Network regions, central sites, and network sites**

|**Network Region**|**Central Site**|**Network Sites**|
|:-----|:-----|:-----|
|北アメリカ  <br/> |シカゴ  <br/> |シカゴ  <br/> ニューヨーク  <br/> デトロイト  <br/> ポートランド  <br/> リノ  <br/> アルバカーキ  <br/> |
|EMEA  <br/> |ロンドン  <br/> |ロンドン  <br/> ケルン  <br/> |
|APAC  <br/> |北京  <br/> |北京  <br/> マニラ  <br/> |
   
### <a name="identify-network-sites"></a>ネットワーク サイトの特定

ネットワーク サイトは、組織の物理的な現場 (オフィス、一連の建物、キャンパスなど) がある場所を表します。 LAN 接続を使用し、他のサイトに WAN 接続された物理的な現場は、ネットワーク サイトと見なされます。 Start by inventorying all of your organization's offices. このトポロジ例では、北アメリカ ネットワーク地域はニューヨーク、シカゴ、デトロイト、ポートランド、リノ、アルバカーキの各ネットワーク サイトで構成されています。
  
すべてのネットワーク サイトをネットワーク地域に関連付ける必要があります。ネットワーク サイトの WAN リンクが制限されているかどうかに応じて、帯域幅ポリシーがネットワーク サイトに関連付けられます。CAC ポリシーと、CAC ポリシーを使用して割り当てる帯域幅の詳細については、このトピックで後述する「帯域幅ポリシーの定義」を参照してください。CAC を構成するには、ネットワーク サイトをネットワーク地域に関連付けます。次に、帯域幅割り当てポリシーを作成して、特定のサイトまたは地域間の帯域幅が制限された接続や、サイトと地域間の WAN 接続に適用します。 
  
### <a name="identify-network-links"></a>ネットワーク リンクの特定

ネットワーク リンクは、異なる地域やサイトにリンクする物理的な WAN への接続を表します。このトポロジの例には、地域のネットワーク リンクが 2 つ、地域とサイト間のネットワーク リンクが 5 つ、2 つのサイト間のネットワーク リンクが 1 つあります。
  
北アメリカと EMEA 間の地域リンクは NA-EMEA-LINK として、APAC と EMEA 間の地域リンクは EMEA-APAC-LINK として表されています。
  
サイト リンクは、ポートランド、リノ、アルバカーキと北アメリカ地域、マニラと APAC 地域、およびケルンと EMEA 地域を接続する線で示されています。リノとアルバカーキ間の線は、これら 2 つのサイト間の直接のネットワーク リンクを表しています。
  
### <a name="define-bandwidth-policies"></a>帯域幅ポリシーの定義

ネットワーク運用チームと連携して、組織の WAN リンクでリアルタイムの音声/ビデオ トラフィックに使用できる WAN 帯域幅量を決定します。通常は、帯域幅使用量が制限される場合 (音声/ビデオ モダリティに割り当てることができる帯域幅よりも帯域幅使用量が多くなると予測される場合) に、帯域幅ポリシーが WAN リンクに適用されます。
  
CAC bandwidth policies define the maximum bandwidth that can be reserved for real-time audio and video modalities. CAC では他のトラフィックの帯域幅を制限しないため、サイズの大きいファイルの転送や音楽のストリーミングなどの他のデータ トラフィックによって、ネットワーク帯域幅がすべて使い果たされるのを防ぐことはできません。
  
CAC 帯域幅ポリシーでは、次のいずれかまたはすべてを定義できます。
  
- 音声に割り当てる最大合計帯域幅
    
- ビデオに割り当てる最大合計帯域幅
    
- 1 つの音声通話 (セッション) に割り当てる最大帯域幅
    
- 1 つのビデオ通話 (セッション) に割り当てる最大帯域幅
    
> [!NOTE]
> All CAC bandwidth values represent the maximum  *unidirectional*  bandwidth limits.
  
> [!NOTE]
> The Skype for Business Server Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user). セッションの確立後、使用帯域幅が正確に計上されます。 この設定は慎重に使用する必要があります。 For details, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) or [Modify a Voice Policy and Configure PSTN Usage Records](http://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx) in the Deployment documentation.
  
セッションあたりの帯域幅使用率を最適化するには、使用される音声およびビデオのコーデック タイプを考慮します。特に、頻繁に使用されることが予想されるコーデックの帯域幅の割り当てが不足しないようにしてください。逆に、多くの帯域幅を必要とするコーデックがメディアで使用されないようにする場合は、このようなコーデックを使用できないようにセッションあたりの最大帯域幅を少なく設定する必要があります。音声の場合、状況によっては使用できないコーデックもあります。次に例を示します。
  
- Peer-to-peer audio calls between Skype for Business endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.
    
- Conference calls between Skype for Business endpoints and the A/V Conferencing service will use either G.722 or Siren.
    
- Calls to the public switched telephone network (PSTN) either to or from Skype for Business endpoints will use either G.711 or RTAudio (8kHz).
    
セッションあたりの最大帯域幅設定を最適化するために次の表を使用してください。
  
**Bandwidth utilization by codecs**

|**Codec**|**Bandwidth requirement with no forward error correction (FEC)**|**Bandwidth requirement with forward error correction (FEC)**|
|:-----|:-----|:-----|
|RTAudio (8kHz)  <br/> |49.8 kbps  <br/> |61.6 kbps  <br/> |
|RTAudio (16kHz)  <br/> |67 kbps  <br/> |96 kbps  <br/> |
|Siren  <br/> |57.6 kbps  <br/> |73.6 kbps  <br/> |
|G.711  <br/> |102 kbps  <br/> |166 kbps  <br/> |
|G.722  <br/> |105.6 kbps  <br/> |169.6 kbps  <br/> |
|RTVideo (CIF 15 fps)  <br/> |260 kbps  <br/> |該当なし  <br/> |
|RTVideo (VGA 30 fps)  <br/> |610 kbps  <br/> |該当なし  <br/> |
   
> [!NOTE]
> 帯域幅要件では、Ethernet II、IP、UDP (ユーザー データグラム プロトコル)、RTP (リアルタイム転送プロトコル)、および SRTP (セキュア リアルタイム転送プロトコル) のオーバーヘッドが考慮されています。また、RTCP のオーバーヘッドとして 10 kbps が付加されています。 
  
G.722.1 と Siren のコーデックは類似していますが、ビット レートが異なります。
  
G.722, the default codec for Skype for Business Server conferencing, is completely different from the G.722.1 and Siren codecs.
  
The Siren codec is used in Skype for Business Server in the following situations:
  
- 帯域幅ポリシーの設定が低すぎて G.722 を使用できない場合
    
- If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Skype for Business Server conferencing service (because those clients do not support the G.722 codec).
    
**Bandwidth utilization by scenario**

|**Scenario**|**Bandwidth requirement optimized for quantity (kbps)**|**Bandwidth requirement for Balanced mode (kbps)**|**Bandwidth requirement optimized for quality (kbps)**|
|:-----|:-----|:-----|:-----|
|ピアツーピアの音声通話  <br/> |45 kbps  <br/> |62 kbps  <br/> |91 kbps  <br/> |
|電話会議  <br/> |53 kbps  <br/> |101 kbps  <br/> |165 kbps  <br/> |
|PSTN calls (between Skype for Business and PSTN gateway, with media bypass)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|PSTN calls (between Skype for Business and Mediation Server, without media bypass)  <br/> |45 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|PSTN calls (between Mediation Server and PSTN gateway, without media bypass)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Skype for Business - Polycom calls  <br/> |101 kbps  <br/> |101 kbps  <br/> |101 kbps  <br/> |
   
### <a name="identify-ip-subnets"></a>IP サブネットの特定

ネットワーク管理者と連携して各ネットワーク サイトに割り当てる IP サブネットを決定する必要があります。ネットワーク管理者が既に IP サブネットをネットワーク地域およびネットワーク サイトに分類している場合、作業は大幅に簡略化されます。
  
この例では、北アメリカ地域のニューヨーク サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットが割り当てられています。普段はデトロイトに勤務している Bob が研修でニューヨークのオフィスに行ったとします。コンピューターを起動してネットワークに接続すると、ニューヨーク用に予約されている 4 つの範囲のいずれか (172.29.80.103 など) の IP アドレスが取得されます。
  
> [!CAUTION]
> The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass. A Skype for Business client takes its local IP address and masks the IP address with the associated subnet mask. When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match. For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets. (If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.) For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Skype for Business will request the bypass ID associated with subnet 172.29.81.0. クライアントが仮想サブネットに属していても、サブネットが 172.29.0.0/16 として定義されている場合、レジストラーは 172.29.81.0 のサブネットのみを検索するため、これを一致と見なしません。 Therefore, it is important that the administrator enters subnets exactly as provided by Skype for Business clients (which are provisioned with subnets during network configuration either statically or by DHCP.) 
  
## <a name="best-practices-for-call-admission-control"></a>通話受付管理のベスト プラクティス

パフォーマンスの向上と展開の簡略化を実現するには、通話受付管理を展開するときに次のベスト プラクティスを適用します。
  
- 現在のメディア トラフィックと予測されるメディア トラフィックに対して WAN が十分にプロビジョニングされていることを確認します。
    
    > [!NOTE]
    > 帯域幅制限にバッファーを考慮することをお勧めします。合計使用帯域幅に影響し、帯域幅制限の超過を招く可能性のある競合状態が発生する場合があります。たとえば、メディア トラフィックが帯域幅制限に近づいているときに 2 つの通話を開始しようとすると、一方の通話の方が早く開始されたためにもう一方の通話が拒否されることがあります。 
  
- 最適な CAC 設定を選択し、ネットワークの使用状況の変化に合わせて CAC 設定を更新できるように、ネットワークの使用状況と通話詳細記録を監視します。
    
- CAC 帯域幅ポリシーを使用して QoS 設定を補完します。
    
- ブロックされた通話を PSTN に再ルーティングする場合、PSTN の機能と処理能力を確認します。 For details, see [Planning Outbound Call Routing](http://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx).
    
    > [!NOTE]
    > 処理能力は、潜在的な PSTN の再ルーティングをサポートするために開く必要のあるポート数を表します。 
  

