---
title: Media Quality and Network Connectivity Performance
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: This topic defines the set of network performance requirements for Skype for Business Online services and how you can choose to use the Internet or ExpressRoute for connectivity between your network and Skype for Business Online based your assessment of the network connectivity. If you have decided to deploy Azure ExpressRoute for dedicated connectivity to Office 365, this document also provides guidance on how to plan your ExpressRoute connections in different Skype for Business Online deployment scenarios.
ms.openlocfilehash: 438328058ace76beb24bbdf1d64804441694b045
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Media Quality and Network Connectivity Performance in Skype for Business Online

This topic defines the set of network performance requirements for Skype for Business Online services and how you can choose to use the Internet or ExpressRoute for connectivity between your network and Skype for Business Online based your assessment of the network connectivity. If you have decided to deploy Azure ExpressRoute for dedicated connectivity to Office 365, this document also provides guidance on how to plan your ExpressRoute connections in different Skype for Business Online deployment scenarios.
  
The quality of Real-Time media (audio, video, and application sharing) over IP is greatly impacted by the quality of end-to-end network connectivity. For optimal Skype for Business Online media quality, it is important for you to make sure there is a high-quality connection between your company network and Skype for Business Online. The best way to accomplish this is to set up your internal network and cloud connectivity based on the capacity of your network to accommodate for peak traffic volume for Skype for Business Online across all connections.
  
Azure ExpressRoute isn't a requirement for Office 365 services including Skype for Business Online. However, Azure ExpressRoute is one of the deployment options that are available that will help make sure that connectivity to Office 365 meets the Skype for Business network performance requirements and ensures the most optimal Skype for Business Online media quality experience.
  
> [!TIP]
> Although this topic provides you with overall networking performance guidance, complete guidance for network assessment is outside of the scope of this document. To find a list of Skype for Business Online partners who can help you with the network performance measurements as part of a thorough and complete network assessment, please visit [Skype for Business Partner Solutions](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Network connectivity requirements to Skype for Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Factors that impact Skype for Business Online media quality

There are many different factors that contribute to Skype for Business Online Real-Time media (audio, video, and application sharing) quality that include the devices that are used, the environment, and the network connectivity. 
  
#### <a name="devices"></a>Devices

In a Real-Time media session, media capturing and rendering devices that are used by all participants such as headsets and Web cams have a great impact on the overall audio and video quality. Lower quality devices or devices with incorrect device drivers will produce lower overall sound quality for audio and lower image quality for video. Certified devices or good quality devices, on the other hand, help with echo cancellation, noise filtering, video resolution and reduce latency.
  
Although certified audio and video media devices aren't required, it's highly recommended devices certified for Skype for Business for the most optimal media experience. For a list of all Skype for Business certified devices, see [Phones and Devices for Skype for Business](https://technet.microsoft.com/en-us/office/dn947482). You can use the [Skype for Business Online Call Quality Dashboard](../using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard.md), found in the **Skype for Business admin center**, to verify devices in use are working correctly and monitor audio and video media quality.
  
> [!TIP]
> **A certified device is required for the most optimal Skype for Business media quality experience**.
  
It's important to remember that any media devices, Skype for Business clients, and Skype for Business Servers through which Real-Time media flows, introduce some amount of latency. The device and software processing latency, along with network latency, have a great impact on and contribute to the end-to-end overall latency and the end user's experience.
  
#### <a name="environment"></a>Environment

ユーザーが会議を行い、オーディオ デバイスとビデオ デバイスを使用する環境と周辺領域は、オーディオとビデオの品質のもう 1 つの要因です。ノイズのある環境から通話しているユーザーのオーディオは、エコーがかかり、こもっていて、不明瞭です。暗くて照明が不十分な環境にいるユーザーは、ビデオで明るくクリアな画質を実現することができません。会議室の設定で、マイクとビデオ デバイスの場所は、参加者が受信する音声と画像の品質に直接影響します。
  
To get a clearer picture of a user's audio and video experience use the Skype for Business app **Tools** > **Options** > **Audio Device** or **Video Device** to make changes to the device in use and customize it's settings. You can also check the audio quality of a call by clicking **Check Call Quality**. If they click **Check Call Quality**, they can then report the quality and issues found with the test call.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### <a name="network"></a>ネットワーク

The quality of the Real-Time media over IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:
  
- **Latency** This is the time it takes to get an IP packet from point A to point B on the network. This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between. Latency is measured as one-way or Round-trip Time (RTT).
    
- **Packet Loss** This is often defined as a percentage of packets that are lost in a given window of time. Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.
    
- **Inter-packet arrival jitter or simply jitter** This is the average change in delay between successive packets. Most modern VoIP software including Skype for Business can adapt to some levels of jitter through buffering. It's only when the jitter exceeds the buffering that a participant will notice the effects of jitter.
    
> [!NOTE]
>  Buffering for jitter will increase end-to-end latency.
  
With many concurrent Skype for Business Online Real-Time media sessions, as well as other network traffic generated by other Office 365 services and other business applications, making sure that there is sufficient bandwidth over the entire network path that connects your network to the Skype for Business Online service is critical to avoid network congestion and ensure excellent media Real-Time media (audio, video, and application sharing) quality. 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementing Quality of Service (QoS) across congested networks

In addition, traffic congestion across a network will greatly impact media quality. To allow audio and video packets to travel the network quicker and to be prioritized over other network traffic in a congested network, Quality of Service (QoS) can be used to help provide an optimal end-user experience for audio and video communications.
  
QoS provides a way for you to assign higher priorities to network packets that are carrying audio or video data. By assigning a higher priority to these packets, audio and video communications are likely to travel over the network faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups. That's because the network packets used for file transfers or database backups by default are assigned "best effort" as a priority and network congestion won't have as large impact. If you don't assign a higher priority to the media (audio, video, and application sharing) packets and leave them also assigned as "best effort", they too will be processed along with all other network traffic. Depending on the amount of network congestion, this will potentially end up in a lower overall audio and video quality experience for your users.
  
It is highly recommended that you implement QoS on your network to make sure that network congestion within your network won't have an impact. However, for this to have the maximum impact, all networking endpoints must support QoS, meaning that all endpoints must honor QoS marking and packet prioritization. Skype for Business Online services honor QoS marking and prioritization within the Microsoft network. However, traffic that is routed across a public connection like the Internet from your company network to the Microsoft network doesn't preserve QoS markings and packet prioritization. Private connections from your network to Office 365 using [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) offer a deployment solution that preserves QoS markings and packet prioritization that will in turn increase overall audio and video quality for your end users.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Network performance requirements to connect to Skype for Business Online
<a name="bkNetworkPerf"> </a>

Skype for Business Real-Time media travels through many different devices, client apps, server software, and across different networks. The end-to-end latency of Real-Time media is the total amount of latency that is introduced across all components and network segments. The quality of the end-to-end network connection is determined by the network segment with the worst quality. This segment acts as a bottleneck for this network traffic.
  
The following diagram illustrates one-way audio flow in a conference from one Skype for Business participant to another.
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In this conferencing scenario, the media path consists across the following network segments:
  
1. **Connection from User 1 to the edge of the Microsoft network** This usually includes a network connection such as WiFi or Ethernet, the WAN connection from User 1 to the Internet egress point (your network Edge device), and the Internet connection from your network Edge to Microsoft network Edge.
    
2. **Connection within Microsoft network** This is between the Microsoft Edge to Skype for Business Online data center, where the A/V Conferencing servers are used.
    
3. **Connection within Microsoft Network** This is between the Skype for Business Online data center and Microsoft network Edge.
    
4. **Connection from Microsoft network edge to User 2** This includes the Internet connection from your network Edge to Microsoft network Edge, the WAN connection from User 2 to the Internet egress point (your network Edge), and the network connection such as a WiFi or an Ethernet.
    
The following diagram shows breakdown of components and network segments of a Skype for Business Online PSTN call:
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In a PSTN call scenario, the media path crosses the following network segments:
  
1. **Connection from a Skype for Business client caller to the edge of the Microsoft Network** This usually includes a network connection such as WiFi or Ethernet, the WAN connection from the Skype for Business client caller to the Internet egress point (your network Edge device), and the Internet connection from your network Edge to Microsoft network Edge.
    
2. **Connection within Microsoft network** This is between the Microsoft Edge to Skype for Business Online data center, where a Mediation Server is used.
    
3. **Connection within Microsoft Network** This is between the Skype for Business Online data center and Microsoft network Edge.
    
4. **Connection between Microsoft Network and the PSTN service provider partners** This is the connection that exists to place a PSTN call from the Skype for Business client that is outside of the Microsoft network.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Network Performance requirements from a Skype for Business client to Microsoft network Edge
<a name="bkSfBClienttoEdge"></a>

For optimal Skype for Business media quality, the following network performance metrics targets or thresholds are required for a connection from your company's network to the Microsoft network Edge. This segment of the network includes your internal network, this includes all WiFi and Ethernet connections, any company site-to-site traffic over a WAN connection, for example Multiprotocol Label Switching (MPLS), as well as the Internet or ExpressRoute partner connections to the Microsoft network Edge.
  
> [!CAUTION]
> **Connectivity between a Skype for Business client on your company network to Office 365 services must meet these following network performance requirements and thresholds.**
  
|||
|:-----|:-----|
|**Metric** <br/> |**Target** <br/> |
|Latency (one way)  <br/> |< 50 ミリ秒  <br/> |
|Latency (RTT or Round-trip Time)  <br/> |< 100 ミリ秒  <br/> |
|Burst packet loss  <br/> |< 任意の 200 ミリ秒間隔で 10%  <br/> |
|パケット損失  <br/> |< 任意の 15 秒間隔で 1%  <br/> |
|Packet inter-arrival Jitter  <br/> |< 15 秒間隔で 30 ミリ秒  <br/> |
|Packet reorder  <br/> |< 順序が適切でないパケットが 0.05%  <br/> |
   
 **Other performance target requirements:**
  
- The Microsoft network has over 160 Edge locations worldwide. We work with major Internet Service Providers (ISPs) worldwide through those Edge sites. The latency metric target assumes your company site or sites and the Microsoft Edges are on the same continent.
    
- Your company site or sites to the Microsoft network Edge connection include first hop network access, which can be WiFi or another wireless technology. 
    
- The network performance target assumes proper bandwidth and/or quality of service planning. In other words, This applies directly to Skype for Business Real-Time media traffic when the network connection is under a peak load.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Network performance requirements from your network Edge to Microsoft network Edge
<a name="bkYourNetworkEdge"> </a>

The following are the network performance targets or thresholds that are required for the connection between your network Edge and the Microsoft network Edge. This segment of the network excludes the customer's internal network or WAN, and is intended as guidance when testing your network traffic that is sent over the Internet, or through an ExpressRoute partner network and can also be used when negotiating a performance Service Level Agreement (SLA) with your ExpressRoute provider.
  
> [!CAUTION]
> **Connectivity between your company network Edge to the Microsoft network edge must meet these following network performance requirements and thresholds.**
  
|||
|:-----|:-----|
|**Metric** <br/> |**Target** <br/> |
|Latency (one way)  <br/> |< 30 ミリ秒  <br/> |
|Latency (RTT)  <br/> |< 60 ミリ秒  <br/> |
|Burst packet loss  <br/> |< 任意の 200 ミリ秒間隔で 1%  <br/> |
|パケット損失  <br/> |< 任意の 15 秒間隔で 0.1%  <br/> |
|Packet inter-arrival Jitter  <br/> |< 任意の 15 秒間隔で 15 ミリ秒  <br/> |
|Packet reorder  <br/> |< 順序が適切でないパケットが 0.01%  <br/> |
   
 **Other performance target requirements:**
  
- The performance target requires connection between any of your company's network Edge and its nearest Microsoft network Edge, to be on the same continent.
    
- The network performance target assumes proper bandwidth and/or quality of service planning. This also applies to Skype for Business Real-Time media traffic when the network connection is under a peak load. For proper bandwidth and QoS planning, please refer to [ExpressRoute and QoS in Skype for Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## <a name="measuring-network-performance"></a>Measuring network performance
<a name="bkNetworkPerf"> </a>

To measure the actual network performance, especially for latency and packet loss, from any company network site to a network Edge, you can use tools such as ping, test against a set of Skype for Business media relay services running from the Microsoft Edge and data center sites. 
  
For testing Internet connections to the Microsoft network, it is recommended that you test against the following VIPs of the Skype for Business media relays. The *Anycast VIP*  will resolve to an IP address of a Media Relay in a Microsoft network Edge site that is closest to the testing location.
  
||||
|:-----|:-----|:-----|
|**IP address** <br/> |**Type** <br/> |**場所** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide Anycast IP  <br/> |
   
 **Here are some high level recommendations to follow for assessing network performance:**
  
- You should assess your internal network as well as the connections to Office 365.
    
- You should assess and gather data for all of your networks over a long period of time. We recommend for you to perform your testing of network performance for a minimum of a week, so that you can see usage patterns for all business days and hours. This will show you peak times.
    
- You should take multiple samples of network performance measurements. We recommend taking a measurement every 10 minutes from a company site during the entire period of time you are gathering data. For comparing the Skype for Business Online network performance requirements, take the 90th percentile measurement value from this sample data set. 
    
- You should continuously assess the network's performance. Network utilization varies over time due to usage pattern changes, new enterprise-based applications that use a large amount of bandwidth, and changes to your organizational or physical company locations. It is important for you to continuously monitor your network performance against these network performance requirements and targets/thresholds and make timely adjustments to ensure the most optimal Real-Time media quality. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Measuring Network Performance using Azure VMs
<a name="bkNetworkPerf"> </a>

Instead of testing against the Microsoft network Edge sites, there are network assessment solutions from Skype for Business customers and partners that leverage testing setup for services in the Microsoft Azure cloud. In those solutions, the network assessment tools test latency, packet loss and jitter against custom endpoints set up as a service in the Azure cloud. As a result, the test network traffic travels through one additional network segment, which is the connection within the Microsoft network between the network edges and Azure data centers that hosts the network assessment service.
  
For those network assessment solutions based on Azure hosted testing services. We recommend performing the network assessment within country and/or region. For example, for customer sites in east U.S., the assessment should be performed against a testing service instance hosted in Azure's east US data center region. 
  
Below are the latency (RTT) targets for the Azure service based network assessment setup. The one-way latency targets will be half of the corresponding RTT targets. The packet loss and jitter goals stays the same as those defined for Skype Media Relay based testing.
  
|||||
|:-----|:-----|:-----|:-----|
|**Customer region** <br/> |**Azure region** <br/> |**Your network Edge - Azure Round-trip Time (RTT)** <br/> |**Your Site - Azure Round-trip Time (RTT)** <br/> |
|Central US  <br/> |Central US  <br/> |99  <br/> |139  <br/> |
|East US  <br/> |East US  <br/> |86  <br/> |126  <br/> |
|North Central US  <br/> |North Central US  <br/> |97  <br/> |137  <br/> |
|South Central US  <br/> |South Central US  <br/> |94  <br/> |134  <br/> |
|West US  <br/> |West US  <br/> |94  <br/> |134  <br/> |
|Hawaii US  <br/> |West US  <br/> |116  <br/> |156  <br/> |
|Canada Central  <br/> |Canada Central  <br/> |138  <br/> |178  <br/> |
|Canada East  <br/> |Canada East  <br/> |131  <br/> |171  <br/> |
|North Europe  <br/> |North Europe  <br/> |99  <br/> |139  <br/> |
|West Europe  <br/> |West Europe  <br/> |95  <br/> |135  <br/> |
|East Asia  <br/> |East Asia  <br/> |118  <br/> |158  <br/> |
|Southeast Asia  <br/> |Southeast Asia  <br/> |97  <br/> |137  <br/> |
|Japan East  <br/> |Japan East  <br/> |111  <br/> |151  <br/> |
|Japan West  <br/> |Japan West  <br/> |118  <br/> |158  <br/> |
|Brazil South  <br/> |Brazil South  <br/> |70  <br/> |110  <br/> |
|Australia East  <br/> |Australia East  <br/> |124  <br/> |164  <br/> |
|Australia Southeast  <br/> |Australia Southeast  <br/> |124  <br/> |164  <br/> |
|Central India  <br/> |中央インド  <br/> |103  <br/> |143  <br/> |
|South India  <br/> |South India  <br/> |103  <br/> |143  <br/> |
|West India  <br/> |西インド  <br/> |103  <br/> |143  <br/> |
|China East  <br/> |China East  <br/> |120  <br/> |160  <br/> |
|中国北部  <br/> |中国北部  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Media quality and ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute for Office 365 is a dedicated network connection for connecting to Office 365. It offers customers the ability to have control over the path their Office 365 network traffic takes. They no longer have to be concerned with the unpredictable routing that happens on the Internet where data is carried by unknown carriers, providers and ISPs. ExpressRoute 経由で送信されるネットワーク トラフィックは、マイクロソフトのネットワークに、ExpressRoute パートナーのネットワーク経由で直接送信されます。 これにより、専用接続を使用して独自のオフサイトのデータ センターに配置されているかのように、Office 365 を扱います。
  
Azure ExpressRoute is available for all Office 365 licensing offerings. ただし、Azure ExpressRoute プレミアムのアドオンは、グローバルなルーティングを有効にするのには Office 365 の必要があります。 ExpressRoute を実装している、接続クライアント数が 500 以上での office 365 のお客様では、ない余計な出費で必要な*ExpressRoute のプレミアム ・ アドオン*を取得できます。
  
### <a name="is-expressroute-required-for-good-media-quality"></a>適切なメディアの品質の ExpressRoute が必要ですか。

Azure の ExpressRoute では、ビジネス オンラインのメディアの品質の最適の Skype を取得する必要はありません。 ただし、1 つの展開を支援するオプションを確認、クラウドの接続が、Skype ビジネス ネットワークのパフォーマンスの目標のしきい値を満たしています。
  
Office 365 は、高いパフォーマンスとセキュリティで保護されたサービス、インターネットを使用するには。 私たちは、継続的にセキュリティとパフォーマンスを向上させるには、新しいセキュリティ機能と地域のエッジのノードへの投資に進みます。 Azure の ExpressRoute では、Office 365 サービスの Skype を含むオンライン ビジネスのための必要条件はありません。 Azure の ExpressRoute は、展開のいずれかのオプションが利用可能な有用な Office 365 への接続は、Skype のビジネス ネットワークのパフォーマンスの要件を満たしているし、確実にビジネスのオンラインのメディアの品質を最適な Skype かどうかを確認発生します。
  
ビジネス オンラインのメディアの品質の Skype は、企業サイトと Microsoft ネットワークのエッジ間の接続が、Skype のビジネスのクライアントから Microsoft ネットワークへの[ネットワークのパフォーマンス要件のパフォーマンス目標を満たしていることが重要です。エッジ](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)、ネットワークのエッジと、Microsoft ネットワークのエッジ間の接続が[ネットワークに Microsoft ネットワーク エッジのエッジからネットワークのパフォーマンス要件](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)のパフォーマンス目標を満たしているとします。  
  
ピーク時のメディア トラフィックの量が、内部ネットワークとクラウドの接続の容量を含む、企業の物理的なネットワーク接続に対応できることが重要です。 Azure の ExpressRoute は、お客様がオンライン ビジネスのクラウド接続用の Skype では、これらのパフォーマンス要件をすべて満たしていることを確認する多くの方法の 1 つです。
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>音声品質の SLA には、ExpressRoute が必要ですか。

残念ですが、ExpressRoute オンライン音声品質の SLA のビジネス用の Skype の必要はありません。 [オンライン音声品質の SLA のビジネス用の Skype](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)は、正しいライセンスと VoIP または PSTN の呼び出しの任意の型を作成するには、そのユーザーを有効にするサブスクリプション内でのオンライン ビジネスの音声サービスのユーザーは、Skype での配置の対象となる呼び出しに適用されます。 音声品質の SLA では、次の条件のすべてを網羅したを含める必要があります。
  
- マイクロソフトからの呼び出しは、IP 電話を認定します。
    
- ワイヤード (有線) イーサネット接続です。
    
- Microsoft ネットワークの問題のための音声品質の問題です。
    
> [!NOTE]
> 音声品質の SLA では、ExpressRoute パートナーおよびその他のネットワークを含むサードパーティ製のネットワークの問題の低い呼び出し品質が原因となったこれらの呼び出しを除外します。 
  
### <a name="internet-or-azure-expressroute"></a>インターネットまたは Azure ExpressRoute でしょうか。

お客様のビジネス オンラインの Skype への接続性オプションのネットワーク上の意思決定を行う、前にネットワークおよび現在インターネットに接続するネットワークのパフォーマンスの要件を[に記載されているネットワークのパフォーマンス要件に基づいて評価する必要があります。Skype への接続は、オンライン ビジネスの](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)です。
  
ピーク時との間に十分な容量に Microsoft ネットワークのエッジにサイトおよび Microsoft ネットワークのエッジに、ネットワークのエッジからのネットワークのパフォーマンスの要件を満たしている現在のインターネット接続経由でネットワークのパフォーマンスが設定されている場合は、することができます。ビジネス オンラインの Skype に接続する、既存のインターネット接続を使用し続けます。
  
ネットワーク パフォーマンスの要件は満たされている会社のサイトを最初に対処する、全体的なネットワーク パフォーマンスを向上させるために、既存のネットワーク サービス プロバイダーを強くお勧めします。 ただし、それらはまだ中が満たされた場合、Azure の ExpressRoute を使用して防止できますオンライン ビジネスのクラウドの接続のため、Skype を使用して、ネットワークのパフォーマンス要件に対応できます。
  
Azure の ExpressRoute には、次の他のメリットが用意されています。
  
- サービス レベル契約 (SLA) の可用性、ネットワークと Microsoft のネットワーク間の接続。 ExpressRoute では、99.9% の保証、可用性 SLA があります。
    
- Office 365 サービスに必要な計画的および保証された帯域です。 ExpressRoute を使用してビジネス ・ トラフィックの Skype または Office 365 のトラフィックのみを送信することによってこれを達成し、他のすべてのインターネット トラフィックがネットワークの他のインターネットの egress または ingress ポイントを通過できます。
    
- ExpressRoute は、ネットワークと Microsoft のネットワークとの間の QoS の DSCP マーキングを保持するために設計されています。
    
ExpressRoute QoS とキャパシティ ・ プランニングの詳細については、 [ExpressRoute とオンライン ビジネスの Skype で QoS](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US)を参照してください。
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>できますセットアップ Azure ExpressRoute Skype のオンラインのみビジネスでしょうか。

はい、オンライン ビジネスの Skype だけに、社内ネットワークから最適なネットワーク接続を確認するのには Azure ExpressRoute を設定することができます。 これは、リアルタイムのメディア品質を最適なユーザーが、インターネット経由で他の Office 365 サービスに接続を続行することができますし。
  
ボーダー ゲートウェイ プロトコル (BGP) は、インターネット経由でネットワーク トラフィックをルーティングするために使用されるインターネット上のルーティング プロトコルです。 自律システム (AS) 間で、インターネット経由でルーティング情報を交換するために設計されています。 BGP コミュニティの値は、着信または発信ルートに適用できる属性のタグです。 BGP コミュニティは地理的条件、サービスの種類またはその他の条件に基づいて特定の宛先に到達するために外部リンクとして受信する信号によく使用されます。
  
BGP コミュニティ サポートでは、Microsoft がプレフィックスおよびルートをタグ付けに属しているサービスに基づいて、適切な BGP コミュニティの値には。 マイクロソフトはパブリック ・ ピアリングによって通知されたプレフィックスにタグを付けるし、ピアリングの領域を示す、適切な BGP コミュニティの値を持つマイクロソフトの接頭番号がでホストされています。 コミュニティの最適なルーティングを提供する適切なルーティングを決定する値を使用できます。 オンライン ビジネスの ExpressRoute への接続をセットアップするビジネス オンライン BGP コミュニティの値の Skype は、Skype を使用できます。 [ExpressRoute ルーティングの要件](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/)の詳細が表示されます。
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>ビジネス オンラインの Skype の ExpressRoute 接続のシナリオ
<a name="bkNetworkPerf"> </a>

するは、前述の推奨事項に基づく ExpressRoute、ここでは、についての推奨事項と ExpressRoute 接続の数を決定する場合が表示されます。
  
### <a name="online-only-deployment---single-site"></a>オンラインのみの展開: 1 つのサイト

会社のサイトに最も近いの間で 1 つの ExpressRoute 接続を設定する必要があります、Skype を使用して、オンライン ビジネス サービスのすべてのユーザーと、オフィスが 1 つの物理的な場所の中心し、Azure の ExpressRoute の展開を決定する場合は、[ExpressRoute ピアリングの場所](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)です。
  
次の図は、この種類の配置の例を示します。 この例では、contoso 社はオーランド (フロリダ) にある大学です。 Contoso には、10,000 の教職員と生徒がいます。 エッジのマイクロソフトのサイトにその場所からインターネットのテストは、クラスのピーク時に 5% のパケットの損失よりも大きいことがわかりました。 ビジネス オンラインのリアルタイム トラフィックの Skype の特に Office 365 をネットワークの輻輳を回避することができますので、帯域幅が過剰にプロビジョニングされた ExpressRoute を使用して Office 365 に専用の接続を取得することにしました。 ジョージア州アトランタ MeetMe サイトで ExpressRoute をマイクロソフトのクラウドに接続するとします。
  
![ExpressRoute の 1 つのサイトです。](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>オンラインのみの展開: 同じ大陸の複数のサイト

ExpressRoute を使用して、メインのサイトに接続し、必要に応じて追加することを推奨、会社が同じ地域または大陸の複数のオフィスからオンライン ビジネス サービスの Skype を使用して、Azure の ExpressRoute を実装するために選択した場合は、推奨されるネットワークのパフォーマンス目標を満たしていない他の場所のピアリング ExpressRoute。
  
次の例では、Contoso は、ニューヨークに本社を置くが、米国全体での他のオフィスがある米国の旅行サービス会社です。 オフィスでは、MPLS を使用して Office 365 に接続するため、WAN を介して相互に接続されました。 初期設定、インターネットのルーターから ExpressRoute への接続をニュージャージー州 Hoboken でニューヨーク MeetMe サイトにします。 
  
この設定により、Microsoft のネットワーク (ニューヨークのエッジ ・ サイト) に、サイトのほとんどからのネットワーク トラフィックが、Skype のビジネス クライアントの接続ネットワークでのパフォーマンスの目標が、Skype のビジネスのクライアントからネットワークのパフォーマンス要件を[に記載されているを満たすことができます。マイクロソフト ネットワークのエッジ](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)。 ただし、contoso 社の西海岸のオフィスからニューヨークまでの待機時間は一方向の往復をでしょう。 さらに、ホノルルには、contoso 社の第 2 位のオフィス、ホノルルからニューヨークまでの待機時間が一方向 80ms を超えています。 これらのオフィスのユーザーの適切なメディアの品質保証のため、contoso 社は、サンノゼのサイトとシリコン バレーの ExpressRoute MeetMe サイトとの間の西海岸 ExpressRoute の接続を追加することにしました。
  
![同じ大陸のルーターの高速のマルチ サイトです。](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>オンラインのみの展開: 別の大陸に複数のサイト

オンライン ビジネス サービスは、Skype を使用しているすべてのユーザーと、オフィスでは、複数の大陸にわたって複数の物理的な場所で、Azure ExpressRoute の展開を決定する場合場合、は、大陸ごとに少なくとも 1 つの ExpressRoute 接続を設定する必要があります。間の最も近い[ExpressRoute ピアリングの場所](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)に各大陸のメインのサイトです。 費用 vs 効果では、によって、ネットワークのパフォーマンスの目標は満たされているサイトからの追加の ExpressRoute 接続を展開する選択できます。
  
次の例では、Contoso は、北アメリカ、ヨーロッパ主要都市にオフィスを持つ大規模な企業の法律事務所をします。 Contoso 社は、インターネットに接続し、内部ネットワークのパフォーマンス評価に基づき、北米、ヨーロッパのすべてのオフィスの 1 つの ExpressRoute 回路の 2 つの ExpressRoute 接続を展開することにしました。
  
![複数のサイトおよび大陸に ExpressRoute。](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>ハイブリッド展開

設置、Lync がある場合またはビジネス展開するための Skype オンライン ビジネスの統合のためのハイブリッド Skype を実装して、Azure の ExpressRoute を展開する場合は、する必要がありますごとに少なくとも 1 つの ExpressRoute 接続を確立することをお勧めします。設置 Lync または Skype ビジネス エッジ ・ サイトとオフィスの大陸ごとに少なくとも 1 つの ExpressRoute 接続します。 によってコストとメリット、大陸ごとに選択できますからオフィスのネットワークのパフォーマンスの目標は満たされている追加の ExpressRoute 接続を展開します。
  
ビジネス展開するため、設置型の Skype を使っている場合[エッジ サーバーの計画と展開ガイド 』](https://technet.microsoft.com/en-us/library/mt346417.aspx)に従う必要があります。 具体的には、エッジ トランスポート サーバーは、外部ネットワークから到達可能でなければなりません。 エッジ サーバーにルーティング可能なパブリック IP アドレスを割り当てることによって、またはネットワーク アドレス変換 (NAT) を使用して、これは、通常です。
  
次の例では、Contoso は、ビジネスのエンタープライズ VoIP 展開の既存のオンプレミス Skype をいます。 オンプレミス ユーザーを Office 365 のオンライン サービスに移行します。 すべての設置とオンラインのユーザー、PSTN の既存のインフラストラクチャを使用することが続行できるように、ハイブリッド展開を使用することも決定します。 Contoso 社のデータ センターの設置とエッジ トランスポート サーバーのビジネス用の Skype は、シカゴでは。 展開、contoso 社は、シカゴのデータ センターとシカゴの ExpressRoute との間の 1 つの ExpressRoute 接続を設定することにしました。 西海岸、ホノルルのオフィスのサービス向上のために ExpressRoute の接続を追加します。
  
![ExpressRoute ハイブリッド。](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>クラウド コネクタ版でオンラインの展開

クラウド コネクタ エディションのオンライン ビジネスの Skype は、オンプレミスの PSTN への接続を実装するパッケージ化された仮想マシン (Vm) のセットで構成されるハイブリッドを提供することです。 ビジネス サーバー トポロジの場合、仮想化された環境で最小限の Skype を配布すると、landlines と既存のオンプレミス PSTN 音声インフラストラクチャを通じて、携帯電話で通話を送受信することができます。
  
Azure ExpressRoute とコネクタのエディションをクラウドに展開すると、大陸ごとの最も近い[ExpressRoute ピアリングの場所](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)にメインのサイトとの間には、各大陸の 1 つ以上の高速ルート接続を設定することをお勧めします。 によってコストとメリット、大陸ごとに選択できますネットワークのパフォーマンスの目標は満たされているサイトからの追加の ExpressRoute 接続を展開します。
  
ビジネス展開するため、設置型の Skype を使っている場合は、 [Skype ビジネス クラウド コネクタ ・ エディションのための計画ガイド](https://technet.microsoft.com/EN-US/library/mt605227.aspx)に従ってください。 具体的には、アクセス エッジ、A と、音声ビデオ エッジ サービスに対して、パブリック IP アドレスを割り当てる必要があります、Office 365 のデータ ・ センターから到達可能です。
  
次の例では、Contoso は、いくつかの主要なヨーロッパの国や都市でのプレゼンスを持つヨーロッパの会計事務所です。 サインアップと Skype のオンライン ビジネスのすべての共同作業のニーズに、引き続き、PSTN のインフラストラクチャを使用する物理的な場所がある国およびキャリアの契約が既に存在しているクラウドのコネクタを配置することにしました。 ビジネス クライアントの接続ネットワークのパフォーマンス目標が[ネットワークのパフォーマンス」に記載の Skype を満たすロンドンの 1 つの ExpressRoute 接続を役立つことに決定、すべてのサイトおよび Microsoft ネットワークのエッジからテストに基づき、マイクロソフト、Skype のビジネスのクライアントからの要件は、エッジをネットワーク](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)。
  
![ExpressRoute クラウド コネクタ 1 つです。](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Contoso 社の他の配置オプションを次に示します。 この例では、クラウドのコネクタが展開されている各サイトの ExpressRoute への接続を設定することにしました。 
  
![ExpressRoute クラウド コネクタ 2 つです。](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>関連トピック

[Skype for Business Online の ExpressRoute および QoS](expressroute-and-qos-in-skype-for-business-online.md)

