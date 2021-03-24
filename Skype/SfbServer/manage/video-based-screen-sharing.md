---
title: Skype for Business Server のビデオベースの画面共有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: ビデオ ベースの画面共有 (VbSS) の Skype for Business Server の計画と構成情報
ms.openlocfilehash: 9d2466a314876a4ce576727c7673474003994365
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103063"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="0ec5f-103">Skype for Business Server のビデオベースの画面共有</span><span class="sxs-lookup"><span data-stu-id="0ec5f-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="0ec5f-104">Skype For Business Server 2015 のビデオ ベースの画面共有 (VbSS) がダウンロード可能になります [。Skype for Business Server 2015 累積的な更新プログラム KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)です。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690).</span></span> <span data-ttu-id="0ec5f-105">VbSS は Skype for Business Server 2019 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="0ec5f-106">ビデオ ベースのスクリーン共有 (VbSS) は、Lync の画面共有から成長しました。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="0ec5f-107">VbSS と従来の画面共有の違いは、使用される基になるプロトコルと、そのプロトコルの優良な機能と関係があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="0ec5f-108">画面共有はリモート デスクトップ プロトコル (RDP) を使用します。これは、ユーザーのコンピューター間で何千もの 1 対 1 セッションを作成する場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="0ec5f-109">新しいテクノロジ VbSS は、ユーザー データグラム プロトコル (UDP) を利用します。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="0ec5f-110">Skype for Business Server は、ユーザーの 1 対 1、および 1 対多 (マルチパーティ) の会話と会議のエクスペリエンスを改善したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="0ec5f-111">VbSS では、メディア プラットフォーム (UDP を基になるプロトコルに依存) を利用し、ビデオの開始時間、視聴している視聴の品質 (特に、視聴中の動きが速い場合)、および全体的な信頼性を向上させる目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="0ec5f-112">画面共有を改善する目的の一部は、VbSS と RDP の間の移行が可能な限りシームレスに行われる点です。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="0ec5f-113">VbSS は、Skype for Business Server の画面共有で使用される基になるテクノロジの更新プログラムです。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="0ec5f-114">たとえば、職場に多くのレガシ クライアントがある場合、RDP は会議や会話のフェールセーフとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="0ec5f-115">Skype for Business Server では、内部ロジックを使用して、クライアントの接続時に適用する 2 つのメソッド (VbSS または従来の画面共有) を決定します。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="0ec5f-116">状況で VbSS が呼び出された場合、RDP は VbSS に置き換わる可能性があります。また、表示エクスペリエンスが中断される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="0ec5f-117">計画</span><span class="sxs-lookup"><span data-stu-id="0ec5f-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="0ec5f-118">VbSS の長所と短所</span><span class="sxs-lookup"><span data-stu-id="0ec5f-118">VbSS pros and cons</span></span>

<span data-ttu-id="0ec5f-119">VbSS への切り替えは、次の 3 つの重要な改善を目的とします。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="0ec5f-120">画面共有を行う (最大 5%)RDP に比べて信頼性が高い。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="0ec5f-121">セッションのセットアップとビデオ エクスペリエンスを RDP 単独と比較して高速化します (半分の時間でセットアップし、1 秒あたりのフレーム数が 6:1 向上しました)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="0ec5f-122">3-D グラフィックスなどの高モーション コンテンツを共有する場合でも、低帯域幅の状況では RDP よりもはるかに優れた機能を実現します。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="0ec5f-123">これらの数値は、ネットワークの正常性と適切なパフォーマンス調整に依存し、クライアントがモバイル デバイス上にある場合は、独自の外部ネットワークに関係する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="0ec5f-124">また、共有コンテンツのいくつかの忠実度/鮮明さは、信頼性、速度、および効率のために取引されている点にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-124">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency.</span></span> <span data-ttu-id="0ec5f-125">ほとんどの場合、これはユーザーに容易に表示されません。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-125">In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="0ec5f-126">ポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="0ec5f-126">Ports and protocols</span></span>

<span data-ttu-id="0ec5f-127">**必要なサーバー ポート**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-127">**Required server ports**</span></span>

|<span data-ttu-id="0ec5f-128">**サーバーの役割**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-128">**Server role**</span></span>|<span data-ttu-id="0ec5f-129">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-129">**Service name**</span></span>|<span data-ttu-id="0ec5f-130">**ポートまたはポートの範囲**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-130">**Port or port range**</span></span>|<span data-ttu-id="0ec5f-131">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-131">**Protocol**</span></span>|<span data-ttu-id="0ec5f-132">**注**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0ec5f-133">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="0ec5f-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="0ec5f-134">Skype for Business Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="0ec5f-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="0ec5f-135">5065</span><span class="sxs-lookup"><span data-stu-id="0ec5f-135">5065</span></span>  <br/> |<span data-ttu-id="0ec5f-136">TCP</span><span class="sxs-lookup"><span data-stu-id="0ec5f-136">TCP</span></span>  <br/> |<span data-ttu-id="0ec5f-137">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="0ec5f-138">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="0ec5f-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="0ec5f-139">Skype for Business Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="0ec5f-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="0ec5f-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="0ec5f-140">49152-65535</span></span>  <br/> |<span data-ttu-id="0ec5f-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="0ec5f-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="0ec5f-142">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="0ec5f-143">**必要なクライアント ポート**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-143">**Required client ports**</span></span>

|<span data-ttu-id="0ec5f-144">**コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-144">**Component**</span></span>|<span data-ttu-id="0ec5f-145">**ポート範囲**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-145">**Port range**</span></span>|<span data-ttu-id="0ec5f-146">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-146">**Protocol**</span></span>|<span data-ttu-id="0ec5f-147">**注**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0ec5f-148">クライアント</span><span class="sxs-lookup"><span data-stu-id="0ec5f-148">Clients</span></span>  <br/> |<span data-ttu-id="0ec5f-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="0ec5f-149">1024-65535</span></span>  <br/> |<span data-ttu-id="0ec5f-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="0ec5f-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="0ec5f-151">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="0ec5f-152">次のメディア ポートで QoS が有効で VbSS も有効になっている場合、デスクトップ共有を含む会議中に、AS MCU は画面共有トラフィックに次の太字で示すビデオ ポート設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0ec5f-153">これらの設定は特別なケースであり、これらの両方の機能を実装する場合は、これらの正確な設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="0ec5f-154">これにより、QoS に関するドキュメントの他の [推奨設定が上書きされます](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-154">This overrides other recommended settings in the [documentation for QoS](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos).</span></span> <span data-ttu-id="0ec5f-155">アプリケーション共有では、これらのポート値の定義に加ASMCUSVC.exe QoS GPO でアプリケーションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="0ec5f-156">**Application Server QoS/VbSS 必須設定**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="0ec5f-157">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-157">**Property**</span></span>|<span data-ttu-id="0ec5f-158">**ポート値**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-158">**Port value**</span></span>|<span data-ttu-id="0ec5f-159">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0ec5f-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="0ec5f-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="0ec5f-161">49152</span><span class="sxs-lookup"><span data-stu-id="0ec5f-161">49152</span></span>  <br/> |<span data-ttu-id="0ec5f-162">UDP</span><span class="sxs-lookup"><span data-stu-id="0ec5f-162">UDP</span></span>  <br/> |
|<span data-ttu-id="0ec5f-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="0ec5f-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="0ec5f-164">8348</span><span class="sxs-lookup"><span data-stu-id="0ec5f-164">8348</span></span>  <br/> |<span data-ttu-id="0ec5f-165">UDP</span><span class="sxs-lookup"><span data-stu-id="0ec5f-165">UDP</span></span>  <br/> |
|<span data-ttu-id="0ec5f-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="0ec5f-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-167">**57501**</span></span> <br/> |<span data-ttu-id="0ec5f-168">UDP</span><span class="sxs-lookup"><span data-stu-id="0ec5f-168">UDP</span></span>  <br/> |
|<span data-ttu-id="0ec5f-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="0ec5f-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-170">**8034**</span></span> <br/> |<span data-ttu-id="0ec5f-171">UDP</span><span class="sxs-lookup"><span data-stu-id="0ec5f-171">UDP</span></span>  <br/> |
|<span data-ttu-id="0ec5f-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="0ec5f-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="0ec5f-173">40803</span><span class="sxs-lookup"><span data-stu-id="0ec5f-173">40803</span></span>  <br/> |<span data-ttu-id="0ec5f-174">TCP</span><span class="sxs-lookup"><span data-stu-id="0ec5f-174">TCP</span></span>  <br/> |
|<span data-ttu-id="0ec5f-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="0ec5f-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="0ec5f-176">8348</span><span class="sxs-lookup"><span data-stu-id="0ec5f-176">8348</span></span>  <br/> |<span data-ttu-id="0ec5f-177">TCP</span><span class="sxs-lookup"><span data-stu-id="0ec5f-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="0ec5f-178">キャパシティ プランニング</span><span class="sxs-lookup"><span data-stu-id="0ec5f-178">Capacity planning</span></span>

<span data-ttu-id="0ec5f-179">Skype for Business Server 2015 累積更新プログラム 2 (CU2) 以降を実行している各フロント エンド サーバーは、RDP を使用した画面共有に最大 375 人の参加者をサポートします (会議ごとに 250 人のみ)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="0ec5f-180">VbSS が導入され使用される場合、この容量は CU3 の後に変更されません。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="0ec5f-181">つまり、ラボでパフォーマンスとストレステストを行いましたが、次の測定値は、(もちろん使用状況に応じて) 独自の展開に関して考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="0ec5f-182">次の場合と仮定します。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-182">Assuming:</span></span>
  
- <span data-ttu-id="0ec5f-183">展開で Skype for Business Server 2015 CU2 以降を使用しています。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="0ec5f-184">Skype for Business Server 環境のすべてのユーザーの画面解像度は 1920x1080 より高くなります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="0ec5f-185">フル容量 (上記のように、フロント エンド サーバーあたり合計で 375 の画面共有参加者ですが、会議ごとに 250 人のみ) では、フロントエンド サーバーが 1 ギガビット のネットワーク カードの約 89% を利用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="0ec5f-186">これは、Skype for Business Server CU2 (RDP) の既存の画面共有テクノロジが、発表者の PC のネイティブ解像度で画面コンテンツを送信する理由です。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="0ec5f-187">そのため、画面解像度が高いほど、Skype for Business Server 2015 CU2 との画面共有のネットワークボトルネックが既に発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="0ec5f-188">これを軽減するには、次の 1 つ以上のオプションが役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="0ec5f-189">フロント エンド サーバーを 1 ギガビット ネットワーク カードから 10 ギガビット イーサネット カードにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="0ec5f-190">トラフィックの負荷分散を行うフロントエンド サーバーの数を増やします。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="0ec5f-191">VbSS と RDP で使用される帯域幅 (ビットレート) を制限するには、いずれかのチャネルで使用される最大帯域幅に上限を設定します。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="0ec5f-192">この表の数値は、個々のネットワークと共有されるコンテンツの影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-192">The numbers in this table are influenced by individual networks and by the content being shared.</span></span> <span data-ttu-id="0ec5f-193">ネットワークまたはネットワークのベースラインを確立するためにテストしてください。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-193">Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="0ec5f-194">**1080p コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-194">**1080p Content**</span></span>|<span data-ttu-id="0ec5f-195">**RDP の平均**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-195">**RDP Average**</span></span>|<span data-ttu-id="0ec5f-196">**RDP ピーク**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-196">**RDP Peak**</span></span>|<span data-ttu-id="0ec5f-197">**VbSS の平均**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-197">**VbSS Average**</span></span>|<span data-ttu-id="0ec5f-198">**VbSS Peak**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0ec5f-199">PPT</span><span class="sxs-lookup"><span data-stu-id="0ec5f-199">PPT</span></span>  <br/> |<span data-ttu-id="0ec5f-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-200">200kbps</span></span>  <br/> |<span data-ttu-id="0ec5f-201">12 mbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-201">12mbps</span></span>  <br/> |<span data-ttu-id="0ec5f-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-202">100kbps</span></span>  <br/> |<span data-ttu-id="0ec5f-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="0ec5f-204">CAD</span><span class="sxs-lookup"><span data-stu-id="0ec5f-204">CAD</span></span>  <br/> |<span data-ttu-id="0ec5f-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-205">3mbps</span></span>  <br/> |<span data-ttu-id="0ec5f-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-206">7mbps</span></span>  <br/> |<span data-ttu-id="0ec5f-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-207">1mbps</span></span>  <br/> |<span data-ttu-id="0ec5f-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="0ec5f-209">ビデオ</span><span class="sxs-lookup"><span data-stu-id="0ec5f-209">Video</span></span>  <br/> |<span data-ttu-id="0ec5f-210">5 mbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-210">5mbps</span></span>  <br/> |<span data-ttu-id="0ec5f-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-211">7mbps</span></span>  <br/> |<span data-ttu-id="0ec5f-212">1.3mbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="0ec5f-213">2.2mbps</span><span class="sxs-lookup"><span data-stu-id="0ec5f-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="0ec5f-214">メディア トラフィックのネットワーク帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="0ec5f-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="0ec5f-215">VbSS 帯域幅は次の値です。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="0ec5f-216">**ビデオ コーデック**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-216">**Video codec**</span></span>|<span data-ttu-id="0ec5f-217">**解像度と縦横比**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="0ec5f-218">**最大ビデオ ペイロード ビット レート (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="0ec5f-219">**最小ビデオ ペイロード ビット レート (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="0ec5f-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0ec5f-220">H.264</span><span class="sxs-lookup"><span data-stu-id="0ec5f-220">H.264</span></span>  <br/> |<span data-ttu-id="0ec5f-221">1920x1080 (16:9)</span><span class="sxs-lookup"><span data-stu-id="0ec5f-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="0ec5f-222">(縦横比は、共有者のモニター解像度によって異なりますが、必ずしも 16:9 とは限りではありません)</span><span class="sxs-lookup"><span data-stu-id="0ec5f-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="0ec5f-223">4000</span><span class="sxs-lookup"><span data-stu-id="0ec5f-223">4000</span></span>  <br/> |<span data-ttu-id="0ec5f-224">1500</span><span class="sxs-lookup"><span data-stu-id="0ec5f-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="0ec5f-225">クライアントとサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="0ec5f-225">Clients and servers support</span></span>

<span data-ttu-id="0ec5f-226">ビデオ ベースの画面共有には、Skype for Business Server 2015 CU3 以降、および Skype [for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)および Meetings サポート[](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)のモバイル クライアント機能比較に記載されているサポート クライアントの現在のバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="0ec5f-227">画面共有が RDP に移行する状況は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="0ec5f-228">アカウントが、ASMCU が VbSS をサポートする最小ビルドを満たしない環境でホストされている場合。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="0ec5f-229">以前のバージョンの Skype for Business クライアントを使用しているユーザーがセッションに参加する場合 (たとえば、16.0.6330.1000 未満の Windows クライアント バージョンを使用しているユーザー、Skype for Business Room System Devices、Skype for Business Mobile Apps など)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="0ec5f-230">ユーザーが Skype for Business Web App から共有している場合。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="0ec5f-231">Mac で Skype for Business を使用しているユーザーが、Skype for Business Online または Skype for Business Server 2015 に 2018 年 7 月の累積的な更新プログラム (以降) が含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="0ec5f-232">他のユーザーがプログラム/Windows 共有を開始した場合。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="0ec5f-233">ユーザーがセッションの記録を開始した場合。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="0ec5f-234">セッション中にリモート スクリーン コントロールを呼び出した場合。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="0ec5f-235">250 人を超える参加者との会議 (VbSS は現在サポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="0ec5f-236">セッションが RDP に移行すると、VbSS に戻らなく点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-236">Be aware that once the session transitions to RDP it will not transition back to VbSS.</span></span> <span data-ttu-id="0ec5f-237">繰り返しますが、VbSS からの移行はシームレスであり、希望を持ってほとんどの状況で簡単に検出できません。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-237">Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0ec5f-238">Skype for Business の画面共有で VbSS から RDP への移行をブロックまたはブロックしようとはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="0ec5f-239">VbSS の有効化、無効化、および構成</span><span class="sxs-lookup"><span data-stu-id="0ec5f-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="0ec5f-240">素晴らしい点は、Skype for Business Server 2015 累積的な更新プログラム 3 (CU3) 以降をインストールすると、すべてのユーザーが既定で 1 対 1 およびマルチパーティ VbSS に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="0ec5f-241">すべてのユーザーに対してこの機能を有効にしない理由がある場合、これは問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="0ec5f-242">その場合は、次の手順を使用してユーザーを無効にできます (ユーザーを有効にする手順は次のとおりです)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="0ec5f-243">VbSS を使用してユーザーを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="0ec5f-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="0ec5f-244">Skype for Business 管理コンソールでこのコマンドレットを実行することで、VbSS を使用しないユーザーに VbSS を許可しないユーザー ポリシーを割り当てできます ([PolicyName] を、これを実行しているポリシーに置き換えてください)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="0ec5f-245">また、グローバル会議ポリシーを更新して、割り当てられたポリシーのないすべてのユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="0ec5f-246">このコマンドの詳細については [、「Set-CsConferencingPolicy」を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-246">For more information on this command, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="0ec5f-247">VbSS を完全にオフにする必要がある場合は、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="0ec5f-248">このコマンドの詳細については [、「Set-CsMediaConfiguration」を参照してください](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-248">For more information on this command, see [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0ec5f-249">複数パーティの Skype for Business 会議では、すべてのクライアント エンドポイントが会議開催者のポリシー設定を尊重します。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="0ec5f-250">ユーザーが VbSS を使用する方法</span><span class="sxs-lookup"><span data-stu-id="0ec5f-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="0ec5f-251">Skype for Business 管理コンソールでこのコマンドレットを実行することで、VbSS を使用する必要があるすべてのユーザーに VbSS を許可する特定のユーザー ポリシーを割り当てできます ([PolicyName] をこれを実行しているポリシーに置き換えてください)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="0ec5f-252">また、グローバル会議ポリシーを更新して、割り当てられたポリシーのないすべてのユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="0ec5f-253">このコマンドの詳細については [、「Set-CsConferencingPolicy」を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-253">For more information on this command, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="0ec5f-254">VbSS をオフにした後で (既定ではオンになっています) 必要がある場合は、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="0ec5f-255">このコマンドの詳細については [、「Set-CsMediaConfiguration」を参照してください](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-255">For more information on this command, see [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0ec5f-256">複数パーティの Skype for Business 会議では、すべてのクライアント エンドポイントが会議開催者のポリシー設定を尊重します。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0ec5f-257">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ec5f-257">See also</span></span>

[<span data-ttu-id="0ec5f-258">Skype for Business Server 2015 累積的な更新プログラム KB3061064</span><span class="sxs-lookup"><span data-stu-id="0ec5f-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/download/details.aspx?id=47690)
  
[<span data-ttu-id="0ec5f-259">ビデオ ベースの画面共有 (VBSS) は、Skype for Business Server 2015 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="0ec5f-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/kb/3170163)