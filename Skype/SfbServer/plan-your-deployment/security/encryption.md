---
title: Skype for Business Server の暗号化
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server は、TLS と MTLS を使ってインスタントメッセージを暗号化します。 トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。 Skype for Business Server をサードパーティの IPPBX システムまたは SIP trunks TLS に接続する場合はオプションですが、仲介サーバーとメディアゲートウェイ間では強くお勧めします。 この接続に TLS を構成する場合は MTLS も必要です。 そのため、ゲートウェイは、仲介サーバーによって信頼されている CA からの証明書を使って構成する必要があります。
ms.openlocfilehash: 64e7199cf761ad7d7ec18b00e8f3b7f27fed6f04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815665"
---
# <a name="encryption-for-skype-for-business-server"></a><span data-ttu-id="53b50-107">Skype for Business Server の暗号化</span><span class="sxs-lookup"><span data-stu-id="53b50-107">Encryption for Skype for Business Server</span></span>
 
<span data-ttu-id="53b50-108">Skype for Business Server は、TLS と MTLS を使ってインスタントメッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="53b50-108">Skype for Business Server uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="53b50-109">トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。</span><span class="sxs-lookup"><span data-stu-id="53b50-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="53b50-110">Skype for Business Server をサードパーティの IPPBX システムまたは SIP trunks TLS に接続する場合はオプションですが、仲介サーバーとメディアゲートウェイ間では強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53b50-110">When connecting Skype for Business Server to third-party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="53b50-111">この接続に TLS を構成する場合は MTLS も必要です。</span><span class="sxs-lookup"><span data-stu-id="53b50-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="53b50-112">そのため、ゲートウェイは、仲介サーバーによって信頼されている CA からの証明書を使って構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53b50-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53b50-113">SSL 3.0 に関するセキュリティ アドバイザリが 2014 年に公開されました。</span><span class="sxs-lookup"><span data-stu-id="53b50-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="53b50-114">Skype for Business Server 2015 での SSL 3.0 の無効化は、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="53b50-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="53b50-115">セキュリティアドバイザリの詳細については、「 [Lync server 2013 および Skype For Business server 2015 での SSL 3.0 の無効化](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53b50-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).</span></span><br/>
<span data-ttu-id="53b50-116">**セキュリティメモ:** 最強の暗号化プロトコルを使用するために、Skype for Business Server 2015 は次の順序で TLS 暗号化プロトコルをクライアントに提供します。 **tls 1.2、tls 1.1、tls 1.0**。</span><span class="sxs-lookup"><span data-stu-id="53b50-116">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="53b50-117">TLS は Skype for Business Server 2015 の重要な側面であり、サポートされている環境を維持するために必要です。</span><span class="sxs-lookup"><span data-stu-id="53b50-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span><br/>
<span data-ttu-id="53b50-118">**セキュリティメモ:** 最強の暗号化プロトコルを使用するために、Skype for Business Server 2019 は次の順序で TLS 暗号化プロトコルをクライアントに提供します。 tls **1.3、tls 1.2**。</span><span class="sxs-lookup"><span data-stu-id="53b50-118">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2019 will offer TLS encryption protocols in the following order to clients: **TLS 1.3, TLS 1.2**.</span></span> <span data-ttu-id="53b50-119">TLS は Skype for Business Server 2019 の重要な側面であり、サポートされている環境を維持するために必要です。</span><span class="sxs-lookup"><span data-stu-id="53b50-119">TLS is a critical aspect of Skype for Business Server 2019 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="53b50-120">次の表に、各種トラフィックのプロトコル要件をまとめます。</span><span class="sxs-lookup"><span data-stu-id="53b50-120">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="53b50-121">**トラフィックの保護**</span><span class="sxs-lookup"><span data-stu-id="53b50-121">**Traffic Protection**</span></span>

|<span data-ttu-id="53b50-122">**トラフィックの種類**</span><span class="sxs-lookup"><span data-stu-id="53b50-122">**Traffic type**</span></span>|<span data-ttu-id="53b50-123">**保護用プロトコル**</span><span class="sxs-lookup"><span data-stu-id="53b50-123">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="53b50-124">サーバー間</span><span class="sxs-lookup"><span data-stu-id="53b50-124">Server-to-server</span></span>  <br/> |<span data-ttu-id="53b50-125">MTLS</span><span class="sxs-lookup"><span data-stu-id="53b50-125">MTLS</span></span>  <br/> |
|<span data-ttu-id="53b50-126">クライアントからサーバー</span><span class="sxs-lookup"><span data-stu-id="53b50-126">Client-to-server</span></span>  <br/> |<span data-ttu-id="53b50-127">TLS</span><span class="sxs-lookup"><span data-stu-id="53b50-127">TLS</span></span>  <br/> |
|<span data-ttu-id="53b50-128">インスタント メッセージングとプレゼンス</span><span class="sxs-lookup"><span data-stu-id="53b50-128">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="53b50-129">TLS </span><span class="sxs-lookup"><span data-stu-id="53b50-129">TLS</span></span>  <br/> |
|<span data-ttu-id="53b50-130">オーディオとビデオ、メディアのデスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="53b50-130">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="53b50-131">SRTP</span><span class="sxs-lookup"><span data-stu-id="53b50-131">SRTP</span></span>  <br/> |
|<span data-ttu-id="53b50-132">デスクトップ共有 (シグナリング)</span><span class="sxs-lookup"><span data-stu-id="53b50-132">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="53b50-133">TLS</span><span class="sxs-lookup"><span data-stu-id="53b50-133">TLS</span></span>  <br/> |
|<span data-ttu-id="53b50-134">Web 会議</span><span class="sxs-lookup"><span data-stu-id="53b50-134">Web conferencing</span></span>  <br/> |<span data-ttu-id="53b50-135">TLS</span><span class="sxs-lookup"><span data-stu-id="53b50-135">TLS</span></span>  <br/> |
|<span data-ttu-id="53b50-136">会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張</span><span class="sxs-lookup"><span data-stu-id="53b50-136">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="53b50-137">HTTPS</span><span class="sxs-lookup"><span data-stu-id="53b50-137">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="53b50-138">メディアの暗号化</span><span class="sxs-lookup"><span data-stu-id="53b50-138">Media Encryption</span></span>

<span data-ttu-id="53b50-p106">メディア トラフィックは、Secure RTP (SRTP) を使用して暗号化されます。これは、秘密保持機能、認証、RTP トラフィックなどに対する再生攻撃からの保護機能を提供するリアルタイム転送プロトコル (RTP) のプロファイルです。さらに、仲介サーバーとその次のホップ間で双方向にやりとりされるメディアも SRTP を使用して暗号化されます。仲介サーバーとメディア ゲートウェイ間で双方向にやりとりされるメディアはオプションで暗号化され、暗号化することが推奨されます。仲介サーバーはメディア ゲートウェイに対する暗号化をサポートできますが、ゲートウェイは MTLS および証明書のストレージをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="53b50-p106">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended. The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53b50-143">ハイブリッドの設定の詳細については、「[ハイブリッド接続の計画](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53b50-143">For more information about setting up hybrid, see [Plan hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).</span></span>
  
## <a name="fips"></a><span data-ttu-id="53b50-144">FIPS</span><span class="sxs-lookup"><span data-stu-id="53b50-144">FIPS</span></span>

<span data-ttu-id="53b50-145">Skype for Business Server および Microsoft Exchange Server 2016 は、Windows Server オペレーティングシステムがシステム暗号化用の FIPS 140-2 アルゴリズムを使用するように構成されている場合に、米国連邦情報処理標準 (FIPS) 140-2 アルゴリズムのサポートで動作します。.</span><span class="sxs-lookup"><span data-stu-id="53b50-145">Skype for Business Server and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="53b50-146">FIPS サポートを実装するには、Skype for Business Server を実行している各サーバーでサポートされるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53b50-146">To implement FIPS support, you must configure each server running Skype for Business Server to support it.</span></span>
  

