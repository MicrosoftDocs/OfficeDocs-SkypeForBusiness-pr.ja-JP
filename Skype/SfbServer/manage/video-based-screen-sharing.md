---
title: Skype for Business Server のビデオベースの画面共有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype for Business Server の計画およびビデオベースの画面共有の構成情報 (VbSS)
ms.openlocfilehash: f0d474772b94389c1d69264be61b3bee2b46a385
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817047"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="da996-103">Skype for Business Server のビデオベースの画面共有</span><span class="sxs-lookup"><span data-stu-id="da996-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="da996-104">Skype for Business Server 2015 でビデオベースの画面共有 (VbSS) をダウンロードできるようになりました。 [skype for Business server 2015 累積更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)。</span><span class="sxs-lookup"><span data-stu-id="da996-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690).</span></span> <span data-ttu-id="da996-105">VbSS は、Skype for Business Server 2019 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="da996-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="da996-106">ビデオベースの画面共有または VbSS は、Lync 画面共有を拡大しています。</span><span class="sxs-lookup"><span data-stu-id="da996-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="da996-107">VbSS と従来の画面共有との違いは、使用している基本プロトコルと、それぞれの長所が関係しています。</span><span class="sxs-lookup"><span data-stu-id="da996-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="da996-108">画面共有ではリモート デスクトップ プロトコル (RDP) を使用していますが、このプロトコルはコンピューター間での数千もの 1 対 1 セッションを生成する点で優れています。</span><span class="sxs-lookup"><span data-stu-id="da996-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="da996-109">一方 VbSS は新しい技術で、ユーザー データグラム プロトコル (UDP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="da996-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="da996-110">Skype for Business Server では、ユーザーの1対1、および1対多 (マルチパーティ) の会話と会議のエクスペリエンスを向上させる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="da996-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="da996-111">VbSS ではメディア プラットフォーム (基本プロトコルとして UDP に依存) を使用して、ビデオの開始時刻、表示の質 (特に高速移動対象)、および全体的信頼性の向上を目標としています。</span><span class="sxs-lookup"><span data-stu-id="da996-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="da996-112">画面共有を改善する目標には、VbSS と RDP 間での移行が生じる場合に、できるだけシームレスに行うことも含まれています。</span><span class="sxs-lookup"><span data-stu-id="da996-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="da996-113">VbSS は、Skype for Business Server の画面共有に使用されている基盤技術の更新プログラムであるため、ネットワークトラフィックの SIP の詳細を表示しているか、共有しているコンテンツを共有している場合を除き、どのテクノロジを利用しているかを検出することは困難な場合があります。は、高速移動でも3-d もできます。</span><span class="sxs-lookup"><span data-stu-id="da996-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="da996-114">たとえば、職場に多くのレガシクライアントがある場合、RDP は、会議や会話へのフェイルセーフとして提供されたままになります。</span><span class="sxs-lookup"><span data-stu-id="da996-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="da996-115">Skype for Business Server は内部ロジックを使って、クライアントが接続するときに適用する2つの方法 (VbSS または従来の画面共有) を決定します。</span><span class="sxs-lookup"><span data-stu-id="da996-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="da996-116">必要とされる状況では、VbSS に代えて RDP を使用することができ、実際にそうすることで、表示エクスペリエンスが中断されなくなります。</span><span class="sxs-lookup"><span data-stu-id="da996-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="da996-117">計画</span><span class="sxs-lookup"><span data-stu-id="da996-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="da996-118">VbSS の長所と短所</span><span class="sxs-lookup"><span data-stu-id="da996-118">VbSS pros and cons</span></span>

<span data-ttu-id="da996-119">VbSS に切り替える目的は、次の 3 つの重要な改善を行うことにあります。</span><span class="sxs-lookup"><span data-stu-id="da996-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="da996-120">RDP だけのときよりも画面共有 (最大 5%) の信頼性を向上させる。</span><span class="sxs-lookup"><span data-stu-id="da996-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="da996-121">RDP だけのときよりもセッション セットアップとビデオ エクスペリエンスを速くする (セットアップ時間を半分に、フレーム/秒を 6:1 に改善)。</span><span class="sxs-lookup"><span data-stu-id="da996-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="da996-122">低帯域幅条件下で 3-D グラフィックなどの高速運動コンテンツを共有する場合でも、RDP よりも動作を向上させる。</span><span class="sxs-lookup"><span data-stu-id="da996-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="da996-123">3 つの改善点は、ネットワークの良好で適正なパフォーマンス調整に依存することに留意してください。クライアントがモバイル デバイスを使用している場合には、外部のネットワークも関係してきます。</span><span class="sxs-lookup"><span data-stu-id="da996-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="da996-p105">また共有コンテンツの忠実で生き生きとした再現性の一部は、信頼性、速度、および効率の犠牲になることにも留意してください。多くの場合これは、容易にユーザーの目に付くようなものではありません。</span><span class="sxs-lookup"><span data-stu-id="da996-p105">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency. In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="da996-126">ポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="da996-126">Ports and protocols</span></span>

<span data-ttu-id="da996-127">**必要なサーバーポート**</span><span class="sxs-lookup"><span data-stu-id="da996-127">**Required server ports**</span></span>

|<span data-ttu-id="da996-128">**サーバーの役割**</span><span class="sxs-lookup"><span data-stu-id="da996-128">**Server role**</span></span>|<span data-ttu-id="da996-129">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="da996-129">**Service name**</span></span>|<span data-ttu-id="da996-130">**ポートまたはポート範囲**</span><span class="sxs-lookup"><span data-stu-id="da996-130">**Port or port range**</span></span>|<span data-ttu-id="da996-131">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="da996-131">**Protocol**</span></span>|<span data-ttu-id="da996-132">**メモ**</span><span class="sxs-lookup"><span data-stu-id="da996-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da996-133">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="da996-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="da996-134">Skype for Business Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="da996-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="da996-135">5065</span><span class="sxs-lookup"><span data-stu-id="da996-135">5065</span></span>  <br/> |<span data-ttu-id="da996-136">TCP</span><span class="sxs-lookup"><span data-stu-id="da996-136">TCP</span></span>  <br/> |<span data-ttu-id="da996-137">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="da996-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="da996-138">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="da996-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="da996-139">Skype for Business Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="da996-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="da996-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="da996-140">49152-65535</span></span>  <br/> |<span data-ttu-id="da996-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="da996-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="da996-142">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="da996-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="da996-143">**必要なクライアントポート**</span><span class="sxs-lookup"><span data-stu-id="da996-143">**Required client ports**</span></span>

|<span data-ttu-id="da996-144">**コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="da996-144">**Component**</span></span>|<span data-ttu-id="da996-145">**ポートの範囲**</span><span class="sxs-lookup"><span data-stu-id="da996-145">**Port range**</span></span>|<span data-ttu-id="da996-146">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="da996-146">**Protocol**</span></span>|<span data-ttu-id="da996-147">**メモ**</span><span class="sxs-lookup"><span data-stu-id="da996-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da996-148">クライアント</span><span class="sxs-lookup"><span data-stu-id="da996-148">Clients</span></span>  <br/> |<span data-ttu-id="da996-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="da996-149">1024-65535</span></span>  <br/> |<span data-ttu-id="da996-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="da996-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="da996-151">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="da996-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="da996-152">次のメディアポートと VbSS の QoS が有効になっている場合は、デスクトップ共有を含む会議中に、画面共有トラフィックについて太字で示されているビデオポート設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="da996-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="da996-153">これらの設定は特殊なケースであり、これらの機能を両方とも実装する場合は、これらの厳密な設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da996-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="da996-154">これは、 [QoS のドキュメント](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)で他の推奨設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="da996-154">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="da996-155">アプリケーション共有の場合は、これらのポート値を定義するだけでなく、QoS GPO に ASMCUSVC を指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="da996-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="da996-156">**Application Server の QoS/VbSS required 設定**</span><span class="sxs-lookup"><span data-stu-id="da996-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="da996-157">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="da996-157">**Property**</span></span>|<span data-ttu-id="da996-158">**ポートの値**</span><span class="sxs-lookup"><span data-stu-id="da996-158">**Port value**</span></span>|<span data-ttu-id="da996-159">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="da996-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="da996-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="da996-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="da996-161">49152</span><span class="sxs-lookup"><span data-stu-id="da996-161">49152</span></span>  <br/> |<span data-ttu-id="da996-162">UDP</span><span class="sxs-lookup"><span data-stu-id="da996-162">UDP</span></span>  <br/> |
|<span data-ttu-id="da996-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="da996-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="da996-164">8348</span><span class="sxs-lookup"><span data-stu-id="da996-164">8348</span></span>  <br/> |<span data-ttu-id="da996-165">UDP</span><span class="sxs-lookup"><span data-stu-id="da996-165">UDP</span></span>  <br/> |
|<span data-ttu-id="da996-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="da996-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="da996-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="da996-167">**57501**</span></span> <br/> |<span data-ttu-id="da996-168">UDP</span><span class="sxs-lookup"><span data-stu-id="da996-168">UDP</span></span>  <br/> |
|<span data-ttu-id="da996-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="da996-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="da996-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="da996-170">**8034**</span></span> <br/> |<span data-ttu-id="da996-171">UDP</span><span class="sxs-lookup"><span data-stu-id="da996-171">UDP</span></span>  <br/> |
|<span data-ttu-id="da996-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="da996-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="da996-173">40803</span><span class="sxs-lookup"><span data-stu-id="da996-173">40803</span></span>  <br/> |<span data-ttu-id="da996-174">TCP</span><span class="sxs-lookup"><span data-stu-id="da996-174">TCP</span></span>  <br/> |
|<span data-ttu-id="da996-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="da996-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="da996-176">8348</span><span class="sxs-lookup"><span data-stu-id="da996-176">8348</span></span>  <br/> |<span data-ttu-id="da996-177">TCP</span><span class="sxs-lookup"><span data-stu-id="da996-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="da996-178">処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="da996-178">Capacity planning</span></span>

<span data-ttu-id="da996-179">Skype for Business Server 2015 累積更新プログラム 2 (CU2) 以降を実行している各フロントエンドサーバーでは、RDP を使用して画面共有を行うための最大375の参加者がサポートされます (ただし、会議あたりの250のみ)。</span><span class="sxs-lookup"><span data-stu-id="da996-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="da996-180">この数は、VbSS が導入された後も、ポスト CU-3 で変わりません。</span><span class="sxs-lookup"><span data-stu-id="da996-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="da996-181">それはそれとして、当社ラボではパフォーマンスおよびストレス試験が行われ、展開に関して次の測定内容も考慮される予定です (当然ながら用途による)。</span><span class="sxs-lookup"><span data-stu-id="da996-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="da996-182">前提事項:</span><span class="sxs-lookup"><span data-stu-id="da996-182">Assuming:</span></span>
  
- <span data-ttu-id="da996-183">展開で Skype for Business Server 2015 CU2 以降を使用している。</span><span class="sxs-lookup"><span data-stu-id="da996-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="da996-184">Skype for Business Server 環境内のすべてのユーザーには、1920 x 1080 よりも高い画面解像度が設定されています。</span><span class="sxs-lookup"><span data-stu-id="da996-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="da996-185">(上で説明したように) フルキャパシティでは、フロントエンドサーバーあたりの375画面共有の参加者は250合計でで、1 Gb のネットワークカードの89% を利用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da996-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="da996-186">これは、Skype for Business Server CU2 (RDP) の既存のスクリーン共有テクノロジによって、画面上のコンテンツが発表者の PC のネイティブ解像度で伝送されるためです。</span><span class="sxs-lookup"><span data-stu-id="da996-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="da996-187">そのため、画面の解像度を高く考慮すると、Skype for Business Server 2015 CU2 での画面共有のネットワークボトルネックが既に発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da996-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="da996-188">これを緩和するには、次のオプションを 1 つまたは複数採用すると効果的です。</span><span class="sxs-lookup"><span data-stu-id="da996-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="da996-189">フロントエンドサーバーを1ギガビットネットワークカードから10ギガビットイーサネットカードにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="da996-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="da996-190">負荷分散トラフィックのフロントエンドサーバーの数を増やします。</span><span class="sxs-lookup"><span data-stu-id="da996-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="da996-191">VbSS と RDP の両チャンネルで使用する最大帯域幅に上限を設け、それぞれの帯域幅 (ビットレート) を制限する。</span><span class="sxs-lookup"><span data-stu-id="da996-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="da996-p109">この表の数字は、個々のネットワークや共有されるコンテンツに影響されます。テストして、使用するネットワークのベースラインを確立してください。</span><span class="sxs-lookup"><span data-stu-id="da996-p109">The numbers in this table are influenced by individual networks and by the content being shared. Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="da996-194">\*\*1080p コンテンツ \*\*</span><span class="sxs-lookup"><span data-stu-id="da996-194">**1080p Content**</span></span>|<span data-ttu-id="da996-195">**RDP の平均**</span><span class="sxs-lookup"><span data-stu-id="da996-195">**RDP Average**</span></span>|<span data-ttu-id="da996-196">**RDP のピーク**</span><span class="sxs-lookup"><span data-stu-id="da996-196">**RDP Peak**</span></span>|<span data-ttu-id="da996-197">**VbSS の平均**</span><span class="sxs-lookup"><span data-stu-id="da996-197">**VbSS Average**</span></span>|<span data-ttu-id="da996-198">**VbSS のピーク**</span><span class="sxs-lookup"><span data-stu-id="da996-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da996-199">PPT</span><span class="sxs-lookup"><span data-stu-id="da996-199">PPT</span></span>  <br/> |<span data-ttu-id="da996-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="da996-200">200kbps</span></span>  <br/> |<span data-ttu-id="da996-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="da996-201">12mbps</span></span>  <br/> |<span data-ttu-id="da996-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="da996-202">100kbps</span></span>  <br/> |<span data-ttu-id="da996-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="da996-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="da996-204">CAD</span><span class="sxs-lookup"><span data-stu-id="da996-204">CAD</span></span>  <br/> |<span data-ttu-id="da996-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="da996-205">3mbps</span></span>  <br/> |<span data-ttu-id="da996-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="da996-206">7mbps</span></span>  <br/> |<span data-ttu-id="da996-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="da996-207">1mbps</span></span>  <br/> |<span data-ttu-id="da996-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="da996-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="da996-209">ビデオ</span><span class="sxs-lookup"><span data-stu-id="da996-209">Video</span></span>  <br/> |<span data-ttu-id="da996-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="da996-210">5mbps</span></span>  <br/> |<span data-ttu-id="da996-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="da996-211">7mbps</span></span>  <br/> |<span data-ttu-id="da996-212">1.3mbps</span><span class="sxs-lookup"><span data-stu-id="da996-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="da996-213">2.2mbps</span><span class="sxs-lookup"><span data-stu-id="da996-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="da996-214">メディア トラフィックのネットワーク帯域幅の要件</span><span class="sxs-lookup"><span data-stu-id="da996-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="da996-215">VbSS の帯域幅:</span><span class="sxs-lookup"><span data-stu-id="da996-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="da996-216">**ビデオ コーデック**</span><span class="sxs-lookup"><span data-stu-id="da996-216">**Video codec**</span></span>|<span data-ttu-id="da996-217">**解像度と縦横比**</span><span class="sxs-lookup"><span data-stu-id="da996-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="da996-218">**最大ビデオ ペイロード ビット レート (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="da996-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="da996-219">**最小ビデオ ペイロード ビット レート (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="da996-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da996-220">H.264</span><span class="sxs-lookup"><span data-stu-id="da996-220">H.264</span></span>  <br/> |<span data-ttu-id="da996-221">1920x1080 (16:9)</span><span class="sxs-lookup"><span data-stu-id="da996-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="da996-222">(縦横比は共有者のモニター解像度に応じて異なり、必ずしも 16:9 ではない。)</span><span class="sxs-lookup"><span data-stu-id="da996-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="da996-223">4000</span><span class="sxs-lookup"><span data-stu-id="da996-223">4000</span></span>  <br/> |<span data-ttu-id="da996-224">1500</span><span class="sxs-lookup"><span data-stu-id="da996-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="da996-225">クライアントおよびサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="da996-225">Clients and servers support</span></span>

<span data-ttu-id="da996-226">ビデオベースの画面共有には、Skype for business Server 2015 CU3 以降で以降が必要です。 [skype For business と会議のサポートのモバイルクライアントの機能比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)で一覧[](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)表示されているサポートクライアントの最新バージョンです。</span><span class="sxs-lookup"><span data-stu-id="da996-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="da996-227">画面の共有が RDP に移行されるのは、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="da996-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="da996-228">ASMCU が VbSS をサポートできる最低限のビルドに満たない環境でアカウントがホストされている。</span><span class="sxs-lookup"><span data-stu-id="da996-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="da996-229">以前のバージョンの Skype for Business クライアントを使用しているユーザーが、16.0.6330.1000、Skype for Business Room System デバイス、Skype for Business モバイルアプリなど、Windows クライアントバージョンを使用しているユーザーがいる場合。</span><span class="sxs-lookup"><span data-stu-id="da996-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="da996-230">ユーザーが Skype for Business Web App から共有している場合。</span><span class="sxs-lookup"><span data-stu-id="da996-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="da996-231">他のユーザーが Skype for Business for Mac を使用していて、2018年7月の累積更新プログラム (以降) で skype for Business Online または Skype for business Server 2015 を使っていない場合。</span><span class="sxs-lookup"><span data-stu-id="da996-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="da996-232">他のユーザーがプログラム/Windows 共有を開始した場合。</span><span class="sxs-lookup"><span data-stu-id="da996-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="da996-233">他のユーザーがセッションの記録を開始した場合。</span><span class="sxs-lookup"><span data-stu-id="da996-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="da996-234">セッション中に誰かがリモート画面コントロールを起動した場合。</span><span class="sxs-lookup"><span data-stu-id="da996-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="da996-235">250 人を超える参加者による会議 (VbSS がサポートされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="da996-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="da996-p110">セッションが RDP に移行すると、VbSS には戻らないことに留意してください。VbSS からの移行はシームレスに行われるようになっているため、多くの場合気づきません。</span><span class="sxs-lookup"><span data-stu-id="da996-p110">Be aware that once the session transitions to RDP it will not transition back to VbSS. Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="da996-238">これは、Skype for Business の画面共有の VbSS から RDP への切り替え、またはブロックすることをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="da996-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="da996-239">VbSS の有効化、無効化、および構成</span><span class="sxs-lookup"><span data-stu-id="da996-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="da996-240">最適な方法は、Skype for Business Server 2015 累積更新プログラム 3 (CU3 以降で) 以降をインストールすると、すべてのユーザーが既定で1対1およびマルチパーティの VbSS を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="da996-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="da996-241">そのためこの機能を有効にしたくないユーザーがいる場合には問題となります。</span><span class="sxs-lookup"><span data-stu-id="da996-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="da996-242">その場合、次の手順に従って、ユーザーを無効化します (その後で有効化します)。</span><span class="sxs-lookup"><span data-stu-id="da996-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="da996-243">ユーザーが VbSS を使用できないようにする方法</span><span class="sxs-lookup"><span data-stu-id="da996-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="da996-244">Skype for Business 管理コンソールでこのコマンドレットを実行することにより、vbss を使用していないユーザーに対して VbSS を許可しないユーザーポリシーを割り当てることができます (これを実行しているポリシーで [PolicyName] と置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="da996-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="da996-245">またグローバル会議ポリシーを更新することもでき、そうすれば割り当てられたポリシーのないすべてのユーザーに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="da996-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="da996-246">このコマンドの詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da996-246">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="da996-247">VbSS を完全にオフにしたい場合は、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="da996-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="da996-248">このコマンドの詳細については、「 [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da996-248">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="da996-249">マルチパーティの Skype for Business 会議では、すべてのクライアントエンドポイントに、会議の開催者のポリシー設定が尊重されます。</span><span class="sxs-lookup"><span data-stu-id="da996-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="da996-250">ユーザーが VbSS を使用できるようにする方法</span><span class="sxs-lookup"><span data-stu-id="da996-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="da996-251">Skype for Business 管理コンソールでこのコマンドレットを実行することにより、VbSS を使用する必要がある特定のユーザーポリシーを割り当てることができます (これを行うには、[PolicyName] をポリシーで置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="da996-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="da996-252">またグローバル会議ポリシーを更新することもでき、そうすれば割り当てられたポリシーのないすべてのユーザーに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="da996-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="da996-253">このコマンドの詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da996-253">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="da996-254">VbSS をオフにした後でオンに戻したい場合は、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="da996-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="da996-255">このコマンドの詳細については、「 [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da996-255">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="da996-256">マルチパーティの Skype for Business 会議では、すべてのクライアントエンドポイントに、会議の開催者のポリシー設定が尊重されます。</span><span class="sxs-lookup"><span data-stu-id="da996-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="da996-257">関連項目</span><span class="sxs-lookup"><span data-stu-id="da996-257">See also</span></span>

[<span data-ttu-id="da996-258">Skype for Business Server 2015 累積更新 KB3061064</span><span class="sxs-lookup"><span data-stu-id="da996-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[<span data-ttu-id="da996-259">ビデオベースの画面共有 (VBSS) は、Skype for Business Server 2015 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="da996-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/en-us/kb/3170163)
