---
title: Skype for Business Server の暗号化
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
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server は、TLS と MTLS を使用してインスタント メッセージを暗号化します。 すべてのサーバー間トラフィックでは、トラフィックが内部ネットワークに限定されているのか、内部ネットワーク境界を越えるのかにかかわらず、MTLS が必要です。 Skype for Business Server をサードパーティの IPPBX システムまたは SIP トランク TLS に接続する場合はオプションですが、仲介サーバーとメディア ゲートウェイの間での接続を強く推奨します。 このリンクで TLS が構成されている場合は、MTLS が必要です。 したがって、仲介サーバーによって信頼されている CA からの証明書を使用してゲートウェイを構成する必要があります。
ms.openlocfilehash: 48af03d7f6aed5b744ad4e0c460622194a87d96e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832207"
---
# <a name="encryption-for-skype-for-business-server"></a><span data-ttu-id="6c2b3-107">Skype for Business Server の暗号化</span><span class="sxs-lookup"><span data-stu-id="6c2b3-107">Encryption for Skype for Business Server</span></span>
 
<span data-ttu-id="6c2b3-108">Skype for Business Server は、TLS と MTLS を使用してインスタント メッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-108">Skype for Business Server uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="6c2b3-109">すべてのサーバー間トラフィックでは、トラフィックが内部ネットワークに限定されているのか、内部ネットワーク境界を越えるのかにかかわらず、MTLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="6c2b3-110">Skype for Business Server をサード パーティ製 IPPBX システムまたは SIP トランク TLS に接続する場合はオプションですが、仲介サーバーとメディア ゲートウェイの間の接続を強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-110">When connecting Skype for Business Server to third-party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="6c2b3-111">このリンクで TLS が構成されている場合は、MTLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="6c2b3-112">したがって、仲介サーバーによって信頼されている CA からの証明書を使用してゲートウェイを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c2b3-113">SSL 3.0 に関するセキュリティ アドバイザリは、2014 年に公開されました。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="6c2b3-114">Skype for Business Server 2015 で SSL 3.0 を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="6c2b3-115">セキュリティ アドバイザリの詳細については [、「Lync Server 2013 および Skype for Business Server 2015 での SSL 3.0](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)の無効化」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).</span></span><br/>
<span data-ttu-id="6c2b3-116">**セキュリティに関するメモ:** 最も強力な暗号化プロトコルを使用するために、Skype for Business Server 2015 は TLS 暗号化プロトコルをクライアントに提供します **。TLS 1.2、TLS 1.1、TLS 1.0。**</span><span class="sxs-lookup"><span data-stu-id="6c2b3-116">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="6c2b3-117">TLS は Skype for Business Server 2015 の重要な側面であり、サポートされている環境を維持するために必要です。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span><br/>
<span data-ttu-id="6c2b3-118">**セキュリティに関するメモ:** 最も強力な暗号化プロトコルを使用するために、Skype for Business Server 2019 は TLS 暗号化プロトコルをクライアントに提供します **。TLS 1.3、TLS 1.2。**</span><span class="sxs-lookup"><span data-stu-id="6c2b3-118">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2019 will offer TLS encryption protocols in the following order to clients: **TLS 1.3, TLS 1.2**.</span></span> <span data-ttu-id="6c2b3-119">TLS は Skype for Business Server 2019 の重要な側面であり、サポートされている環境を維持するために必要です。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-119">TLS is a critical aspect of Skype for Business Server 2019 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="6c2b3-120">次の表に、各種トラフィックのプロトコル要件をまとめます。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-120">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="6c2b3-121">**トラフィックの保護**</span><span class="sxs-lookup"><span data-stu-id="6c2b3-121">**Traffic Protection**</span></span>

|<span data-ttu-id="6c2b3-122">**トラフィックの種類**</span><span class="sxs-lookup"><span data-stu-id="6c2b3-122">**Traffic type**</span></span>|<span data-ttu-id="6c2b3-123">**保護用プロトコル**</span><span class="sxs-lookup"><span data-stu-id="6c2b3-123">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6c2b3-124">サーバー間</span><span class="sxs-lookup"><span data-stu-id="6c2b3-124">Server-to-server</span></span>  <br/> |<span data-ttu-id="6c2b3-125">MTLS</span><span class="sxs-lookup"><span data-stu-id="6c2b3-125">MTLS</span></span>  <br/> |
|<span data-ttu-id="6c2b3-126">クライアントからサーバー</span><span class="sxs-lookup"><span data-stu-id="6c2b3-126">Client-to-server</span></span>  <br/> |<span data-ttu-id="6c2b3-127">TLS</span><span class="sxs-lookup"><span data-stu-id="6c2b3-127">TLS</span></span>  <br/> |
|<span data-ttu-id="6c2b3-128">インスタント メッセージングおよびプレゼンス</span><span class="sxs-lookup"><span data-stu-id="6c2b3-128">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="6c2b3-129">TLS</span><span class="sxs-lookup"><span data-stu-id="6c2b3-129">TLS</span></span>  <br/> |
|<span data-ttu-id="6c2b3-130">オーディオとビデオ、およびメディアのデスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="6c2b3-130">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="6c2b3-131">SRTP</span><span class="sxs-lookup"><span data-stu-id="6c2b3-131">SRTP</span></span>  <br/> |
|<span data-ttu-id="6c2b3-132">デスクトップ共有 (シグナリング)</span><span class="sxs-lookup"><span data-stu-id="6c2b3-132">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="6c2b3-133">TLS</span><span class="sxs-lookup"><span data-stu-id="6c2b3-133">TLS</span></span>  <br/> |
|<span data-ttu-id="6c2b3-134">Web 会議</span><span class="sxs-lookup"><span data-stu-id="6c2b3-134">Web conferencing</span></span>  <br/> |<span data-ttu-id="6c2b3-135">TLS</span><span class="sxs-lookup"><span data-stu-id="6c2b3-135">TLS</span></span>  <br/> |
|<span data-ttu-id="6c2b3-136">会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張</span><span class="sxs-lookup"><span data-stu-id="6c2b3-136">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="6c2b3-137">HTTPS</span><span class="sxs-lookup"><span data-stu-id="6c2b3-137">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="6c2b3-138">メディアの暗号化</span><span class="sxs-lookup"><span data-stu-id="6c2b3-138">Media Encryption</span></span>

<span data-ttu-id="6c2b3-139">メディア トラフィックは、RTP トラフィックに機密性、認証、リプレイ攻撃保護を提供する Real-Time トランスポート プロトコル (RTP) のプロファイルである Secure RTP (SRTP) を使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-139">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="6c2b3-140">さらに、仲介サーバーとその内部の次ホップの間で双方向に流れるメディアも、SRTP を使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-140">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="6c2b3-141">仲介サーバーとメディア ゲートウェイの間で両方向に流れるメディアは、必要に応じて暗号化され、推奨されます。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-141">Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended.</span></span> <span data-ttu-id="6c2b3-142">仲介サーバーはメディア ゲートウェイへの暗号化をサポートできますが、ゲートウェイは MTLS と証明書の保存をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-142">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c2b3-143">ハイブリッドの設定の詳細については、「ハイブリッド接続を計画 [する」を参照してください](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-143">For more information about setting up hybrid, see [Plan hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).</span></span>
  
## <a name="fips"></a><span data-ttu-id="6c2b3-144">FIPS</span><span class="sxs-lookup"><span data-stu-id="6c2b3-144">FIPS</span></span>

<span data-ttu-id="6c2b3-145">Windows Server オペレーティング システムがシステム暗号化に FIPS 140-2 アルゴリズムを使用するように構成されている場合、Skype for Business Server および Microsoft Exchange Server 2016 は Federal Information Processing Standard (FIPS) 140-2 アルゴリズムのサポートと一緒に動作します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-145">Skype for Business Server and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="6c2b3-146">FIPS サポートを実装するには、Skype for Business Server を実行している各サーバーを構成してサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-146">To implement FIPS support, you must configure each server running Skype for Business Server to support it.</span></span>
  

