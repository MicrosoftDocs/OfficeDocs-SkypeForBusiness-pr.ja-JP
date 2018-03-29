---
title: Skype for Business Server 2015 のビデオベースの画面共有
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 'Skype ビデオ ベースの画面を共有するため (VbSS) は、現在ダウンロード可能になっているビジネス サーバー 2015 の計画と構成について: ビジネス サーバー 2015 累積的な更新プログラム KB3061064 の Skype です。'
ms.openlocfilehash: 21b7868efb9b1a6621aa85cae277114629d67551
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="video-based-screen-sharing-for-skype-for-business-server-2015"></a><span data-ttu-id="1d438-103">Skype for Business Server 2015 のビデオベースの画面共有</span><span class="sxs-lookup"><span data-stu-id="1d438-103">Video based Screen Sharing for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1d438-104">Skype ビデオ ベースの画面を共有するため (VbSS) は、現在ダウンロード可能になっているビジネス サーバー 2015 の計画と構成について:[ビジネス サーバー 2015 累積的な更新プログラム KB3061064 の Skype](https://www.microsoft.com/en-us/download/details.aspx?id=47690)です。</span><span class="sxs-lookup"><span data-stu-id="1d438-104">Skype for Business Server 2015 planning and configuration information for Video-based Screen Sharing (VbSS), which is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690).</span></span>
  
<span data-ttu-id="1d438-105">ビデオ ベースの画面を共有、または VbSS、画面の共有 Lync から生まれました。</span><span class="sxs-lookup"><span data-stu-id="1d438-105">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="1d438-106">VbSS と従来の画面共有との違いは、使用している基本プロトコルと、それぞれの長所が関係しています。</span><span class="sxs-lookup"><span data-stu-id="1d438-106">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="1d438-107">画面共有ではリモート デスクトップ プロトコル (RDP) を使用していますが、このプロトコルはコンピューター間での数千もの 1 対 1 セッションを生成する点で優れています。</span><span class="sxs-lookup"><span data-stu-id="1d438-107">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="1d438-108">一方 VbSS は新しい技術で、ユーザー データグラム プロトコル (UDP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d438-108">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="1d438-109">ビジネス サーバーの人の 1 対 1、および 1 対多 (複数の相手) の会話の向上を必要とし、会議の経験の Skype です。</span><span class="sxs-lookup"><span data-stu-id="1d438-109">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="1d438-110">VbSS ではメディア プラットフォーム (基本プロトコルとして UDP に依存) を使用して、ビデオの開始時刻、表示の質 (特に高速移動対象)、および全体的信頼性の向上を目標としています。</span><span class="sxs-lookup"><span data-stu-id="1d438-110">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="1d438-111">画面共有を改善する目標には、VbSS と RDP 間での移行が生じる場合に、できるだけシームレスに行うことも含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d438-111">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="1d438-112">VbSS が Skype のビジネス サーバーの共有] 画面で使用される基盤となるテクノロジーの更新のため、ある可能性があります、ネットワーク トラフィック内の SIP の詳細を見ているかを共有している場合を除きを強化するテクノロジーの内容を検出することが困難高速移動] または [3-D です。</span><span class="sxs-lookup"><span data-stu-id="1d438-112">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="1d438-113">たとえば、職場は多くのレガシ クライアントは場合、RDP は念のため、会議や会話を利用できます。</span><span class="sxs-lookup"><span data-stu-id="1d438-113">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="1d438-114">Skype ビジネス サーバーのでは、内部ロジックを使用して、(VbSS または従来の画面共有) クライアントが接続するときに適用する 2 つの方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="1d438-114">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="1d438-115">必要とされる状況では、VbSS に代えて RDP を使用することができ、実際にそうすることで、表示エクスペリエンスが中断されなくなります。</span><span class="sxs-lookup"><span data-stu-id="1d438-115">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="1d438-116">計画</span><span class="sxs-lookup"><span data-stu-id="1d438-116">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="1d438-117">VbSS の長所と短所</span><span class="sxs-lookup"><span data-stu-id="1d438-117">VbSS pros and cons</span></span>

<span data-ttu-id="1d438-118">VbSS に切り替える目的は、次の 3 つの重要な改善を行うことにあります。</span><span class="sxs-lookup"><span data-stu-id="1d438-118">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="1d438-119">RDP だけのときよりも画面共有 (最大 5%) の信頼性を向上させる。</span><span class="sxs-lookup"><span data-stu-id="1d438-119">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="1d438-120">RDP だけのときよりもセッション セットアップとビデオ エクスペリエンスを速くする (セットアップ時間を半分に、フレーム/秒を 6:1 に改善)。</span><span class="sxs-lookup"><span data-stu-id="1d438-120">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="1d438-121">低帯域幅条件下で 3-D グラフィックなどの高速運動コンテンツを共有する場合でも、RDP よりも動作を向上させる。</span><span class="sxs-lookup"><span data-stu-id="1d438-121">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="1d438-122">3 つの改善点は、ネットワークの良好で適正なパフォーマンス調整に依存することに留意してください。クライアントがモバイル デバイスを使用している場合には、外部のネットワークも関係してきます。</span><span class="sxs-lookup"><span data-stu-id="1d438-122">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="1d438-p104">また共有コンテンツの忠実で生き生きとした再現性の一部は、信頼性、速度、および効率の犠牲になることにも留意してください。多くの場合これは、容易にユーザーの目に付くようなものではありません。</span><span class="sxs-lookup"><span data-stu-id="1d438-p104">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency. In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="1d438-125">ポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="1d438-125">Ports and protocols</span></span>

<span data-ttu-id="1d438-126">**必要なサーバー ポート**</span><span class="sxs-lookup"><span data-stu-id="1d438-126">**Required server ports**</span></span>

|<span data-ttu-id="1d438-127">**サーバーの役割**</span><span class="sxs-lookup"><span data-stu-id="1d438-127">**Server role**</span></span>|<span data-ttu-id="1d438-128">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="1d438-128">**Service name**</span></span>|<span data-ttu-id="1d438-129">**ポートまたはポートの範囲**</span><span class="sxs-lookup"><span data-stu-id="1d438-129">**Port or port range**</span></span>|<span data-ttu-id="1d438-130">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="1d438-130">**Protocol**</span></span>|<span data-ttu-id="1d438-131">**メモ**</span><span class="sxs-lookup"><span data-stu-id="1d438-131">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d438-132">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1d438-132">Front End Servers</span></span>  <br/> |<span data-ttu-id="1d438-133">ビジネス サーバー アプリケーションの共有サービスの Skype</span><span class="sxs-lookup"><span data-stu-id="1d438-133">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="1d438-134">5065</span><span class="sxs-lookup"><span data-stu-id="1d438-134">5065</span></span>  <br/> |<span data-ttu-id="1d438-135">TCP</span><span class="sxs-lookup"><span data-stu-id="1d438-135">TCP</span></span>  <br/> |<span data-ttu-id="1d438-136">アプリケーション共有の SIP リッスン要求を受信するために使用。</span><span class="sxs-lookup"><span data-stu-id="1d438-136">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="1d438-137">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1d438-137">Front End Servers</span></span>  <br/> |<span data-ttu-id="1d438-138">ビジネス サーバー アプリケーションの共有サービスの Skype</span><span class="sxs-lookup"><span data-stu-id="1d438-138">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="1d438-139">49152-65535</span><span class="sxs-lookup"><span data-stu-id="1d438-139">49152-65535</span></span>  <br/> |<span data-ttu-id="1d438-140">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1d438-140">TCP/UDP</span></span>  <br/> |<span data-ttu-id="1d438-141">アプリケーション共有で使用するメディア ポート範囲。</span><span class="sxs-lookup"><span data-stu-id="1d438-141">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="1d438-142">**必要なクライアント ポート**</span><span class="sxs-lookup"><span data-stu-id="1d438-142">**Required client ports**</span></span>

|<span data-ttu-id="1d438-143">**コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="1d438-143">**Component**</span></span>|<span data-ttu-id="1d438-144">**ポートの範囲**</span><span class="sxs-lookup"><span data-stu-id="1d438-144">**Port range**</span></span>|<span data-ttu-id="1d438-145">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="1d438-145">**Protocol**</span></span>|<span data-ttu-id="1d438-146">**メモ**</span><span class="sxs-lookup"><span data-stu-id="1d438-146">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d438-147">クライアント</span><span class="sxs-lookup"><span data-stu-id="1d438-147">Clients</span></span>  <br/> |<span data-ttu-id="1d438-148">1024-65535</span><span class="sxs-lookup"><span data-stu-id="1d438-148">1024-65535</span></span>  <br/> |<span data-ttu-id="1d438-149">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1d438-149">TCP/UDP</span></span>  <br/> |<span data-ttu-id="1d438-150">アプリケーション共有。</span><span class="sxs-lookup"><span data-stu-id="1d438-150">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="1d438-151">次のメディア ポート QoS が有効になっているし、VbSS が有効になりますと MCU に示すようにビデオのポートの設定を使用して、デスクトップの共有を含む会議中に太字の下の共有のトラフィックを選別します。</span><span class="sxs-lookup"><span data-stu-id="1d438-151">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1d438-152">これらの設定は、特殊なケース、およびこれらの機能の両方を実装する場合、これらの正確な設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d438-152">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="1d438-153">これには、 [QoS のマニュアル](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)で推奨されるその他の設定がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="1d438-153">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="1d438-154">/Fo オプション アプリケーションを共有するこれらのポートの値を定義するだけでなく、QoS の GPO で ASMCUSVC.exe を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d438-154">Fo application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="1d438-155">**サーバーの QoS と VbSS のアプリケーションに必要な設定**</span><span class="sxs-lookup"><span data-stu-id="1d438-155">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="1d438-156">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="1d438-156">**Property**</span></span>|<span data-ttu-id="1d438-157">**ポート値**</span><span class="sxs-lookup"><span data-stu-id="1d438-157">**Port value**</span></span>|<span data-ttu-id="1d438-158">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="1d438-158">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d438-159">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="1d438-159">AudioPortStart</span></span>  <br/> |<span data-ttu-id="1d438-160">49152</span><span class="sxs-lookup"><span data-stu-id="1d438-160">49152</span></span>  <br/> |<span data-ttu-id="1d438-161">UDP</span><span class="sxs-lookup"><span data-stu-id="1d438-161">UDP</span></span>  <br/> |
|<span data-ttu-id="1d438-162">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="1d438-162">AudioPortCount</span></span>  <br/> |<span data-ttu-id="1d438-163">8348</span><span class="sxs-lookup"><span data-stu-id="1d438-163">8348</span></span>  <br/> |<span data-ttu-id="1d438-164">UDP</span><span class="sxs-lookup"><span data-stu-id="1d438-164">UDP</span></span>  <br/> |
|<span data-ttu-id="1d438-165">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="1d438-165">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="1d438-166">**57501**</span><span class="sxs-lookup"><span data-stu-id="1d438-166">**57501**</span></span> <br/> |<span data-ttu-id="1d438-167">UDP</span><span class="sxs-lookup"><span data-stu-id="1d438-167">UDP</span></span>  <br/> |
|<span data-ttu-id="1d438-168">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="1d438-168">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="1d438-169">**8034**</span><span class="sxs-lookup"><span data-stu-id="1d438-169">**8034**</span></span> <br/> |<span data-ttu-id="1d438-170">UDP</span><span class="sxs-lookup"><span data-stu-id="1d438-170">UDP</span></span>  <br/> |
|<span data-ttu-id="1d438-171">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="1d438-171">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="1d438-172">40803</span><span class="sxs-lookup"><span data-stu-id="1d438-172">40803</span></span>  <br/> |<span data-ttu-id="1d438-173">UDP</span><span class="sxs-lookup"><span data-stu-id="1d438-173">UDP</span></span>  <br/> |
|<span data-ttu-id="1d438-174">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="1d438-174">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="1d438-175">8348</span><span class="sxs-lookup"><span data-stu-id="1d438-175">8348</span></span>  <br/> |<span data-ttu-id="1d438-176">UDP</span><span class="sxs-lookup"><span data-stu-id="1d438-176">UDP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="1d438-177">処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="1d438-177">Capacity planning</span></span>

<span data-ttu-id="1d438-178">ビジネス サーバー 2015 累積的な更新プログラム 2 (CU2) の Skype を実行する各フロント エンド サーバーでは、RDP (会議ごとだけが 250) を使用して共有画面の最大 375 の参加者をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1d438-178">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="1d438-179">この数は、VbSS が導入された後も、ポスト CU-3 で変わりません。</span><span class="sxs-lookup"><span data-stu-id="1d438-179">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="1d438-180">それはそれとして、当社ラボではパフォーマンスおよびストレス試験が行われ、展開に関して次の測定内容も考慮される予定です (当然ながら用途による)。</span><span class="sxs-lookup"><span data-stu-id="1d438-180">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="1d438-181">前提事項:</span><span class="sxs-lookup"><span data-stu-id="1d438-181">Assuming:</span></span>
  
- <span data-ttu-id="1d438-182">展開では、ビジネス サーバー 2015 CU2 の Skype を使用しています。</span><span class="sxs-lookup"><span data-stu-id="1d438-182">You're using Skype for Business Server 2015 CU2 in your deployment.</span></span>
    
- <span data-ttu-id="1d438-183">ビジネス サーバー環境に、Skype のすべてのユーザーには、画面の解像度が 1920 x 1080 よりも高いがあります。</span><span class="sxs-lookup"><span data-stu-id="1d438-183">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="1d438-184">完全に (上記で説明したようにフロント エンド サーバーごとの 375 の画面共有参加者にある会議ごとの合計のみが 250)、ネットワーク カードの 1 ギガビットの ~ 89%、フロント エンド サーバーを利用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d438-184">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="1d438-185">ビジネス サーバー CU2 (RDP) 用の Skype の技術を共有する既存の画面が発表者の PC のネイティブ解像度で画面に表示されるコンテンツに転送するためです。</span><span class="sxs-lookup"><span data-stu-id="1d438-185">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="1d438-186">これより高い画面解像度考慮すると発生する可能性既に Skype ビジネス サーバー 2015 CU2 の共有] 画面で、ネットワークのボトルネック。</span><span class="sxs-lookup"><span data-stu-id="1d438-186">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="1d438-187">これを緩和するには、次のオプションを 1 つまたは複数採用すると効果的です。</span><span class="sxs-lookup"><span data-stu-id="1d438-187">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="1d438-188">10 ギガビットのイーサネット カードに、1 ギガビット ネットワーク カードから、フロント エンド サーバーをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="1d438-188">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="1d438-189">トラフィックを負荷分散するフロント エンド サーバーの数を増やします。</span><span class="sxs-lookup"><span data-stu-id="1d438-189">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="1d438-190">VbSS と RDP の両チャンネルで使用する最大帯域幅に上限を設け、それぞれの帯域幅 (ビットレート) を制限する。</span><span class="sxs-lookup"><span data-stu-id="1d438-190">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="1d438-p108">この表の数字は、個々のネットワークや共有されるコンテンツに影響されます。テストして、使用するネットワークのベースラインを確立してください。</span><span class="sxs-lookup"><span data-stu-id="1d438-p108">The numbers in this table are influenced by individual networks and by the content being shared. Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="1d438-193">**1080 p のコンテンツ**</span><span class="sxs-lookup"><span data-stu-id="1d438-193">**1080p Content**</span></span>|<span data-ttu-id="1d438-194">**RPD の平均値**</span><span class="sxs-lookup"><span data-stu-id="1d438-194">**RPD Average**</span></span>|<span data-ttu-id="1d438-195">**RDP のピーク**</span><span class="sxs-lookup"><span data-stu-id="1d438-195">**RDP Peak**</span></span>|<span data-ttu-id="1d438-196">**VbSS の平均値**</span><span class="sxs-lookup"><span data-stu-id="1d438-196">**VbSS Average**</span></span>|<span data-ttu-id="1d438-197">**VbSS のピーク**</span><span class="sxs-lookup"><span data-stu-id="1d438-197">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d438-198">PPT</span><span class="sxs-lookup"><span data-stu-id="1d438-198">PPT</span></span>  <br/> |<span data-ttu-id="1d438-199">200 kbps</span><span class="sxs-lookup"><span data-stu-id="1d438-199">200kbps</span></span>  <br/> |<span data-ttu-id="1d438-200">12mbps</span><span class="sxs-lookup"><span data-stu-id="1d438-200">12mbps</span></span>  <br/> |<span data-ttu-id="1d438-201">100 kbps</span><span class="sxs-lookup"><span data-stu-id="1d438-201">100kbps</span></span>  <br/> |<span data-ttu-id="1d438-202">3mbps</span><span class="sxs-lookup"><span data-stu-id="1d438-202">3mbps</span></span>  <br/> |
|<span data-ttu-id="1d438-203">CAD</span><span class="sxs-lookup"><span data-stu-id="1d438-203">CAD</span></span>  <br/> |<span data-ttu-id="1d438-204">3mbps</span><span class="sxs-lookup"><span data-stu-id="1d438-204">3mbps</span></span>  <br/> |<span data-ttu-id="1d438-205">7mbps</span><span class="sxs-lookup"><span data-stu-id="1d438-205">7mbps</span></span>  <br/> |<span data-ttu-id="1d438-206">1mbps</span><span class="sxs-lookup"><span data-stu-id="1d438-206">1mbps</span></span>  <br/> |<span data-ttu-id="1d438-207">3mbps</span><span class="sxs-lookup"><span data-stu-id="1d438-207">3mbps</span></span>  <br/> |
|<span data-ttu-id="1d438-208">ビデオ</span><span class="sxs-lookup"><span data-stu-id="1d438-208">Video</span></span>  <br/> |<span data-ttu-id="1d438-209">5mbps</span><span class="sxs-lookup"><span data-stu-id="1d438-209">5mbps</span></span>  <br/> |<span data-ttu-id="1d438-210">7mbps</span><span class="sxs-lookup"><span data-stu-id="1d438-210">7mbps</span></span>  <br/> |<span data-ttu-id="1d438-211">1.3mbps</span><span class="sxs-lookup"><span data-stu-id="1d438-211">1.3mbps</span></span>  <br/> |<span data-ttu-id="1d438-212">2.2mbps</span><span class="sxs-lookup"><span data-stu-id="1d438-212">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="1d438-213">メディア トラフィックのネットワーク帯域幅の要件</span><span class="sxs-lookup"><span data-stu-id="1d438-213">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="1d438-214">VbSS の帯域幅:</span><span class="sxs-lookup"><span data-stu-id="1d438-214">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="1d438-215">**ビデオ コーデック**</span><span class="sxs-lookup"><span data-stu-id="1d438-215">**Video codec**</span></span>|<span data-ttu-id="1d438-216">**解像度と縦横比**</span><span class="sxs-lookup"><span data-stu-id="1d438-216">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="1d438-217">**ビデオ ペイロードの最大ビット レート (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="1d438-217">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="1d438-218">**最小ビデオ ペイロードのビット レート (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="1d438-218">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d438-219">H.264</span><span class="sxs-lookup"><span data-stu-id="1d438-219">H.264</span></span>  <br/> |<span data-ttu-id="1d438-220">1920x1080 (16:9)</span><span class="sxs-lookup"><span data-stu-id="1d438-220">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="1d438-221">(縦横比は共有者のモニター解像度に応じて異なり、必ずしも 16:9 ではない。)</span><span class="sxs-lookup"><span data-stu-id="1d438-221">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="1d438-222">4000</span><span class="sxs-lookup"><span data-stu-id="1d438-222">4000</span></span>  <br/> |<span data-ttu-id="1d438-223">1500</span><span class="sxs-lookup"><span data-stu-id="1d438-223">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="1d438-224">クライアントおよびサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="1d438-224">Clients and servers support</span></span>

<span data-ttu-id="1d438-225">ベースのビデオ画面の共有には、Skype ビジネス サーバー 2015 CU3 またはそれ以降、および[ビジネスの Skype のモバイル クライアントの機能の比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)と[会議のサポート](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)に記載されているサポートのクライアントの現在のバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="1d438-225">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="1d438-226">画面共有に移行 RDP では、上記のような状況があります。</span><span class="sxs-lookup"><span data-stu-id="1d438-226">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="1d438-227">ASMCU が VbSS をサポートできる最低限のビルドに満たない環境でアカウントがホストされている。</span><span class="sxs-lookup"><span data-stu-id="1d438-227">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="1d438-228">ビジネス クライアントで、Skype の古いバージョンを使用している他のユーザーのセッションに参加する場合などのすべてのユーザーを使用して 16.0.6330.1000、ビジネス ルーム システム デバイスでは、Skype または Skype のビジネス ・ モバイル ・ アプリケーションよりも下位にある任意の Windows クライアント バージョンです。</span><span class="sxs-lookup"><span data-stu-id="1d438-228">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="1d438-229">場合は、Skype からは、ビジネスの Web アプリケーションのユーザーを共有しています。</span><span class="sxs-lookup"><span data-stu-id="1d438-229">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="1d438-230">Businesson Mac の Skype を使用している他のユーザーが置かれて Skype のオンライン ビジネスの場合です。</span><span class="sxs-lookup"><span data-stu-id="1d438-230">If someone is using Skype for Businesson Mac and not is homed on Skype for Business Online.</span></span>
- <span data-ttu-id="1d438-231">プログラム/Windows の共有またはセッション中に誰かがレコーディングを始めた場合。</span><span class="sxs-lookup"><span data-stu-id="1d438-231">If someone starts any Program/Windows Sharing, and/or recording during the session.</span></span>
- <span data-ttu-id="1d438-232">セッション中に誰かがリモート画面コントロールを起動した場合。</span><span class="sxs-lookup"><span data-stu-id="1d438-232">If someone invokes Remote Screen Control during the session.</span></span>

    <span data-ttu-id="1d438-p109">セッションが RDP に移行すると、VbSS には戻らないことに留意してください。VbSS からの移行はシームレスに行われるようになっているため、多くの場合気づきません。</span><span class="sxs-lookup"><span data-stu-id="1d438-p109">Be aware that once the session transitions to RDP it will not transition back to VbSS. Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
  
- <span data-ttu-id="1d438-235">250 人を超える参加者による会議 (VbSS がサポートされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="1d438-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1d438-236">ブロックをサポートしていないか、ビジネスの画面共有するため、VbSS から Skype での RDP への移行をブロックしようとしています。</span><span class="sxs-lookup"><span data-stu-id="1d438-236">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="1d438-237">VbSS の有効化、無効化、および構成</span><span class="sxs-lookup"><span data-stu-id="1d438-237">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="1d438-238">ビジネス サーバー 2015 累積的な更新プログラム 3 (CU3)、既定で 1 対 1 および複数相手の VbSS のユーザーが有効にすべての Skype をインストールしたら、非常に便利ですがします。</span><span class="sxs-lookup"><span data-stu-id="1d438-238">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3), all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="1d438-239">そのためこの機能を有効にしたくないユーザーがいる場合には問題となります。</span><span class="sxs-lookup"><span data-stu-id="1d438-239">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="1d438-240">その場合、次の手順に従って、ユーザーを無効化します (その後で有効化します)。</span><span class="sxs-lookup"><span data-stu-id="1d438-240">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="1d438-241">ユーザーが VbSS を使用できないようにする方法</span><span class="sxs-lookup"><span data-stu-id="1d438-241">How to disable users from using VbSS</span></span>

- <span data-ttu-id="1d438-242">VbSS をビジネスの管理コンソール (こうためのポリシーを使用して置換 [グループ]) の Skype でこのコマンドレットを実行することによって VbSS を使用するべきではないすべてのユーザーに使用できないユーザーのポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1d438-242">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="1d438-243">またグローバル会議ポリシーを更新することもでき、そうすれば割り当てられたポリシーのないすべてのユーザーに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="1d438-243">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="1d438-244">このコマンドの詳細については、[セット CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d438-244">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="1d438-245">VbSS を完全にオフにしたい場合は、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d438-245">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="1d438-246">このコマンドの詳細については、[一連の CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d438-246">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1d438-247">ビジネス会議のための複数の Skype ですべてのクライアント エンドポイントは、会議の開催者のポリシーの設定を尊重します。</span><span class="sxs-lookup"><span data-stu-id="1d438-247">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="1d438-248">ユーザーが VbSS を使用できるようにする方法</span><span class="sxs-lookup"><span data-stu-id="1d438-248">How to enable users to use VbSS</span></span>

- <span data-ttu-id="1d438-249">VbSS をビジネスの管理コンソール (こうためのポリシーを使用して置換 [グループ]) の Skype でこのコマンドレットを実行することによって VbSS を使用する必要があるすべてのユーザーに許可する特定のユーザー ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1d438-249">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="1d438-250">またグローバル会議ポリシーを更新することもでき、そうすれば割り当てられたポリシーのないすべてのユーザーに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="1d438-250">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="1d438-251">このコマンドの詳細については、[セット CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d438-251">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="1d438-252">VbSS をオフにした後でオンに戻したい場合は、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d438-252">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="1d438-253">このコマンドの詳細については、[一連の CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d438-253">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1d438-254">ビジネス会議のための複数相手の Skype ですべてのクライアント エンドポイントは、会議の開催者のポリシーの設定を尊重します。</span><span class="sxs-lookup"><span data-stu-id="1d438-254">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1d438-255">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d438-255">See also</span></span>

#### 

[<span data-ttu-id="1d438-256">Skype ビジネス サーバー 2015年の累積的な更新プログラム KB3061064 の</span><span class="sxs-lookup"><span data-stu-id="1d438-256">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[<span data-ttu-id="1d438-257">ビジネス サーバー 2015 の Skype では、ベースのビデオ画面の共有 (VBSS)</span><span class="sxs-lookup"><span data-stu-id="1d438-257">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/en-us/kb/3170163)

