---
title: Skype for Business Server 2015 の暗号化
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/15/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: ビジネス サーバー 2015 の Skype は、インスタント メッセージの暗号化に TLS および MTLS を使用します。 トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。 Skype をビジネス サーバー 2015 のサード パーティ製の IPPBX システムまたは SIP トランクの TLS 接続があるとき省略可能ですが、仲介サーバーとメディア ゲートウェイの間で強く推奨されます。 この接続に TLS を構成する場合は MTLS も必要です。 そのため、ゲートウェイは、仲介サーバーによって信頼されている CA から証明書を構成しなければなりません。
ms.openlocfilehash: bf17f2c8ff8180fa5622957c665da3f4608ca833
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="encryption-for-skype-for-business-server-2015"></a><span data-ttu-id="aea86-107">Skype for Business Server 2015 の暗号化</span><span class="sxs-lookup"><span data-stu-id="aea86-107">Encryption for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aea86-108">ビジネス サーバー 2015 の Skype は、インスタント メッセージの暗号化に TLS および MTLS を使用します。</span><span class="sxs-lookup"><span data-stu-id="aea86-108">Skype for Business Server 2015 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="aea86-109">トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。</span><span class="sxs-lookup"><span data-stu-id="aea86-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="aea86-110">Skype をビジネス サーバー 2015 のサード パーティ製の IPPBX システムまたは SIP トランクの TLS 接続があるとき省略可能ですが、仲介サーバーとメディア ゲートウェイの間で強く推奨されます。</span><span class="sxs-lookup"><span data-stu-id="aea86-110">When connecting Skype for Business Server 2015 to 3rd party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="aea86-111">この接続に TLS を構成する場合は MTLS も必要です。</span><span class="sxs-lookup"><span data-stu-id="aea86-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="aea86-112">そのため、ゲートウェイは、仲介サーバーによって信頼されている CA から証明書を構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="aea86-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aea86-113">SSL 3.0 に関するセキュリティ アドバイザリが 2014 年に公開されました。</span><span class="sxs-lookup"><span data-stu-id="aea86-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="aea86-114">ビジネス サーバー 2015 の Skype で SSL 3.0 を無効にすることは、サポートされているオプションです。</span><span class="sxs-lookup"><span data-stu-id="aea86-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="aea86-115">セキュリティ アドバイザリに関する詳細については、 [Lync Server 2013 とビジネス サーバー 2015 の Skype で SSL 3.0 を無効にする](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea86-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).</span></span> 
  
> [!セキュリティに関する注意の最も強力な暗号化プロトコルのことを確認する]<span data-ttu-id="aea86-116"> を使用すると、ビジネス サーバー 2015 の Skype では、クライアントを TLS 暗号化プロトコルを次の順序でが、: **TLS 1.2、TLS 1.1、TLS 1.0**です。</span><span class="sxs-lookup"><span data-stu-id="aea86-116"> To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="aea86-117">TLS は、Skype のビジネス サーバー 2015 の重要な側面と、サポートされている環境を維持するために必要なためです。</span><span class="sxs-lookup"><span data-stu-id="aea86-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="aea86-118">次の表に、各種トラフィックのプロトコル要件をまとめます。</span><span class="sxs-lookup"><span data-stu-id="aea86-118">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="aea86-119">**トラフィックの保護**</span><span class="sxs-lookup"><span data-stu-id="aea86-119">**Traffic Protection**</span></span>

|<span data-ttu-id="aea86-120">**トラフィックの種類**</span><span class="sxs-lookup"><span data-stu-id="aea86-120">**Traffic type**</span></span>|<span data-ttu-id="aea86-121">**によって保護されています。**</span><span class="sxs-lookup"><span data-stu-id="aea86-121">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aea86-122">サーバー間</span><span class="sxs-lookup"><span data-stu-id="aea86-122">Server-to-server</span></span>  <br/> |<span data-ttu-id="aea86-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="aea86-123">MTLS</span></span>  <br/> |
|<span data-ttu-id="aea86-124">クライアントからサーバー</span><span class="sxs-lookup"><span data-stu-id="aea86-124">Client-to-server</span></span>  <br/> |<span data-ttu-id="aea86-125">TLS</span><span class="sxs-lookup"><span data-stu-id="aea86-125">TLS</span></span>  <br/> |
|<span data-ttu-id="aea86-126">インスタント メッセージングとプレゼンス</span><span class="sxs-lookup"><span data-stu-id="aea86-126">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="aea86-127">TLS</span><span class="sxs-lookup"><span data-stu-id="aea86-127">TLS</span></span>  <br/> |
|<span data-ttu-id="aea86-128">オーディオとビデオ、メディアのデスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="aea86-128">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="aea86-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="aea86-129">SRTP</span></span>  <br/> |
|<span data-ttu-id="aea86-130">デスクトップ共有 (シグナリング)</span><span class="sxs-lookup"><span data-stu-id="aea86-130">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="aea86-131">TLS</span><span class="sxs-lookup"><span data-stu-id="aea86-131">TLS</span></span>  <br/> |
|<span data-ttu-id="aea86-132">Web 会議</span><span class="sxs-lookup"><span data-stu-id="aea86-132">Web conferencing</span></span>  <br/> |<span data-ttu-id="aea86-133">TLS</span><span class="sxs-lookup"><span data-stu-id="aea86-133">TLS</span></span>  <br/> |
|<span data-ttu-id="aea86-134">会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張</span><span class="sxs-lookup"><span data-stu-id="aea86-134">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="aea86-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="aea86-135">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="aea86-136">メディアの暗号化</span><span class="sxs-lookup"><span data-stu-id="aea86-136">Media Encryption</span></span>

<span data-ttu-id="aea86-p105">メディア トラフィックは、Secure RTP (SRTP) を使用して暗号化されます。これは、秘密保持機能、認証、RTP トラフィックなどに対する再生攻撃からの保護機能を提供するリアルタイム転送プロトコル (RTP) のプロファイルです。さらに、仲介サーバーとその次のホップ間で双方向にやりとりされるメディアも SRTP を使用して暗号化されます。仲介サーバーとメディア ゲートウェイ間で双方向にやりとりされるメディアはオプションで暗号化され、暗号化することが推奨されます。仲介サーバーはメディア ゲートウェイに対する暗号化をサポートできますが、ゲートウェイは MTLS および証明書のストレージをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea86-p105">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended. The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aea86-141">ハイブリッド環境を実装する場合も、Skype ビジネス サーバー 2015 の暗号化レベルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea86-141">If you are implementing a hybrid environment, you must also modify the Skype for Business Server 2015 encryption level.</span></span> <span data-ttu-id="aea86-142">既定では、暗号化レベルは "必須" です。</span><span class="sxs-lookup"><span data-stu-id="aea86-142">By default, the encryption level is Required.</span></span> <span data-ttu-id="aea86-143">ビジネス サーバー管理シェルには、Skype を使用して、サポートされているにこの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea86-143">You must change this setting to Supported by using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="aea86-144">ハイブリッドを設定する方法の詳細については、展開に関するドキュメントで[ビジネス上でオンラインに設置型の Skype のユーザーの移動](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea86-144">For more information about setting up hybrid, see [Move users from Skype for Business Online to on premises](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md) in the Deployment documentation.</span></span>
  
## <a name="fips"></a><span data-ttu-id="aea86-145">FIPS</span><span class="sxs-lookup"><span data-stu-id="aea86-145">FIPS</span></span>

<span data-ttu-id="aea86-146">システムの FIPS 140-2 のアルゴリズムを使用するのには、Windows サーバー オペレーティング システムが構成されている場合に、連邦情報処理規格 (FIPS) 140-2 のアルゴリズムをサポートして Skype ビジネス サーバー 2015、2016 の Microsoft Exchange Server の動作します。暗号化します。</span><span class="sxs-lookup"><span data-stu-id="aea86-146">Skype for Business Server 2015 and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="aea86-147">FIPS のサポートを実装するには、サポートするようにサーバー 2015 のビジネス用の Skype を実行する各サーバーを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="aea86-147">To implement FIPS support, you must configure each server running Skype for Business Server 2015 to support it.</span></span>
  

