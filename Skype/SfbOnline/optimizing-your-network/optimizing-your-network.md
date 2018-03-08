---
title: "ネットワークを最適化します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: "次の要件は、長期的な正常性と成功をすべての skype for Business Online の機能が組織をセットアップしていることを確認する実際に重要です。一部の非常に技術的な -、このドキュメントは、ですが、いくつかのではないことがあると考えています。ヘルプを Skype for Business Online の設定が、必要な場合は、考慮すべき事項を理解するには、このドキュメントをご覧ください。Microsoft FastTrack センター、Microsoft のサービスとアカウント チーム、または Microsoft パートナーは、これらの要件を満たしているかを把握するのには、作業している場合についての注意事項も提供されます。"
ms.openlocfilehash: 1fadaa506331b7f848c007d0b97c0987c7ba212c
ms.sourcegitcommit: f0b8e01e74f63c40e4d4979efe0beef4dde1f6c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2018
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a><span data-ttu-id="0e7ab-106">Skype for Business Online のネットワークを最適化します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-106">Optimizing your network for Skype for Business Online</span></span>

<span data-ttu-id="0e7ab-p102">次の要件は、長期的な正常性と成功をすべての skype for Business Online の機能が組織をセットアップしていることを確認する実際に重要です。一部の非常に技術的な -、このドキュメントは、ですが、いくつかのではないことがあると考えています。ヘルプを Skype for Business Online の設定が、必要な場合は、考慮すべき事項を理解するには、このドキュメントをご覧ください。[Microsoft FastTrack センター](https://fasttrack.microsoft.com/office)Microsoft のサービスとアカウント チームは、これらの要件を満たしているかを把握するのには、 [Microsoft パートナー](https://partnercenter.microsoft.com/en-us/pcv/search)と、作業している場合についての注意事項も提供されます。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p102">The following requirements are really important to ensure the long-term health and success for all Skype for Business Online features you are setting up for your organization. We know some of you are very technical - this document is for you, but there are some of you that aren't. If you need help setting up Skype for Business Online, you should read this document to become familiar with the things you need to consider. It will also give you things to talk about when you are working with the [Microsoft FastTrack Center](https://fasttrack.microsoft.com/office), your Microsoft Services and account teams, or with [Microsoft partners](https://partnercenter.microsoft.com/en-us/pcv/search) to figure out how you can meet these requirements.</span></span>

[<span data-ttu-id="0e7ab-111">Skype for Business Server 2015 でユーザー モデル</span><span class="sxs-lookup"><span data-stu-id="0e7ab-111">User models in Skype for Business Server 2015</span></span>](../../SfBServer/plan-for-skype-for-business-server/capacity-planning/skype-for-business-server-2015-user-models.md)
  
## <a name="a-quick-overview"></a><span data-ttu-id="0e7ab-112">概要</span><span class="sxs-lookup"><span data-stu-id="0e7ab-112">A quick overview</span></span>

<span data-ttu-id="0e7ab-113">Skype for Business では、同僚や組織または世界のビジネス パートナーと接続することができます。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-113">Skype for Business lets you connect with co-workers or business partners in your company or around the world.</span></span>
  
<span data-ttu-id="0e7ab-114">Skype for Business では、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-114">With Skype for Business, you can:</span></span>
  
- <span data-ttu-id="0e7ab-115">IM、音声、またはビデオ通話での会話を開始します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-115">Start conversations with IM, voice, or video calls.</span></span>
    
- <span data-ttu-id="0e7ab-116">ときに、連絡先が利用できる、オンライン会議でプレゼンテーションを行うか。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-116">See when your contacts are available online, in a meeting, or presenting.</span></span>
    
- <span data-ttu-id="0e7ab-117">会議の業務のセキュリティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-117">Set industrial-strength security for meetings.</span></span>
    
- <span data-ttu-id="0e7ab-118">大規模な対象ユーザーをオンラインでブロードキャストします。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-118">Broadcast online to a large audience.</span></span>
    
- <span data-ttu-id="0e7ab-119">会議中に画面を表示または他のユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-119">Present your screen during meetings or give control to others.</span></span>
    
- <span data-ttu-id="0e7ab-120">[Skype for Business 他の Office プログラムを使ってチャット、通話、またはをクリックして会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-120">Use Skype for Business in other Office programs to chat, call, or join a meeting with a click.</span></span>
    
## <a name="why-is-this-all-so-important"></a><span data-ttu-id="0e7ab-121">理由が非常に重要ですか。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-121">Why is this all so important?</span></span>

<span data-ttu-id="0e7ab-p103">リアルタイムのメディア (オーディオ、ビデオ、およびアプリケーションの共有) オーバー IP の品質は大幅に影響を受ける-エンドツー エンド ネットワーク接続の質します。最適な Skype for Business Online のメディアの品質では、それが、会社のネットワークと Skype for Business Online の間の高品質の接続があることを確認する重要です。これを行う最適な方法では、内部ネットワークとネットワークの容量を対応するために [最大使用数トラフィック ボリュームの skype for Business Online、すべての接続に基づくクラウド接続を設定します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p103">The quality of real-time media (audio, video, and application sharing) over IP is greatly impacted by the quality of end-to-end network connectivity. For optimal Skype for Business Online media quality, it is important for you to make sure there is a high-quality connection between your company network and Skype for Business Online. The best way to accomplish this is to set up your internal network and cloud connectivity based on the capacity of your network to accommodate for peak traffic volume for Skype for Business Online across all connections.</span></span>
  
<span data-ttu-id="0e7ab-p104">[Microsoft パートナー](https://partnercenter.microsoft.com/en-us/pcv/search)と連携すると、さまざまな Office 365 アプリケーション Skype for Business Online クラウド リアルタイムの音声、ネットワークに接続できるし、skype for Business ビデオの通信機能が必要サービスは、次の Office 365 リアルタイム ワークロードをサポートする具体的に構成する必要があります。これには、必要なのトラフィック量を実行して、ユーザーのサービスの品質、ビジネス クラスの機能を提供するには、(QoS) をサポートしている十分な帯域幅のあるネットワークが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p104">Working with a [Microsoft partner](https://partnercenter.microsoft.com/en-us/pcv/search), you can connect a variety of Office 365 applications including Skype for Business Online in the cloud to your network and real-time voice and video communications capabilities for Skype for Business require network services must be specifically configured to support these Office 365 real-time workloads. This includes a network that has sufficient bandwidth to carry the required volume of traffic and be capable of supporting Quality of Service (QoS) to deliver a business class experience for your users.</span></span>
  
<span data-ttu-id="0e7ab-127">ここで情報と共に正常を計画および for Business Online のサービスと機能とネットワークのサービスがこのような要件を満たしていることを確認するのには、Skype を展開するために役立つその他のリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-127">Along with the information here, there are other resources that can help you successfully plan and deploy Skype for Business Online services and features and to ensure that your network services meet those requirements:</span></span>
  
- [<span data-ttu-id="0e7ab-128">ExpressRoute を使用して通話のフロー</span><span class="sxs-lookup"><span data-stu-id="0e7ab-128">Call flow using ExpressRoute</span></span>](call-flow-using-expressroute.md)
    
- [<span data-ttu-id="0e7ab-129">ExpressRoute と Skype for Business Online ネットワーク通信</span><span class="sxs-lookup"><span data-stu-id="0e7ab-129">ExpressRoute and QoS in Skype for Business Online</span></span>](expressroute-and-qos-in-skype-for-business-online.md)
    
- [<span data-ttu-id="0e7ab-130">メディアの品質と skype for Business Online のネットワーク接続パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="0e7ab-130">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
## <a name="implement-quality-of-service-qos-for-skype-for-business"></a><span data-ttu-id="0e7ab-131">ビジネス用 Skype (QoS) サービスの品質を実装します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-131">Implement Quality of Service (QoS) for Skype for Business</span></span>

<span data-ttu-id="0e7ab-p105">Skype for Business Online に移動、音声、ビデオ、および共有セッションのトラフィックを処理するネットワークの容量を確認を行う必要があります。Microsoft の利用可能なその他の Office 365 サービスと、会社のサイトごとに、必要なネットワーク トラフィックを決定するための[Skype for Business の帯域幅計算機](https://www.microsoft.com/en-us/download/details.aspx?id=19011)をダウンロードします。トラフィックの量を計算して、そのトラフィックの全体的なネットワークへの影響を分析、モデリング リアルタイム コミュニケーション トラフィック メディア フローと Skype の所在地ごとのトラフィックのビジネスの金額など、使用モデリングを行う必要があります。完了したら、このデータを分析する必要がありますが向上する優れたエンド ユーザー エクスペリエンスを提供するためにキューのサイズをお勧めして、ネットワークが必要があるの推奨事項を提供します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p105">Before moving to Skype for Business Online, you should take a look at your network's capacity to handle audio, video and sharing session traffic. As with other Office 365 services, Microsoft has available for download the [Skype for Business Bandwidth Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=19011) that's used to determine the required network traffic for each of your company sites. You should perform usage modeling, including modeling real-time communication traffic media flows and the amount of Skype for Business traffic per company location, calculating traffic volume, and analyzing how that traffic impacts your overall network. After you've done that, analysis of this data should provide recommendations of where your network needs to be improved and recommend queue sizes in order to provide an excellent end user experience.</span></span>
  
<span data-ttu-id="0e7ab-p106">リアルタイムのトラフィックをビジネス用 Skype では、パケット損失、遅延およびジッター、混雑ネットワークで頻繁に発生する区別します。管理された外部 Wan、管理の内部 Lan および WiFi ネットワークを enterprise ベースのサービスの品質 (QoS) - - クラスのサービスとも呼ばれますを展開も必要があります。これは、適切と優先順位を Skype の音声とビデオなどのビジネス リアルタイム トラフィック用ローカル ネットワーク上の他の非リアルタイム トラフィックを wan、エンドユーザーのエクスペリエンスを向上させる作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p106">Skype for Business real-time traffic is sensitive to packet loss, delay and jitter, which occur frequently in congested networks. Quality of Service (QoS) - sometimes called Class of Service - must also be deployed on managed external WANs, managed internal LANs, and enterprise-based WiFi networks. This will help to properly prioritize Skype for Business real-time traffic such as audio and video over other non-real time traffic on local networks and over WAN, creating a better experience for end users.</span></span>
  
<span data-ttu-id="0e7ab-p107">(優先の転送 - DSCP 46) EF で Skype for Business の音声を展開する必要が、AF41 でキュー」と「Skype for Business ビデオを展開する必要があります (保証の転送 - DSCP 34) キューします。これは、電話システムでの Office 365 またはその他のテレフォニー機能を展開するかどうかに関係なく、ピア ツー ピアおよび会議のトラフィックにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p107">Skype for Business audio must be deployed in the EF (Expedited Forwarding - DSCP 46) queue and Skype for Business video must be deployed in the AF41 (Assured Forwarding - DSCP 34) queue. This is true even for peer-to-peer and conferencing traffic, regardless of whether Phone System in Office 365 or other telephony features are being deployed.</span></span>
  
<span data-ttu-id="0e7ab-p108">既存の QoS ポリシー IP テレフォニーの他の製品の LAN および WAN に既に格納する可能性があります、中には、Skype for Business は、ユーザーとサービスを使用して別の場所に移動するには、モバイルを許可します。このため、QoS ポリシーする必要がありますのマークが付いて LAN、WAN およびワイヤレス ネットワークの管理されたネットワーク経由でビジネス トラフィック用のすべての Skype を優先順位付けされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p108">While existing QoS policies might be in place already on the LAN and WAN for other IP telephony products, Skype for Business allows users to be mobile and to move from location to location while using the service. Because of this, QoS policies must be marked on the LAN, WAN and wireless networks in order to be sure that all Skype for Business traffic is being prioritized across managed networks.</span></span>
  
<span data-ttu-id="0e7ab-143">ネットワークのサイズを変更するために、 [Skype for Business の帯域幅計算機](https://www.microsoft.com/en-us/download/details.aspx?id=19011)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-143">To help you will sizing your network, download the [Skype for Business Bandwidth Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=19011).</span></span>
  
<span data-ttu-id="0e7ab-144">詳細については、メディアの品質と QoS、[メディアの品質と Skype for Business Online でネットワーク接続のパフォーマンス](media-quality-and-network-connectivity-performance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-144">For more about media quality and QoS, see [Media Quality and Network Connectivity Performance in Skype for Business Online](media-quality-and-network-connectivity-performance.md).</span></span>
  
<span data-ttu-id="0e7ab-145">詳細については、セットアップと管理 QoS、[サービスの品質を管理する](https://technet.microsoft.com/en-us/library/gg425841.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-145">For more about setting up and managing QoS, see [Managing Quality of Service](https://technet.microsoft.com/en-us/library/gg425841.aspx).</span></span>
  
## <a name="bypass-proxies-and-wan-optimization-devices"></a><span data-ttu-id="0e7ab-146">プロキシを使用しないと WAN 最適化デバイス</span><span class="sxs-lookup"><span data-stu-id="0e7ab-146">Bypass proxies and WAN optimization devices</span></span>

<span data-ttu-id="0e7ab-p109">すべての Office 365 for Business Online Skype を含む暗号化されており、通常ことはできませんプロキシ デバイスを検査します。これらの理由により、 [Office 365 の Url と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)に、ユーザーの接続として定義されたすべての Office 365 ネットワーク トラフィックのプロキシ デバイスを使用してをお勧めします。プロキシのデバイスがリアルタイムの Skype for Business Online のメディア ストリームで遅延が生じるので、そのトラフィックのでは、少なくともプロキシ デバイスを使用してを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p109">All Office 365 including Skype for Business Online is encrypted and is typically not able to be inspected by proxy devices. For these reasons we recommend bypassing proxy devices for all Office 365 network traffic as defined as connections your users make to [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Since proxy devices will likely introduce delay in real-time Skype for Business Online media streams we strongly recommend bypassing proxy devices at a minimum for that traffic.</span></span>
  
<span data-ttu-id="0e7ab-150">Office 365 のトラフィックのファイアウォールに送信する PAC ファイルを使用して Office 365 の Url を除外することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-150">Microsoft recommends excluding Office 365 URLs using PAC files to send Office 365 traffic to a firewall.</span></span>
  
<span data-ttu-id="0e7ab-151">すぎる場合に役立ついくつかの利用可能なリソースを紹介します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-151">Here are some available resources that can help too:</span></span>
  
- [<span data-ttu-id="0e7ab-152">基準計画とパフォーマンスの履歴を使用して、office 365 パフォーマンスのチューニング</span><span class="sxs-lookup"><span data-stu-id="0e7ab-152">Office 365 performance tuning using baselines and performance history</span></span>](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [<span data-ttu-id="0e7ab-153">ネットワークと Office 365 の移行計画</span><span class="sxs-lookup"><span data-stu-id="0e7ab-153">Network and migration planning for Office 365</span></span>](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [<span data-ttu-id="0e7ab-154">Office 365 プロキシ Pac ジェネレーター</span><span class="sxs-lookup"><span data-stu-id="0e7ab-154">Office 365 Proxy Pac generator</span></span>](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [<span data-ttu-id="0e7ab-155">Office 365 を使って WAN 最適化コント ローラーまたはトラフィック/検査デバイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-155">Using WAN Optimization Controller or Traffic/Inspection devices with Office 365</span></span>](https://aka.ms/kb2690045)
    
- [<span data-ttu-id="0e7ab-156">Office 365 向け ExpressRoute とルーティング</span><span class="sxs-lookup"><span data-stu-id="0e7ab-156">Routing with ExpressRoute for Office 365</span></span>](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## <a name="bypass-double-encryption"></a><span data-ttu-id="0e7ab-157">二重の暗号化を使用しません。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-157">Bypass double encryption</span></span>

<span data-ttu-id="0e7ab-p110">最適な考えられるオーディオとビデオのエクスペリエンスは、ユーザーを提供するには、しないように Skype for Business メディア (音声とビデオ) 仮想プライベート ネットワーク (VPN) トンネルを通過するソリューションを実装する必要があります。トランスポート層セキュリティ (TLS) を暗号化するビジネス トラフィック用のすべての Skype とメディアのワークロードをセキュリティで保護されたリアルタイム プロトコル (SRTP) を暗号化します。TLS 暗号化シグナリングされ、メディア ワークロード SRTP 暗号化されます。このトラフィック VPN トンネルでは、暗号化、およびその他のネットワーク ホップのクライアントと Office 365 の間の余分なレイヤーを追加するには、送信の可能性があります機能性が低下セッション ジッター、パケット損失と待機時間が低下するため。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p110">To provide users the best possible audio and video experience, you must implement a solution that prevents Skype for Business media (audio and video) from traversing a Virtual Private Network (VPN) tunnel. All Skype for Business traffic is encrypted with Transport Layer Security (TLS) and the media workloads are encrypted with Secure Real Time Protocol (SRTP). Signaling is encrypted with TLS and the media workloads are encrypted with SRTP. Sending this traffic over the VPN tunnel adds an extra layer of encryption, and additional network hops between the client and Office 365, both of which can result in a degraded session because it increases jitter, packet loss and latency.</span></span>
  
<span data-ttu-id="0e7ab-p111">1 つのオプションから VPN トンネルを通過するビジネス トラフィック用 Skype を防ぐためには、分割トンネルです。分割トンネルを実装するには、顧客は、VPN ベンダーのソフトウェアで次の操作方法の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p111">One option to prevent Skype for Business traffic from traversing the VPN tunnel is Split Tunneling. To implement split-tunneling, customers should consult with their VPN vendor on the specifics of how to do this in their software.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e7ab-164">これは、Skype for Business のメディアのワークロードに必要なし、その他の Office 365 サービスに適用されていません。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-164">This is only required for the Skype for Business media workloads and isn't applicable to other Office 365 services.</span></span> 
  
<span data-ttu-id="0e7ab-165">追加情報:</span><span class="sxs-lookup"><span data-stu-id="0e7ab-165">Additional resources:</span></span>
  
- [<span data-ttu-id="0e7ab-166">Lync のメディア VPN トンネルのバイパスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-166">Enabling Lync Media to Bypass a VPN Tunnel</span></span>](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- <span data-ttu-id="0e7ab-167">[詳細については、直接アクセス、トンネルの分割] と [強制トンネル](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)</span><span class="sxs-lookup"><span data-stu-id="0e7ab-167">[More on Direct Access, Split Tunneling and Force Tunneling](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)</span></span>
    
- [<span data-ttu-id="0e7ab-168">直接アクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-168">Enable Direct Access</span></span>](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## <a name="ensure-the-right-ports-and-protocols-are-open"></a><span data-ttu-id="0e7ab-169">右側のポートとプロトコルを開いていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-169">Ensure the right ports and protocols are open</span></span>

<span data-ttu-id="0e7ab-p112">ユーザーには、Url および IP の到達ことを確認する必要があります O365 サービスに必要なアドレスです。すべての Skype for Business Online の Url と IP アドレスの完全な一覧については、 [Office 365 の Url と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p112">Customers must ensure reachability of the URLs and IP addresses that are required for the O365 service. For a complete listing of all IP addresses and URLs for Skype for Business Online, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span>
  
<span data-ttu-id="0e7ab-p113">Skype for Business のクライアントは、さまざまなポートとプロトコルを使用します。対話 (ピア ツー ピア vs マルチパーティ) の種類によって異なります方向と Skype for Business セッションのためのネットワーク トラフィックの流れとによっては、コンテンツの共有と音声/ビデオを使用します。確認して、元と移行先ポートに特別な注意を払いのポートとプロトコル] の一覧を開く必要があります。たとえば、オーディオ トラフィックだけ 20 ポート (50000 50019 TCP/UDP) を使用して、クライアント側にあるが接続先ポート任意の場所でサービスの横にある 10 K ポート範囲 (50000 59999 TCP/UDP)。これには、ファイアウォールの TCP 443、UDP 3478 を開いても含まれます。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p113">Skype for Business clients use a variety of ports and protocols. The direction and flow of network traffic for a Skype for Business session will vary depending on the type of interactions (peer-to-peer vs multiparty) and depending on the use of content sharing and voice/video. You must review and open the list of ports and protocols, paying special attention to the source and destination ports. For example, audio traffic uses just 20 ports (50000-50019 TCP/UDP) at the client side, but the destination port could be anywhere in a 10K port range (50000-59999 TCP/UDP) at the service side. This also includes opening TCP 443 and UDP 3478 on the firewall.</span></span>
  
<span data-ttu-id="0e7ab-177">その他のネットワークの構成を必要も Skype for Business Online をサポートしてがあります。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-177">Additional network configuration might also be required to support Skype for Business Online.</span></span>
  
  
## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a><span data-ttu-id="0e7ab-178">使用の携帯電話とデバイス向けに Skype の最適化</span><span class="sxs-lookup"><span data-stu-id="0e7ab-178">Use Phones and Devices Optimized for Skype for Business</span></span>

<span data-ttu-id="0e7ab-p114">リアルタイム メディア セッションでは、ヘッドセットや web カムなどのすべての参加者が使用されているメディア デバイスは、全体的なオーディオとビデオの品質にとても便利な影響を与えます。低品質デバイスまたは正しくないデバイス ドライバーのデバイスのビデオとオーディオの下の画像の品質の下の全体的な音声品質が生成されます。認定済みのデバイスまたはデバイスの品質、に関するヘルプ一方で、[キャンセル通知をエコー、ノイズ フィルター処理、ビデオの解像度がし、待機時間を削減します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p114">In a real-time media session, media devices that are used by all participants such as headsets and web cams have a great impact on the overall audio and video quality. Lower-quality devices or devices with incorrect device drivers will produce lower overall sound quality for audio and lower image quality for video. Certified devices or good quality devices, on the other hand, help with echo cancellation, noise filtering, video resolution and reduce latency.</span></span>
  
<span data-ttu-id="0e7ab-p115">電話とデバイス エンドユーザーの音声とビデオの品質に大きな違いを作成します。Skype for Business の証明書プログラム「Lync 互換性のある」プログラムの進化は、デバイスが音声とビデオの Microsoft の基準を満たしていることを確認します。IP 電話、USB オーディオおよびビデオ デバイス、Pc との会議室デバイスをテストおよび Microsoft によって修飾された数値があります。組織内 Skype for Business、およびさまざまなニーズを満たすために別のデバイスを提供する作業用に最適化されたデバイスのリストとエンドユーザーの個人設定を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p115">Phones and devices make a huge difference in the quality of audio and video for end users. The Skype for Business certification program is an evolution of the "Lync Compatible" program and validates that the device meets Microsoft standards for audio and video. There are a number of IP Phones, USB audio and video devices, PCs and meeting room devices that have been tested and qualified by Microsoft. You should review the list of devices that are optimized for Skype for Business, and work to provide different devices in order to meet the various needs and personal preferences of your end users in your organization.</span></span>
  
<span data-ttu-id="0e7ab-186">サポートされていると、認定済みのデバイスでの詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-186">See the following for more information on supported and certified devices:</span></span>  
  
- [<span data-ttu-id="0e7ab-187">Skype for Business Online 電話を取得します。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-187">Getting phones for Skype for Business Online</span></span>](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [<span data-ttu-id="0e7ab-188">Skype for Business の電話とデバイス</span><span class="sxs-lookup"><span data-stu-id="0e7ab-188">Phones and Devices for Skype for Business</span></span>](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [<span data-ttu-id="0e7ab-189">個人の周辺のソリューション カタログ</span><span class="sxs-lookup"><span data-stu-id="0e7ab-189">Solutions Catalog for Personal Peripherals</span></span>](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [<span data-ttu-id="0e7ab-190">Microsoft Lync の認定された電話とデバイス</span><span class="sxs-lookup"><span data-stu-id="0e7ab-190">Phones and devices qualified for Microsoft Lync</span></span>](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
<span data-ttu-id="0e7ab-p116">環境とユーザーの会議とオーディオおよびビデオ デバイスを使用している配列を周囲の領域は、オーディオとビデオの品質を別の大きな要因です。ノイズの環境からダイヤルインするユーザーがいるエコー、こもった感じ不明確な音声されます。濃いまたは低簡易環境でのユーザーはビデオの消去、明るい画像の品質を作成することはできません。会議室では、マイクとビデオ デバイスの場所は、参加者が受信するサウンドと画像の品質に直接影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p116">The environment and surrounding area where users are meeting and using audio and video devices is another big factor for audio and video quality. Users calling from a noisy environment will have echoed, muffled and unclear audio. Users in a dark or low light environment won't be able to produce bright, clear image quality for video. In a conference room setting, the location of the microphone and video device have a direct impact on the sound and image quality that participants will receive.</span></span>
  
<span data-ttu-id="0e7ab-p117">明確に把握するユーザーの音声とビデオのエクスペリエンスの使用の Skype for Business アプリ**ツール**に > **オプション** > **オーディオ デバイス**または**ビデオ デバイス**で使用するデバイスを変更するの設定をカスタマイズします。**通話品質の確認**] をクリックして、音声通話の品質を確認することもできます。**通話品質の確認**] をクリックした場合は、品質とテスト通話が検出された問題を報告ができます。</span><span class="sxs-lookup"><span data-stu-id="0e7ab-p117">To get a clearer picture of a user's audio and video experience use the Skype for Business app **Tools** > **Options** > **Audio Device** or **Video Device** to make changes to the device in use and customize it's settings. You can also check the audio quality of a call by clicking **Check Call Quality**. If they click **Check Call Quality**, they can then report the quality and issues found with the test call.</span></span>
  
![Skype for Business クライアントの音声をテストします。](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## <a name="related-topics"></a><span data-ttu-id="0e7ab-199">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0e7ab-199">Related topics</span></span> 

[<span data-ttu-id="0e7ab-200">ExpressRoute と Skype for Business Online ネットワーク通信</span><span class="sxs-lookup"><span data-stu-id="0e7ab-200">ExpressRoute and QoS in Skype for Business Online</span></span>](expressroute-and-qos-in-skype-for-business-online.md)
  

