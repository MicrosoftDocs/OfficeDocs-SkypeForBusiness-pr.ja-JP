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
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009570"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="16ffe-103">Skype for Business Server のビデオベースの画面共有</span><span class="sxs-lookup"><span data-stu-id="16ffe-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="16ffe-104">Skype For business Server 2015 のビデオベースの画面共有 (VbSS) をダウンロードできるようになりました: [skype For Business server 2015 の累積更新プログラム KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)。</span><span class="sxs-lookup"><span data-stu-id="16ffe-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690).</span></span> <span data-ttu-id="16ffe-105">VbSS は、Skype for Business Server 2019 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="16ffe-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="16ffe-106">ビデオベースの画面共有または VbSS が Lync 画面共有から成長しています。</span><span class="sxs-lookup"><span data-stu-id="16ffe-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="16ffe-107">VbSS と従来の画面共有の違いは、使用されている基になるプロトコルと、それらがどのようなものであるかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="16ffe-108">画面共有は、リモートデスクトッププロトコル (RDP) を使用します。これは、ユーザーのコンピューター間で数千の1対1セッションを作成するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="16ffe-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="16ffe-109">新しいテクノロジである VbSS は、ユーザーデータグラムプロトコル (UDP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="16ffe-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="16ffe-110">Skype for Business Server では、ユーザーの1対1、および1対多 (複数者) の会話と会議のエクスペリエンスを改善する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="16ffe-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="16ffe-111">VbSS は、ビデオの開始時間を短縮することを目標として、ビデオの開始時間を短縮することを目標としたメディアプラットフォーム (特に、監視しているものが速い場合)、および全体的な信頼性を利用することになります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="16ffe-112">画面共有を改善する目的の一部は、VbSS と RDP 間の移行が、発生時に可能な限りシームレスになることです。</span><span class="sxs-lookup"><span data-stu-id="16ffe-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="16ffe-113">VbSS は、Skype for Business Server の画面共有に使用される基盤テクノロジへの更新プログラムであるため、ネットワークトラフィックの SIP 詳細を確認したり、コンテンツを共有したりしていない限り、使用しているテクノロジを検出するのは困難な場合があります。は、高速移動または3-d です。</span><span class="sxs-lookup"><span data-stu-id="16ffe-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="16ffe-114">たとえば、職場に多数のレガシクライアントがある場合でも、会議や会話へのフェイルセーフとして RDP を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="16ffe-115">Skype for Business Server は内部ロジックを使用して、クライアントの接続時に適用する2つの方法 (VbSS または従来の画面共有) を決定します。</span><span class="sxs-lookup"><span data-stu-id="16ffe-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="16ffe-116">RDP は、状況に応じて VbSS に置き換えられ、表示が中断されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="16ffe-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="16ffe-117">計画</span><span class="sxs-lookup"><span data-stu-id="16ffe-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="16ffe-118">VbSS の長所と短所</span><span class="sxs-lookup"><span data-stu-id="16ffe-118">VbSS pros and cons</span></span>

<span data-ttu-id="16ffe-119">VbSS を目的として、3つの重要な改善を行います。</span><span class="sxs-lookup"><span data-stu-id="16ffe-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="16ffe-120">画面共有を作成する (最大5%)RDP のみに比べて信頼性が向上しています。</span><span class="sxs-lookup"><span data-stu-id="16ffe-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="16ffe-121">セッションのセットアップとビデオエクスペリエンスを RDP だけに比べて高速化します (時間が半分で、フレームごとに6:1 が向上します)。</span><span class="sxs-lookup"><span data-stu-id="16ffe-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="16ffe-122">低帯域幅条件では、3-d グラフィックスなどの高モーションコンテンツを共有する場合でも、RDP よりもはるかに優れた機能を発揮します。</span><span class="sxs-lookup"><span data-stu-id="16ffe-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="16ffe-123">これらの数字は、ネットワークの正常性とパフォーマンスの調整に依存しており、クライアントがモバイルデバイス上にある場合は、自分の外部のネットワークが関係する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="16ffe-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="16ffe-124">また、信頼性、速度、効率のために、共有コンテンツの忠実性/犠牲が利用されていることにも注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-124">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency.</span></span> <span data-ttu-id="16ffe-125">ほとんどの場合、これはユーザーにはすぐに表示されません。</span><span class="sxs-lookup"><span data-stu-id="16ffe-125">In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="16ffe-126">ポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="16ffe-126">Ports and protocols</span></span>

<span data-ttu-id="16ffe-127">**必要なサーバーポート**</span><span class="sxs-lookup"><span data-stu-id="16ffe-127">**Required server ports**</span></span>

|<span data-ttu-id="16ffe-128">サーバーの役割は、新しいファームを作成するとき、またはサーバーを既存のファームに参加させるときに指定します。</span><span class="sxs-lookup"><span data-stu-id="16ffe-128">**Server role**</span></span>|<span data-ttu-id="16ffe-129">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="16ffe-129">**Service name**</span></span>|<span data-ttu-id="16ffe-130">**ポートまたはポート範囲**</span><span class="sxs-lookup"><span data-stu-id="16ffe-130">**Port or port range**</span></span>|<span data-ttu-id="16ffe-131">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="16ffe-131">**Protocol**</span></span>|<span data-ttu-id="16ffe-132">**メモ**</span><span class="sxs-lookup"><span data-stu-id="16ffe-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16ffe-133">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="16ffe-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="16ffe-134">Skype for Business Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="16ffe-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="16ffe-135">5065</span><span class="sxs-lookup"><span data-stu-id="16ffe-135">5065</span></span>  <br/> |<span data-ttu-id="16ffe-136">TCP</span><span class="sxs-lookup"><span data-stu-id="16ffe-136">TCP</span></span>  <br/> |<span data-ttu-id="16ffe-137">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="16ffe-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="16ffe-138">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="16ffe-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="16ffe-139">Skype for Business Server アプリケーション共有サービス</span><span class="sxs-lookup"><span data-stu-id="16ffe-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="16ffe-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="16ffe-140">49152-65535</span></span>  <br/> |<span data-ttu-id="16ffe-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="16ffe-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="16ffe-142">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="16ffe-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="16ffe-143">**必要なクライアントポート**</span><span class="sxs-lookup"><span data-stu-id="16ffe-143">**Required client ports**</span></span>

|<span data-ttu-id="16ffe-144">**コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="16ffe-144">**Component**</span></span>|<span data-ttu-id="16ffe-145">**ポート範囲**</span><span class="sxs-lookup"><span data-stu-id="16ffe-145">**Port range**</span></span>|<span data-ttu-id="16ffe-146">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="16ffe-146">**Protocol**</span></span>|<span data-ttu-id="16ffe-147">**メモ**</span><span class="sxs-lookup"><span data-stu-id="16ffe-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16ffe-148">クライアント</span><span class="sxs-lookup"><span data-stu-id="16ffe-148">Clients</span></span>  <br/> |<span data-ttu-id="16ffe-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="16ffe-149">1024-65535</span></span>  <br/> |<span data-ttu-id="16ffe-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="16ffe-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="16ffe-151">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="16ffe-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="16ffe-152">次のメディアポートで QoS が有効になっていて、VbSS も有効になっている場合、では、デスクトップ共有を含む電話会議中に、MCU としての画面共有トラフィックについて、次に太字で示されているビデオポート設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="16ffe-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="16ffe-153">これらの設定は特別なケースなので、これらの機能の両方を実装する場合は、これらの設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="16ffe-154">これは、 [QoS のドキュメント](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx)で推奨されるその他の設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="16ffe-154">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="16ffe-155">アプリケーション共有の場合は、これらのポート値を定義するだけでなく、QoS GPO で ASMCUSVC を指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="16ffe-156">**アプリケーションサーバーの QoS/VbSS 必要な設定**</span><span class="sxs-lookup"><span data-stu-id="16ffe-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="16ffe-157">**Property**</span><span class="sxs-lookup"><span data-stu-id="16ffe-157">**Property**</span></span>|<span data-ttu-id="16ffe-158">**ポート値**</span><span class="sxs-lookup"><span data-stu-id="16ffe-158">**Port value**</span></span>|<span data-ttu-id="16ffe-159">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="16ffe-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16ffe-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="16ffe-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="16ffe-161">49152</span><span class="sxs-lookup"><span data-stu-id="16ffe-161">49152</span></span>  <br/> |<span data-ttu-id="16ffe-162">受信</span><span class="sxs-lookup"><span data-stu-id="16ffe-162">UDP</span></span>  <br/> |
|<span data-ttu-id="16ffe-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="16ffe-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="16ffe-164">8348</span><span class="sxs-lookup"><span data-stu-id="16ffe-164">8348</span></span>  <br/> |<span data-ttu-id="16ffe-165">受信</span><span class="sxs-lookup"><span data-stu-id="16ffe-165">UDP</span></span>  <br/> |
|<span data-ttu-id="16ffe-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="16ffe-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="16ffe-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="16ffe-167">**57501**</span></span> <br/> |<span data-ttu-id="16ffe-168">受信</span><span class="sxs-lookup"><span data-stu-id="16ffe-168">UDP</span></span>  <br/> |
|<span data-ttu-id="16ffe-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="16ffe-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="16ffe-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="16ffe-170">**8034**</span></span> <br/> |<span data-ttu-id="16ffe-171">受信</span><span class="sxs-lookup"><span data-stu-id="16ffe-171">UDP</span></span>  <br/> |
|<span data-ttu-id="16ffe-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="16ffe-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="16ffe-173">40803</span><span class="sxs-lookup"><span data-stu-id="16ffe-173">40803</span></span>  <br/> |<span data-ttu-id="16ffe-174">TCP</span><span class="sxs-lookup"><span data-stu-id="16ffe-174">TCP</span></span>  <br/> |
|<span data-ttu-id="16ffe-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="16ffe-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="16ffe-176">8348</span><span class="sxs-lookup"><span data-stu-id="16ffe-176">8348</span></span>  <br/> |<span data-ttu-id="16ffe-177">TCP</span><span class="sxs-lookup"><span data-stu-id="16ffe-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="16ffe-178">容量計画</span><span class="sxs-lookup"><span data-stu-id="16ffe-178">Capacity planning</span></span>

<span data-ttu-id="16ffe-179">Skype for Business Server 2015 の累積的な更新プログラム 2 (CU2) 以降を実行している各フロントエンドサーバーは、RDP を使用して画面を共有するために最大375の参加者をサポートします (ただし、会議ごとに250のみ)。</span><span class="sxs-lookup"><span data-stu-id="16ffe-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="16ffe-180">この容量は、VbSS が導入されて使用されると、CU3 は変更されません。</span><span class="sxs-lookup"><span data-stu-id="16ffe-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="16ffe-181">このラボでは、パフォーマンスとストレステストを行ってきましたが、(使用状況に応じて) 独自の展開に関して、以下の測定も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="16ffe-182">場合</span><span class="sxs-lookup"><span data-stu-id="16ffe-182">Assuming:</span></span>
  
- <span data-ttu-id="16ffe-183">展開で Skype for Business Server 2015 CU2 以降を使用している。</span><span class="sxs-lookup"><span data-stu-id="16ffe-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="16ffe-184">Skype for Business Server 環境内のすべてのユーザーの画面解像度は1920x1080 を超えています。</span><span class="sxs-lookup"><span data-stu-id="16ffe-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="16ffe-185">全容量 (上記のとおり) では、フロントエンドサーバーごとに375画面共有参加者が合計で、1ギガビットのネットワークカードの使用率は89最大で250の場合があります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="16ffe-186">これは、Skype for Business Server CU2 (RDP) の既存のスクリーン共有テクノロジによって、画面上のコンテンツが発表者の PC のネイティブの解像度で送信されるためです。</span><span class="sxs-lookup"><span data-stu-id="16ffe-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="16ffe-187">そのため、を使用すると、より高い画面解像度が考慮されていますが、既に Skype for Business Server 2015 CU2 での画面共有のネットワークボトルネックが発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="16ffe-188">これを緩和するには、次のオプションのうちの1つまたは複数が役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="16ffe-189">フロントエンドサーバーを1ギガビットのネットワークカードから10ギガビットのイーサネットカードにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="16ffe-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="16ffe-190">負荷分散トラフィックのためのフロントエンドサーバーの数を増やします。</span><span class="sxs-lookup"><span data-stu-id="16ffe-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="16ffe-191">いずれかのチャネルで使用される最大帯域幅に cap を入れることにより、VbSS および RDP に使用される帯域幅 (ビットレート) を制限します。</span><span class="sxs-lookup"><span data-stu-id="16ffe-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="16ffe-192">この表の番号は、個別のネットワークおよび共有されるコンテンツによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="16ffe-192">The numbers in this table are influenced by individual networks and by the content being shared.</span></span> <span data-ttu-id="16ffe-193">テストして、ネットワークまたはネットワークのベースラインを確立してください。</span><span class="sxs-lookup"><span data-stu-id="16ffe-193">Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="16ffe-194">**1080p コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="16ffe-194">**1080p Content**</span></span>|<span data-ttu-id="16ffe-195">**RDP の平均**</span><span class="sxs-lookup"><span data-stu-id="16ffe-195">**RDP Average**</span></span>|<span data-ttu-id="16ffe-196">**RDP ピーク**</span><span class="sxs-lookup"><span data-stu-id="16ffe-196">**RDP Peak**</span></span>|<span data-ttu-id="16ffe-197">**VbSS Average**</span><span class="sxs-lookup"><span data-stu-id="16ffe-197">**VbSS Average**</span></span>|<span data-ttu-id="16ffe-198">**VbSS のピーク**</span><span class="sxs-lookup"><span data-stu-id="16ffe-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16ffe-199">PPT</span><span class="sxs-lookup"><span data-stu-id="16ffe-199">PPT</span></span>  <br/> |<span data-ttu-id="16ffe-200">200 kbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-200">200kbps</span></span>  <br/> |<span data-ttu-id="16ffe-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-201">12mbps</span></span>  <br/> |<span data-ttu-id="16ffe-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-202">100kbps</span></span>  <br/> |<span data-ttu-id="16ffe-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="16ffe-204">CAD</span><span class="sxs-lookup"><span data-stu-id="16ffe-204">CAD</span></span>  <br/> |<span data-ttu-id="16ffe-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-205">3mbps</span></span>  <br/> |<span data-ttu-id="16ffe-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-206">7mbps</span></span>  <br/> |<span data-ttu-id="16ffe-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-207">1mbps</span></span>  <br/> |<span data-ttu-id="16ffe-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="16ffe-209">ビデオ</span><span class="sxs-lookup"><span data-stu-id="16ffe-209">Video</span></span>  <br/> |<span data-ttu-id="16ffe-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-210">5mbps</span></span>  <br/> |<span data-ttu-id="16ffe-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-211">7mbps</span></span>  <br/> |<span data-ttu-id="16ffe-212">1.3 mbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="16ffe-213">2.2 mbps</span><span class="sxs-lookup"><span data-stu-id="16ffe-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="16ffe-214">メディアトラフィックのネットワーク帯域幅の要件</span><span class="sxs-lookup"><span data-stu-id="16ffe-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="16ffe-215">VbSS 帯域幅は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="16ffe-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="16ffe-216">**ビデオ コーデック**</span><span class="sxs-lookup"><span data-stu-id="16ffe-216">**Video codec**</span></span>|<span data-ttu-id="16ffe-217">**解像度と縦横比**</span><span class="sxs-lookup"><span data-stu-id="16ffe-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="16ffe-218">**最大ビデオペイロードビットレート (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="16ffe-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="16ffe-219">**最小ビデオペイロードビットレート (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="16ffe-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16ffe-220">.H</span><span class="sxs-lookup"><span data-stu-id="16ffe-220">H.264</span></span>  <br/> |<span data-ttu-id="16ffe-221">1920x1080 (16:9)</span><span class="sxs-lookup"><span data-stu-id="16ffe-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="16ffe-222">(縦横比は、共有先のモニターの解像度に依存し、必ずしも16:9 になることはありません)。</span><span class="sxs-lookup"><span data-stu-id="16ffe-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="16ffe-223">4000</span><span class="sxs-lookup"><span data-stu-id="16ffe-223">4000</span></span>  <br/> |<span data-ttu-id="16ffe-224">1500</span><span class="sxs-lookup"><span data-stu-id="16ffe-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="16ffe-225">クライアントとサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="16ffe-225">Clients and servers support</span></span>

<span data-ttu-id="16ffe-226">ビデオベースの画面共有には、Skype for Business Server 2015 CU3 以降が必要です。また、「Skype for Business および[会議のサポート](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)」[の「モバイルクライアント機能の比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)」に記載されているサポート対象クライアントの現在のバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="16ffe-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="16ffe-227">画面共有が RDP に移行される状況としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="16ffe-228">ASMCU が VbSS をサポートする最小ビルドを満たさない環境でアカウントがホストされている場合。</span><span class="sxs-lookup"><span data-stu-id="16ffe-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="16ffe-229">以前のバージョンの Skype for Business クライアントを使用しているユーザーがセッションに参加している場合は、たとえば、16.0.6330.1000、Skype for Business Room System デバイス、または Skype for Business モバイルアプリよりも低い Windows クライアントバージョンを使用しているユーザーがいます。</span><span class="sxs-lookup"><span data-stu-id="16ffe-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="16ffe-230">ユーザーが Skype for Business Web App から共有している場合。</span><span class="sxs-lookup"><span data-stu-id="16ffe-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="16ffe-231">他のユーザーが Mac で Skype for Business を使用していて、7月、2018累積的な更新プログラム (またはそれ以降) を使用している Skype for Business Online または Skype for Business Server 2015 に所属していない場合。</span><span class="sxs-lookup"><span data-stu-id="16ffe-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="16ffe-232">誰かがプログラム/Windows 共有を開始した場合。</span><span class="sxs-lookup"><span data-stu-id="16ffe-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="16ffe-233">誰かがセッションの記録を開始した場合。</span><span class="sxs-lookup"><span data-stu-id="16ffe-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="16ffe-234">セッション中に誰かがリモート画面コントロールを呼び出した場合。</span><span class="sxs-lookup"><span data-stu-id="16ffe-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="16ffe-235">参加者が250人を超える会議 (VbSS は現時点ではサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="16ffe-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="16ffe-236">セッションが RDP に移行されると、VbSS には戻らないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="16ffe-236">Be aware that once the session transitions to RDP it will not transition back to VbSS.</span></span> <span data-ttu-id="16ffe-237">ここでも、VbSS からの移行はシームレスであることを意図しているため、ほとんどの状況では簡単に検出できません。</span><span class="sxs-lookup"><span data-stu-id="16ffe-237">Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="16ffe-238">Skype for Business の画面共有では、VbSS から RDP への移行をブロックまたはブロックしようとすることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="16ffe-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="16ffe-239">VbSS の有効化、無効化、および構成</span><span class="sxs-lookup"><span data-stu-id="16ffe-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="16ffe-240">すばらしいことですが、Skype for Business Server 2015 の累積的な更新プログラム 3 (CU3) 以降をインストールすると、すべてのユーザーが既定で1対1およびマルチパーティの VbSS に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="16ffe-241">この機能をすべてのユーザーに対して有効にしない理由がある場合は、この問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16ffe-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="16ffe-242">その場合は、次の手順を使用してユーザーを無効にすることができます ([ユーザーを有効にする] 手順は次のようになっています)。</span><span class="sxs-lookup"><span data-stu-id="16ffe-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="16ffe-243">ユーザーが VbSS を使用できないようにする方法</span><span class="sxs-lookup"><span data-stu-id="16ffe-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="16ffe-244">Skype for Business 管理コンソールでこのコマンドレットを実行することによって、vbss を使用しないユーザーに VbSS を許可しないユーザーポリシーを割り当てることができます ([PolicyName] を、これを実行しているポリシーに置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="16ffe-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="16ffe-245">また、グローバル会議ポリシーを更新して、ポリシーが割り当てられていないすべてのユーザーに影響を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="16ffe-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="16ffe-246">このコマンドの詳細については、「 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ffe-246">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="16ffe-247">VbSS を完全にオフにする必要がある場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="16ffe-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="16ffe-248">このコマンドの詳細については、「 [get-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ffe-248">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="16ffe-249">マルチパーティの Skype for Business 会議では、すべてのクライアントエンドポイントが会議開催者のポリシー設定を尊重します。</span><span class="sxs-lookup"><span data-stu-id="16ffe-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="16ffe-250">ユーザーが VbSS を使用できるようにする方法</span><span class="sxs-lookup"><span data-stu-id="16ffe-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="16ffe-251">Skype for Business 管理コンソールで次のコマンドレットを実行することによって、vbss を使用する必要があるユーザーに対して、VbSS を許可する特定のユーザーポリシーを割り当てることができます ([PolicyName] を、これを実行しているポリシーに置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="16ffe-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="16ffe-252">また、グローバル会議ポリシーを更新して、ポリシーが割り当てられていないすべてのユーザーに影響を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="16ffe-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="16ffe-253">このコマンドの詳細については、「 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ffe-253">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="16ffe-254">VbSS をオフにした後で有効にする必要がある場合 (既定でオンになっている場合) は、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="16ffe-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="16ffe-255">このコマンドの詳細については、「 [get-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ffe-255">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="16ffe-256">マルチパーティの Skype for Business 会議では、すべてのクライアントエンドポイントが会議開催者のポリシー設定を尊重します。</span><span class="sxs-lookup"><span data-stu-id="16ffe-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="16ffe-257">関連項目</span><span class="sxs-lookup"><span data-stu-id="16ffe-257">See also</span></span>

[<span data-ttu-id="16ffe-258">Skype for Business Server 2015 の累積的な更新プログラムの KB3061064</span><span class="sxs-lookup"><span data-stu-id="16ffe-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/download/details.aspx?id=47690)
  
[<span data-ttu-id="16ffe-259">ビデオベースの画面共有 (VBSS) は Skype for Business Server 2015 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="16ffe-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/kb/3170163)
