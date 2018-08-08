---
title: Skype for Business での IPv6 の計画
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: '概要: 実装の IPv6 ビジネス サーバーの Skype をインストールする前にします。'
ms.openlocfilehash: 6bd33522492edb68ba3e0a6873e81afee59216d8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968139"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a><span data-ttu-id="b31c0-103">Skype for Business での IPv6 の計画</span><span class="sxs-lookup"><span data-stu-id="b31c0-103">Plan for IPv6 in Skype for Business</span></span>
 
<span data-ttu-id="b31c0-104">**の概要:** ビジネス サーバーの Skype をインストールする前に、IPv6 を実装します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-104">**Summary:** Implement IPv6 before you install Skype for Business Server.</span></span>
  
<span data-ttu-id="b31c0-105">Skype ビジネス サーバー用には、IP バージョン 6 (IPv6) のサポートが含まれています。 アドレスを IP バージョン 4 (IPv4) の継続的なサポートと対応します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-105">Skype for Business Server includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> 

<span data-ttu-id="b31c0-106">IPv4 アドレスは 32 ビットのアドレスで、これを使用することでコンピューターはインターネットを介して通信できます。</span><span class="sxs-lookup"><span data-stu-id="b31c0-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="b31c0-107">により世界中のデバイス数の増加、使用可能な IPv4 アドレス実行します。このため、多くの新しいデバイスを移動して、IPv6 アドレスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b31c0-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="b31c0-108">IPv6 アドレスは、IPv4 アドレスと同じ機能 (および追加機能) を実行しますが、32 ビットだけではなく、128 ビットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="b31c0-109">これにより、新しいアドレス セットだけでなく、より多くのアドレスも提供できます。</span><span class="sxs-lookup"><span data-stu-id="b31c0-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> 

<span data-ttu-id="b31c0-110">典型的な IPv4 アドレスの例には 192.0.2.235 などがありますが、IPv6 アドレスでは 2001:0db8:85a3:0000:0000:8a2e:0370:7334 のようになります。</span><span class="sxs-lookup"><span data-stu-id="b31c0-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="b31c0-111">書式設定と IPv6 アドレスを使用するデバイスの機能の変更には、ビジネスのサーバーのインストール、Skype でいくつかの展開と構成の考慮事項が必要です。</span><span class="sxs-lookup"><span data-stu-id="b31c0-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Skype for Business Server installation.</span></span> 

<span data-ttu-id="b31c0-112">このトピックには次のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="b31c0-112">This topic includes the following sections:</span></span>
  
- [<span data-ttu-id="b31c0-113">Overview of IP address types</span><span class="sxs-lookup"><span data-stu-id="b31c0-113">Overview of IP address types</span></span>](ipv6.md#over)
    
- [<span data-ttu-id="b31c0-114">Technical requirements for IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-114">Technical requirements for IPv6</span></span>](ipv6.md#tech)
    
- [<span data-ttu-id="b31c0-115">Migration and coexistence considerations for IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-115">Migration and coexistence considerations for IPv6</span></span>](ipv6.md#migration)
    
<span data-ttu-id="b31c0-116">IPv6 アドレスを使用して、判断した場合は、[ビジネスの Skype の構成の IP アドレスの種類](ip-address-types.md)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b31c0-116">If you determine you will be using IPv6 addresses, refer to the [Configure IP address types in Skype for Business](ip-address-types.md) article.</span></span>
  
## <a name="overview-of-ip-address-types"></a><span data-ttu-id="b31c0-117">IP アドレス タイプの概要</span><span class="sxs-lookup"><span data-stu-id="b31c0-117">Overview of IP address types</span></span>
<span data-ttu-id="b31c0-118"><a name="over"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-118"></span></span>

<span data-ttu-id="b31c0-119">Skype のビジネス サーバーの IP アドレスを構成するとき、3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b31c0-119">You have three options when configuring IP addresses in Skype for Business Server.</span></span> <span data-ttu-id="b31c0-120">Skype のビジネスをサポートするサーバー IP バージョン 4 (IPv4) では、唯一の IP バージョン 6 (IPv6) の場合、だけを構成するか、両方の組み合わせ (と呼ばれる、デュアル ・ スタック)。</span><span class="sxs-lookup"><span data-stu-id="b31c0-120">You can configure Skype for Business Server to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a dual stack).</span></span> <span data-ttu-id="b31c0-121">各種の構成には、いくつか考慮すべき問題があります。</span><span class="sxs-lookup"><span data-stu-id="b31c0-121">There are several issues to consider with each type of configuration:</span></span>
  
- <span data-ttu-id="b31c0-122">**IPv4 のみ**IPv6 は、IPv4 アドレスが世界を実行するために作成されました。</span><span class="sxs-lookup"><span data-stu-id="b31c0-122">**IPv4 only** IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="b31c0-123">最終的には、IPv6 は、世界中が、この時点で完全にサポート、IPv6 をサポートしていない多くの企業と、企業と通信する必要があるデバイスと、時間のない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b31c0-123">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="b31c0-124">ビジネス サーバーの実装については、Skype は、ほとんどの既存のデバイスと通信できることを確認するのには、IPv4 のみの構成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b31c0-124">An IPv4-only configuration will help to ensure that your Skype for Business Server implementation can communicate with most existing devices.</span></span>
    
- <span data-ttu-id="b31c0-125">**IPv6 のみ**逆に、完全な IPv6 実装は多くの既存のデバイスとの通信を除外します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-125">**IPv6 only** Conversely, a full IPv6 implementation will exclude communication with many existing devices.</span></span>
    
- <span data-ttu-id="b31c0-126">**デュアル ・ スタック**デュアル ・ スタックとは、IPv4 と IPv6 アドレスの両方が有効になっているネットワークです。</span><span class="sxs-lookup"><span data-stu-id="b31c0-126">**Dual Stack** Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="b31c0-127">この構成は Skype でビジネス サーバーの全 IPv4 からフル IPv6 への移行が数年を要するほとんどの場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="b31c0-127">This configuration is supported in Skype for Business Server because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>
    
<span data-ttu-id="b31c0-128">次のセクションでは、ビジネス サーバー機能のさまざまな Skype のこれら 3 つの構成間での互換性を説明します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-128">The following sections outline the compatibility among these three configurations for various Skype for Business Server features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b31c0-p106">クライアントまたはサーバーを IPv6 のみの構成にすることは、試験や検証の目的でのみサポートされています。IPv6 のみの構成は運用展開ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b31c0-p106">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span> 
  
### <a name="client-registration"></a><span data-ttu-id="b31c0-131">クライアントの登録</span><span class="sxs-lookup"><span data-stu-id="b31c0-131">Client Registration</span></span>
<span data-ttu-id="b31c0-132"><a name="client"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-132"></span></span>

|<span data-ttu-id="b31c0-133">**クライアント エンドポイント ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="b31c0-133">**Client endpoint network**</span></span>|<span data-ttu-id="b31c0-134">**サーバー ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="b31c0-134">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b31c0-135">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-135">IPv4</span></span>  <br/> |<span data-ttu-id="b31c0-136">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-136">IPv4</span></span>  <br/> |
|<span data-ttu-id="b31c0-137">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-137">IPv4</span></span>  <br/> |<span data-ttu-id="b31c0-138">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-138">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-139">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-139">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-140">IPv4</span></span>  <br/> |
|<span data-ttu-id="b31c0-141">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-141">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-142">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-142">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-143">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-143">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-144">IPv6</span></span>  <br/> |
|<span data-ttu-id="b31c0-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-145">IPv6</span></span>  <br/> |<span data-ttu-id="b31c0-146">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-146">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-147">IPv6</span></span>  <br/> |<span data-ttu-id="b31c0-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-148">IPv6</span></span>  <br/> |
   
### <a name="peer-to-peer-client"></a><span data-ttu-id="b31c0-149">ピアツーピア クライアント</span><span class="sxs-lookup"><span data-stu-id="b31c0-149">Peer-to-Peer Client</span></span>
<span data-ttu-id="b31c0-150"><a name="peer"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-150"></span></span>

<span data-ttu-id="b31c0-p107">ピアツーピア通信には、オーディオ、音声ビデオ、アプリケーション共有、ファイル転送などがあります。両方のクライアントが正常に登録された後、次の組み合わせがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b31c0-p107">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>
  
|<span data-ttu-id="b31c0-153">**クライアント エンドポイント 1**</span><span class="sxs-lookup"><span data-stu-id="b31c0-153">**Client endpoint 1**</span></span>|<span data-ttu-id="b31c0-154">**クライアント エンドポイント 2**</span><span class="sxs-lookup"><span data-stu-id="b31c0-154">**Client endpoint 2**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b31c0-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-155">IPv4</span></span>  <br/> |<span data-ttu-id="b31c0-156">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-156">IPv4</span></span>  <br/> |
|<span data-ttu-id="b31c0-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-157">IPv4</span></span>  <br/> |<span data-ttu-id="b31c0-158">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-158">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-159">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-159">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-160">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-160">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-161">IPv6</span></span>  <br/> |<span data-ttu-id="b31c0-162">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-162">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-163">IPv6</span></span>  <br/> |<span data-ttu-id="b31c0-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-164">IPv6</span></span>  <br/> |
   
### <a name="conferencing"></a><span data-ttu-id="b31c0-165">会議</span><span class="sxs-lookup"><span data-stu-id="b31c0-165">Conferencing</span></span>
<span data-ttu-id="b31c0-166"><a name="conf"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-166"></span></span>

<span data-ttu-id="b31c0-167">会議には、音声ビデオ、アプリケーション共有、およびホワイト ボードやファイル共有などのデータ コラボレーション アプリケーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b31c0-167">Conferencing includes audio/video, application sharing, and data collaboration applications like whiteboarding and file sharing.</span></span>
  
|<span data-ttu-id="b31c0-168">**クライアント エンドポイント ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="b31c0-168">**Client endpoint network**</span></span>|<span data-ttu-id="b31c0-169">**サーバー ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="b31c0-169">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b31c0-170">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-170">IPv4</span></span>  <br/> |<span data-ttu-id="b31c0-171">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-171">IPv4</span></span>  <br/> |
|<span data-ttu-id="b31c0-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-172">IPv4</span></span>  <br/> |<span data-ttu-id="b31c0-173">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-173">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-174">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-174">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-175">IPv4</span></span>  <br/> |
|<span data-ttu-id="b31c0-176">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-176">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-177">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-177">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-178">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-178">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-179">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-179">IPv6</span></span>  <br/> |
|<span data-ttu-id="b31c0-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-180">IPv6</span></span>  <br/> |<span data-ttu-id="b31c0-181">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-181">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-182">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-182">IPv6</span></span>  <br/> |<span data-ttu-id="b31c0-183">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-183">IPv6</span></span>  <br/> |
   
### <a name="mediation-serverpstn"></a><span data-ttu-id="b31c0-184">仲介サーバー/PSTN</span><span class="sxs-lookup"><span data-stu-id="b31c0-184">Mediation Server/PSTN</span></span>
<span data-ttu-id="b31c0-185"><a name="med"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-185"></span></span>

<span data-ttu-id="b31c0-186">Skype ビジネス サーバーのトラフィックは、IPv6 インタ フェースを使用する場合、メディア バイ パスを公衆交換電話網 (PSTN) 呼び出しをサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b31c0-186">Skype for Business Server does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="b31c0-187">メディア バイパスが必要な場合は、PSTN ゲートウェイを IPv4 に構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b31c0-187">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span> 
  
|<span data-ttu-id="b31c0-188">**プライマリ ・ インタ フェース 1**</span><span class="sxs-lookup"><span data-stu-id="b31c0-188">**Primary interface 1**</span></span>|<span data-ttu-id="b31c0-189">**PSTN インターフェイス (仲介サーバー上)**</span><span class="sxs-lookup"><span data-stu-id="b31c0-189">**PSTN interface (on Mediation Server)**</span></span>|<span data-ttu-id="b31c0-190">**PSTN ゲートウェイの設定**</span><span class="sxs-lookup"><span data-stu-id="b31c0-190">**PSTN gateway setting**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b31c0-191">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-191">IPv4</span></span>  <br/> |<span data-ttu-id="b31c0-192">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-192">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-193">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-193">IPv4</span></span>  <br/> |
|<span data-ttu-id="b31c0-194">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-194">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-195">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-195">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-196">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-196">IPv4</span></span>  <br/> |
|<span data-ttu-id="b31c0-197">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-197">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-198">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-198">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-199">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-199">IPv6</span></span>  <br/> |
   
1. <span data-ttu-id="b31c0-200">主要なインターフェイスは、ビジネスのサーバー コンポーネントの Skype と通信するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b31c0-200">The primary interface is the interface that communicates with the Skype for Business Server components.</span></span>
  
### <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="b31c0-201">リモート ユーザーのピアツーピア通信</span><span class="sxs-lookup"><span data-stu-id="b31c0-201">Remote User Peer-to-Peer Communications</span></span>
<span data-ttu-id="b31c0-202"><a name="remote"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-202"></span></span>

<span data-ttu-id="b31c0-203">リモート ユーザーとのピアツーピア通信には、インスタント メッセージング、音声ビデオ、アプリケーション共有、およびファイル転送が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b31c0-203">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>
  
|<span data-ttu-id="b31c0-204">**リモート ユーザー ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="b31c0-204">**Remote user network**</span></span>|<span data-ttu-id="b31c0-205">**エッジ サーバー (外部エッジ)**</span><span class="sxs-lookup"><span data-stu-id="b31c0-205">**Edge server (External edge)**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b31c0-206">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-206">IPv4</span></span>  <br/> |<span data-ttu-id="b31c0-207">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-207">IPv4</span></span>  <br/> |
|<span data-ttu-id="b31c0-208">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-208">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-209">IPv4</span><span class="sxs-lookup"><span data-stu-id="b31c0-209">IPv4</span></span>  <br/> |
|<span data-ttu-id="b31c0-210">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-210">Dual stack</span></span>  <br/> |<span data-ttu-id="b31c0-211">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-211">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-212">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-212">IPv6</span></span>  <br/> |<span data-ttu-id="b31c0-213">デュアル スタック</span><span class="sxs-lookup"><span data-stu-id="b31c0-213">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b31c0-214">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-214">IPv6</span></span>  <br/> |<span data-ttu-id="b31c0-215">IPv6</span><span class="sxs-lookup"><span data-stu-id="b31c0-215">IPv6</span></span>  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="b31c0-216">フロントエンド プールとエッジ プールの構成</span><span class="sxs-lookup"><span data-stu-id="b31c0-216">Front End Pool and Edge Pool Configuration</span></span>
<span data-ttu-id="b31c0-217"><a name="FE_pool"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-217"></span></span>

<span data-ttu-id="b31c0-218">次の表は、フロント エンド サーバー プールと内部エッジ サーバー プールのサポート ・ マトリックスを示します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-218">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>
  
<span data-ttu-id="b31c0-219">**フロントエンド プールとエッジ プール (内部エッジ) のマトリックス**</span><span class="sxs-lookup"><span data-stu-id="b31c0-219">**Front End Pool and Edge Pool (Internal Edge) Matrix**</span></span>

||<span data-ttu-id="b31c0-220">**エッジ プール: IPv4**</span><span class="sxs-lookup"><span data-stu-id="b31c0-220">**Edge Pool: IPv4**</span></span> <br/> |<span data-ttu-id="b31c0-221">**エッジ プール: デュアル スタック**</span><span class="sxs-lookup"><span data-stu-id="b31c0-221">**Edge Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="b31c0-222">**エッジ プール: IPv6**</span><span class="sxs-lookup"><span data-stu-id="b31c0-222">**Edge Pool: IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b31c0-223">**フロントエンド プール: IPv4**</span><span class="sxs-lookup"><span data-stu-id="b31c0-223">**Front End Pool: IPv4**</span></span> <br/> |<span data-ttu-id="b31c0-224">はい</span><span class="sxs-lookup"><span data-stu-id="b31c0-224">Yes</span></span>  <br/> |<span data-ttu-id="b31c0-225">あり</span><span class="sxs-lookup"><span data-stu-id="b31c0-225">Yes</span></span>  <br/> |<span data-ttu-id="b31c0-226">いいえ</span><span class="sxs-lookup"><span data-stu-id="b31c0-226">No</span></span>  <br/> |
|<span data-ttu-id="b31c0-227">**フロントエンド プール: デュアル スタック**</span><span class="sxs-lookup"><span data-stu-id="b31c0-227">**Front End Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="b31c0-228">はい</span><span class="sxs-lookup"><span data-stu-id="b31c0-228">Yes</span></span>  <br/> |<span data-ttu-id="b31c0-229">あり</span><span class="sxs-lookup"><span data-stu-id="b31c0-229">Yes</span></span>  <br/> |<span data-ttu-id="b31c0-230">いいえ</span><span class="sxs-lookup"><span data-stu-id="b31c0-230">No</span></span>  <br/> |
|<span data-ttu-id="b31c0-231">**フロントエンド プール: IPv6**</span><span class="sxs-lookup"><span data-stu-id="b31c0-231">**Front End Pool: IPv6**</span></span> <br/> |<span data-ttu-id="b31c0-232">いいえ</span><span class="sxs-lookup"><span data-stu-id="b31c0-232">No</span></span>  <br/> |<span data-ttu-id="b31c0-233">なし</span><span class="sxs-lookup"><span data-stu-id="b31c0-233">No</span></span>  <br/> |<span data-ttu-id="b31c0-234">あり\*</span><span class="sxs-lookup"><span data-stu-id="b31c0-234">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="b31c0-235">\*ラボ環境でのみ、この組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-235">\* Use this combination only in a lab environment.</span></span>
  
<span data-ttu-id="b31c0-236">次のテーブルは、内部エッジ インターフェイスと外部エッジ インターフェイスの組み合わせのサポート マトリックスです。</span><span class="sxs-lookup"><span data-stu-id="b31c0-236">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>
  
<span data-ttu-id="b31c0-237">**エッジ プール (内部エッジ) とエッジ プール (外部エッジ) のマトリックス**</span><span class="sxs-lookup"><span data-stu-id="b31c0-237">**Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix**</span></span>

||<span data-ttu-id="b31c0-238">**エッジ プール (外部エッジ): IPv4**</span><span class="sxs-lookup"><span data-stu-id="b31c0-238">**Edge Pool (External Edge) : IPv4**</span></span> <br/> |<span data-ttu-id="b31c0-239">**エッジ プール (外部エッジ): デュアル スタック**</span><span class="sxs-lookup"><span data-stu-id="b31c0-239">**Edge Pool (External Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="b31c0-240">**エッジ プール (外部エッジ): IPv6**</span><span class="sxs-lookup"><span data-stu-id="b31c0-240">**Edge Pool (External Edge): IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b31c0-241">**エッジ プール (内部エッジ): IPv4**</span><span class="sxs-lookup"><span data-stu-id="b31c0-241">**Edge Pool (Internal Edge): IPv4**</span></span> <br/> |<span data-ttu-id="b31c0-242">はい</span><span class="sxs-lookup"><span data-stu-id="b31c0-242">Yes</span></span>  <br/> |<span data-ttu-id="b31c0-243">あり</span><span class="sxs-lookup"><span data-stu-id="b31c0-243">Yes</span></span>  <br/> |<span data-ttu-id="b31c0-244">いいえ</span><span class="sxs-lookup"><span data-stu-id="b31c0-244">No</span></span>  <br/> |
|<span data-ttu-id="b31c0-245">**エッジ プール (内部エッジ): デュアル スタック**</span><span class="sxs-lookup"><span data-stu-id="b31c0-245">**Edge Pool (Internal Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="b31c0-246">いいえ</span><span class="sxs-lookup"><span data-stu-id="b31c0-246">No</span></span>  <br/> |<span data-ttu-id="b31c0-247">あり</span><span class="sxs-lookup"><span data-stu-id="b31c0-247">Yes</span></span>  <br/> |<span data-ttu-id="b31c0-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="b31c0-248">No</span></span>  <br/> |
|<span data-ttu-id="b31c0-249">**エッジ プール (内部エッジ): IPv6**</span><span class="sxs-lookup"><span data-stu-id="b31c0-249">**Edge Pool (Internal Edge): IPv6**</span></span> <br/> |<span data-ttu-id="b31c0-250">いいえ</span><span class="sxs-lookup"><span data-stu-id="b31c0-250">No</span></span>  <br/> |<span data-ttu-id="b31c0-251">なし</span><span class="sxs-lookup"><span data-stu-id="b31c0-251">No</span></span>  <br/> |<span data-ttu-id="b31c0-252">あり\*</span><span class="sxs-lookup"><span data-stu-id="b31c0-252">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="b31c0-253">\*ラボ環境でのみ、この組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-253">\* Use this combination only in a lab environment.</span></span>
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="b31c0-254">IPv6 の高度なエンタープライズ VoIP のサポート</span><span class="sxs-lookup"><span data-stu-id="b31c0-254">Advanced Enterprise Voice Support for IPv6</span></span>
<span data-ttu-id="b31c0-255"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-255"></span></span>

<span data-ttu-id="b31c0-p109">通話受付管理 (CAC)、拡張 9-1-1 (E9-1-1)、メディア バイパスなどの展開は、IPv4 のみ、またはデュアル スタック実装として構成する必要があります。IPv6 だけを使用するエンドポイントは、これらのどの機能も使用できません。</span><span class="sxs-lookup"><span data-stu-id="b31c0-p109">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation. Endpoints using only IPv6 cannot use any of these features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b31c0-258">展開では、デュアル スタック、でもビジネス サーバーのクライアントに対して、Skype に接続する場合、Skype ビジネス サーバーの IPv6 を使用して、Skype のビジネス サーバーと、~ 9-1-1 をサポートするために適切な IPv4 アドレスにマップするよう最善の努力。</span><span class="sxs-lookup"><span data-stu-id="b31c0-258">In a dual-stacked deployment, even if a Skype for Business Server client connects to a Skype for Business Server by using IPv6, Skype for Business Server will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span> 
  
<span data-ttu-id="b31c0-259">IPv6 アドレスを使用して、場所情報サービスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b31c0-259">Location Information service with IPv6 addresses is not supported.</span></span>
  
<span data-ttu-id="b31c0-p110">Exchange ユニファイド メッセージング (UM) では IPv6 をサポートしていません。Exchange UM の場合は、DNS 解決が IPv6 アドレスを返さないことを確認します。IPv6 を使用すると、通話がボイス メールに送信されたときに障害が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b31c0-p110">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span> 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a><span data-ttu-id="b31c0-263">IPv6 のビジネス サーバー機能をサポートするためには、他の Skype</span><span class="sxs-lookup"><span data-stu-id="b31c0-263">Other Skype for Business Server Feature Support for IPv6</span></span>
<span data-ttu-id="b31c0-264"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-264"></span></span>

<span data-ttu-id="b31c0-265">機能やコンポーネントに記載されている、だけでなくビジネス サーバー用の Skype は次の機能の IPv6 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b31c0-265">In addition to the features and components mentioned previously, Skype for Business Server supports IPv6 for the following features:</span></span>
  
- <span data-ttu-id="b31c0-266">**常設チャット**</span><span class="sxs-lookup"><span data-stu-id="b31c0-266">**Persistent Chat**</span></span>
    
    <span data-ttu-id="b31c0-267">永続的なチャットの IPv6 を構成するには、トポロジ ビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-267">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="b31c0-268">永続的なチャットの構成の詳細については、永続的なチャット サーバーの展開のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b31c0-268">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>
    
- <span data-ttu-id="b31c0-269">**Quality of Experience (QoE) と通話詳細記録 (CDR) のレポート**</span><span class="sxs-lookup"><span data-stu-id="b31c0-269">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="b31c0-270">IPv4 と IPv6 のいずれの場合でも、監視レポートには監視サーバー データベースに格納されている IP アドレスがそのまま含まれます。</span><span class="sxs-lookup"><span data-stu-id="b31c0-270">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>
    
## <a name="technical-requirements-for-ipv6"></a><span data-ttu-id="b31c0-271">IPv6 の技術要件</span><span class="sxs-lookup"><span data-stu-id="b31c0-271">Technical requirements for IPv6</span></span>
<span data-ttu-id="b31c0-272"><a name="tech"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-272"></span></span>

<span data-ttu-id="b31c0-273">Skype ビジネス サーバーの IPv6 用に構成を計画する場合は、次の要件に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b31c0-273">If you plan to configure Skype for Business Server for IPv6, keep the following requirements in mind:</span></span>
  
- <span data-ttu-id="b31c0-274">Skype で IPv6 アドレスを使用して、ビジネス サーバー、ドメイン ネーム システムのレコードを発見、IPv6 アドレスに解決する必要があります (DNS) レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b31c0-274">To use IPv6 addresses with Skype for Business Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="b31c0-275">IPv6 DNS はホスト AAAA (クアッド A) レコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-275">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="b31c0-276">展開内で IPv4 と IPv6 の両方を使用する場合は、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA レコードの両方を構成し保持するのが最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="b31c0-276">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="b31c0-277">自身の展開を IPv6 に完全に移行した場合でも、IPv4 を使用する外部ユーザーのために IPv4 DNS ホスト レコードが引き続き必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b31c0-277">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="b31c0-p113">IPv6 DNS ホスト レコードは IPv6 の使用を始める前から展開できます。クライアントまたはサーバーが IPv6 を使用しない場合、そのレコードは参照されません。移行時のテクノロジは、どのレコードを使用するかを、移行テクノロジの構成およびポリシーに基づいて判断します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-p113">You can deploy IPv6 DNS host records before you start using IPv6. If the client or server doesn't use IPv6, the record will not be referenced. Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>
    
- <span data-ttu-id="b31c0-281">各 IPv6 アドレスは、スコープを持ちます。</span><span class="sxs-lookup"><span data-stu-id="b31c0-281">Each IPv6 address has a scope.</span></span> <span data-ttu-id="b31c0-282">IPv6 に対応するために使用できる 3 つの範囲、IPv6 のグローバル アドレス (IPv4 のパブリック アドレスに似ています)、IPv6 一意なローカル アドレス (プライベート IPv4 アドレスの範囲に似ています)、および IPv6 のリンク ローカル アドレス (自動プライベート IP アドレスに似ていますWindows サーバー IPv4 の場合)。</span><span class="sxs-lookup"><span data-stu-id="b31c0-282">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="b31c0-283">プール内のすべてのサーバーには、同じスコープの IPv6 アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b31c0-283">All the servers within a pool should have IPv6 addresses with the same scope.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="b31c0-284">IPv6 では、複雑なトピックし、は、ネットワーク チームと、インターネット プロバイダーは、Windows サーバー レベルとビジネスのサーバー レベルの Skype を割り当てられたアドレスが期待どおりに動作するように慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b31c0-284">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Skype for Business Server level work as expected.</span></span> <span data-ttu-id="b31c0-285">IPv6 のアドレス指定と計画その他のリソースは、このトピックの最後にあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b31c0-285">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span> 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a><span data-ttu-id="b31c0-286">IPv6 の移行および共存の検討事項</span><span class="sxs-lookup"><span data-stu-id="b31c0-286">Migration and coexistence considerations for IPv6</span></span>
<span data-ttu-id="b31c0-287"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-287"></span></span>

<span data-ttu-id="b31c0-288">IP バージョン 6 (IPv6) は、Lync Server 2010 または Office Communications Server ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b31c0-288">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="b31c0-289">試験運用のため、ビジネス サーバー デュアル スタックの共存の Lync Server 2010 と Skype をテストできます。</span><span class="sxs-lookup"><span data-stu-id="b31c0-289">For piloting purposes, you can test Lync Server 2010 and Skype for Business Server dual-stack coexistence.</span></span> <span data-ttu-id="b31c0-290">特定の中央サイトのすべてのプールにアップグレードを Skype ビジネス サーバーの IPv6 を有効にする前にことをお勧めします。 (デュアル スタック ネットワーク) のプールのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="b31c0-290">We recommend that all pools for a given central site are upgraded to Skype for Business Server before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="b31c0-291">IPv6 に対応したプールのみを構成する必要がある場合は、テスト用のラボ環境に IPv6 専用のプールを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b31c0-291">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>
  
<span data-ttu-id="b31c0-292">次のシナリオは、移行と共存でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b31c0-292">The following scenarios are supported during migration and coexistence:</span></span>
  
- <span data-ttu-id="b31c0-293">IPv4 モードの場合は、ビジネス サーバー、Lync Server 2013 では、Lync Server 2010 プールの Skype が Skype とデュアル スタック モードでのビジネスのサーバーに共存します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-293">Skype for Business Server, Lync Server 2013, and Lync Server 2010 pools in IPv4 mode, coexisting with Skype for Business Server in dual-stack mode.</span></span>
    
- <span data-ttu-id="b31c0-294">IPv6 専用のプールが孤立している場合、IPv6 のみのモードでのビジネス サーバー プールの Skype です。</span><span class="sxs-lookup"><span data-stu-id="b31c0-294">Skype for Business Server pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b31c0-295">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="b31c0-295">See also</span></span>
<span data-ttu-id="b31c0-296"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="b31c0-296"></span></span>

[<span data-ttu-id="b31c0-297">Skype for Business での IP アドレスの種類の構成</span><span class="sxs-lookup"><span data-stu-id="b31c0-297">Configure IP address types in Skype for Business</span></span>](ip-address-types.md)

[<span data-ttu-id="b31c0-298">IP バージョン 6 のアドレス指定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="b31c0-298">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)
  
[<span data-ttu-id="b31c0-299">IPv6 グローバル ユニキャスト アドレスの形式</span><span class="sxs-lookup"><span data-stu-id="b31c0-299">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)
  
[<span data-ttu-id="b31c0-300">一意のローカル IPv6 ユニキャスト アドレス</span><span class="sxs-lookup"><span data-stu-id="b31c0-300">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)