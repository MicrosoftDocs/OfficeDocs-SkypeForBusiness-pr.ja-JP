---
title: ネットワークの最適化
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 組織のために設定しているすべての Skype for Business Online の機能を長期間にわたり健全で正常に使用するには、次の要件に従うことが重要です。このドキュメントは技術的な専門性に長けているユーザー向けですが、専門的な知識がないユーザーにとっても参考になります。Skype for Business Online の設定でサポートが必要な場合は、このドキュメントをお読みの上、検討する必要がある事項についてよく理解するようにしてください。このドキュメントは、Microsoft FastTrack Center、お客様の Microsoft Services とアカウント チーム、または Microsoft パートナーと連携してこれらの要件に適合できる方法を見つけ出すときに検討が必要な内容も記載しています。
ms.openlocfilehash: 5101b59c4e911f6fbad36ff2c601428a8fa25177
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010950"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a><span data-ttu-id="d0cdc-106">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="d0cdc-106">Optimizing your network for Skype for Business Online</span></span>

<span data-ttu-id="d0cdc-p102">[] 組織のために設定しているすべての Skype for Business Online の機能を長期間にわたり健全で正常に使用するには、次の要件に従うことが重要です。このドキュメントは技術的な専門性に長けているユーザー向けですが、専門的な知識がないユーザーにとっても参考になります。Skype for Business Online の設定でサポートが必要な場合は、このドキュメントをお読みの上、検討する必要がある事項についてよく理解するようにしてください。このドキュメントは、[Microsoft FastTrack Center](https://fasttrack.microsoft.com/office)、お客様の Microsoft Services とアカウント チーム、または [Microsoft パートナー](https://partnercenter.microsoft.com/pcv/search)と連携してこれらの要件に適合できる方法を見つけ出すときに検討が必要な内容も記載しています。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p102">The following requirements are really important to ensure the long-term health and success for all Skype for Business Online features you are setting up for your organization. We know some of you are very technical - this document is for you, but there are some of you that aren't. If you need help setting up Skype for Business Online, you should read this document to become familiar with the things you need to consider. It will also give you things to talk about when you are working with the [Microsoft FastTrack Center](https://fasttrack.microsoft.com/office), your Microsoft Services and account teams, or with [Microsoft partners](https://partnercenter.microsoft.com/pcv/search) to figure out how you can meet these requirements.</span></span>

## <a name="a-quick-overview"></a><span data-ttu-id="d0cdc-111">簡単な概要</span><span class="sxs-lookup"><span data-stu-id="d0cdc-111">A quick overview</span></span>

<span data-ttu-id="d0cdc-112">Skype for Business を使うと、社内または世界中の同僚やビジネス パートナーと連絡することができます。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-112">Skype for Business lets you connect with co-workers or business partners in your company or around the world.</span></span>

<span data-ttu-id="d0cdc-113">Skype for Business では次のことができます。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-113">With Skype for Business, you can:</span></span>

- <span data-ttu-id="d0cdc-114">IM、音声、ビデオ通話で会話を開始する。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-114">Start conversations with IM, voice, or video calls.</span></span>

- <span data-ttu-id="d0cdc-115">オンライン、会議、発表で連絡先がいつ利用可能かを確認する。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-115">See when your contacts are available online, in a meeting, or presenting.</span></span>

- <span data-ttu-id="d0cdc-116">業務用の強力なセキュリティを会議に設定する。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-116">Set industrial-strength security for meetings.</span></span>

- <span data-ttu-id="d0cdc-117">オンラインでの多数の出席者に対するブロードキャスト。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-117">Broadcast online to a large audience.</span></span>

- <span data-ttu-id="d0cdc-118">会議中に自分の画面を表示したり、他の出席者による制御を許可する。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-118">Present your screen during meetings or give control to others.</span></span>

- <span data-ttu-id="d0cdc-119">Skype for Business を他の Office プログラムで使用して、ワンクリックでチャット、通話、会議に参加する。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-119">Use Skype for Business in other Office programs to chat, call, or join a meeting with a click.</span></span>

## <a name="why-is-this-all-so-important"></a><span data-ttu-id="d0cdc-120">これがすべて重要である理由。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-120">Why is this all so important?</span></span>

<span data-ttu-id="d0cdc-p103">IP 上のリアルタイム メディア (オーディオ、ビデオ、アプリケーション共有など) の品質は、エンド ツー エンドのネットワーク接続の品質に大きく影響されます。Skype for Business Online メディアの最適な品質を得るために、会社のネットワークと Skype for Business Online 間の接続が高品質であることを確認することが重要です。これを達成するためには、内部ネットワークとクラウド接続を、接続全体にわたって Skype for Business Online のピーク時のトラフィック量を処理するネットワークのキャパシティに基づいて設定することが最善の方法になります。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p103">The quality of real-time media (audio, video, and application sharing) over IP is greatly impacted by the quality of end-to-end network connectivity. For optimal Skype for Business Online media quality, it is important for you to make sure there is a high-quality connection between your company network and Skype for Business Online. The best way to accomplish this is to set up your internal network and cloud connectivity based on the capacity of your network to accommodate for peak traffic volume for Skype for Business Online across all connections.</span></span>

<span data-ttu-id="d0cdc-124">[Microsoft パートナー](https://partnercenter.microsoft.com/pcv/search)と連携して、クラウド内の Skype For business Online などのさまざまな office 365 アプリケーションをネットワークに接続することができます。また、Skype for business 用のリアルタイムの音声およびビデオ通信機能を利用するには、これらの office 365 リアルタイムのワークロードをサポートするようにネットワークサービスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-124">Working with a [Microsoft partner](https://partnercenter.microsoft.com/pcv/search), you can connect a variety of Office 365 applications including Skype for Business Online in the cloud to your network and real-time voice and video communications capabilities for Skype for Business require network services must be specifically configured to support these Office 365 real-time workloads.</span></span> <span data-ttu-id="d0cdc-125">これには、必要なトラフィック量を伝送するための十分な帯域幅を備えたネットワークと、ユーザーに対してビジネスクラスのエクスペリエンスを実現するためにサービスの品質 (QoS) をサポートできるものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-125">This includes a network that has sufficient bandwidth to carry the required volume of traffic and be capable of supporting Quality of Service (QoS) to deliver a business class experience for your users.</span></span>

<span data-ttu-id="d0cdc-126">ここで記載されている情報に加えて、次のリソースが Skype for Business Online のサービスと機能を正しく計画、展開することや、お使いのネットワーク サービスが要件と満たしているかを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-126">Along with the information here, there are other resources that can help you successfully plan and deploy Skype for Business Online services and features and to ensure that your network services meet those requirements:</span></span>

- [<span data-ttu-id="d0cdc-127">ExpressRoute を使用したコール フロー</span><span class="sxs-lookup"><span data-stu-id="d0cdc-127">Call flow using ExpressRoute</span></span>](call-flow-using-expressroute.md)

- [<span data-ttu-id="d0cdc-128">Skype for Business Online での ExpressRoute および QoS</span><span class="sxs-lookup"><span data-stu-id="d0cdc-128">ExpressRoute and QoS in Skype for Business Online</span></span>](expressroute-and-qos-in-skype-for-business-online.md)

- [<span data-ttu-id="d0cdc-129">Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="d0cdc-129">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a><span data-ttu-id="d0cdc-130">Skype for Business のサービスの品質 (QoS) の実装</span><span class="sxs-lookup"><span data-stu-id="d0cdc-130">Implement Quality of Service (QoS) for Skype for Business</span></span>

<span data-ttu-id="d0cdc-p105">Skype for Business Online に移行する前に、音声、ビデオ、セッションのトラフィックの共有を処理するためのネットワークに目を向ける必要があります。他の Office 365 サービスと同様に、Microsoft は、会社の各サイトで必要なネットワーク トラフィックを判別するために使用される [Skype for Business Bandwidth Calculator](https://www.microsoft.com/download/details.aspx?id=19011) をダウンロードで提供しています。会社のサイト別のリアルタイムの通信トラフィック メディア フローと Skype for Business トラフィックの量のモデリングを含む、使用状況のモデリングと、トラフィック量の計算と、トラフィックによるネットワーク全体への影響の分析を実行する必要があります。これを完了すると、このデータの分析によりお使いのネットワークで改善が必要な点についての推奨事項が提示され、優れたエンド ユーザー エクスペリエンスを実現するためのキュー サイズも提案されます。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p105">Before moving to Skype for Business Online, you should take a look at your network's capacity to handle audio, video and sharing session traffic. As with other Office 365 services, Microsoft has available for download the [Skype for Business Bandwidth Calculator](https://www.microsoft.com/download/details.aspx?id=19011) that's used to determine the required network traffic for each of your company sites. You should perform usage modeling, including modeling real-time communication traffic media flows and the amount of Skype for Business traffic per company location, calculating traffic volume, and analyzing how that traffic impacts your overall network. After you've done that, analysis of this data should provide recommendations of where your network needs to be improved and recommend queue sizes in order to provide an excellent end user experience.</span></span>

<span data-ttu-id="d0cdc-p106">Skype for Business のリアルタイム トラフィックは、混雑したネットワークで頻繁に発生するパケット損失、遅延、ジッターの影響を受けやすいです。サービスの品質 (QoS) は、サービス クラスと呼ばれることもありますが、管理対象の外部 WAN、管理対象の内部 LAN、およびエンタープライズ ベースの WiFi ネットワークでも展開する必要があります。これにより、ローカル ネットワーク上や WAN を経由する非リアルタイム トラフィックよりも、音声やビデオなどの Skype for Business のリアルタイム トラフィックを正しく優先させることができます。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p106">Skype for Business real-time traffic is sensitive to packet loss, delay and jitter, which occur frequently in congested networks. Quality of Service (QoS) - sometimes called Class of Service - must also be deployed on managed external WANs, managed internal LANs, and enterprise-based WiFi networks. This will help to properly prioritize Skype for Business real-time traffic such as audio and video over other non-real time traffic on local networks and over WAN, creating a better experience for end users.</span></span>

<span data-ttu-id="d0cdc-p107">Skype for Business の音声は EF (完全優先転送 - DSCP 46) キューで展開される必要があります。Skype for Business のビデオは AF41 (相対的優先転送 - DSCP 34) で展開される必要があります。これは、Office 365 の電話システムまたはその他のテレフォニー機能が展開されているかどうかに関係なく、ピアツーピアおよび会議トラフィックにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p107">Skype for Business audio must be deployed in the EF (Expedited Forwarding - DSCP 46) queue and Skype for Business video must be deployed in the AF41 (Assured Forwarding - DSCP 34) queue. This is true even for peer-to-peer and conferencing traffic, regardless of whether Phone System in Office 365 or other telephony features are being deployed.</span></span>

<span data-ttu-id="d0cdc-p108">既存の QoS ポリシーが、その他の IP テレフォニー製品での LAN または WAN 上で確立している中で、Skype for Business ではユーザーがサービスを使用中でもモバイルでの利用に切り替えたり、場所を移動したりすることが可能になります。このため、すべての Skype for Business トラフィックに対して管理対象ネットワーク全体にわたり必ず優先順位が付けられるようにするために、QoS ポリシーは LAN、WAN、およびワイヤレスネットワークでマーク付けされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p108">While existing QoS policies might be in place already on the LAN and WAN for other IP telephony products, Skype for Business allows users to be mobile and to move from location to location while using the service. Because of this, QoS policies must be marked on the LAN, WAN and wireless networks in order to be sure that all Skype for Business traffic is being prioritized across managed networks.</span></span>

<span data-ttu-id="d0cdc-142">ネットワークのサイズ変更を行いやすくするために、[Skype for Business Bandwidth Calculator](https://www.microsoft.com/download/details.aspx?id=19011) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-142">To help you will sizing your network, download the [Skype for Business Bandwidth Calculator](https://www.microsoft.com/download/details.aspx?id=19011).</span></span>

<span data-ttu-id="d0cdc-143">メディアの品質と QoS の詳細については、「 [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](media-quality-and-network-connectivity-performance.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-143">For more about media quality and QoS, see [Media Quality and Network Connectivity Performance in Skype for Business Online](media-quality-and-network-connectivity-performance.md).</span></span>

<span data-ttu-id="d0cdc-144">QoS の設定と管理の詳細については、「[サービスの品質の管理](https://technet.microsoft.com/library/gg425841.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-144">For more about setting up and managing QoS, see [Managing Quality of Service](https://technet.microsoft.com/library/gg425841.aspx).</span></span>

## <a name="bypass-proxies-and-wan-optimization-devices"></a><span data-ttu-id="d0cdc-145">プロキシと WAN 最適化デバイスをバイパスする</span><span class="sxs-lookup"><span data-stu-id="d0cdc-145">Bypass proxies and WAN optimization devices</span></span>

<span data-ttu-id="d0cdc-p109">Skype for Business Online を含めて Office 365 はすべて暗号化され、通常はプロキシ デバイスでは検査できません。このような理由により、ユーザーが [Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)への接続として定義したように、すべての Office 365 ネットワーク トラフィックについてプロキシ デバイスをバイパスすることをお勧めします。プロキシ デバイスはリアルタイムの Skype for Business Online メディア ストリームでは遅延を引き起こす可能性があるため、それらのトラフィックではプロキシ デバイスを可能な限りバイパスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p109">All Office 365 including Skype for Business Online is encrypted and is typically not able to be inspected by proxy devices. For these reasons we recommend bypassing proxy devices for all Office 365 network traffic as defined as connections your users make to [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Since proxy devices will likely introduce delay in real-time Skype for Business Online media streams we strongly recommend bypassing proxy devices at a minimum for that traffic.</span></span>

<span data-ttu-id="d0cdc-149">Microsoft は、PAC ファイルを使用して Office 365 の URL が Office 365 トラフィックをファイアウォールに送信しないようにすることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-149">Microsoft recommends excluding Office 365 URLs using PAC files to send Office 365 traffic to a firewall.</span></span>

<span data-ttu-id="d0cdc-150">次のいくつかのリソースに記載されている情報もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-150">Here are some available resources that can help too:</span></span>

- [<span data-ttu-id="d0cdc-151">ベースラインとパフォーマンス履歴を使用して、Office 365 のパフォーマンスをチューニングする</span><span class="sxs-lookup"><span data-stu-id="d0cdc-151">Office 365 performance tuning using baselines and performance history</span></span>](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [<span data-ttu-id="d0cdc-152">Office 365 のネットワークと移行計画</span><span class="sxs-lookup"><span data-stu-id="d0cdc-152">Network and migration planning for Office 365</span></span>](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [<span data-ttu-id="d0cdc-153">Office 365 プロキシ PAC ジェネレータ</span><span class="sxs-lookup"><span data-stu-id="d0cdc-153">Office 365 Proxy Pac generator</span></span>](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [<span data-ttu-id="d0cdc-154">Office 365 での WAN 最適化コントローラーおよびキャッシュ デバイスの使用</span><span class="sxs-lookup"><span data-stu-id="d0cdc-154">Using WAN Optimization Controller or Traffic/Inspection devices with Office 365</span></span>](https://aka.ms/kb2690045)

- [<span data-ttu-id="d0cdc-155">Office 365 向け ExpressRoute でのルーティング</span><span class="sxs-lookup"><span data-stu-id="d0cdc-155">Routing with ExpressRoute for Office 365</span></span>](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a><span data-ttu-id="d0cdc-156">二重暗号化をバイパスする</span><span class="sxs-lookup"><span data-stu-id="d0cdc-156">Bypass double encryption</span></span>

<span data-ttu-id="d0cdc-p110">可能な限りの最良の音声とビデオのエクスペリエンスをユーザーに提供するために、Skype for Business のメディア (音声とビデオ) が仮想プライベート ネットワーク (VPN) トンネルを使用しないようにするソリューションを実装する必要があります。すべての Skype for Business トラフィックはトランスポート層セキュリティ (TLS) で暗号化され、メディアのワークロードは Secure Real Time Protocol (SRTP) で暗号化されます。シグナリングは TLS で暗号化され、メディアのワークロードは SRTP で暗号化されます。このトラフィックを VPN トンネル経由で送信すると、暗号化の追加の層が追加され、追加のネットワークがクライアントと Office 365 の間をホップします。これらの両方とも、ジッター、パケット損失、遅延が増えることが原因でセッションの低下を生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p110">To provide users the best possible audio and video experience, you must implement a solution that prevents Skype for Business media (audio and video) from traversing a Virtual Private Network (VPN) tunnel. All Skype for Business traffic is encrypted with Transport Layer Security (TLS) and the media workloads are encrypted with Secure Real Time Protocol (SRTP). Signaling is encrypted with TLS and the media workloads are encrypted with SRTP. Sending this traffic over the VPN tunnel adds an extra layer of encryption, and additional network hops between the client and Office 365, both of which can result in a degraded session because it increases jitter, packet loss and latency.</span></span>

<span data-ttu-id="d0cdc-p111">Skype for Business トラフィックが VPN トンネルを使用しないようにするための 1 つのオプションが分割トンネリングです。分割トンネリングを実装する場合は、お客様がお使いのソフトウェアでのその方法の詳細について、ご自身の VPN ベンダーに問い合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p111">One option to prevent Skype for Business traffic from traversing the VPN tunnel is Split Tunneling. To implement split-tunneling, customers should consult with their VPN vendor on the specifics of how to do this in their software.</span></span>

> [!NOTE]
> <span data-ttu-id="d0cdc-163">これは、Skype for Business のメディアのワークロードについてのみ必要です。他の Office 365 サービスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-163">This is only required for the Skype for Business media workloads and isn't applicable to other Office 365 services.</span></span>

<span data-ttu-id="d0cdc-164">追加情報:</span><span class="sxs-lookup"><span data-stu-id="d0cdc-164">Additional resources:</span></span>

- [<span data-ttu-id="d0cdc-165">Enabling Lync Media to Bypass a VPN Tunnel (Lync メディアが VPN トンネルをバイパスするようにする)</span><span class="sxs-lookup"><span data-stu-id="d0cdc-165">Enabling Lync Media to Bypass a VPN Tunnel</span></span>](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [<span data-ttu-id="d0cdc-166">More on Direct Access, Split Tunneling and Force Tunneling (DirectAccess での分割トンネリングと強制トンネリングの詳細情報)</span><span class="sxs-lookup"><span data-stu-id="d0cdc-166">More on Direct Access, Split Tunneling and Force Tunneling</span></span>](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)

- [<span data-ttu-id="d0cdc-167">Enable Direct Access (DirectAccess を有効にする)</span><span class="sxs-lookup"><span data-stu-id="d0cdc-167">Enable Direct Access</span></span>](https://technet.microsoft.com/library/jj574163.aspx)

## <a name="ensure-the-right-ports-and-protocols-are-open"></a><span data-ttu-id="d0cdc-168">正しいポートとプロトコルが開いていることを確認する</span><span class="sxs-lookup"><span data-stu-id="d0cdc-168">Ensure the right ports and protocols are open</span></span>

<span data-ttu-id="d0cdc-p112">お客様は、O365 サービスで必要となる URL と IP アドレスにアクセス可能であるか確認する必要があります。Skype for Business Online のすべての IP アドレスと URL のリストについては、「[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p112">Customers must ensure reachability of the URLs and IP addresses that are required for the O365 service. For a complete listing of all IP addresses and URLs for Skype for Business Online, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span>

<span data-ttu-id="d0cdc-p113">Skype for Business クライアントは、さまざまなポートとプロトコルを使用します。 Skype for Business セッションのネットワーク トラフィックの向きと流れは、相互作用の種類 (ピアツーピア、マルチパーティ) によって、およびコンテンツ共有と音声/ビデオの使用に応じて、異なります。 接続元と接続先のポートについて特に注意しながら、ポートとプロトコルのリストを確認して開く必要があります。 たとえば、音声トラフィックは 20 個のポート (50000 から 50019 までの TCP/UDP) をクライアント側で使用しますが、送信先のポートがサービス側で 10000 個のポートの範囲内 (50000 から 59999 までの TCP/UDP) にある可能性があります。送信先のポートには、ファイアウォール上の開いている TCP 443 と UDP 3478 も含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p113">Skype for Business clients use a variety of ports and protocols. The direction and flow of network traffic for a Skype for Business session will vary depending on the type of interactions (peer-to-peer vs multiparty) and depending on the use of content sharing and voice/video. You must review and open the list of ports and protocols, paying special attention to the source and destination ports. For example, audio traffic uses just 20 ports (50000-50019 TCP/UDP) at the client side, but the destination port could be anywhere in a 10K port range (50000-59999 TCP/UDP) at the service side. This also includes opening TCP 443 and UDP 3478 on the firewall.</span></span>

<span data-ttu-id="d0cdc-176">Skype for Business Online をサポートするために追加のネットワーク構成が必要になる可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-176">Additional network configuration might also be required to support Skype for Business Online.</span></span>


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a><span data-ttu-id="d0cdc-177">Skype for Business 用に最適化された電話機およびデバイスを使用する</span><span class="sxs-lookup"><span data-stu-id="d0cdc-177">Use Phones and Devices Optimized for Skype for Business</span></span>

<span data-ttu-id="d0cdc-178">リアルタイム メディア セッションでは、ヘッドセットや Web カメラなどの参加者全員が使用するメディア デバイスは、オーディオとビデオの全体的な品質に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-178">In a real-time media session, media devices that are used by all participants such as headsets and web cams have a great impact on the overall audio and video quality.</span></span> <span data-ttu-id="d0cdc-179">低品質デバイスまたは不適切なデバイスドライバーを使用しているデバイスでは、オーディオ品質が低くなり、ビデオの画質が低下します。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-179">Lower-quality devices or devices with incorrect device drivers will produce lower overall sound quality for audio and lower image quality for video.</span></span> <span data-ttu-id="d0cdc-180">一方、認定デバイスまたは高品質なデバイスは、エコー キャンセル、ノイズ フィルタリング、ビデオ解像度、遅延低減に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-180">Certified devices or good quality devices, on the other hand, help with echo cancellation, noise filtering, video resolution and reduce latency.</span></span>

<span data-ttu-id="d0cdc-p115">電話機とデバイスによって、エンド ユーザーの音声とビデオの品質に大きな違いが生じます。Skype for Business 認定プログラムは「Lync 互換」プログラムが発展したもので、デバイスが音声とビデオに関する Microsoft 標準に適合しているかを検証します。数多くの IP 電話、USB オーディオとビデオ デバイス、PC、および会議室が Microsoft によりテストされ、認定されています。お客様は Skype for Business 用に最適化されたデバイスのリストを確認して、ご自身および組織のエンド ユーザーのさまざまなニーズと個人設定に合わせて異なるデバイスを用意するよう努める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p115">Phones and devices make a huge difference in the quality of audio and video for end users. The Skype for Business certification program is an evolution of the "Lync Compatible" program and validates that the device meets Microsoft standards for audio and video. There are a number of IP Phones, USB audio and video devices, PCs and meeting room devices that have been tested and qualified by Microsoft. You should review the list of devices that are optimized for Skype for Business, and work to provide different devices in order to meet the various needs and personal preferences of your end users in your organization.</span></span>

<span data-ttu-id="d0cdc-185">サポートされている認定済みデバイスの詳細については、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-185">See the following for more information on supported and certified devices:</span></span>  

- [<span data-ttu-id="d0cdc-186">Skype for Business Online で使う電話を入手する</span><span class="sxs-lookup"><span data-stu-id="d0cdc-186">Getting phones for Skype for Business Online</span></span>](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [<span data-ttu-id="d0cdc-187">Skype for Business の電話とデバイス</span><span class="sxs-lookup"><span data-stu-id="d0cdc-187">Phones and Devices for Skype for Business</span></span>](https://technet.microsoft.com/office/dn947482.aspx)

- [<span data-ttu-id="d0cdc-188">個人用周辺機器のソリューション カタログ</span><span class="sxs-lookup"><span data-stu-id="d0cdc-188">Solutions Catalog for Personal Peripherals</span></span>](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [<span data-ttu-id="d0cdc-189">Microsoft Lync で認定済みの電話とデバイス</span><span class="sxs-lookup"><span data-stu-id="d0cdc-189">Phones and devices qualified for Microsoft Lync</span></span>](https://technet.microsoft.com/office/dn788944.aspx)

<span data-ttu-id="d0cdc-p116">ユーザーが会議を行い、オーディオ デバイスとビデオ デバイスを使用する環境と周辺領域は、オーディオとビデオの品質のもう 1 つの要因です。ノイズのある環境から通話しているユーザーのオーディオは、エコーがかかり、こもっていて、不明瞭です。暗くて照明が不十分な環境にいるユーザーは、ビデオで明るくクリアな画質を実現することができません。会議室の設定で、マイクとビデオ デバイスの場所は、参加者が受信する音声と画像の品質に直接影響します。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-p116">The environment and surrounding area where users are meeting and using audio and video devices is another big factor for audio and video quality. Users calling from a noisy environment will have echoed, muffled and unclear audio. Users in a dark or low light environment won't be able to produce bright, clear image quality for video. In a conference room setting, the location of the microphone and video device have a direct impact on the sound and image quality that participants will receive.</span></span>

<span data-ttu-id="d0cdc-194">ユーザーのオーディオとビデオのエクスペリエンスをより明確にするために、Skype for business アプリの**ツール** > **オプション** > の**オーディオデバイス**または**ビデオデバイス**を使って、使用中のデバイスに変更を加え、設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-194">To get a clearer picture of a user's audio and video experience use the Skype for Business app **Tools** > **Options** > **Audio Device** or **Video Device** to make changes to the device in use and customize it's settings.</span></span> <span data-ttu-id="d0cdc-195">通話の音質を確認するには、[**通話品質の確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0cdc-195">You can also check the audio quality of a call by clicking **Check Call Quality**.</span></span> <span data-ttu-id="d0cdc-196">If they click **Check Call Quality**, they can then report the quality and issues found with the test call.</span><span class="sxs-lookup"><span data-stu-id="d0cdc-196">If they click **Check Call Quality**, they can then report the quality and issues found with the test call.</span></span>

![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a><span data-ttu-id="d0cdc-198">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d0cdc-198">Related topics</span></span>

[<span data-ttu-id="d0cdc-199">Skype for Business Online の ExpressRoute および QoS</span><span class="sxs-lookup"><span data-stu-id="d0cdc-199">ExpressRoute and QoS in Skype for Business Online</span></span>](expressroute-and-qos-in-skype-for-business-online.md)
