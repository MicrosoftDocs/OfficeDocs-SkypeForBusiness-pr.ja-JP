---
title: Skype のビジネス サーバー用の暗号化
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: ビジネス サーバー用の Skype は、インスタント メッセージの暗号化に TLS および MTLS を使用します。 トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。 Skype をビジネス サーバーのサード パーティ製の IPPBX システムまたは SIP トランク TLS 接続があるとき省略可能ですが、仲介サーバーとメディア ゲートウェイの間で強く推奨されます。 この接続に TLS を構成する場合は MTLS も必要です。 そのため、ゲートウェイは、仲介サーバーによって信頼されている CA から証明書を構成しなければなりません。
ms.openlocfilehash: 1a109bea59644e00b3b010c42d9b12918296b47c
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789377"
---
# <a name="encryption-for-skype-for-business-server"></a><span data-ttu-id="1e17f-107">Skype のビジネス サーバー用の暗号化</span><span class="sxs-lookup"><span data-stu-id="1e17f-107">Encryption for Skype for Business Server</span></span>
 
<span data-ttu-id="1e17f-108">ビジネス サーバー用の Skype は、インスタント メッセージの暗号化に TLS および MTLS を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e17f-108">Skype for Business Server uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="1e17f-109">トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。</span><span class="sxs-lookup"><span data-stu-id="1e17f-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="1e17f-110">Skype をビジネス サーバーのサード ・ パーティ製の IPPBX システムまたは SIP トランク TLS 接続があるとき省略可能ですが、仲介サーバーとメディア ゲートウェイの間で強く推奨されます。</span><span class="sxs-lookup"><span data-stu-id="1e17f-110">When connecting Skype for Business Server to third-party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="1e17f-111">この接続に TLS を構成する場合は MTLS も必要です。</span><span class="sxs-lookup"><span data-stu-id="1e17f-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="1e17f-112">そのため、ゲートウェイは、仲介サーバーによって信頼されている CA から証明書を構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1e17f-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e17f-113">SSL 3.0 に関するセキュリティ アドバイザリが 2014 年に公開されました。</span><span class="sxs-lookup"><span data-stu-id="1e17f-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="1e17f-114">ビジネス サーバー 2015 の Skype で SSL 3.0 を無効にすることは、サポートされているオプションです。</span><span class="sxs-lookup"><span data-stu-id="1e17f-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="1e17f-115">セキュリティ アドバイザリに関する詳細については、 [Lync Server 2013 とビジネス サーバー 2015 の Skype で SSL 3.0 を無効にする](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e17f-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).</span></span><br/>
<span data-ttu-id="1e17f-116">**セキュリティに関するメモ:** 最も強力な暗号化プロトコルが使用されることを確認するには、ビジネス サーバー 2015 の Skype すると、TLS 暗号化プロトコルを次の順序でクライアント: **TLS 1.2、TLS 1.1、TLS 1.0**です。</span><span class="sxs-lookup"><span data-stu-id="1e17f-116">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="1e17f-117">TLS は、Skype のビジネス サーバー 2015 の重要な側面と、サポートされている環境を維持するために必要なためです。</span><span class="sxs-lookup"><span data-stu-id="1e17f-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span><br/>
<span data-ttu-id="1e17f-118">**セキュリティに関するメモ:** 最も強力な暗号化プロトコルが使用されることを確認するには、ビジネス サーバー 2019 の Skype すると、TLS 暗号化プロトコルを次の順序でクライアント: **TLS 1.3、TLS 1.2**です。</span><span class="sxs-lookup"><span data-stu-id="1e17f-118">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2019 will offer TLS encryption protocols in the following order to clients: **TLS 1.3, TLS 1.2**.</span></span> <span data-ttu-id="1e17f-119">TLS は、Skype のビジネス サーバー 2019 の重要な側面と、サポートされている環境を維持するために必要なためです。</span><span class="sxs-lookup"><span data-stu-id="1e17f-119">TLS is a critical aspect of Skype for Business Server 2019 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="1e17f-120">次の表に、各種トラフィックのプロトコル要件をまとめます。</span><span class="sxs-lookup"><span data-stu-id="1e17f-120">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="1e17f-121">**トラフィックの保護**</span><span class="sxs-lookup"><span data-stu-id="1e17f-121">**Traffic Protection**</span></span>

|<span data-ttu-id="1e17f-122">**トラフィックの種類**</span><span class="sxs-lookup"><span data-stu-id="1e17f-122">**Traffic type**</span></span>|<span data-ttu-id="1e17f-123">**保護用プロトコル**</span><span class="sxs-lookup"><span data-stu-id="1e17f-123">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1e17f-124">サーバー間</span><span class="sxs-lookup"><span data-stu-id="1e17f-124">Server-to-server</span></span>  <br/> |<span data-ttu-id="1e17f-125">MTLS</span><span class="sxs-lookup"><span data-stu-id="1e17f-125">MTLS</span></span>  <br/> |
|<span data-ttu-id="1e17f-126">クライアントからサーバー</span><span class="sxs-lookup"><span data-stu-id="1e17f-126">Client-to-server</span></span>  <br/> |<span data-ttu-id="1e17f-127">TLS</span><span class="sxs-lookup"><span data-stu-id="1e17f-127">TLS</span></span>  <br/> |
|<span data-ttu-id="1e17f-128">インスタント メッセージングとプレゼンス</span><span class="sxs-lookup"><span data-stu-id="1e17f-128">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="1e17f-129">TLS</span><span class="sxs-lookup"><span data-stu-id="1e17f-129">TLS</span></span>  <br/> |
|<span data-ttu-id="1e17f-130">オーディオとビデオ、メディアのデスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="1e17f-130">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="1e17f-131">SRTP</span><span class="sxs-lookup"><span data-stu-id="1e17f-131">SRTP</span></span>  <br/> |
|<span data-ttu-id="1e17f-132">デスクトップ共有 (シグナリング)</span><span class="sxs-lookup"><span data-stu-id="1e17f-132">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="1e17f-133">TLS</span><span class="sxs-lookup"><span data-stu-id="1e17f-133">TLS</span></span>  <br/> |
|<span data-ttu-id="1e17f-134">Web 会議</span><span class="sxs-lookup"><span data-stu-id="1e17f-134">Web conferencing</span></span>  <br/> |<span data-ttu-id="1e17f-135">TLS</span><span class="sxs-lookup"><span data-stu-id="1e17f-135">TLS</span></span>  <br/> |
|<span data-ttu-id="1e17f-136">会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張</span><span class="sxs-lookup"><span data-stu-id="1e17f-136">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="1e17f-137">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1e17f-137">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="1e17f-138">メディアの暗号化</span><span class="sxs-lookup"><span data-stu-id="1e17f-138">Media Encryption</span></span>

<span data-ttu-id="1e17f-p106">メディア トラフィックは、Secure RTP (SRTP) を使用して暗号化されます。これは、秘密保持機能、認証、RTP トラフィックなどに対する再生攻撃からの保護機能を提供するリアルタイム転送プロトコル (RTP) のプロファイルです。さらに、仲介サーバーとその次のホップ間で双方向にやりとりされるメディアも SRTP を使用して暗号化されます。仲介サーバーとメディア ゲートウェイ間で双方向にやりとりされるメディアはオプションで暗号化され、暗号化することが推奨されます。仲介サーバーはメディア ゲートウェイに対する暗号化をサポートできますが、ゲートウェイは MTLS および証明書のストレージをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e17f-p106">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended. The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e17f-143">ハイブリッドを設定する方法の詳細については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間でのハイブリッド接続を計画](../../../SfBServer2019/hybrid/plan-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e17f-143">For more information about setting up hybrid, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfBServer2019/hybrid/plan-hybrid-connectivity.md).</span></span>
  
## <a name="fips"></a><span data-ttu-id="1e17f-144">FIPS</span><span class="sxs-lookup"><span data-stu-id="1e17f-144">FIPS</span></span>

<span data-ttu-id="1e17f-145">システム暗号化を FIPS 140-2 のアルゴリズムを使用するのには、Windows サーバー オペレーティング システムが構成されている場合に、連邦情報処理規格 (FIPS) 140-2 のアルゴリズムをサポートして Skype ビジネス サーバーと Microsoft Exchange Server 2016 の動作します。.</span><span class="sxs-lookup"><span data-stu-id="1e17f-145">Skype for Business Server and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="1e17f-146">FIPS のサポートを実装するには、ビジネスをサポートするサーバーとの Skype を実行する各サーバーを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1e17f-146">To implement FIPS support, you must configure each server running Skype for Business Server to support it.</span></span>
  

