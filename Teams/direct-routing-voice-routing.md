---
title: 直接ルーティング用のボイスルーティングを構成する
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
description: Microsoft Phone システムのダイレクトルーティングでボイスルーティングを構成する方法について説明します。
ms.openlocfilehash: 0611684c79d92572ade41f2545096fe1d9bb4dd2
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159014"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="b87a0-103">直接ルーティング用のボイスルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="b87a0-104">この記事では、電話システムのダイレクトルーティングのボイスルーティングを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="b87a0-105">これは、次の手順の手順3で、直接ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="b87a0-106">手順1</span><span class="sxs-lookup"><span data-stu-id="b87a0-106">Step 1.</span></span> [<span data-ttu-id="b87a0-107">SBC と Microsoft 電話システムを接続して接続を検証する</span><span class="sxs-lookup"><span data-stu-id="b87a0-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="b87a0-108">手順2</span><span class="sxs-lookup"><span data-stu-id="b87a0-108">Step 2.</span></span> [<span data-ttu-id="b87a0-109">ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="b87a0-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="b87a0-110">**手順3音声ルーティングを構成する**(この記事)</span><span class="sxs-lookup"><span data-stu-id="b87a0-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="b87a0-111">手順4。</span><span class="sxs-lookup"><span data-stu-id="b87a0-111">Step 4.</span></span> [<span data-ttu-id="b87a0-112">数値を別の形式に変換する</span><span class="sxs-lookup"><span data-stu-id="b87a0-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="b87a0-113">直接ルーティングを設定するために必要なすべての手順については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b87a0-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="b87a0-114">音声ルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="b87a0-114">Voice routing overview</span></span>

<span data-ttu-id="b87a0-115">Microsoft 電話システムには、次のことに基づいて特定のセッションボーダーコントローラー (SBC) に通話を送信できるルーティングメカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="b87a0-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="b87a0-116">呼び出した番号のパターン</span><span class="sxs-lookup"><span data-stu-id="b87a0-116">The called number pattern</span></span> 
- <span data-ttu-id="b87a0-117">呼び出された番号パターンと、通話を発信した特定のユーザー</span><span class="sxs-lookup"><span data-stu-id="b87a0-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="b87a0-118">SBCs は、アクティブなバックアップとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="b87a0-119">Active として構成されている SBC を特定の通話ルートで利用できない場合、通話はバックアップ SBC にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="b87a0-120">音声ルーティングは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="b87a0-121">**ボイスルーティングポリシー** – PSTN の使用を可能にするコンテナーであり、ユーザーまたは複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="b87a0-122">**Pstn 使用状況**–ボイスルートと pstn 使用のコンテナー。さまざまな音声ルーティングポリシーで共有できます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="b87a0-123">**ボイスルーティング**–番号パターンとオンライン PSTN ゲートウェイのセットによって、通話番号がパターンと一致する通話に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="b87a0-124">**オンライン PSTN ゲートウェイ**-sbc を介して通話を発信するときに適用される構成 (たとえば、P-指定された ID (pai) や優先コーデックなど) を保存する sbc へのポインターです。音声ルートに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="b87a0-125">例 1: 1 つの PSTN 利用状況での音声ルーティング</span><span class="sxs-lookup"><span data-stu-id="b87a0-125">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="b87a0-126">次の図は、通話フローにおけるボイスルーティングポリシーの2つの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="b87a0-127">**通話フロー 1 (左側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx を呼び出した場合、通話は SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="b87a0-128">Sbc1.contoso.biz と sbc2.contoso.biz のどちらも使用できない場合は、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="b87a0-129">**通話フロー 2 (右側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx への通話を発信した場合、通話はまず SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="b87a0-130">どちらの SBC も使用できない場合は、優先度の低いルートが試されます (sbc3.contoso.biz と sbc4.contoso.biz)。</span><span class="sxs-lookup"><span data-stu-id="b87a0-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="b87a0-131">利用可能な SBCs がない場合は、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-131">If none of the SBCs are available, the call is dropped.</span></span> 

![ボイスルーティングポリシーの例を示しています](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="b87a0-133">どちらの例でも、ボイスルートには優先順位が割り当てられていますが、ルートの SBCs はランダムな順序で試行されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b87a0-134">ユーザーに Microsoft の通話プランライセンスも付与されていない限り、そのパターンに一致する番号 (1 425 XXX XX XX または + 1 206 XXX XX xx) は、この構成の例では削除されません。</span><span class="sxs-lookup"><span data-stu-id="b87a0-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="b87a0-135">ユーザーが通話プランライセンスを持っている場合は、Microsoft 通話プランのポリシーに従って、通話が自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="b87a0-136">Microsoft 通話プランは、Microsoft 通話プランライセンスを持つすべてのユーザーに対して、最後のルートとして自動的に適用され、追加の通話ルーティング構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b87a0-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="b87a0-137">次の図に示す例では、すべての米国とカナダの電話番号に通話を送信するための音声ルートが追加されています (通話は、番号パターン + 1 XXX XXX XX XX) に移動します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![ボイスルーティングポリシーを3番目のルートとともに示しています](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="b87a0-139">その他の通話:</span><span class="sxs-lookup"><span data-stu-id="b87a0-139">For all other calls:</span></span>

- <span data-ttu-id="b87a0-140">ユーザーが両方のライセンス (Microsoft 電話システムと Microsoft 通話プラン) を持っている場合は、自動ルートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="b87a0-141">管理者が作成したオンラインボイスルートの番号パターンと一致しない場合、その通話は Microsoft の通話プランを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="b87a0-142">ユーザーが Microsoft 電話システムしか使用していない場合は、一致するルールがないため、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b87a0-143">ルート "Other + 1" の優先度の値は、パターン + 1 XXX XXX XX XX と一致するルートが1つだけであるため、この例では問題ありません。</span><span class="sxs-lookup"><span data-stu-id="b87a0-143">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="b87a0-144">ユーザーが + 1 324 567 89 89 に通話を発信し、sbc5.contoso.biz と sbc6.contoso.biz の両方を利用できない場合は、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="b87a0-145">次の表は、3つのボイスルートを使った構成をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="b87a0-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="b87a0-146">この例では、3つのルートすべてが同じ PSTN 使用量 "US とカナダ" に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-146">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="b87a0-147">すべてのルートは、"US とカナダ" の PSTN 使用と関連付けられており、PSTN の使用は "米国限定" ボイスルーティングポリシーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-147">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="b87a0-148">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="b87a0-148">**PSTN usage**</span></span>|<span data-ttu-id="b87a0-149">**ボイスルート**</span><span class="sxs-lookup"><span data-stu-id="b87a0-149">**Voice route**</span></span>|<span data-ttu-id="b87a0-150">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="b87a0-150">**Number pattern**</span></span>|<span data-ttu-id="b87a0-151">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="b87a0-151">**Priority**</span></span>|<span data-ttu-id="b87a0-152">**SBC**</span><span class="sxs-lookup"><span data-stu-id="b87a0-152">**SBC**</span></span>|<span data-ttu-id="b87a0-153">**説明**</span><span class="sxs-lookup"><span data-stu-id="b87a0-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b87a0-154">米国およびカナダ</span><span class="sxs-lookup"><span data-stu-id="b87a0-154">US and Canada</span></span>|<span data-ttu-id="b87a0-155">"レドモンド 1"</span><span class="sxs-lookup"><span data-stu-id="b87a0-155">"Redmond 1"</span></span>|<span data-ttu-id="b87a0-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="b87a0-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b87a0-157">1</span><span class="sxs-lookup"><span data-stu-id="b87a0-157">1</span></span>|<span data-ttu-id="b87a0-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="b87a0-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="b87a0-160">呼び出された数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート</span><span class="sxs-lookup"><span data-stu-id="b87a0-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b87a0-161">米国およびカナダ</span><span class="sxs-lookup"><span data-stu-id="b87a0-161">US and Canada</span></span>|<span data-ttu-id="b87a0-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="b87a0-162">"Redmond 2"</span></span>|<span data-ttu-id="b87a0-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="b87a0-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b87a0-164">2</span><span class="sxs-lookup"><span data-stu-id="b87a0-164">2</span></span>|<span data-ttu-id="b87a0-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="b87a0-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="b87a0-167">呼び出した数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のバックアップルート</span><span class="sxs-lookup"><span data-stu-id="b87a0-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b87a0-168">米国およびカナダ</span><span class="sxs-lookup"><span data-stu-id="b87a0-168">US and Canada</span></span>|<span data-ttu-id="b87a0-169">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="b87a0-169">"Other +1"</span></span>|<span data-ttu-id="b87a0-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="b87a0-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="b87a0-171">3</span><span class="sxs-lookup"><span data-stu-id="b87a0-171">3</span></span>|<span data-ttu-id="b87a0-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="b87a0-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="b87a0-174">"発信番号" のルート + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)</span><span class="sxs-lookup"><span data-stu-id="b87a0-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="b87a0-175">使用例 1: 構成手順</span><span class="sxs-lookup"><span data-stu-id="b87a0-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="b87a0-176">次の例は、次の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-176">The following example shows how to:</span></span>

1. <span data-ttu-id="b87a0-177">単一の PSTN 使用を作成します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-177">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="b87a0-178">3つのボイスルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-178">Configure three voice routes.</span></span>
3. <span data-ttu-id="b87a0-179">ボイスルーティングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-179">Create a voice routing policy.</span></span>
4. <span data-ttu-id="b87a0-180">Spencer Low という名前のユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-180">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="b87a0-181">[Microsoft Teams 管理センター](#admincenterexample1)または[PowerShell](#powershellexample1)を使用して、次の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-181">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b87a0-182">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="b87a0-182">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="b87a0-183">手順 1: "US とカナダ" の PSTN 使用量を作成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-183">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="b87a0-184">Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > の**直接ルーティング**] に移動し、右上隅の [ **PSTN 使用状況レコードの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-184">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="b87a0-185">[**追加**] をクリックし、「**米国」と「カナダ**」と入力して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-185">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="b87a0-186">手順 2: 3 つのボイスルーティングルート (Redmond 1、Redmond 2、その他 + 1) を作成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-186">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="b87a0-187">次の手順では、ボイスルートの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-187">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="b87a0-188">次の手順を使用して、前の表で説明した設定を使用して、この例で Redmond 1、Redmond 2、その他の + 1 という名前の3つのボイスルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-188">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="b87a0-189">Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > の**直接ルーティング**] に移動し、[**ボイス**ルーティング] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-189">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="b87a0-190">[**追加**] をクリックして、ボイスルートの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-190">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="b87a0-191">優先度を設定し、ダイヤル番号のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-191">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="b87a0-192">音声ルートを使用して SBC を登録するには、[ **sbcs 登録 (オプション)**] で [ **sbcs の追加**] をクリックし、登録する sbcs を選択して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-192">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="b87a0-193">PSTN 使用状況レコードを追加するには、[ **pstn 使用状況レコード] (オプション)** の [ **pstn 使用量の追加**] をクリックし、追加する pstn レコードを選択して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-193">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="b87a0-194">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-194">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="b87a0-195">手順 3: "US Only" という名前の音声ルーティングポリシーを作成し、ポリシーに "US" と "カナダ" の PSTN 使用を追加する</span><span class="sxs-lookup"><span data-stu-id="b87a0-195">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="b87a0-196">Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > **音声ルーティングポリシー**] に移動し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="b87a0-197">名前として「 **US** 」と入力して、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-197">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="b87a0-198">[ **Pstn 使用状況レコード**] で、[ **pstn 使用量の追加**] をクリックし、"米国およびカナダ" の pstn 利用状況レコードを選択して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-198">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="b87a0-199">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-199">Click **Save**.</span></span>

<span data-ttu-id="b87a0-200">詳細については、「[ボイスルーティングポリシーを管理](manage-voice-routing-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b87a0-200">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="b87a0-201">手順 4: Spencer Low という名前のユーザーに音声ルーティングポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b87a0-201">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="b87a0-202">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-202">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b87a0-203">**[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-203">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="b87a0-204">[**音声ルーティングポリシー**] で、[US のみ] ポリシーを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-204">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="b87a0-205">詳細については、「[ボイスルーティングポリシーを管理](manage-voice-routing-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b87a0-205">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b87a0-206">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="b87a0-206">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="b87a0-207">手順 1: "US とカナダ" の PSTN 使用量を作成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-207">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="b87a0-208">Skype for Business Online のリモート PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-208">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="b87a0-209">次のように入力して使用が作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-209">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="b87a0-210">これは、切り捨てられる可能性がある名前のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-210">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="b87a0-211">次の例は、 `(Get-CSOnlinePSTNUsage).usage` Powershell コマンドを実行して完全な名前を表示した場合の結果を示しています (トランケートされません)。</span><span class="sxs-lookup"><span data-stu-id="b87a0-211">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="b87a0-212">手順 2: 3 つのボイスルーティングルート (Redmond 1、Redmond 2、その他 + 1) を作成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-212">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="b87a0-213">"Redmond 1" ルートを作成するには、Skype for Business Online の PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-213">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b87a0-214">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b87a0-214">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="b87a0-215">レドモンド2ルートを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-215">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b87a0-216">他の + 1 ルートを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-216">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="b87a0-217">数値 Pattern 属性の正規表現が有効な式であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-217">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="b87a0-218">次の web サイトを使ってテストできます。[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="b87a0-218">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="b87a0-219">場合によっては、すべての通話を同じ SBC にルーティングする必要があります。use-Number パターン ". \*"</span><span class="sxs-lookup"><span data-stu-id="b87a0-219">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="b87a0-220">すべての通話を同じ SBC にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-220">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="b87a0-221">次の`Get-CSOnlineVoiceRoute`ようなオプションを使用して PowerShell コマンドを実行して、ルートが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-221">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="b87a0-222">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b87a0-222">Which should return:</span></span>
<pre>
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
</pre>

<span data-ttu-id="b87a0-223">この例では、ルート "Other + 1" は優先度4を自動的に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-223">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="b87a0-224">手順 3: "US Only" という名前の音声ルーティングポリシーを作成し、ポリシーに "US" と "カナダ" の PSTN 使用を追加する</span><span class="sxs-lookup"><span data-stu-id="b87a0-224">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="b87a0-225">Skype for Business Online の PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-225">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b87a0-226">結果は、次の例のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-226">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="b87a0-227">手順 4: Spencer Low という名前のユーザーに音声ルーティングポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b87a0-227">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="b87a0-228">Skype for Business Online の PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-228">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="b87a0-229">このコマンドを入力して、ポリシーの割り当てを確認します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-229">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="b87a0-230">このコマンドは次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-230">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="b87a0-231">例 2: 複数の PSTN 使用によるボイスルーティング</span><span class="sxs-lookup"><span data-stu-id="b87a0-231">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="b87a0-232">例1で作成した音声ルーティングポリシーでは、Microsoft 通話プランライセンスもユーザーに割り当てられていない限り、米国とカナダでの電話番号への通話のみが許可されています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-232">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="b87a0-233">次の例では、"制限なし" のボイスルーティングポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-233">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="b87a0-234">このポリシーは、例1で作成された "US and カナダ" PSTN 使用量と、新しい "国際" PSTN の使用状況を再利用します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-234">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="b87a0-235">このポリシーは、SBCs sbc2.contoso.biz と sbc5.contoso.biz に対するその他のすべての通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-235">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="b87a0-236">次に示す例では、ユーザー Spencer 低に米国限定ポリシーを割り当て、ユーザー John 森には制限なしのポリシーを割り当てて、ルーティングが次のように行われるようにします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-236">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="b87a0-237">Spencer 安値– US のみのポリシー。</span><span class="sxs-lookup"><span data-stu-id="b87a0-237">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="b87a0-238">通話は米国とカナダの番号のみに許可されています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-238">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="b87a0-239">Redmond の番号範囲に発信する場合は、特定の SBCs セットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87a0-239">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="b87a0-240">米国以外の番号は、通話プランライセンスがユーザーに割り当てられていない限り、ルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="b87a0-240">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="b87a0-241">John 森–国際ポリシー。</span><span class="sxs-lookup"><span data-stu-id="b87a0-241">John Woods – International policy.</span></span>  <span data-ttu-id="b87a0-242">通話は任意の番号に許可されています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-242">Calls are allowed to any number.</span></span> <span data-ttu-id="b87a0-243">Redmond の番号範囲に発信する場合は、特定の SBCs セットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87a0-243">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="b87a0-244">米国以外の番号は、sbc2.contoso.biz と sbc5.contoso.biz を使ってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-244">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![ユーザー Spencer Low に割り当てられている音声ルーティングポリシーを表示します](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="b87a0-246">その他のすべての通話では、ユーザーに両方のライセンス (Microsoft Phone システムと Microsoft 通話プラン) がある場合、自動ルートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-246">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="b87a0-247">管理者が作成したオンラインボイスルートの番号パターンと一致しない場合は、Microsoft 通話プランを使って通話がルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-247">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="b87a0-248">ユーザーが Microsoft 電話システムのみを使用している場合は、一致するルールがないため、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-248">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![ユーザー John 森に割り当てられているボイスルーティングポリシーを示しています](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="b87a0-250">次の表は、ルーティングポリシーの "制限なし" を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-250">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="b87a0-251">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="b87a0-251">**PSTN usage**</span></span>|<span data-ttu-id="b87a0-252">**ボイスルート**</span><span class="sxs-lookup"><span data-stu-id="b87a0-252">**Voice route**</span></span>|<span data-ttu-id="b87a0-253">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="b87a0-253">**Number pattern**</span></span>|<span data-ttu-id="b87a0-254">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="b87a0-254">**Priority**</span></span>|<span data-ttu-id="b87a0-255">**SBC**</span><span class="sxs-lookup"><span data-stu-id="b87a0-255">**SBC**</span></span>|<span data-ttu-id="b87a0-256">**説明**</span><span class="sxs-lookup"><span data-stu-id="b87a0-256">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b87a0-257">米国およびカナダ</span><span class="sxs-lookup"><span data-stu-id="b87a0-257">US and Canada</span></span>|<span data-ttu-id="b87a0-258">"レドモンド 1"</span><span class="sxs-lookup"><span data-stu-id="b87a0-258">"Redmond 1"</span></span>|<span data-ttu-id="b87a0-259">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="b87a0-259">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b87a0-260">1</span><span class="sxs-lookup"><span data-stu-id="b87a0-260">1</span></span>|<span data-ttu-id="b87a0-261">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-261">sbc1.contoso.biz</span></span><br/><span data-ttu-id="b87a0-262">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-262">sbc2.contoso.biz</span></span>|<span data-ttu-id="b87a0-263">呼び出し先の番号 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート</span><span class="sxs-lookup"><span data-stu-id="b87a0-263">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b87a0-264">米国およびカナダ</span><span class="sxs-lookup"><span data-stu-id="b87a0-264">US and Canada</span></span>|<span data-ttu-id="b87a0-265">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="b87a0-265">"Redmond 2"</span></span>|<span data-ttu-id="b87a0-266">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="b87a0-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b87a0-267">2</span><span class="sxs-lookup"><span data-stu-id="b87a0-267">2</span></span>|<span data-ttu-id="b87a0-268">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-268">sbc3.contoso.biz</span></span><br/><span data-ttu-id="b87a0-269">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-269">sbc4.contoso.biz</span></span>|<span data-ttu-id="b87a0-270">呼び出し先の番号のバックアップルート + 1 425 XXX XX XX または + 1 206 XXX XX xx</span><span class="sxs-lookup"><span data-stu-id="b87a0-270">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b87a0-271">米国およびカナダ</span><span class="sxs-lookup"><span data-stu-id="b87a0-271">US and Canada</span></span>|<span data-ttu-id="b87a0-272">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="b87a0-272">"Other +1"</span></span>|<span data-ttu-id="b87a0-273">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="b87a0-273">^\\+1(\d{10})$</span></span>|<span data-ttu-id="b87a0-274">3</span><span class="sxs-lookup"><span data-stu-id="b87a0-274">3</span></span>|<span data-ttu-id="b87a0-275">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-275">sbc5.contoso.biz</span></span><br/><span data-ttu-id="b87a0-276">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-276">sbc6.contoso.biz</span></span>|<span data-ttu-id="b87a0-277">呼び出し先の番号のルーティング + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)</span><span class="sxs-lookup"><span data-stu-id="b87a0-277">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="b87a0-278">International</span><span class="sxs-lookup"><span data-stu-id="b87a0-278">International</span></span>|<span data-ttu-id="b87a0-279">International</span><span class="sxs-lookup"><span data-stu-id="b87a0-279">International</span></span>|<span data-ttu-id="b87a0-280">\d +</span><span class="sxs-lookup"><span data-stu-id="b87a0-280">\d+</span></span>|<span data-ttu-id="b87a0-281">4</span><span class="sxs-lookup"><span data-stu-id="b87a0-281">4</span></span>|<span data-ttu-id="b87a0-282">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-282">sbc2.contoso.biz</span></span><br/><span data-ttu-id="b87a0-283">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b87a0-283">sbc5.contoso.biz</span></span>|<span data-ttu-id="b87a0-284">任意の番号パターンのルート</span><span class="sxs-lookup"><span data-stu-id="b87a0-284">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="b87a0-285">ボイスルーティングポリシーの PSTN 使用の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="b87a0-285">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="b87a0-286">使用状況は順番に適用され、最初の使用で一致が見つかった場合は、他の使用法は評価されません。</span><span class="sxs-lookup"><span data-stu-id="b87a0-286">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="b87a0-287">"国際" PSTN 使用量は、"米国およびカナダ" PSTN の使用の後に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87a0-287">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="b87a0-288">PSTN の使用順序を変更するには、 `Set-CSOnlineVoiceRoutingPolicy`コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-288">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="b87a0-289">たとえば、"US" と "カナダ" の順序を "第 1" と "海外" の順に変更するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-289">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="b87a0-290">"Other + 1" と "海外" のボイスルートの優先度は、自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-290">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="b87a0-291">"Redmond 1" と "レドモンド 2" よりも優先順位が低い場合は、問題ありません。</span><span class="sxs-lookup"><span data-stu-id="b87a0-291">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="b87a0-292">例 2: 構成手順</span><span class="sxs-lookup"><span data-stu-id="b87a0-292">Example 2: Configuration steps</span></span>

<span data-ttu-id="b87a0-293">次の例は、次の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-293">The following example shows how to:</span></span>

1. <span data-ttu-id="b87a0-294">「国際」と呼ばれる新しい PSTN 使用法を作成します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-294">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="b87a0-295">国際通話と呼ばれる新しいボイスルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-295">Create a new voice route called International.</span></span>
3. <span data-ttu-id="b87a0-296">制限なしと呼ばれる音声ルーティングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-296">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="b87a0-297">ユーザー John 森にポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-297">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="b87a0-298">[Microsoft Teams 管理センター](#admincenterexample2)または[PowerShell](#powershellexample2)を使用して、次の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-298">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b87a0-299">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="b87a0-299">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="b87a0-300">手順 1: "国際" PSTN 使用量を作成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-300">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="b87a0-301">Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > の**直接ルーティング**] に移動し、右上隅の [ **PSTN 使用状況レコードの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-301">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="b87a0-302">[**追加**] をクリックし、[**国際**] と入力して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-302">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="b87a0-303">手順 2: "国際" ボイスルーティングを作成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-303">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="b87a0-304">Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > の**直接ルーティング**] に移動し、[**ボイス**ルーティング] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-304">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="b87a0-305">[**追加**] をクリックし、名前として「国際」と入力して、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-305">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="b87a0-306">優先度を4に設定して、ダイヤルされた番号のパターンを \d + に設定します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-306">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="b87a0-307">[ **Sbcs 登録 (オプション)**] で [ **sbcs の追加**] をクリックし、[sbc2.contoso.biz] と [sbc5.contoso.biz] を選択して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-307">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="b87a0-308">[ **Pstn 使用状況レコード] (オプション)** で、[ **pstn 使用量の追加**] をクリックし、"国際" pstn 使用状況レコードを選択して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-308">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="b87a0-309">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-309">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="b87a0-310">手順 3: "制限なし" という名前の音声ルーティングポリシーを作成し、"US and カナダ" と "国際" PSTN の使用をポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="b87a0-310">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="b87a0-311">PSTN の使用状況 "US とカナダ" は、電話番号 "+ 1 425 XXX XX XX" と "+ 1 206 XXX XX XX" への通話に対する特別な処理を、ローカルまたはオンプレミスの通話として維持するために、この音声ルーティングポリシーで再利用されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-311">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="b87a0-312">Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > **音声ルーティングポリシー**] に移動し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-312">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="b87a0-313">名前として「**制限なし**」と入力し、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-313">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="b87a0-314">[ **Pstn 使用状況レコード**] の [ **pstn 使用量の追加**] をクリックし、"米国およびカナダ" の pstn 利用状況レコードを選択し、[国際] pstn 使用状況レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-314">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="b87a0-315">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-315">Click **Apply**.</span></span>

    <span data-ttu-id="b87a0-316">PSTN の使用順序に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b87a0-316">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="b87a0-317">この例で使用されているように、通話が "+ 1 425 XXX XX XX" に設定されている場合、通話は "US とカナダ" の使用に設定され、特殊なルーティングロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-317">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="b87a0-318">つまり、sbc1.contoso.biz と sbc2.contoso.biz を使用して通話がルーティングされ、次にバックアップルートとして sbc3.contoso.biz と sbc4.contoso.biz が送信されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-318">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="b87a0-319">"国際" という PSTN の使用が "US とカナダ" よりも前にある場合は、ルーティングロジックの一部として、+ 1 425 XXX XX XX への通話が sbc2.contoso.biz と sbc5.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-319">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="b87a0-320">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-320">Click **Save**.</span></span>

<span data-ttu-id="b87a0-321">詳細については、「[ボイスルーティングポリシーを管理](manage-voice-routing-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b87a0-321">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="b87a0-322">手順 4: John 森という名前のユーザーにボイスルーティングポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b87a0-322">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="b87a0-323">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-323">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b87a0-324">**[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-324">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="b87a0-325">[**音声ルーティングポリシー**] で、[制限なし] ポリシーを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b87a0-325">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="b87a0-326">結果として、John 森の通話に適用されるボイスポリシーは無制限であり、米国、カナダ、国際通話で利用可能な通話ルーティングのロジックに従っていることになります。</span><span class="sxs-lookup"><span data-stu-id="b87a0-326">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b87a0-327">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="b87a0-327">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="b87a0-328">手順 1: "国際" PSTN 使用量を作成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-328">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="b87a0-329">Skype for Business Online のリモート PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-329">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="b87a0-330">手順 2: "インターナショナル" という名前の新しいボイスルートを作成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-330">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="b87a0-331">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b87a0-331">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="b87a0-332">手順 3: "制限なし" という名前の音声ルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-332">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="b87a0-333">PSTN の利用状況 "レドモンド 1" と "Redmond" は、電話番号 "+ 1 425 XXX XX XX" と "+ 1 206 XXX XX XX" への通話に対する特別な処理を、ローカルまたはオンプレミスの通話として維持するために、この音声ルーティングポリシーで再利用されています。</span><span class="sxs-lookup"><span data-stu-id="b87a0-333">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="b87a0-334">PSTN の使用順序に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b87a0-334">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="b87a0-335">次の例のように、利用状況を設定して、"+ 1 425 XXX XX XX" という数値を指定した場合は、通話は "US およびカナダ" の使用に設定され、特殊なルーティングロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-335">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="b87a0-336">つまり、sbc1.contoso.biz と sbc2.contoso.biz を使用して通話がルーティングされ、次にバックアップルートとして sbc3.contoso.biz と sbc4.contoso.biz が送信されます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-336">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="b87a0-337">"国際" という PSTN の使用が "US とカナダ" よりも前にある場合は、ルーティングロジックの一部として、+ 1 425 XXX XX XX への通話が sbc2.contoso.biz と sbc5.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b87a0-337">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="b87a0-338">コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-338">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="b87a0-339">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b87a0-339">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="b87a0-340">手順 4: John 森という名前のユーザーに音声ルーティングポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b87a0-340">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="b87a0-341">次に、コマンドを使用して課題を確認します。</span><span class="sxs-lookup"><span data-stu-id="b87a0-341">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="b87a0-342">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b87a0-342">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="b87a0-343">結果として、John 森の通話に適用されるボイスポリシーは無制限であり、米国、カナダ、国際通話で利用可能な通話ルーティングのロジックに従うことになります。</span><span class="sxs-lookup"><span data-stu-id="b87a0-343">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="b87a0-344">関連項目</span><span class="sxs-lookup"><span data-stu-id="b87a0-344">See also</span></span>

[<span data-ttu-id="b87a0-345">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="b87a0-345">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="b87a0-346">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="b87a0-346">Configure Direct Routing</span></span>](direct-routing-configure.md)
