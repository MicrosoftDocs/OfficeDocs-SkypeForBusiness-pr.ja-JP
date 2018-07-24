---
title: ビデオ ベースの画面共有 Skype のビジネス サーバー
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype 画面ビデオ ・ ベース (VbSS) を共有するためのビジネス サーバーの計画と構成について
ms.openlocfilehash: 8f76fbe0879cc9abd452d8b1e0064627c215b20e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968327"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="434f6-103">ビデオ ベースの画面共有 Skype のビジネス サーバー</span><span class="sxs-lookup"><span data-stu-id="434f6-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="434f6-104">ベースのビデオ画面の共有 (VbSS) ビジネス サーバー 2015 の Skype がダウンロードできないようになりました。[ビジネス サーバー 2015 累積的な更新プログラム KB3061064 の Skype](https://www.microsoft.com/en-us/download/details.aspx?id=47690)です。</span><span class="sxs-lookup"><span data-stu-id="434f6-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690).</span></span> <span data-ttu-id="434f6-105">VbSS は、Skype のビジネス サーバー 2019 で含まれています。</span><span class="sxs-lookup"><span data-stu-id="434f6-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="434f6-106">ビデオ ベースの画面を共有、または VbSS、画面の共有 Lync から生まれました。</span><span class="sxs-lookup"><span data-stu-id="434f6-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="434f6-107">VbSS と従来の画面共有との違いは、使用している基本プロトコルと、それぞれの長所が関係しています。</span><span class="sxs-lookup"><span data-stu-id="434f6-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="434f6-108">画面共有ではリモート デスクトップ プロトコル (RDP) を使用していますが、このプロトコルはコンピューター間での数千もの 1 対 1 セッションを生成する点で優れています。</span><span class="sxs-lookup"><span data-stu-id="434f6-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="434f6-109">一方 VbSS は新しい技術で、ユーザー データグラム プロトコル (UDP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="434f6-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="434f6-110">ビジネス サーバーの人の 1 対 1、および 1 対多 (複数の相手) の会話の向上を必要とし、会議の経験の Skype です。</span><span class="sxs-lookup"><span data-stu-id="434f6-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="434f6-111">VbSS ではメディア プラットフォーム (基本プロトコルとして UDP に依存) を使用して、ビデオの開始時刻、表示の質 (特に高速移動対象)、および全体的信頼性の向上を目標としています。</span><span class="sxs-lookup"><span data-stu-id="434f6-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="434f6-112">画面共有を改善する目標には、VbSS と RDP 間での移行が生じる場合に、できるだけシームレスに行うことも含まれています。</span><span class="sxs-lookup"><span data-stu-id="434f6-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="434f6-113">VbSS が Skype のビジネス サーバーの共有] 画面で使用される基盤となるテクノロジーの更新のため、ある可能性があります、ネットワーク トラフィック内の SIP の詳細を見ているかを共有している場合を除きを強化するテクノロジーの内容を検出することが困難高速移動] または [3-D です。</span><span class="sxs-lookup"><span data-stu-id="434f6-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="434f6-114">たとえば、職場は多くのレガシ クライアントは場合、RDP は念のため、会議や会話を利用できます。</span><span class="sxs-lookup"><span data-stu-id="434f6-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="434f6-115">Skype ビジネス サーバーのでは、内部ロジックを使用して、(VbSS または従来の画面共有) クライアントが接続するときに適用する 2 つの方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="434f6-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="434f6-116">必要とされる状況では、VbSS に代えて RDP を使用することができ、実際にそうすることで、表示エクスペリエンスが中断されなくなります。</span><span class="sxs-lookup"><span data-stu-id="434f6-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="434f6-117">計画</span><span class="sxs-lookup"><span data-stu-id="434f6-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="434f6-118">VbSS の長所と短所</span><span class="sxs-lookup"><span data-stu-id="434f6-118">VbSS pros and cons</span></span>

<span data-ttu-id="434f6-119">VbSS に切り替える目的は、次の 3 つの重要な改善を行うことにあります。</span><span class="sxs-lookup"><span data-stu-id="434f6-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="434f6-120">RDP だけのときよりも画面共有 (最大 5%) の信頼性を向上させる。</span><span class="sxs-lookup"><span data-stu-id="434f6-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="434f6-121">RDP だけのときよりもセッション セットアップとビデオ エクスペリエンスを速くする (セットアップ時間を半分に、フレーム/秒を 6:1 に改善)。</span><span class="sxs-lookup"><span data-stu-id="434f6-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="434f6-122">低帯域幅条件下で 3-D グラフィックなどの高速運動コンテンツを共有する場合でも、RDP よりも動作を向上させる。</span><span class="sxs-lookup"><span data-stu-id="434f6-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="434f6-123">3 つの改善点は、ネットワークの良好で適正なパフォーマンス調整に依存することに留意してください。クライアントがモバイル デバイスを使用している場合には、外部のネットワークも関係してきます。</span><span class="sxs-lookup"><span data-stu-id="434f6-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="434f6-p105">また共有コンテンツの忠実で生き生きとした再現性の一部は、信頼性、速度、および効率の犠牲になることにも留意してください。多くの場合これは、容易にユーザーの目に付くようなものではありません。</span><span class="sxs-lookup"><span data-stu-id="434f6-p105">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency. In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="434f6-126">ポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="434f6-126">Ports and protocols</span></span>

<span data-ttu-id="434f6-127">**必要なサーバー ポート**</span><span class="sxs-lookup"><span data-stu-id="434f6-127">**Required server ports**</span></span>

|<span data-ttu-id="434f6-128">**サーバーの役割**</span><span class="sxs-lookup"><span data-stu-id="434f6-128">**Server role**</span></span>|<span data-ttu-id="434f6-129">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="434f6-129">**Service name**</span></span>|<span data-ttu-id="434f6-130">**ポートまたはポート範囲**</span><span class="sxs-lookup"><span data-stu-id="434f6-130">**Port or port range**</span></span>|<span data-ttu-id="434f6-131">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="434f6-131">**Protocol**</span></span>|<span data-ttu-id="434f6-132">**メモ**</span><span class="sxs-lookup"><span data-stu-id="434f6-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="434f6-133">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="434f6-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="434f6-134">ビジネス サーバー アプリケーションの共有サービスの Skype</span><span class="sxs-lookup"><span data-stu-id="434f6-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="434f6-135">5065</span><span class="sxs-lookup"><span data-stu-id="434f6-135">5065</span></span>  <br/> |<span data-ttu-id="434f6-136">TCP</span><span class="sxs-lookup"><span data-stu-id="434f6-136">TCP</span></span>  <br/> |<span data-ttu-id="434f6-137">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="434f6-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="434f6-138">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="434f6-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="434f6-139">ビジネス サーバー アプリケーションの共有サービスの Skype</span><span class="sxs-lookup"><span data-stu-id="434f6-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="434f6-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="434f6-140">49152-65535</span></span>  <br/> |<span data-ttu-id="434f6-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="434f6-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="434f6-142">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="434f6-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="434f6-143">**必要なクライアント ポート**</span><span class="sxs-lookup"><span data-stu-id="434f6-143">**Required client ports**</span></span>

|<span data-ttu-id="434f6-144">**コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="434f6-144">**Component**</span></span>|<span data-ttu-id="434f6-145">**ポートの範囲**</span><span class="sxs-lookup"><span data-stu-id="434f6-145">**Port range**</span></span>|<span data-ttu-id="434f6-146">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="434f6-146">**Protocol**</span></span>|<span data-ttu-id="434f6-147">**メモ**</span><span class="sxs-lookup"><span data-stu-id="434f6-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="434f6-148">クライアント</span><span class="sxs-lookup"><span data-stu-id="434f6-148">Clients</span></span>  <br/> |<span data-ttu-id="434f6-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="434f6-149">1024-65535</span></span>  <br/> |<span data-ttu-id="434f6-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="434f6-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="434f6-151">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="434f6-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="434f6-152">次のメディア ポート QoS が有効になっているし、VbSS が有効になりますと MCU に示すようにビデオのポートの設定を使用して、デスクトップの共有を含む会議中に太字の下の共有のトラフィックを選別します。</span><span class="sxs-lookup"><span data-stu-id="434f6-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="434f6-153">これらの設定は、特殊なケース、およびこれらの機能の両方を実装する場合、これらの正確な設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="434f6-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="434f6-154">これには、 [QoS のマニュアル](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)で推奨されるその他の設定がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="434f6-154">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="434f6-155">/Fo オプション アプリケーションを共有するこれらのポートの値を定義するだけでなく、QoS の GPO で ASMCUSVC.exe を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="434f6-155">Fo application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="434f6-156">**サーバーの QoS と VbSS のアプリケーションに必要な設定**</span><span class="sxs-lookup"><span data-stu-id="434f6-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="434f6-157">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="434f6-157">**Property**</span></span>|<span data-ttu-id="434f6-158">**ポート値**</span><span class="sxs-lookup"><span data-stu-id="434f6-158">**Port value**</span></span>|<span data-ttu-id="434f6-159">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="434f6-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="434f6-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="434f6-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="434f6-161">49152</span><span class="sxs-lookup"><span data-stu-id="434f6-161">49152</span></span>  <br/> |<span data-ttu-id="434f6-162">UDP</span><span class="sxs-lookup"><span data-stu-id="434f6-162">UDP</span></span>  <br/> |
|<span data-ttu-id="434f6-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="434f6-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="434f6-164">8348</span><span class="sxs-lookup"><span data-stu-id="434f6-164">8348</span></span>  <br/> |<span data-ttu-id="434f6-165">UDP</span><span class="sxs-lookup"><span data-stu-id="434f6-165">UDP</span></span>  <br/> |
|<span data-ttu-id="434f6-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="434f6-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="434f6-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="434f6-167">**57501**</span></span> <br/> |<span data-ttu-id="434f6-168">UDP</span><span class="sxs-lookup"><span data-stu-id="434f6-168">UDP</span></span>  <br/> |
|<span data-ttu-id="434f6-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="434f6-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="434f6-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="434f6-170">**8034**</span></span> <br/> |<span data-ttu-id="434f6-171">UDP</span><span class="sxs-lookup"><span data-stu-id="434f6-171">UDP</span></span>  <br/> |
|<span data-ttu-id="434f6-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="434f6-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="434f6-173">40803</span><span class="sxs-lookup"><span data-stu-id="434f6-173">40803</span></span>  <br/> |<span data-ttu-id="434f6-174">UDP</span><span class="sxs-lookup"><span data-stu-id="434f6-174">UDP</span></span>  <br/> |
|<span data-ttu-id="434f6-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="434f6-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="434f6-176">8348</span><span class="sxs-lookup"><span data-stu-id="434f6-176">8348</span></span>  <br/> |<span data-ttu-id="434f6-177">UDP</span><span class="sxs-lookup"><span data-stu-id="434f6-177">UDP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="434f6-178">処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="434f6-178">Capacity planning</span></span>

<span data-ttu-id="434f6-179">Skype ビジネス サーバー 2015 累積的な更新プログラム 2 (CU2) またはそれ以降を実行する各フロント エンド サーバーでは、RDP (会議ごとだけが 250) を使用して共有画面の最大 375 の参加者をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="434f6-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="434f6-180">この数は、VbSS が導入された後も、ポスト CU-3 で変わりません。</span><span class="sxs-lookup"><span data-stu-id="434f6-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="434f6-181">それはそれとして、当社ラボではパフォーマンスおよびストレス試験が行われ、展開に関して次の測定内容も考慮される予定です (当然ながら用途による)。</span><span class="sxs-lookup"><span data-stu-id="434f6-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="434f6-182">前提事項:</span><span class="sxs-lookup"><span data-stu-id="434f6-182">Assuming:</span></span>
  
- <span data-ttu-id="434f6-183">サーバー 2015 CU2 のビジネスや、展開の後では、Skype を使用しています。</span><span class="sxs-lookup"><span data-stu-id="434f6-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="434f6-184">ビジネス サーバー環境に、Skype のすべてのユーザーには、画面の解像度が 1920 x 1080 よりも高いがあります。</span><span class="sxs-lookup"><span data-stu-id="434f6-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="434f6-185">完全に (上記で説明したようにフロント エンド サーバーごとの 375 の画面共有参加者にある会議ごとの合計のみが 250)、ネットワーク カードの 1 ギガビットの ~ 89%、フロント エンド サーバーを利用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="434f6-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="434f6-186">ビジネス サーバー CU2 (RDP) 用の Skype の技術を共有する既存の画面が発表者の PC のネイティブ解像度で画面に表示されるコンテンツに転送するためです。</span><span class="sxs-lookup"><span data-stu-id="434f6-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="434f6-187">これより高い画面解像度考慮すると発生する可能性既に Skype ビジネス サーバー 2015 CU2 の共有] 画面で、ネットワークのボトルネック。</span><span class="sxs-lookup"><span data-stu-id="434f6-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="434f6-188">これを緩和するには、次のオプションを 1 つまたは複数採用すると効果的です。</span><span class="sxs-lookup"><span data-stu-id="434f6-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="434f6-189">10 ギガビットのイーサネット カードに、1 ギガビット ネットワーク カードから、フロント エンド サーバーをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="434f6-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="434f6-190">トラフィックを負荷分散するフロント エンド サーバーの数を増やします。</span><span class="sxs-lookup"><span data-stu-id="434f6-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="434f6-191">VbSS と RDP の両チャンネルで使用する最大帯域幅に上限を設け、それぞれの帯域幅 (ビットレート) を制限する。</span><span class="sxs-lookup"><span data-stu-id="434f6-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="434f6-p109">この表の数字は、個々のネットワークや共有されるコンテンツに影響されます。テストして、使用するネットワークのベースラインを確立してください。</span><span class="sxs-lookup"><span data-stu-id="434f6-p109">The numbers in this table are influenced by individual networks and by the content being shared. Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="434f6-194">**1080p コンテンツ **</span><span class="sxs-lookup"><span data-stu-id="434f6-194">**1080p Content**</span></span>|<span data-ttu-id="434f6-195">**RDP の平均値**</span><span class="sxs-lookup"><span data-stu-id="434f6-195">**RDP Average**</span></span>|<span data-ttu-id="434f6-196">**RDP のピーク**</span><span class="sxs-lookup"><span data-stu-id="434f6-196">**RDP Peak**</span></span>|<span data-ttu-id="434f6-197">**VbSS の平均**</span><span class="sxs-lookup"><span data-stu-id="434f6-197">**VbSS Average**</span></span>|<span data-ttu-id="434f6-198">**VbSS のピーク**</span><span class="sxs-lookup"><span data-stu-id="434f6-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="434f6-199">PPT</span><span class="sxs-lookup"><span data-stu-id="434f6-199">PPT</span></span>  <br/> |<span data-ttu-id="434f6-200">200 kbps</span><span class="sxs-lookup"><span data-stu-id="434f6-200">200kbps</span></span>  <br/> |<span data-ttu-id="434f6-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="434f6-201">12mbps</span></span>  <br/> |<span data-ttu-id="434f6-202">100 kbps</span><span class="sxs-lookup"><span data-stu-id="434f6-202">100kbps</span></span>  <br/> |<span data-ttu-id="434f6-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="434f6-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="434f6-204">CAD</span><span class="sxs-lookup"><span data-stu-id="434f6-204">CAD</span></span>  <br/> |<span data-ttu-id="434f6-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="434f6-205">3mbps</span></span>  <br/> |<span data-ttu-id="434f6-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="434f6-206">7mbps</span></span>  <br/> |<span data-ttu-id="434f6-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="434f6-207">1mbps</span></span>  <br/> |<span data-ttu-id="434f6-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="434f6-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="434f6-209">ビデオ</span><span class="sxs-lookup"><span data-stu-id="434f6-209">Video</span></span>  <br/> |<span data-ttu-id="434f6-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="434f6-210">5mbps</span></span>  <br/> |<span data-ttu-id="434f6-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="434f6-211">7mbps</span></span>  <br/> |<span data-ttu-id="434f6-212">1.3mbps</span><span class="sxs-lookup"><span data-stu-id="434f6-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="434f6-213">2.2mbps</span><span class="sxs-lookup"><span data-stu-id="434f6-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="434f6-214">メディア トラフィックのネットワーク帯域幅の要件</span><span class="sxs-lookup"><span data-stu-id="434f6-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="434f6-215">VbSS の帯域幅:</span><span class="sxs-lookup"><span data-stu-id="434f6-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="434f6-216">**ビデオ コーデック**</span><span class="sxs-lookup"><span data-stu-id="434f6-216">**Video codec**</span></span>|<span data-ttu-id="434f6-217">**解像度と縦横比**</span><span class="sxs-lookup"><span data-stu-id="434f6-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="434f6-218">**最大ビデオ ペイロード ビット レート (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="434f6-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="434f6-219">**最小ビデオ ペイロード ビット レート (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="434f6-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="434f6-220">H.264</span><span class="sxs-lookup"><span data-stu-id="434f6-220">H.264</span></span>  <br/> |<span data-ttu-id="434f6-221">1920x1080 (16:9)</span><span class="sxs-lookup"><span data-stu-id="434f6-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="434f6-222">(縦横比は共有者のモニター解像度に応じて異なり、必ずしも 16:9 ではない。)</span><span class="sxs-lookup"><span data-stu-id="434f6-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="434f6-223">4000</span><span class="sxs-lookup"><span data-stu-id="434f6-223">4000</span></span>  <br/> |<span data-ttu-id="434f6-224">1500</span><span class="sxs-lookup"><span data-stu-id="434f6-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="434f6-225">クライアントおよびサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="434f6-225">Clients and servers support</span></span>

<span data-ttu-id="434f6-226">ベースのビデオ画面の共有には、Skype ビジネス サーバー 2015 CU3 またはそれ以降、および[ビジネスの Skype のモバイル クライアントの機能の比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)と[会議のサポート](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)に記載されているサポートのクライアントの現在のバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="434f6-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="434f6-227">画面共有に移行 RDP では、上記のような状況があります。</span><span class="sxs-lookup"><span data-stu-id="434f6-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="434f6-228">ASMCU が VbSS をサポートできる最低限のビルドに満たない環境でアカウントがホストされている。</span><span class="sxs-lookup"><span data-stu-id="434f6-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="434f6-229">ビジネス クライアントで、Skype の古いバージョンを使用している他のユーザーのセッションに参加する場合などのすべてのユーザーを使用して 16.0.6330.1000、ビジネス ルーム システム デバイスでは、Skype または Skype のビジネス ・ モバイル ・ アプリケーションよりも下位にある任意の Windows クライアント バージョンです。</span><span class="sxs-lookup"><span data-stu-id="434f6-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="434f6-230">場合は、Skype からは、ビジネスの Web アプリケーションのユーザーを共有しています。</span><span class="sxs-lookup"><span data-stu-id="434f6-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="434f6-231">Businesson Mac の Skype を使用している他のユーザーが置かれて Skype のオンライン ビジネスの場合です。</span><span class="sxs-lookup"><span data-stu-id="434f6-231">If someone is using Skype for Businesson Mac and not is homed on Skype for Business Online.</span></span>
- <span data-ttu-id="434f6-232">場合は他のユーザーは、任意のプログラムまたは Windows の共有を開始します。</span><span class="sxs-lookup"><span data-stu-id="434f6-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="434f6-233">場合は他のユーザーは、セッションの記録を開始します。</span><span class="sxs-lookup"><span data-stu-id="434f6-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="434f6-234">セッション中に誰かがリモート画面コントロールを起動した場合。</span><span class="sxs-lookup"><span data-stu-id="434f6-234">If someone invokes Remote Screen Control during the session.</span></span>

    <span data-ttu-id="434f6-p110">セッションが RDP に移行すると、VbSS には戻らないことに留意してください。VbSS からの移行はシームレスに行われるようになっているため、多くの場合気づきません。</span><span class="sxs-lookup"><span data-stu-id="434f6-p110">Be aware that once the session transitions to RDP it will not transition back to VbSS. Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
  
- <span data-ttu-id="434f6-237">250 人を超える参加者による会議 (VbSS がサポートされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="434f6-237">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>
    
> [!NOTE]
> <span data-ttu-id="434f6-238">ブロックをサポートしていないか、ビジネスの画面共有するため、VbSS から Skype での RDP への移行をブロックしようとしています。</span><span class="sxs-lookup"><span data-stu-id="434f6-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="434f6-239">VbSS の有効化、無効化、および構成</span><span class="sxs-lookup"><span data-stu-id="434f6-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="434f6-240">最も優れている点は、ビジネス サーバー 2015 累積的な更新プログラム 3 (CU3) は、Skype をインストールしたか、後で、すべてのユーザーを有効化する 1 対 1 および複数相手の VbSS 既定です。</span><span class="sxs-lookup"><span data-stu-id="434f6-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="434f6-241">そのためこの機能を有効にしたくないユーザーがいる場合には問題となります。</span><span class="sxs-lookup"><span data-stu-id="434f6-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="434f6-242">その場合、次の手順に従って、ユーザーを無効化します (その後で有効化します)。</span><span class="sxs-lookup"><span data-stu-id="434f6-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="434f6-243">ユーザーが VbSS を使用できないようにする方法</span><span class="sxs-lookup"><span data-stu-id="434f6-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="434f6-244">VbSS をビジネスの管理コンソール (こうためのポリシーを使用して置換 [グループ]) の Skype でこのコマンドレットを実行することによって VbSS を使用するべきではないすべてのユーザーに使用できないユーザーのポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="434f6-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="434f6-245">またグローバル会議ポリシーを更新することもでき、そうすれば割り当てられたポリシーのないすべてのユーザーに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="434f6-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="434f6-246">このコマンドの詳細については、[セット CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="434f6-246">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="434f6-247">VbSS を完全にオフにしたい場合は、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="434f6-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="434f6-248">このコマンドの詳細については、[一連の CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="434f6-248">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="434f6-249">ビジネス会議のための複数の Skype ですべてのクライアント エンドポイントは、会議の開催者のポリシーの設定を尊重します。</span><span class="sxs-lookup"><span data-stu-id="434f6-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="434f6-250">ユーザーが VbSS を使用できるようにする方法</span><span class="sxs-lookup"><span data-stu-id="434f6-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="434f6-251">VbSS をビジネスの管理コンソール (こうためのポリシーを使用して置換 [グループ]) の Skype でこのコマンドレットを実行することによって VbSS を使用する必要があるすべてのユーザーに許可する特定のユーザー ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="434f6-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="434f6-252">またグローバル会議ポリシーを更新することもでき、そうすれば割り当てられたポリシーのないすべてのユーザーに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="434f6-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="434f6-253">このコマンドの詳細については、[セット CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="434f6-253">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="434f6-254">VbSS をオフにした後でオンに戻したい場合は、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="434f6-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="434f6-255">このコマンドの詳細については、[一連の CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="434f6-255">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="434f6-256">ビジネス会議のための複数相手の Skype ですべてのクライアント エンドポイントは、会議の開催者のポリシーの設定を尊重します。</span><span class="sxs-lookup"><span data-stu-id="434f6-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="434f6-257">関連項目</span><span class="sxs-lookup"><span data-stu-id="434f6-257">See also</span></span>

[<span data-ttu-id="434f6-258">Skype ビジネス サーバー 2015年の累積的な更新プログラム KB3061064 の</span><span class="sxs-lookup"><span data-stu-id="434f6-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[<span data-ttu-id="434f6-259">ビジネス サーバー 2015 の Skype では、ベースのビデオ画面の共有 (VBSS)</span><span class="sxs-lookup"><span data-stu-id="434f6-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/en-us/kb/3170163)
