---
title: ダイレクト ルーティングの音声ルーティングを構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Phone System Direct Routing を使用して音声ルーティングを構成する方法について説明します。
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383981"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="624cb-103">ダイレクト ルーティングの音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="624cb-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="624cb-104">この記事では、電話システム ダイレクト ルーティングの音声ルーティングを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="624cb-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="624cb-105">これは、ダイレクト ルーティングを構成するための次の手順の手順 3 です。</span><span class="sxs-lookup"><span data-stu-id="624cb-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="624cb-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="624cb-106">Step 1.</span></span> [<span data-ttu-id="624cb-107">SBC を Microsoft Phone System に接続し、接続を検証する</span><span class="sxs-lookup"><span data-stu-id="624cb-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="624cb-108">手順 2.</span><span class="sxs-lookup"><span data-stu-id="624cb-108">Step 2.</span></span> [<span data-ttu-id="624cb-109">直接ルーティング、音声、ボイスメールのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="624cb-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="624cb-110">**手順 3.音声ルーティングを構成** する (この記事)</span><span class="sxs-lookup"><span data-stu-id="624cb-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="624cb-111">手順 4.</span><span class="sxs-lookup"><span data-stu-id="624cb-111">Step 4.</span></span> [<span data-ttu-id="624cb-112">数値を別の形式に翻訳する</span><span class="sxs-lookup"><span data-stu-id="624cb-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="624cb-113">ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングを構成する」を [参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="624cb-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="624cb-114">音声ルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="624cb-114">Voice routing overview</span></span>

<span data-ttu-id="624cb-115">Microsoft Phone System には、次に基づいて通話を特定のセッション ボーダー コントローラー (SBC) に送信できるルーティング メカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="624cb-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="624cb-116">呼び出される番号パターン</span><span class="sxs-lookup"><span data-stu-id="624cb-116">The called number pattern</span></span> 
- <span data-ttu-id="624cb-117">呼び出された番号パターンと、呼び出しを行う特定のユーザー</span><span class="sxs-lookup"><span data-stu-id="624cb-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="624cb-118">SPC はアクティブとバックアップとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="624cb-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="624cb-119">アクティブとして構成されている SBC が特定の通話ルートで利用できない場合、通話はバックアップ SBC にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="624cb-120">音声ルーティングは、次の要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="624cb-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="624cb-121">**音声ルーティング ポリシー** – PSTN 使用状況のコンテナー。ユーザーまたは複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="624cb-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="624cb-122">**PSTN の使用状況** – 音声ルートと PSTN 使用状況のコンテナーです。これは、異なる音声ルーティング ポリシーで共有できます。</span><span class="sxs-lookup"><span data-stu-id="624cb-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="624cb-123">**音声ルート** – 発信番号がパターンに一致する通話に使用する番号パターンとオンライン PSTN ゲートウェイのセット。</span><span class="sxs-lookup"><span data-stu-id="624cb-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="624cb-124">**オンライン PSTN ゲートウェイ** - SBC を介して呼び出しが実行された場合に適用される構成 (FORWARD P-Asserted-Identity (CODEC) や Preferred Codecs など) を格納する SBC へのポインター。を音声ルートに追加できます。</span><span class="sxs-lookup"><span data-stu-id="624cb-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="624cb-125">音声ルーティング ポリシーに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="624cb-125">Voice routing policy considerations</span></span>

<span data-ttu-id="624cb-126">ユーザーが通話プラン のライセンスを持っている場合、そのユーザーの発信通話は Microsoft 通話プラン PSTN インフラストラクチャ経由で自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="624cb-127">オンライン音声ルーティング ポリシーを構成して通話プラン ユーザーに割り当てると、そのユーザーの発信通話がチェックされ、ダイヤルされた番号がオンライン音声ルーティング ポリシーで定義されている番号パターンと一致するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="624cb-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="624cb-128">一致する場合、通話はダイレクト ルーティング トランクを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="624cb-129">一致する通話がない場合、通話は通話プラン PSTN インフラストラクチャを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="624cb-130">グローバル (組織全体の既定) オンライン 音声ルーティング ポリシーを構成して適用すると、組織内のすべての音声対応ユーザーはポリシーを継承し、そのポリシーを継承すると、通話プランユーザーからの PSTN 通話が誤ってダイレクト ルーティング トランクにルーティングされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="624cb-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="624cb-131">すべてのユーザーがグローバル オンライン音声ルーティング ポリシーを使用しない場合は、カスタム オンライン 音声ルーティング ポリシーを構成し、個々の音声対応ユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="624cb-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="624cb-132">例 1: 1 つの PSTN 使用状況を使用した音声ルーティング</span><span class="sxs-lookup"><span data-stu-id="624cb-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="624cb-133">次の図は、コール フローでの音声ルーティング ポリシーの 2 つの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="624cb-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="624cb-134">**コール フロー 1 (左側):** ユーザーが +1 425 XXX XX または +1 206 XXX XX XX を呼び出した場合、呼び出しは SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="624cb-135">使用できる sbc1.contoso.biz sbc2.contoso.biz、通話はドロップされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="624cb-136">**コール フロー 2 (右側):** ユーザーが +1 425 XXX XX または +1 206 XXX XX XX を呼び出した場合、呼び出しは最初に SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="624cb-137">どちらの SBC も利用できない場合は、優先度が低いルートが試 sbc3.contoso.biz が試 sbc4.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="624cb-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="624cb-138">使用できる SPC が存在しない場合、通話はドロップされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-138">If none of the SBCs are available, the call is dropped.</span></span> 

![音声ルーティング ポリシーの例を示す](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="624cb-140">どちらの例でも、音声ルートには優先度が割り当てられますが、ルート内の SPC はランダムな順序で試されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="624cb-141">ユーザーが Microsoft 通話プランのライセンスも持たない限り、例の構成でパターン +1 425 XXX XX XX または +1 206 XXX XX XX に一致する番号を除く任意の番号を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="624cb-141">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="624cb-142">ユーザーが通話プランのライセンスを持つ場合、通話は Microsoft 通話プランのポリシーに従って自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-142">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="624cb-143">Microsoft 通話プランは、Microsoft 通話プラン ライセンスを持つすべてのユーザーへの最後のルートとして自動的に適用され、追加の通話ルーティング構成は必要ない。</span><span class="sxs-lookup"><span data-stu-id="624cb-143">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="624cb-144">次の図に示す例では、米国およびカナダの他のすべての番号に通話を送信する音声ルートが追加されています (番号パターン +1 XXX XXX XX XX という呼び出しに移動する通話)。</span><span class="sxs-lookup"><span data-stu-id="624cb-144">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![第 3 ルートでの音声ルーティング ポリシーの表示](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="624cb-146">その他のすべての通話では、ユーザーが両方のライセンス (Microsoft 電話システムと Microsoft 通話プラン) を持つ場合は、自動ルートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-146">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="624cb-147">管理者が作成したオンライン音声ルートの番号パターンに一致する番号が見当たらない場合、通話は Microsoft 通話プラン経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-147">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="624cb-148">ユーザーが Microsoft Phone System のみを持つ場合、照合ルールが利用できないので通話は削除されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-148">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="624cb-149">ルート "Other +1" の Priority 値は、パターン +1 XXX XXX XX XX に一致するルートが 1 つしか存在しないので、この場合は問題ありません。</span><span class="sxs-lookup"><span data-stu-id="624cb-149">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="624cb-150">ユーザーが +1 324 567 89 89 に電話をかけ、sbc5.contoso.biz と sbc6.contoso.biz の両方が使用できない場合、通話は停止されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-150">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="624cb-151">次の表は、3 つの音声ルートを使用した構成の概要です。</span><span class="sxs-lookup"><span data-stu-id="624cb-151">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="624cb-152">この例では、3 つのルートはすべて、同じ PSTN 使用状況 ("米国とカナダ") の一部です。</span><span class="sxs-lookup"><span data-stu-id="624cb-152">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="624cb-153">すべてのルートは "米国とカナダ" の PSTN 使用状況に関連付けられているので、PSTN の使用状況は "米国のみ" の音声ルーティング ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="624cb-153">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="624cb-154">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="624cb-154">**PSTN usage**</span></span>|<span data-ttu-id="624cb-155">**音声ルート**</span><span class="sxs-lookup"><span data-stu-id="624cb-155">**Voice route**</span></span>|<span data-ttu-id="624cb-156">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="624cb-156">**Number pattern**</span></span>|<span data-ttu-id="624cb-157">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="624cb-157">**Priority**</span></span>|<span data-ttu-id="624cb-158">**SBC**</span><span class="sxs-lookup"><span data-stu-id="624cb-158">**SBC**</span></span>|<span data-ttu-id="624cb-159">**説明**</span><span class="sxs-lookup"><span data-stu-id="624cb-159">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="624cb-160">米国とカナダ</span><span class="sxs-lookup"><span data-stu-id="624cb-160">US and Canada</span></span>|<span data-ttu-id="624cb-161">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="624cb-161">"Redmond 1"</span></span>|<span data-ttu-id="624cb-162">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="624cb-162">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="624cb-163">1</span><span class="sxs-lookup"><span data-stu-id="624cb-163">1</span></span>|<span data-ttu-id="624cb-164">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-164">sbc1.contoso.biz</span></span><br/><span data-ttu-id="624cb-165">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-165">sbc2.contoso.biz</span></span>|<span data-ttu-id="624cb-166">呼び出された番号のアクティブなルート +1 425 XXX XX または +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="624cb-166">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="624cb-167">米国とカナダ</span><span class="sxs-lookup"><span data-stu-id="624cb-167">US and Canada</span></span>|<span data-ttu-id="624cb-168">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="624cb-168">"Redmond 2"</span></span>|<span data-ttu-id="624cb-169">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="624cb-169">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="624cb-170">2</span><span class="sxs-lookup"><span data-stu-id="624cb-170">2</span></span>|<span data-ttu-id="624cb-171">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-171">sbc3.contoso.biz</span></span><br/><span data-ttu-id="624cb-172">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-172">sbc4.contoso.biz</span></span>|<span data-ttu-id="624cb-173">呼び出された番号のバックアップ ルート +1 425 XXX XX または +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="624cb-173">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="624cb-174">米国とカナダ</span><span class="sxs-lookup"><span data-stu-id="624cb-174">US and Canada</span></span>|<span data-ttu-id="624cb-175">"Other +1"</span><span class="sxs-lookup"><span data-stu-id="624cb-175">"Other +1"</span></span>|<span data-ttu-id="624cb-176">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="624cb-176">^\\+1(\d{10})$</span></span>|<span data-ttu-id="624cb-177">3</span><span class="sxs-lookup"><span data-stu-id="624cb-177">3</span></span>|<span data-ttu-id="624cb-178">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-178">sbc5.contoso.biz</span></span><br/><span data-ttu-id="624cb-179">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-179">sbc6.contoso.biz</span></span>|<span data-ttu-id="624cb-180">呼び出された番号のルート +1 XXX XXX XX XX (+1 425 XXX XX または +1 206 XXX XX XX を除く)</span><span class="sxs-lookup"><span data-stu-id="624cb-180">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="624cb-181">例 1: 構成手順</span><span class="sxs-lookup"><span data-stu-id="624cb-181">Example 1: Configuration steps</span></span>

<span data-ttu-id="624cb-182">次の例は、次の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="624cb-182">The following example shows how to:</span></span>

1. <span data-ttu-id="624cb-183">1 つの PSTN 使用状況を作成する。</span><span class="sxs-lookup"><span data-stu-id="624cb-183">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="624cb-184">3 つの音声ルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="624cb-184">Configure three voice routes.</span></span>
3. <span data-ttu-id="624cb-185">音声ルーティング ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="624cb-185">Create a voice routing policy.</span></span>
4. <span data-ttu-id="624cb-186">Spencer Low という名前のユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="624cb-186">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="624cb-187">Microsoft Teams 管理センターまたは [PowerShell](#admincenterexample1) を使用して [、これらの](#powershellexample1) 手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="624cb-187">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="624cb-188">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="624cb-188">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="624cb-189">手順 1: "米国とカナダ" の PSTN 使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="624cb-189">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="624cb-190">Microsoft Teams 管理センターの左側のナビゲーションで、[音声ダイレクト ルーティング] に移動し、右上隅の [PSTN 使用状況レコードの管理] を  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="624cb-190">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="624cb-191">[追加 **] を** クリックし、 **米国とカナダを入力して、[** 適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="624cb-191">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="624cb-192">手順 2: 3 つの音声ルートを作成する (Redmond 1、Redmond 2、Other +1)</span><span class="sxs-lookup"><span data-stu-id="624cb-192">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="624cb-193">次の手順では、音声ルートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="624cb-193">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="624cb-194">前の表で説明した設定を使用して、この例の Redmond 1、Redmond 2、Other +1 という 3 つの音声ルートを作成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="624cb-194">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="624cb-195">Microsoft Teams 管理センターの左側のナビゲーションで、[音声ダイレクト ルーティング] に移動し、[音声ルート  >  **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="624cb-195">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="624cb-196">[ **追加]** をクリックし、音声ルートの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="624cb-196">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="624cb-197">優先度を設定し、ダイヤルされた番号パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="624cb-197">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="624cb-198">音声ルートで SBC を登録するには、[登録済み SBC] **(オプション)** で **[SBC** の追加] をクリックし、登録する SBC を選択し、[適用] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="624cb-198">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="624cb-199">PSTN 使用状況レコードを追加するには、[PSTN 使用状況レコード] **(省略可能)** で **、[PSTN** 使用状況の追加] をクリックし、追加する PSTN レコードを選択して、[適用] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="624cb-199">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="624cb-200">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="624cb-200">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="624cb-201">手順 3: "米国のみ" という名前の音声ルーティング ポリシーを作成し、"米国とカナダ" の PSTN 使用状況をポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="624cb-201">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="624cb-202">Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** ルーティング ポリシー] に移動し、[追加] を  >  クリック **します**。</span><span class="sxs-lookup"><span data-stu-id="624cb-202">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="624cb-203">名前 **として米国のみ** と入力し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="624cb-203">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="624cb-204">**[PSTN 使用状況レコード] で\*\*\*\*、[PSTN** 使用状況の追加] をクリックし、[米国とカナダ] PSTN 使用状況レコードを選択し、[適用] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="624cb-204">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="624cb-205">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="624cb-205">Click **Save**.</span></span>

<span data-ttu-id="624cb-206">詳細については、「音声ルーティング [ポリシーを管理する」を参照してください](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="624cb-206">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="624cb-207">手順 4: Spencer Low という名前のユーザーに音声ルーティング ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="624cb-207">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="624cb-208">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="624cb-208">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="624cb-209">**[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="624cb-209">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="624cb-210">[ **音声ルーティング ポリシー] で**、[米国のみ] ポリシーを選択し、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="624cb-210">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="624cb-211">詳細については、「音声ルーティング [ポリシーを管理する」を参照してください](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="624cb-211">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="624cb-212">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="624cb-212">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="624cb-213">手順 1: "米国とカナダ" の PSTN 使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="624cb-213">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="624cb-214">Skype for Business Online のリモート PowerShell セッションで、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="624cb-214">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="624cb-215">次を入力して、使用状況が作成されたと確認します。</span><span class="sxs-lookup"><span data-stu-id="624cb-215">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="624cb-216">切り捨て可能な名前のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="624cb-216">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="624cb-217">次の例は、PowerShell コマンドを実行して完全な名前を `(Get-CSOnlinePSTNUsage).usage` 表示した結果を示しています (切り捨てはされません)。</span><span class="sxs-lookup"><span data-stu-id="624cb-217">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` PowerShell command to display full names (not truncated):</span></span>

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="624cb-218">手順 2: 3 つの音声ルートを作成する (Redmond 1、Redmond 2、Other +1)</span><span class="sxs-lookup"><span data-stu-id="624cb-218">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="624cb-219">"Redmond 1" ルートを作成するには、Skype for Business Online の PowerShell セッションで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="624cb-219">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="624cb-220">次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-220">Which returns:</span></span>

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

<span data-ttu-id="624cb-221">レドモンド 2 ルートを作成するには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="624cb-221">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="624cb-222">その他の +1 ルートを作成するには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="624cb-222">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="624cb-223">NumberPattern 属性の正規表現が有効な式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="624cb-223">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="624cb-224">この Web サイトを使用してテストできます。 [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="624cb-224">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="624cb-225">場合によっては、すべての通話を同じ SBC にルーティングする必要があります。use -NumberPattern ".\*"</span><span class="sxs-lookup"><span data-stu-id="624cb-225">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="624cb-226">すべての通話を同じ SBC にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="624cb-226">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="624cb-227">次に示すオプションを使用して PowerShell コマンドを実行して、ルートが正 `Get-CSOnlineVoiceRoute` しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="624cb-227">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="624cb-228">次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-228">Which should return:</span></span>

```console
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
```

<span data-ttu-id="624cb-229">この例では、ルート "Other +1" に優先度 4 が自動的に割り当て済みでした。</span><span class="sxs-lookup"><span data-stu-id="624cb-229">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="624cb-230">手順 3: "米国のみ" という名前の音声ルーティング ポリシーを作成し、"米国とカナダ" の PSTN 使用状況をポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="624cb-230">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="624cb-231">Skype for Business Online の PowerShell セッションで、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="624cb-231">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="624cb-232">結果は次の例に示されています。</span><span class="sxs-lookup"><span data-stu-id="624cb-232">The result is shown in this example:</span></span>

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="624cb-233">手順 4: Spencer Low という名前のユーザーに音声ルーティング ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="624cb-233">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="624cb-234">Skype for Business Online の PowerShell セッションで、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="624cb-234">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="624cb-235">次のコマンドを入力して、ポリシーの割り当てを検証します。</span><span class="sxs-lookup"><span data-stu-id="624cb-235">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="624cb-236">コマンドは次を返します。</span><span class="sxs-lookup"><span data-stu-id="624cb-236">The command returns the following:</span></span>

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="624cb-237">例 2: 複数の PSTN 使用状況を使用した音声ルーティング</span><span class="sxs-lookup"><span data-stu-id="624cb-237">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="624cb-238">使用例 1 で作成した音声ルーティング ポリシーでは、Microsoft 通話プランライセンスもユーザーに割り当てられていない限り、米国とカナダの電話番号への通話のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="624cb-238">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="624cb-239">次の例では、"制限なし" 音声ルーティング ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="624cb-239">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="624cb-240">このポリシーは、例 1 で作成した "米国とカナダ" の PSTN 使用状況と、新しい "国際" PSTN 使用状況を再利用します。</span><span class="sxs-lookup"><span data-stu-id="624cb-240">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="624cb-241">このポリシーは、その他のすべての呼び出しを SPC および sbc2.contoso.biz にルーティング sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="624cb-241">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="624cb-242">次に示す例では、Us Only policy をユーザー Spencer Low に割り当て、No Restrictions ポリシーをユーザーの John Woods に割り当てると、ルーティングは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="624cb-242">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="624cb-243">スペンサー 低 – 米国のみポリシー。</span><span class="sxs-lookup"><span data-stu-id="624cb-243">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="624cb-244">通話は米国およびカナダの番号にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-244">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="624cb-245">レドモンド番号範囲に呼び出す場合は、特定のセットの SPC を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="624cb-245">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="624cb-246">米国以外の番号は、通話プランライセンスがユーザーに割り当てられていない限り、ルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="624cb-246">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="624cb-247">John Woods – 国際ポリシー。</span><span class="sxs-lookup"><span data-stu-id="624cb-247">John Woods – International policy.</span></span>  <span data-ttu-id="624cb-248">通話は任意の番号に対して許可されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-248">Calls are allowed to any number.</span></span> <span data-ttu-id="624cb-249">レドモンド番号範囲に呼び出す場合は、特定のセットの SPC を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="624cb-249">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="624cb-250">米国以外の番号は、電話番号と電話番号を sbc2.contoso.biz 使用 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="624cb-250">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![ユーザー Spencer Low に割り当てられている音声ルーティング ポリシーを示す](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="624cb-252">その他のすべての通話では、ユーザーが両方のライセンス (Microsoft 電話システムと Microsoft 通話プラン) を持つ場合は、自動ルートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-252">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="624cb-253">管理者が作成したオンライン音声ルートの番号パターンに一致する番号が見当たらない場合、通話は Microsoft 通話プランを使用してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-253">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="624cb-254">ユーザーが Microsoft Phone System のみを使用している場合、照合ルールが利用できないので通話は削除されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-254">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![ユーザー John Woods に割り当てられた音声ルーティング ポリシーを示す](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="624cb-256">次の表では、ルーティング ポリシー "制限なし" の使用指定と音声ルートの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="624cb-256">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

| <span data-ttu-id="624cb-257">PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="624cb-257">PSTN usage</span></span> | <span data-ttu-id="624cb-258">音声ルート</span><span class="sxs-lookup"><span data-stu-id="624cb-258">Voice route</span></span> | <span data-ttu-id="624cb-259">番号のパターン</span><span class="sxs-lookup"><span data-stu-id="624cb-259">Number pattern</span></span> | <span data-ttu-id="624cb-260">[Priority]</span><span class="sxs-lookup"><span data-stu-id="624cb-260">Priority</span></span> | <span data-ttu-id="624cb-261">SBC</span><span class="sxs-lookup"><span data-stu-id="624cb-261">SBC</span></span> | <span data-ttu-id="624cb-262">説明</span><span class="sxs-lookup"><span data-stu-id="624cb-262">Description</span></span> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="624cb-263">米国とカナダ</span><span class="sxs-lookup"><span data-stu-id="624cb-263">US and Canada</span></span>|<span data-ttu-id="624cb-264">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="624cb-264">"Redmond 1"</span></span>|<span data-ttu-id="624cb-265">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="624cb-265">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="624cb-266">1</span><span class="sxs-lookup"><span data-stu-id="624cb-266">1</span></span>|<span data-ttu-id="624cb-267">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-267">sbc1.contoso.biz</span></span><br/><span data-ttu-id="624cb-268">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-268">sbc2.contoso.biz</span></span>|<span data-ttu-id="624cb-269">呼び出し先番号のアクティブなルート +1 425 XXX XX または +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="624cb-269">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="624cb-270">米国とカナダ</span><span class="sxs-lookup"><span data-stu-id="624cb-270">US and Canada</span></span>|<span data-ttu-id="624cb-271">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="624cb-271">"Redmond 2"</span></span>|<span data-ttu-id="624cb-272">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="624cb-272">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="624cb-273">2</span><span class="sxs-lookup"><span data-stu-id="624cb-273">2</span></span>|<span data-ttu-id="624cb-274">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-274">sbc3.contoso.biz</span></span><br/><span data-ttu-id="624cb-275">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-275">sbc4.contoso.biz</span></span>|<span data-ttu-id="624cb-276">呼び出し先番号のバックアップ ルート +1 425 XXX XX または +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="624cb-276">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="624cb-277">米国とカナダ</span><span class="sxs-lookup"><span data-stu-id="624cb-277">US and Canada</span></span>|<span data-ttu-id="624cb-278">"Other +1"</span><span class="sxs-lookup"><span data-stu-id="624cb-278">"Other +1"</span></span>|<span data-ttu-id="624cb-279">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="624cb-279">^\\+1(\d{10})$</span></span>|<span data-ttu-id="624cb-280">3</span><span class="sxs-lookup"><span data-stu-id="624cb-280">3</span></span>|<span data-ttu-id="624cb-281">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-281">sbc5.contoso.biz</span></span><br/><span data-ttu-id="624cb-282">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-282">sbc6.contoso.biz</span></span>|<span data-ttu-id="624cb-283">呼び出し先番号のルート +1 XXX XXX XX XX (+1 425 XXX XX XX または +1 206 XXX XX XX を除く)</span><span class="sxs-lookup"><span data-stu-id="624cb-283">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="624cb-284">International</span><span class="sxs-lookup"><span data-stu-id="624cb-284">International</span></span>|<span data-ttu-id="624cb-285">International</span><span class="sxs-lookup"><span data-stu-id="624cb-285">International</span></span>|<span data-ttu-id="624cb-286">\d+</span><span class="sxs-lookup"><span data-stu-id="624cb-286">\d+</span></span>|<span data-ttu-id="624cb-287">4</span><span class="sxs-lookup"><span data-stu-id="624cb-287">4</span></span>|<span data-ttu-id="624cb-288">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-288">sbc2.contoso.biz</span></span><br/><span data-ttu-id="624cb-289">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="624cb-289">sbc5.contoso.biz</span></span>|<span data-ttu-id="624cb-290">任意の番号パターンのルーティング</span><span class="sxs-lookup"><span data-stu-id="624cb-290">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="624cb-291">音声ルーティング ポリシーでの PSTN の使用順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="624cb-291">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="624cb-292">使用法は順番に適用され、最初の使用法で一致が見つかった場合、他の使用法は評価されません。</span><span class="sxs-lookup"><span data-stu-id="624cb-292">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="624cb-293">"国際" PSTN の使用は、"米国とカナダ" の PSTN 使用状況の後に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="624cb-293">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="624cb-294">PSTN 使用状況の順序を変更するには、コマンドを実行 `Set-CSOnlineVoiceRoutingPolicy` します。</span><span class="sxs-lookup"><span data-stu-id="624cb-294">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="624cb-295">たとえば、最初の "米国とカナダ" から 2 番目の "国際" から逆順の実行に順序を変更するには、</span><span class="sxs-lookup"><span data-stu-id="624cb-295">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="624cb-296">"その他 +1" および "国際" の音声ルートの優先度が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="624cb-296">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="624cb-297">"Redmond 1" や "Redmond 2" よりも優先度が低い限り、優先順位は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="624cb-297">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="624cb-298">例 2: 構成手順</span><span class="sxs-lookup"><span data-stu-id="624cb-298">Example 2: Configuration steps</span></span>

<span data-ttu-id="624cb-299">次の例は、次の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="624cb-299">The following example shows how to:</span></span>

1. <span data-ttu-id="624cb-300">国際と呼ばれる新しい PSTN 使用状況を作成します。</span><span class="sxs-lookup"><span data-stu-id="624cb-300">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="624cb-301">「国際」という名前の新しい音声ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="624cb-301">Create a new voice route called International.</span></span>
3. <span data-ttu-id="624cb-302">[制限なし] という音声ルーティング ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="624cb-302">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="624cb-303">ユーザー John Woods にポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="624cb-303">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="624cb-304">Microsoft Teams 管理センターまたは [PowerShell](#admincenterexample2) を使用して [、これらの](#powershellexample2) 手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="624cb-304">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="624cb-305">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="624cb-305">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="624cb-306">手順 1: "国際" PSTN 使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="624cb-306">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="624cb-307">Microsoft Teams 管理センターの左側のナビゲーションで、[音声ダイレクト ルーティング] に移動し、右上隅の [PSTN 使用状況レコードの管理] を  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="624cb-307">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="624cb-308">[追加 **] をクリックし**、「国際」 **と入力** して、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="624cb-308">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="624cb-309">手順 2: "国際" 音声ルートを作成する</span><span class="sxs-lookup"><span data-stu-id="624cb-309">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="624cb-310">Microsoft Teams 管理センターの左側のナビゲーションで、[音声ダイレクト ルーティング] に移動し、[音声ルート  >  **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="624cb-310">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="624cb-311">[ **追加]** をクリックし、名前に「国際」と入力して、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="624cb-311">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="624cb-312">優先度を 4 に設定し、ダイヤルされた番号パターンを \d+ に設定します。</span><span class="sxs-lookup"><span data-stu-id="624cb-312">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="624cb-313">[ **登録済み SPC] (オプション)** で **、[SBC** の追加] をクリックし、sbc2.contoso.biz と sbc5.contoso.biz し、[適用] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="624cb-313">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="624cb-314">**[PSTN 使用状況レコード] (省略可能)** で **、[PSTN** 使用状況の追加] をクリックし、[国際] PSTN 使用状況レコードを選び、[適用] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="624cb-314">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="624cb-315">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="624cb-315">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="624cb-316">手順 3: "制限なし" という名前の音声ルーティング ポリシーを作成し、"米国とカナダ" と "国際" の PSTN 使用状況をポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="624cb-316">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="624cb-317">PSTN の使用法 "米国とカナダ" は、この音声ルーティング ポリシーで再利用され、番号 "+1 425 XXX XX XX" および "+1 206 XXX XX XX" をローカルまたはオンプレミスの通話として呼び出す特殊な処理を保持します。</span><span class="sxs-lookup"><span data-stu-id="624cb-317">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="624cb-318">Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** ルーティング ポリシー] に移動し、[追加] を  >  クリック **します**。</span><span class="sxs-lookup"><span data-stu-id="624cb-318">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="624cb-319">名前 **に「制限なし** 」と入力し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="624cb-319">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="624cb-320">**[PSTN 使用状況レコード] で\*\*\*\*、[PSTN** 使用状況の追加] をクリックし、[米国とカナダ] PSTN 使用状況レコードを選択し、[国際] PSTN 使用状況レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="624cb-320">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="624cb-321">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="624cb-321">Click **Apply**.</span></span>

    <span data-ttu-id="624cb-322">PSTN の使用状況の順序をメモします。</span><span class="sxs-lookup"><span data-stu-id="624cb-322">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="624cb-323">この例のように使用法を構成して番号 "+1 425 XXX XX XX" に対して行われた呼び出しの場合、呼び出しは "US and Canada" の使用で設定されたルートに従い、特殊なルーティング ロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-323">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="624cb-324">つまり、通話は最初に sbc1.contoso.biz sbc2.contoso.biz を使用してルーティングされ、sbc3.contoso.biz と sbc4.contoso.biz として使用されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-324">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="624cb-325">"国際" PSTN 使用状況が "米国およびカナダ" より前の場合、ルーティング ロジックの一部として +1 425 XXX XX XX が sbc2.contoso.biz および sbc5.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-325">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="624cb-326">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="624cb-326">Click **Save**.</span></span>

<span data-ttu-id="624cb-327">詳細については、「音声ルーティング [ポリシーを管理する」を参照してください](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="624cb-327">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="624cb-328">手順 4: John Woods という名前のユーザーに音声ルーティング ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="624cb-328">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="624cb-329">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="624cb-329">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="624cb-330">**[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="624cb-330">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="624cb-331">音声 **ルーティング ポリシーで、[** 制限なし] ポリシーを選択し、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="624cb-331">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="624cb-332">その結果、John Woods の通話に適用される音声ポリシーは無制限であり、米国、カナダ、国際通話で利用できる通話ルーティングのロジックに従います。</span><span class="sxs-lookup"><span data-stu-id="624cb-332">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="624cb-333">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="624cb-333">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="624cb-334">手順 1: "国際" PSTN 使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="624cb-334">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="624cb-335">Skype for Business Online のリモート PowerShell セッションで、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="624cb-335">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="624cb-336">手順 2: "国際" という名前の新しい音声ルートを作成する</span><span class="sxs-lookup"><span data-stu-id="624cb-336">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

<span data-ttu-id="624cb-337">次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-337">Which returns:</span></span>

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="624cb-338">手順 3: "制限なし" という名前の音声ルーティング ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="624cb-338">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="624cb-339">PSTN の使用法 "Redmond 1" と "Redmond" は、この音声ルーティング ポリシーで再利用され、"+1 425 XXX XX XX" および "+1 206 XXX XX XX" をローカルまたはオンプレミスの通話として呼び出す特殊な処理を保持します。</span><span class="sxs-lookup"><span data-stu-id="624cb-339">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="624cb-340">PSTN の使用状況の順序をメモします。</span><span class="sxs-lookup"><span data-stu-id="624cb-340">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="624cb-341">次の例のように使用法を構成して番号 "+1 425 XXX XX XX" に対して行われた呼び出しの場合、呼び出しは "米国とカナダ" で設定されたルートに従い、特殊なルーティング ロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-341">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="624cb-342">つまり、通話は最初に sbc1.contoso.biz sbc2.contoso.biz を使用してルーティングされ、sbc3.contoso.biz と sbc4.contoso.biz として使用されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-342">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="624cb-343">"国際" PSTN 使用状況が "米国およびカナダ" より前の場合、ルーティング ロジックの一部として +1 425 XXX XX XX が sbc2.contoso.biz および sbc5.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="624cb-343">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="624cb-344">コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="624cb-344">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="624cb-345">次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-345">Which returns:</span></span>

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="624cb-346">手順 4: John Woods という名前のユーザーに音声ルーティング ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="624cb-346">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="624cb-347">次に、コマンドを使用して課題を確認します。</span><span class="sxs-lookup"><span data-stu-id="624cb-347">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="624cb-348">次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="624cb-348">Which returns:</span></span>

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

<span data-ttu-id="624cb-349">その結果、John Woods の通話に適用される音声ポリシーは無制限であり、米国、カナダ、国際通話で利用できる通話ルーティングのロジックに従います。</span><span class="sxs-lookup"><span data-stu-id="624cb-349">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="624cb-350">関連項目</span><span class="sxs-lookup"><span data-stu-id="624cb-350">See also</span></span>

[<span data-ttu-id="624cb-351">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="624cb-351">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="624cb-352">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="624cb-352">Configure Direct Routing</span></span>](direct-routing-configure.md)
