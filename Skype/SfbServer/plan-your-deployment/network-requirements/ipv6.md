---
title: Skype for Business での IPv6 の計画
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/21/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: '概要: 実装の IPv6 ビジネス サーバー 2015 の Skype をインストールする前にします。'
ms.openlocfilehash: 95868bc4eb99ee340f83d1f46cef70728d779b4f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-ipv6-in-skype-for-business"></a><span data-ttu-id="3860f-103">Skype for Business での IPv6 の計画</span><span class="sxs-lookup"><span data-stu-id="3860f-103">Plan for IPv6 in Skype for Business</span></span>
 
<span data-ttu-id="3860f-104">**の概要:** ビジネス サーバー 2015 の Skype をインストールする前に、IPv6 を実装します。</span><span class="sxs-lookup"><span data-stu-id="3860f-104">**Summary:** Implement IPv6 before you install Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3860f-105">Skype ビジネス サーバー用には、IP バージョン 6 (IPv6) のサポートが含まれています。 アドレスを IP バージョン 4 (IPv4) の継続的なサポートと対応します。</span><span class="sxs-lookup"><span data-stu-id="3860f-105">Skype for Business Server includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> 

<span data-ttu-id="3860f-106">IPv4 アドレスは 32 ビットのアドレスで、これを使用することでコンピューターはインターネットを介して通信できます。</span><span class="sxs-lookup"><span data-stu-id="3860f-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="3860f-107">により世界中のデバイス数の増加、使用可能な IPv4 アドレス実行します。このため、多くの新しいデバイスを移動して、IPv6 アドレスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="3860f-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="3860f-108">IPv6 アドレスは、IPv4 アドレスと同じ機能 (および追加機能) を実行しますが、32 ビットだけではなく、128 ビットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3860f-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="3860f-109">これにより、新しいアドレス セットだけでなく、より多くのアドレスも提供できます。</span><span class="sxs-lookup"><span data-stu-id="3860f-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> 

<span data-ttu-id="3860f-110">典型的な IPv4 アドレスの例には 192.0.2.235 などがありますが、IPv6 アドレスでは 2001:0db8:85a3:0000:0000:8a2e:0370:7334 のようになります。</span><span class="sxs-lookup"><span data-stu-id="3860f-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="3860f-111">書式設定と IPv6 アドレスを使用するデバイスの機能の変更には、ビジネスのサーバーのインストール、Skype でいくつかの展開と構成の考慮事項が必要です。</span><span class="sxs-lookup"><span data-stu-id="3860f-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Skype for Business Server installation.</span></span> 

<span data-ttu-id="3860f-112">このトピックには次のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="3860f-112">This topic includes the following sections:</span></span>
  
- [<span data-ttu-id="3860f-113">Overview of IP address types</span><span class="sxs-lookup"><span data-stu-id="3860f-113">Overview of IP address types</span></span>](ipv6.md#over)
    
- [<span data-ttu-id="3860f-114">Technical requirements for IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-114">Technical requirements for IPv6</span></span>](ipv6.md#tech)
    
- [<span data-ttu-id="3860f-115">Migration and coexistence considerations for IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-115">Migration and coexistence considerations for IPv6</span></span>](ipv6.md#migration)
    
<span data-ttu-id="3860f-116">IPv6 アドレスを使用して、判断した場合は、[ビジネスの Skype の構成の IP アドレスの種類](ip-address-types.md)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3860f-116">If you determine you will be using IPv6 addresses, refer to the [Configure IP address types in Skype for Business](ip-address-types.md) article.</span></span>
  
## <a name="overview-of-ip-address-types"></a><span data-ttu-id="3860f-117">IP アドレス タイプの概要</span><span class="sxs-lookup"><span data-stu-id="3860f-117">Overview of IP address types</span></span>
<span data-ttu-id="3860f-118"><a name="over"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-118"></span></span>

<span data-ttu-id="3860f-119">Skype のビジネス サーバーの IP アドレスを構成するとき、3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3860f-119">You have three options when configuring IP addresses in Skype for Business Server.</span></span> <span data-ttu-id="3860f-120">Skype のビジネスをサポートするサーバー IP バージョン 4 (IPv4) では、唯一の IP バージョン 6 (IPv6) の場合、だけを構成するか、両方の組み合わせ (と呼ばれる、デュアル ・ スタック)。</span><span class="sxs-lookup"><span data-stu-id="3860f-120">You can configure Skype for Business Server to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a dual stack).</span></span> <span data-ttu-id="3860f-121">各種の構成には、いくつか考慮すべき問題があります。</span><span class="sxs-lookup"><span data-stu-id="3860f-121">There are several issues to consider with each type of configuration:</span></span>
  
- <span data-ttu-id="3860f-122">**IPv4 のみ**IPv6 は、IPv4 アドレスが世界を実行するために作成されました。</span><span class="sxs-lookup"><span data-stu-id="3860f-122">**IPv4 only** IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="3860f-123">最終的には、IPv6 は、世界中が、この時点で完全にサポート、IPv6 をサポートしていない多くの企業と、企業と通信する必要があるデバイスと、時間のない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3860f-123">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="3860f-124">ビジネス サーバーの実装については、Skype は、ほとんどの既存のデバイスと通信できることを確認するのには、IPv4 のみの構成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3860f-124">An IPv4-only configuration will help to ensure that your Skype for Business Server implementation can communicate with most existing devices.</span></span>
    
- <span data-ttu-id="3860f-125">**IPv6 のみ**逆に、完全な IPv6 実装は多くの既存のデバイスとの通信を除外します。</span><span class="sxs-lookup"><span data-stu-id="3860f-125">**IPv6 only** Conversely, a full IPv6 implementation will exclude communication with many existing devices.</span></span>
    
- <span data-ttu-id="3860f-126">**デュアル ・ スタック**デュアル ・ スタックとは、IPv4 と IPv6 アドレスの両方が有効になっているネットワークです。</span><span class="sxs-lookup"><span data-stu-id="3860f-126">**Dual Stack** Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="3860f-127">この構成は Skype でビジネス サーバーの全 IPv4 からフル IPv6 への移行が数年を要するほとんどの場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="3860f-127">This configuration is supported in Skype for Business Server because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>
    
<span data-ttu-id="3860f-128">次のセクションでは、ビジネス サーバー機能のさまざまな Skype のこれら 3 つの構成間での互換性を説明します。</span><span class="sxs-lookup"><span data-stu-id="3860f-128">The following sections outline the compatibility among these three configurations for various Skype for Business Server features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3860f-p106">クライアントまたはサーバーを IPv6 のみの構成にすることは、試験や検証の目的でのみサポートされています。IPv6 のみの構成は運用展開ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3860f-p106">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span> 
  
### <a name="client-registration"></a><span data-ttu-id="3860f-131">クライアントの登録</span><span class="sxs-lookup"><span data-stu-id="3860f-131">Client Registration</span></span>
<span data-ttu-id="3860f-132"><a name="client"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-132"></span></span>

|<span data-ttu-id="3860f-133">**クライアント エンドポイントのネットワーク**</span><span class="sxs-lookup"><span data-stu-id="3860f-133">**Client endpoint network**</span></span>|<span data-ttu-id="3860f-134">**サーバー ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="3860f-134">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3860f-135">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-135">IPv4</span></span>  <br/> |<span data-ttu-id="3860f-136">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-136">IPv4</span></span>  <br/> |
|<span data-ttu-id="3860f-137">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-137">IPv4</span></span>  <br/> |<span data-ttu-id="3860f-138">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-138">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-139">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-139">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-140">IPv4</span></span>  <br/> |
|<span data-ttu-id="3860f-141">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-141">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-142">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-142">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-143">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-143">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-144">IPv6</span></span>  <br/> |
|<span data-ttu-id="3860f-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-145">IPv6</span></span>  <br/> |<span data-ttu-id="3860f-146">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-146">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-147">IPv6</span></span>  <br/> |<span data-ttu-id="3860f-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-148">IPv6</span></span>  <br/> |
   
### <a name="peer-to-peer-client"></a><span data-ttu-id="3860f-149">ピアツーピア クライアント</span><span class="sxs-lookup"><span data-stu-id="3860f-149">Peer-to-Peer Client</span></span>
<span data-ttu-id="3860f-150"><a name="peer"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-150"></span></span>

<span data-ttu-id="3860f-p107">ピアツーピア通信には、オーディオ、音声ビデオ、アプリケーション共有、ファイル転送などがあります。両方のクライアントが正常に登録された後、次の組み合わせがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3860f-p107">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>
  
|<span data-ttu-id="3860f-153">**クライアント エンドポイント 1**</span><span class="sxs-lookup"><span data-stu-id="3860f-153">**Client endpoint 1**</span></span>|<span data-ttu-id="3860f-154">**クライアント エンドポイント 2**</span><span class="sxs-lookup"><span data-stu-id="3860f-154">**Client endpoint 2**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3860f-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-155">IPv4</span></span>  <br/> |<span data-ttu-id="3860f-156">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-156">IPv4</span></span>  <br/> |
|<span data-ttu-id="3860f-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-157">IPv4</span></span>  <br/> |<span data-ttu-id="3860f-158">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-158">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-159">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-159">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-160">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-160">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-161">IPv6</span></span>  <br/> |<span data-ttu-id="3860f-162">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-162">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-163">IPv6</span></span>  <br/> |<span data-ttu-id="3860f-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-164">IPv6</span></span>  <br/> |
   
### <a name="conferencing"></a><span data-ttu-id="3860f-165">会議</span><span class="sxs-lookup"><span data-stu-id="3860f-165">Conferencing</span></span>
<span data-ttu-id="3860f-166"><a name="conf"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-166"></span></span>

<span data-ttu-id="3860f-167">会議には、音声ビデオ、アプリケーション共有、およびホワイト ボードやファイル共有などのデータ コラボレーション アプリケーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3860f-167">Conferencing includes audio/video, application sharing, and data collaboration applications like whiteboarding and file sharing.</span></span>
  
|<span data-ttu-id="3860f-168">**クライアント エンドポイントのネットワーク**</span><span class="sxs-lookup"><span data-stu-id="3860f-168">**Client endpoint network**</span></span>|<span data-ttu-id="3860f-169">**サーバー ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="3860f-169">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3860f-170">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-170">IPv4</span></span>  <br/> |<span data-ttu-id="3860f-171">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-171">IPv4</span></span>  <br/> |
|<span data-ttu-id="3860f-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-172">IPv4</span></span>  <br/> |<span data-ttu-id="3860f-173">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-173">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-174">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-174">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-175">IPv4</span></span>  <br/> |
|<span data-ttu-id="3860f-176">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-176">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-177">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-177">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-178">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-178">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-179">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-179">IPv6</span></span>  <br/> |
|<span data-ttu-id="3860f-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-180">IPv6</span></span>  <br/> |<span data-ttu-id="3860f-181">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-181">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-182">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-182">IPv6</span></span>  <br/> |<span data-ttu-id="3860f-183">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-183">IPv6</span></span>  <br/> |
   
### <a name="mediation-serverpstn"></a><span data-ttu-id="3860f-184">仲介サーバー/PSTN</span><span class="sxs-lookup"><span data-stu-id="3860f-184">Mediation Server/PSTN</span></span>
<span data-ttu-id="3860f-185"><a name="med"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-185"></span></span>

<span data-ttu-id="3860f-186">Skype ビジネス サーバーのトラフィックは、IPv6 インタ フェースを使用する場合、メディア バイ パスを公衆交換電話網 (PSTN) 呼び出しをサポートされません。</span><span class="sxs-lookup"><span data-stu-id="3860f-186">Skype for Business Server does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="3860f-187">メディア バイパスが必要な場合は、PSTN ゲートウェイを IPv4 に構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3860f-187">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span> 
  
|<span data-ttu-id="3860f-188">**プライマリ ・ インタ フェース 1**</span><span class="sxs-lookup"><span data-stu-id="3860f-188">**Primary interface 1**</span></span>|<span data-ttu-id="3860f-189">**(仲介サーバー) では、PSTN のインタ フェース**</span><span class="sxs-lookup"><span data-stu-id="3860f-189">**PSTN interface (on Mediation Server)**</span></span>|<span data-ttu-id="3860f-190">**PSTN ゲートウェイの設定**</span><span class="sxs-lookup"><span data-stu-id="3860f-190">**PSTN gateway setting**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3860f-191">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-191">IPv4</span></span>  <br/> |<span data-ttu-id="3860f-192">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-192">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-193">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-193">IPv4</span></span>  <br/> |
|<span data-ttu-id="3860f-194">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-194">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-195">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-195">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-196">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-196">IPv4</span></span>  <br/> |
|<span data-ttu-id="3860f-197">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-197">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-198">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-198">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-199">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-199">IPv6</span></span>  <br/> |
   
1. <span data-ttu-id="3860f-200">主要なインターフェイスは、ビジネスのサーバー コンポーネントの Skype と通信するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="3860f-200">The primary interface is the interface that communicates with the Skype for Business Server components.</span></span>
  
### <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="3860f-201">リモート ユーザーのピアツーピア通信</span><span class="sxs-lookup"><span data-stu-id="3860f-201">Remote User Peer-to-Peer Communications</span></span>
<span data-ttu-id="3860f-202"><a name="remote"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-202"></span></span>

<span data-ttu-id="3860f-203">リモート ユーザーとのピアツーピア通信には、インスタント メッセージング、音声ビデオ、アプリケーション共有、およびファイル転送が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3860f-203">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>
  
|<span data-ttu-id="3860f-204">**リモート ユーザーのネットワーク**</span><span class="sxs-lookup"><span data-stu-id="3860f-204">**Remote user network**</span></span>|<span data-ttu-id="3860f-205">**エッジ サーバー (外部境界)**</span><span class="sxs-lookup"><span data-stu-id="3860f-205">**Edge server (External edge)**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3860f-206">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-206">IPv4</span></span>  <br/> |<span data-ttu-id="3860f-207">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-207">IPv4</span></span>  <br/> |
|<span data-ttu-id="3860f-208">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-208">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-209">IPv4</span><span class="sxs-lookup"><span data-stu-id="3860f-209">IPv4</span></span>  <br/> |
|<span data-ttu-id="3860f-210">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-210">Dual stack</span></span>  <br/> |<span data-ttu-id="3860f-211">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-211">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-212">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-212">IPv6</span></span>  <br/> |<span data-ttu-id="3860f-213">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="3860f-213">Dual stack</span></span>  <br/> |
|<span data-ttu-id="3860f-214">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-214">IPv6</span></span>  <br/> |<span data-ttu-id="3860f-215">IPv6</span><span class="sxs-lookup"><span data-stu-id="3860f-215">IPv6</span></span>  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="3860f-216">フロントエンド プールとエッジ プールの構成</span><span class="sxs-lookup"><span data-stu-id="3860f-216">Front End Pool and Edge Pool Configuration</span></span>
<span data-ttu-id="3860f-217"><a name="FE_pool"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-217"></span></span>

<span data-ttu-id="3860f-218">次の表は、フロント エンド サーバー プールと内部エッジ サーバー プールのサポート ・ マトリックスを示します。</span><span class="sxs-lookup"><span data-stu-id="3860f-218">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>
  
<span data-ttu-id="3860f-219">**フロント エンド プール、エッジ プール (内部エッジ) マトリックス**</span><span class="sxs-lookup"><span data-stu-id="3860f-219">**Front End Pool and Edge Pool (Internal Edge) Matrix**</span></span>

||<span data-ttu-id="3860f-220">**エッジ プール: IPv4**</span><span class="sxs-lookup"><span data-stu-id="3860f-220">**Edge Pool: IPv4**</span></span> <br/> |<span data-ttu-id="3860f-221">**エッジ プール: デュアル スタック**</span><span class="sxs-lookup"><span data-stu-id="3860f-221">**Edge Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="3860f-222">**エッジ プール: IPv6**</span><span class="sxs-lookup"><span data-stu-id="3860f-222">**Edge Pool: IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3860f-223">**フロントエンド プール: IPv4**</span><span class="sxs-lookup"><span data-stu-id="3860f-223">**Front End Pool: IPv4**</span></span> <br/> |<span data-ttu-id="3860f-224">はい</span><span class="sxs-lookup"><span data-stu-id="3860f-224">Yes</span></span>  <br/> |<span data-ttu-id="3860f-225">あり</span><span class="sxs-lookup"><span data-stu-id="3860f-225">Yes</span></span>  <br/> |<span data-ttu-id="3860f-226">いいえ</span><span class="sxs-lookup"><span data-stu-id="3860f-226">No</span></span>  <br/> |
|<span data-ttu-id="3860f-227">**フロントエンド プール: デュアル スタック**</span><span class="sxs-lookup"><span data-stu-id="3860f-227">**Front End Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="3860f-228">はい</span><span class="sxs-lookup"><span data-stu-id="3860f-228">Yes</span></span>  <br/> |<span data-ttu-id="3860f-229">あり</span><span class="sxs-lookup"><span data-stu-id="3860f-229">Yes</span></span>  <br/> |<span data-ttu-id="3860f-230">いいえ</span><span class="sxs-lookup"><span data-stu-id="3860f-230">No</span></span>  <br/> |
|<span data-ttu-id="3860f-231">**フロントエンド プール: IPv6**</span><span class="sxs-lookup"><span data-stu-id="3860f-231">**Front End Pool: IPv6**</span></span> <br/> |<span data-ttu-id="3860f-232">いいえ</span><span class="sxs-lookup"><span data-stu-id="3860f-232">No</span></span>  <br/> |<span data-ttu-id="3860f-233">なし</span><span class="sxs-lookup"><span data-stu-id="3860f-233">No</span></span>  <br/> |<span data-ttu-id="3860f-234">うん\*</span><span class="sxs-lookup"><span data-stu-id="3860f-234">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="3860f-235">\*ラボ環境でのみ、この組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="3860f-235">\* Use this combination only in a lab environment.</span></span>
  
<span data-ttu-id="3860f-236">次のテーブルは、内部エッジ インターフェイスと外部エッジ インターフェイスの組み合わせのサポート マトリックスです。</span><span class="sxs-lookup"><span data-stu-id="3860f-236">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>
  
<span data-ttu-id="3860f-237">**プール (内部エッジ) のエッジとエッジのプール (外部境界) マトリックス**</span><span class="sxs-lookup"><span data-stu-id="3860f-237">**Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix**</span></span>

||<span data-ttu-id="3860f-238">**エッジ プール (外部エッジ): IPv4**</span><span class="sxs-lookup"><span data-stu-id="3860f-238">**Edge Pool (External Edge) : IPv4**</span></span> <br/> |<span data-ttu-id="3860f-239">**エッジ プール (外部エッジ): デュアル スタック**</span><span class="sxs-lookup"><span data-stu-id="3860f-239">**Edge Pool (External Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="3860f-240">**エッジ プール (外部エッジ): IPv6**</span><span class="sxs-lookup"><span data-stu-id="3860f-240">**Edge Pool (External Edge): IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3860f-241">**エッジ プール (内部エッジ): IPv4**</span><span class="sxs-lookup"><span data-stu-id="3860f-241">**Edge Pool (Internal Edge): IPv4**</span></span> <br/> |<span data-ttu-id="3860f-242">はい</span><span class="sxs-lookup"><span data-stu-id="3860f-242">Yes</span></span>  <br/> |<span data-ttu-id="3860f-243">あり</span><span class="sxs-lookup"><span data-stu-id="3860f-243">Yes</span></span>  <br/> |<span data-ttu-id="3860f-244">いいえ</span><span class="sxs-lookup"><span data-stu-id="3860f-244">No</span></span>  <br/> |
|<span data-ttu-id="3860f-245">**エッジ プール (内部エッジ): デュアル スタック**</span><span class="sxs-lookup"><span data-stu-id="3860f-245">**Edge Pool (Internal Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="3860f-246">いいえ</span><span class="sxs-lookup"><span data-stu-id="3860f-246">No</span></span>  <br/> |<span data-ttu-id="3860f-247">あり</span><span class="sxs-lookup"><span data-stu-id="3860f-247">Yes</span></span>  <br/> |<span data-ttu-id="3860f-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="3860f-248">No</span></span>  <br/> |
|<span data-ttu-id="3860f-249">**エッジ プール (内部エッジ): IPv6**</span><span class="sxs-lookup"><span data-stu-id="3860f-249">**Edge Pool (Internal Edge): IPv6**</span></span> <br/> |<span data-ttu-id="3860f-250">いいえ</span><span class="sxs-lookup"><span data-stu-id="3860f-250">No</span></span>  <br/> |<span data-ttu-id="3860f-251">なし</span><span class="sxs-lookup"><span data-stu-id="3860f-251">No</span></span>  <br/> |<span data-ttu-id="3860f-252">うん\*</span><span class="sxs-lookup"><span data-stu-id="3860f-252">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="3860f-253">\*ラボ環境でのみ、この組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="3860f-253">\* Use this combination only in a lab environment.</span></span>
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="3860f-254">IPv6 の高度なエンタープライズ VoIP のサポート</span><span class="sxs-lookup"><span data-stu-id="3860f-254">Advanced Enterprise Voice Support for IPv6</span></span>
<span data-ttu-id="3860f-255"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-255"></span></span>

<span data-ttu-id="3860f-p109">通話受付管理 (CAC)、拡張 9-1-1 (E9-1-1)、メディア バイパスなどの展開は、IPv4 のみ、またはデュアル スタック実装として構成する必要があります。IPv6 だけを使用するエンドポイントは、これらのどの機能も使用できません。</span><span class="sxs-lookup"><span data-stu-id="3860f-p109">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation. Endpoints using only IPv6 cannot use any of these features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3860f-258">展開では、デュアル スタック、でもビジネス サーバーのクライアントに対して、Skype に接続する場合、Skype ビジネス サーバーの IPv6 を使用して、Skype のビジネス サーバーと、~ 9-1-1 をサポートするために適切な IPv4 アドレスにマップするよう最善の努力。</span><span class="sxs-lookup"><span data-stu-id="3860f-258">In a dual-stacked deployment, even if a Skype for Business Server client connects to a Skype for Business Server by using IPv6, Skype for Business Server will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span> 
  
<span data-ttu-id="3860f-259">IPv6 アドレスを使用して、場所情報サービスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3860f-259">Location Information service with IPv6 addresses is not supported.</span></span>
  
<span data-ttu-id="3860f-p110">Exchange ユニファイド メッセージング (UM) では IPv6 をサポートしていません。Exchange UM の場合は、DNS 解決が IPv6 アドレスを返さないことを確認します。IPv6 を使用すると、通話がボイス メールに送信されたときに障害が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3860f-p110">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span> 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a><span data-ttu-id="3860f-263">IPv6 のビジネス サーバー機能をサポートするためには、他の Skype</span><span class="sxs-lookup"><span data-stu-id="3860f-263">Other Skype for Business Server Feature Support for IPv6</span></span>
<span data-ttu-id="3860f-264"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-264"></span></span>

<span data-ttu-id="3860f-265">機能やコンポーネントに記載されている、だけでなくビジネス サーバー用の Skype は次の機能の IPv6 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="3860f-265">In addition to the features and components mentioned previously, Skype for Business Server supports IPv6 for the following features:</span></span>
  
- <span data-ttu-id="3860f-266">**常設チャット**</span><span class="sxs-lookup"><span data-stu-id="3860f-266">**Persistent Chat**</span></span>
    
    <span data-ttu-id="3860f-267">永続的なチャットの IPv6 を構成するには、トポロジ ビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="3860f-267">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="3860f-268">永続的なチャットの構成の詳細については、永続的なチャット サーバーの展開のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3860f-268">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>
    
- <span data-ttu-id="3860f-269">**Quality of Experience (QoE) と通話詳細記録 (CDR) のレポート**</span><span class="sxs-lookup"><span data-stu-id="3860f-269">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="3860f-270">IPv4 と IPv6 のいずれの場合でも、監視レポートには監視サーバー データベースに格納されている IP アドレスがそのまま含まれます。</span><span class="sxs-lookup"><span data-stu-id="3860f-270">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>
    
## <a name="technical-requirements-for-ipv6"></a><span data-ttu-id="3860f-271">IPv6 の技術要件</span><span class="sxs-lookup"><span data-stu-id="3860f-271">Technical requirements for IPv6</span></span>
<span data-ttu-id="3860f-272"><a name="tech"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-272"></span></span>

<span data-ttu-id="3860f-273">Skype ビジネス サーバーの IPv6 用に構成を計画する場合は、次の要件に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3860f-273">If you plan to configure Skype for Business Server for IPv6, keep the following requirements in mind:</span></span>
  
- <span data-ttu-id="3860f-274">Skype で IPv6 アドレスを使用して、ビジネス サーバー、ドメイン ネーム システムのレコードを発見、IPv6 アドレスに解決する必要があります (DNS) レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3860f-274">To use IPv6 addresses with Skype for Business Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="3860f-275">IPv6 DNS はホスト AAAA (クアッド A) レコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="3860f-275">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="3860f-276">展開内で IPv4 と IPv6 の両方を使用する場合は、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA レコードの両方を構成し保持するのが最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="3860f-276">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="3860f-277">自身の展開を IPv6 に完全に移行した場合でも、IPv4 を使用する外部ユーザーのために IPv4 DNS ホスト レコードが引き続き必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3860f-277">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="3860f-p113">IPv6 DNS ホスト レコードは IPv6 の使用を始める前から展開できます。クライアントまたはサーバーが IPv6 を使用しない場合、そのレコードは参照されません。移行時のテクノロジは、どのレコードを使用するかを、移行テクノロジの構成およびポリシーに基づいて判断します。</span><span class="sxs-lookup"><span data-stu-id="3860f-p113">You can deploy IPv6 DNS host records before you start using IPv6. If the client or server doesn't use IPv6, the record will not be referenced. Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>
    
- <span data-ttu-id="3860f-281">各 IPv6 アドレスは、スコープを持ちます。</span><span class="sxs-lookup"><span data-stu-id="3860f-281">Each IPv6 address has a scope.</span></span> <span data-ttu-id="3860f-282">IPv6 に対応するために使用できる 3 つの範囲、IPv6 のグローバル アドレス (IPv4 のパブリック アドレスに似ています)、IPv6 一意なローカル アドレス (プライベート IPv4 アドレスの範囲に似ています)、および IPv6 のリンク ローカル アドレス (自動プライベート IP アドレスに似ていますWindows サーバー IPv4 の場合)。</span><span class="sxs-lookup"><span data-stu-id="3860f-282">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="3860f-283">プール内のすべてのサーバーには、同じスコープの IPv6 アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="3860f-283">All the servers within a pool should have IPv6 addresses with the same scope.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="3860f-284">IPv6 では、複雑なトピックし、は、ネットワーク チームと、インターネット プロバイダーは、Windows サーバー レベルとビジネスのサーバー レベルの Skype を割り当てられたアドレスが期待どおりに動作するように慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3860f-284">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Skype for Business Server level work as expected.</span></span> <span data-ttu-id="3860f-285">IPv6 のアドレス指定と計画その他のリソースは、このトピックの最後にあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3860f-285">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span> 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a><span data-ttu-id="3860f-286">IPv6 の移行および共存の検討事項</span><span class="sxs-lookup"><span data-stu-id="3860f-286">Migration and coexistence considerations for IPv6</span></span>
<span data-ttu-id="3860f-287"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-287"></span></span>

<span data-ttu-id="3860f-288">IP バージョン 6 (IPv6) は、Lync Server 2010 または Office Communications Server ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3860f-288">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="3860f-289">試験運用のため、ビジネス サーバー デュアル スタックの共存の Lync Server 2010 と Skype をテストできます。</span><span class="sxs-lookup"><span data-stu-id="3860f-289">For piloting purposes, you can test Lync Server 2010 and Skype for Business Server dual-stack coexistence.</span></span> <span data-ttu-id="3860f-290">特定の中央サイトのすべてのプールにアップグレードを Skype ビジネス サーバーの IPv6 を有効にする前にことをお勧めします。 (デュアル スタック ネットワーク) のプールのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="3860f-290">We recommend that all pools for a given central site are upgraded to Skype for Business Server before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="3860f-291">IPv6 に対応したプールのみを構成する必要がある場合は、テスト用のラボ環境に IPv6 専用のプールを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3860f-291">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>
  
<span data-ttu-id="3860f-292">次のシナリオは、移行と共存でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3860f-292">The following scenarios are supported during migration and coexistence:</span></span>
  
- <span data-ttu-id="3860f-293">IPv4 モードの場合は、ビジネス サーバー、Lync Server 2013 では、Lync Server 2010 プールの Skype が Skype とデュアル スタック モードでのビジネスのサーバーに共存します。</span><span class="sxs-lookup"><span data-stu-id="3860f-293">Skype for Business Server, Lync Server 2013, and Lync Server 2010 pools in IPv4 mode, coexisting with Skype for Business Server in dual-stack mode.</span></span>
    
- <span data-ttu-id="3860f-294">IPv6 専用のプールが孤立している場合、IPv6 のみのモードでのビジネス サーバー プールの Skype です。</span><span class="sxs-lookup"><span data-stu-id="3860f-294">Skype for Business Server pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3860f-295">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="3860f-295">See also</span></span>
<span data-ttu-id="3860f-296"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="3860f-296"></span></span>

#### 

[<span data-ttu-id="3860f-297">ビジネス用の Skype で IP アドレスの種類を構成します。</span><span class="sxs-lookup"><span data-stu-id="3860f-297">Configure IP address types in Skype for Business</span></span>](ip-address-types.md)
#### 

[<span data-ttu-id="3860f-298">IP バージョン 6 のアドレス指定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="3860f-298">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)
  
[<span data-ttu-id="3860f-299">IPv6 グローバル ユニキャスト アドレスの形式</span><span class="sxs-lookup"><span data-stu-id="3860f-299">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)
  
[<span data-ttu-id="3860f-300">一意のローカル IPv6 ユニキャスト アドレス</span><span class="sxs-lookup"><span data-stu-id="3860f-300">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)

