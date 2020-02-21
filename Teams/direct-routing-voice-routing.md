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
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157989"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="e210b-103">直接ルーティング用のボイスルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="e210b-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="e210b-104">この記事では、電話システムのダイレクトルーティングのボイスルーティングを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e210b-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="e210b-105">これは、次の手順の手順3で、直接ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="e210b-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="e210b-106">手順1</span><span class="sxs-lookup"><span data-stu-id="e210b-106">Step 1.</span></span> [<span data-ttu-id="e210b-107">SBC と Microsoft 電話システムを接続して接続を検証する</span><span class="sxs-lookup"><span data-stu-id="e210b-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="e210b-108">手順2</span><span class="sxs-lookup"><span data-stu-id="e210b-108">Step 2.</span></span> [<span data-ttu-id="e210b-109">ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="e210b-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)    
- <span data-ttu-id="e210b-110">**手順3音声ルーティングを構成する**(この記事)</span><span class="sxs-lookup"><span data-stu-id="e210b-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="e210b-111">手順4。</span><span class="sxs-lookup"><span data-stu-id="e210b-111">Step 4.</span></span> [<span data-ttu-id="e210b-112">数値を別の形式に変換する</span><span class="sxs-lookup"><span data-stu-id="e210b-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="e210b-113">直接ルーティングを設定するために必要なすべての手順については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e210b-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="e210b-114">音声ルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="e210b-114">Voice routing overview</span></span>

<span data-ttu-id="e210b-115">Microsoft 電話システムには、次のことに基づいて特定のセッションボーダーコントローラー (SBC) に通話を送信できるルーティングメカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="e210b-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="e210b-116">呼び出した番号のパターン</span><span class="sxs-lookup"><span data-stu-id="e210b-116">The called number pattern</span></span> 
- <span data-ttu-id="e210b-117">呼び出された番号パターンと、通話を発信した特定のユーザー</span><span class="sxs-lookup"><span data-stu-id="e210b-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="e210b-118">SBCs は、アクティブなバックアップとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="e210b-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="e210b-119">Active として構成されている SBC を特定の通話ルートで利用できない場合、通話はバックアップ SBC にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e210b-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="e210b-120">音声ルーティングは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="e210b-121">**ボイスルーティングポリシー** – PSTN の使用を可能にするコンテナーであり、ユーザーまたは複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e210b-121">**Voice routing policy** – A container for PSTN Usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="e210b-122">**Pstn 使用状況**–ボイスルートと pstn 使用のコンテナー。さまざまな音声ルーティングポリシーで共有できます。</span><span class="sxs-lookup"><span data-stu-id="e210b-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="e210b-123">**ボイスルーティング**–番号パターンとオンライン PSTN ゲートウェイのセットによって、通話番号がパターンと一致する通話に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-123">**Voice Routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="e210b-124">**オンライン PSTN ゲートウェイ**-sbc を介して通話を発信するときに適用される構成 (たとえば、P-指定された ID (pai) や優先コーデックなど) を保存する sbc へのポインターです。音声ルートに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e210b-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="e210b-125">例 1: 1 つの PSTN 利用状況での音声ルーティング</span><span class="sxs-lookup"><span data-stu-id="e210b-125">Example 1: Voice routing with one PSTN Usage</span></span>

<span data-ttu-id="e210b-126">次の図は、通話フローにおけるボイスルーティングポリシーの2つの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="e210b-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="e210b-127">**通話フロー 1 (左側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx を呼び出した場合、通話は SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e210b-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="e210b-128">Sbc1.contoso.biz と sbc2.contoso.biz のどちらも使用できない場合は、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="e210b-129">**通話フロー 2 (右側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx への通話を発信した場合、通話はまず SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e210b-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="e210b-130">どちらの SBC も使用できない場合は、優先度の低いルートが試されます (sbc3.contoso.biz と sbc4.contoso.biz)。</span><span class="sxs-lookup"><span data-stu-id="e210b-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="e210b-131">利用可能な SBCs がない場合は、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-131">If none of the SBCs are available, the call is dropped.</span></span> 

![ボイスルーティングポリシーの例を示しています](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="e210b-133">どちらの例でも、ボイスルートには優先順位が割り当てられていますが、ルートの SBCs はランダムな順序で試行されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e210b-134">ユーザーに Microsoft の通話プランライセンスも付与されていない限り、そのパターンに一致する番号 (1 425 XXX XX XX または + 1 206 XXX XX xx) は、この構成の例では削除されません。</span><span class="sxs-lookup"><span data-stu-id="e210b-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="e210b-135">ユーザーが通話プランライセンスを持っている場合は、Microsoft 通話プランのポリシーに従って、通話が自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e210b-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="e210b-136">Microsoft 通話プランは、Microsoft 通話プランライセンスを持つすべてのユーザーに対して、最後のルートとして自動的に適用され、追加の通話ルーティング構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e210b-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="e210b-137">次の図に示す例では、すべての米国とカナダの電話番号に通話を送信するための音声ルートが追加されています (通話は、番号パターン + 1 XXX XXX XX XX) に移動します。</span><span class="sxs-lookup"><span data-stu-id="e210b-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![ボイスルーティングポリシーを3番目のルートとともに示しています](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="e210b-139">その他の通話:</span><span class="sxs-lookup"><span data-stu-id="e210b-139">For all other calls:</span></span>

- <span data-ttu-id="e210b-140">ユーザーが両方のライセンス (Microsoft 電話システムと Microsoft 通話プラン) を持っている場合は、自動ルートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="e210b-141">管理者が作成したオンラインボイスルートの番号パターンと一致しない場合、その通話は Microsoft の通話プランを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e210b-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="e210b-142">ユーザーが Microsoft 電話システムしか使用していない場合は、一致するルールがないため、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e210b-143">ルート "Other + 1" の優先度の値は、パターン + 1 XXX XXX XX XX と一致するルートが1つだけであるため、この例では問題ありません。</span><span class="sxs-lookup"><span data-stu-id="e210b-143">The Priority value for route "Other +1" doesn’t matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="e210b-144">ユーザーが + 1 324 567 89 89 に通話を発信し、sbc5.contoso.biz と sbc6.contoso.biz の両方を利用できない場合は、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="e210b-145">次の表は、3つのボイスルートを使った構成をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="e210b-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="e210b-146">この例では、3つのルートすべてが同じ PSTN 使用状況 "US とカナダ" に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e210b-146">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>  <span data-ttu-id="e210b-147">すべてのルートは、PSTN の使用状況 "US およびカナダ" と関連付けられ、PSTN の使用状況はボイスルーティングポリシー "US のみ" に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="e210b-147">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> 

|<span data-ttu-id="e210b-148">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="e210b-148">**PSTN usage**</span></span>|<span data-ttu-id="e210b-149">**ボイスルート**</span><span class="sxs-lookup"><span data-stu-id="e210b-149">**Voice route**</span></span>|<span data-ttu-id="e210b-150">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="e210b-150">**Number pattern**</span></span>|<span data-ttu-id="e210b-151">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="e210b-151">**Priority**</span></span>|<span data-ttu-id="e210b-152">**SBC**</span><span class="sxs-lookup"><span data-stu-id="e210b-152">**SBC**</span></span>|<span data-ttu-id="e210b-153">**説明**</span><span class="sxs-lookup"><span data-stu-id="e210b-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e210b-154">米国限定</span><span class="sxs-lookup"><span data-stu-id="e210b-154">US only</span></span>|<span data-ttu-id="e210b-155">"レドモンド 1"</span><span class="sxs-lookup"><span data-stu-id="e210b-155">"Redmond 1"</span></span>|<span data-ttu-id="e210b-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e210b-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e210b-157">1</span><span class="sxs-lookup"><span data-stu-id="e210b-157">1</span></span>|<span data-ttu-id="e210b-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="e210b-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="e210b-160">呼び出された数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート</span><span class="sxs-lookup"><span data-stu-id="e210b-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e210b-161">米国限定</span><span class="sxs-lookup"><span data-stu-id="e210b-161">US only</span></span>|<span data-ttu-id="e210b-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="e210b-162">"Redmond 2"</span></span>|<span data-ttu-id="e210b-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e210b-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e210b-164">両面</span><span class="sxs-lookup"><span data-stu-id="e210b-164">2</span></span>|<span data-ttu-id="e210b-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="e210b-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="e210b-167">呼び出した数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のバックアップルート</span><span class="sxs-lookup"><span data-stu-id="e210b-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e210b-168">米国限定</span><span class="sxs-lookup"><span data-stu-id="e210b-168">US only</span></span>|<span data-ttu-id="e210b-169">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="e210b-169">"Other +1"</span></span>|<span data-ttu-id="e210b-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="e210b-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="e210b-171">3</span><span class="sxs-lookup"><span data-stu-id="e210b-171">3</span></span>|<span data-ttu-id="e210b-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="e210b-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="e210b-174">"発信番号" のルート + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)</span><span class="sxs-lookup"><span data-stu-id="e210b-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||


### <a name="example-1-configuration-steps"></a><span data-ttu-id="e210b-175">使用例 1: 構成手順</span><span class="sxs-lookup"><span data-stu-id="e210b-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="e210b-176">次の例は、次の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e210b-176">The following example shows how to:</span></span>

- <span data-ttu-id="e210b-177">単一の PSTN 使用を作成する</span><span class="sxs-lookup"><span data-stu-id="e210b-177">Create a single PSTN Usage</span></span> 
- <span data-ttu-id="e210b-178">3つのボイスルートを構成する</span><span class="sxs-lookup"><span data-stu-id="e210b-178">Configure three voice routes</span></span>
- <span data-ttu-id="e210b-179">ボイスルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e210b-179">Create a voice routing policy</span></span>
- <span data-ttu-id="e210b-180">ユーザー Spencer Low にポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e210b-180">Assign the policy to user Spencer Low</span></span>

<span data-ttu-id="e210b-181">**手順 1:** PSTN 使用量 "US およびカナダ" を作成する</span><span class="sxs-lookup"><span data-stu-id="e210b-181">**Step 1:** Create the PSTN Usage "US and Canada"</span></span>

<span data-ttu-id="e210b-182">Skype for Business リモート PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e210b-182">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="e210b-183">次のように入力して使用が作成されたことを検証します。</span><span class="sxs-lookup"><span data-stu-id="e210b-183">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="e210b-184">これは、切り捨てられる可能性がある名前のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="e210b-184">Which returns a list of names that may be truncated:</span></span>
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="e210b-185">次の例は、PowerShell コマンド`(Get-CSOnlinePSTNUsage).usage`を実行して完全な名前を表示した場合の結果を示しています (トランケートされません)。</span><span class="sxs-lookup"><span data-stu-id="e210b-185">The example below shows the result of  running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated):</span></span>

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

<span data-ttu-id="e210b-186">**手順 2:** Skype for Business Online の PowerShell セッションで、前の表に示されているように、Redmond 1、レドモンド2、その他の + 1 という3つのルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e210b-186">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as shown in the previous table</span></span>

<span data-ttu-id="e210b-187">"Redmond 1" ルートを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e210b-187">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="e210b-188">戻り値:</span><span class="sxs-lookup"><span data-stu-id="e210b-188">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="e210b-189">レドモンド2ルートを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e210b-189">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="e210b-190">他の + 1 ルートを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e210b-190">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="e210b-191">数値 Pattern 属性の正規表現が有効な式であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e210b-191">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="e210b-192">次の web サイトを使ってテストできます。[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="e210b-192">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="e210b-193">場合によっては、すべての通話を同じ SBC にルーティングする必要があります。use-Number パターン ". \*"</span><span class="sxs-lookup"><span data-stu-id="e210b-193">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="e210b-194">すべての通話を同じ SBC にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="e210b-194">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="e210b-195">次の`Get-CSOnlineVoiceRoute`ようなオプションを使用して PowerShell コマンドを実行して、ルートが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e210b-195">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="e210b-196">戻り値:</span><span class="sxs-lookup"><span data-stu-id="e210b-196">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="e210b-197">この例では、ルート "Other + 1" は優先度4を自動的に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="e210b-197">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="e210b-198">**手順 3:** ボイスルーティングポリシーを「US 専用」にして、「US とカナダ」という PSTN 使用のポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="e210b-198">**Step 3:** Create a voice routing policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="e210b-199">Skype for Business Online の PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e210b-199">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="e210b-200">結果は、次の例のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-200">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="e210b-201">**手順 4:** PowerShell を使用して、音声ルーティングポリシーをユーザー Spencer Low に付与します。</span><span class="sxs-lookup"><span data-stu-id="e210b-201">**Step 4:** By using PowerShell, grant the voice routing policy to the user Spencer Low:</span></span>

<span data-ttu-id="e210b-202">Skype for Business Online の PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e210b-202">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="e210b-203">このコマンドを入力して、ポリシーの割り当てを確認します。</span><span class="sxs-lookup"><span data-stu-id="e210b-203">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="e210b-204">このコマンドは次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="e210b-204">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="e210b-205">例 2: 複数の PSTN 使用によるボイスルーティング</span><span class="sxs-lookup"><span data-stu-id="e210b-205">Example 2: Voice routing with multiple PSTN Usages</span></span>

<span data-ttu-id="e210b-206">例1で作成した音声ルーティングポリシーでは、Microsoft 通話プランライセンスもユーザーに割り当てられていない限り、米国とカナダでの電話番号への通話のみが許可されています。</span><span class="sxs-lookup"><span data-stu-id="e210b-206">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="e210b-207">次の例では、"制限なし" という音声ルーティングポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e210b-207">In the example that follows, you can create the voice routing policy "No Restrictions."</span></span> <span data-ttu-id="e210b-208">このポリシーでは、例1で作成した PSTN の使用状況 "US and カナダ" と、新しい PSTN の使用状況 "海外" が再利用されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-208">The policy reuses the PSTN Usage "US and Canada" created in Example 1, as well as the new PSTN Usage "International."</span></span>  <span data-ttu-id="e210b-209">このポリシーは、SBCs sbc2.contoso.biz と sbc5.contoso.biz に対するその他のすべての通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="e210b-209">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> 

<span data-ttu-id="e210b-210">次に示す例では、ユーザー Spencer 低に米国限定ポリシーを割り当て、ユーザー John 森には制限なしのポリシーを割り当てて、ルーティングが次のように行われるようにします。</span><span class="sxs-lookup"><span data-stu-id="e210b-210">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="e210b-211">Spencer 安値– US のみのポリシー。</span><span class="sxs-lookup"><span data-stu-id="e210b-211">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="e210b-212">通話は米国とカナダの番号のみに許可されています。</span><span class="sxs-lookup"><span data-stu-id="e210b-212">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="e210b-213">Redmond の番号範囲に発信する場合は、特定の SBCs セットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e210b-213">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="e210b-214">米国以外の番号は、通話プランライセンスがユーザーに割り当てられていない限り、ルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="e210b-214">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="e210b-215">John 森–国際ポリシー。</span><span class="sxs-lookup"><span data-stu-id="e210b-215">John Woods – International policy.</span></span>  <span data-ttu-id="e210b-216">通話は任意の番号に許可されています。</span><span class="sxs-lookup"><span data-stu-id="e210b-216">Calls are allowed to any number.</span></span> <span data-ttu-id="e210b-217">Redmond の番号範囲に発信する場合は、特定の SBCs セットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e210b-217">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="e210b-218">米国以外の番号は、sbc2.contoso.biz と sbc5.contoso.biz を使ってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e210b-218">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![ユーザー Spencer Low に割り当てられている音声ルーティングポリシーを表示します](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="e210b-220">その他のすべての通話では、ユーザーに両方のライセンス (Microsoft Phone システムと Microsoft 通話プラン) がある場合、自動ルートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-220">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="e210b-221">管理者が作成したオンラインボイスルートの番号パターンと一致しない場合は、Microsoft 通話プランを使って通話がルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e210b-221">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="e210b-222">ユーザーが Microsoft 電話システムのみを使用している場合は、一致するルールがないため、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-222">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![ユーザー John 森に割り当てられているボイスルーティングポリシーを示しています](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="e210b-224">次の表は、ルーティングポリシーの "制限なし" を使用しています。</span><span class="sxs-lookup"><span data-stu-id="e210b-224">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="e210b-225">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="e210b-225">**PSTN usage**</span></span>|<span data-ttu-id="e210b-226">**ボイスルート**</span><span class="sxs-lookup"><span data-stu-id="e210b-226">**Voice route**</span></span>|<span data-ttu-id="e210b-227">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="e210b-227">**Number pattern**</span></span>|<span data-ttu-id="e210b-228">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="e210b-228">**Priority**</span></span>|<span data-ttu-id="e210b-229">**SBC**</span><span class="sxs-lookup"><span data-stu-id="e210b-229">**SBC**</span></span>|<span data-ttu-id="e210b-230">**説明**</span><span class="sxs-lookup"><span data-stu-id="e210b-230">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e210b-231">米国限定</span><span class="sxs-lookup"><span data-stu-id="e210b-231">US Only</span></span>|<span data-ttu-id="e210b-232">"レドモンド 1"</span><span class="sxs-lookup"><span data-stu-id="e210b-232">"Redmond 1"</span></span>|<span data-ttu-id="e210b-233">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e210b-233">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e210b-234">1</span><span class="sxs-lookup"><span data-stu-id="e210b-234">1</span></span>|<span data-ttu-id="e210b-235">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-235">sbc1.contoso.biz</span></span><br/><span data-ttu-id="e210b-236">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-236">sbc2.contoso.biz</span></span>|<span data-ttu-id="e210b-237">呼び出し先の番号 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート</span><span class="sxs-lookup"><span data-stu-id="e210b-237">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e210b-238">米国限定</span><span class="sxs-lookup"><span data-stu-id="e210b-238">US Only</span></span>|<span data-ttu-id="e210b-239">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="e210b-239">"Redmond 2"</span></span>|<span data-ttu-id="e210b-240">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="e210b-240">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e210b-241">両面</span><span class="sxs-lookup"><span data-stu-id="e210b-241">2</span></span>|<span data-ttu-id="e210b-242">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-242">sbc3.contoso.biz</span></span><br/><span data-ttu-id="e210b-243">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-243">sbc4.contoso.biz</span></span>|<span data-ttu-id="e210b-244">呼び出し先の番号のバックアップルート + 1 425 XXX XX XX または + 1 206 XXX XX xx</span><span class="sxs-lookup"><span data-stu-id="e210b-244">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e210b-245">米国限定</span><span class="sxs-lookup"><span data-stu-id="e210b-245">US Only</span></span>|<span data-ttu-id="e210b-246">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="e210b-246">"Other +1"</span></span>|<span data-ttu-id="e210b-247">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="e210b-247">^\\+1(\d{10})$</span></span>|<span data-ttu-id="e210b-248">3</span><span class="sxs-lookup"><span data-stu-id="e210b-248">3</span></span>|<span data-ttu-id="e210b-249">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-249">sbc5.contoso.biz</span></span><br/><span data-ttu-id="e210b-250">sbc6> contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-250">sbc6>.contoso.biz</span></span>|<span data-ttu-id="e210b-251">呼び出し先の番号のルーティング + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)</span><span class="sxs-lookup"><span data-stu-id="e210b-251">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="e210b-252">International</span><span class="sxs-lookup"><span data-stu-id="e210b-252">International</span></span>|<span data-ttu-id="e210b-253">International</span><span class="sxs-lookup"><span data-stu-id="e210b-253">International</span></span>|<span data-ttu-id="e210b-254">\d +</span><span class="sxs-lookup"><span data-stu-id="e210b-254">\d+</span></span>|<span data-ttu-id="e210b-255">4</span><span class="sxs-lookup"><span data-stu-id="e210b-255">4</span></span>|<span data-ttu-id="e210b-256">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-256">sbc2.contoso.biz</span></span><br/><span data-ttu-id="e210b-257">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e210b-257">sbc5.contoso.biz</span></span>|<span data-ttu-id="e210b-258">任意の番号パターンのルート</span><span class="sxs-lookup"><span data-stu-id="e210b-258">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="e210b-259">ボイスルーティングポリシーの PSTN 使用の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="e210b-259">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="e210b-260">使用状況は順番に適用され、最初の使用で一致が見つかった場合は、他の使用法は評価されません。</span><span class="sxs-lookup"><span data-stu-id="e210b-260">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="e210b-261">PSTN の使用は、PSTN の使用の後に「米国専用」として設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e210b-261">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="e210b-262">PSTN の使用順序を変更するには、 `Set-CSOnlineVoiceRoutingPolicy`コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e210b-262">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="e210b-263">たとえば、"US" と "カナダ" の順序を "第 1" と "海外" の順に変更するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e210b-263">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="e210b-264">"Other + 1" と "海外" のボイスルートの優先度は、自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e210b-264">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="e210b-265">"Redmond 1" と "レドモンド 2" よりも優先順位が低い場合は、問題ありません。</span><span class="sxs-lookup"><span data-stu-id="e210b-265">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>


### <a name="example-2-configuration-steps"></a><span data-ttu-id="e210b-266">例 2: 構成手順</span><span class="sxs-lookup"><span data-stu-id="e210b-266">Example 2: Configuration steps</span></span>

<span data-ttu-id="e210b-267">次の例は、次の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e210b-267">The following example shows how to:</span></span>

- <span data-ttu-id="e210b-268">国際通話と呼ばれる新しい PSTN の利用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="e210b-268">Create a new PSTN Usage called International</span></span>
- <span data-ttu-id="e210b-269">国際電話と呼ばれる新しいボイスルートを作成する</span><span class="sxs-lookup"><span data-stu-id="e210b-269">Create a new voice route called International</span></span>
- <span data-ttu-id="e210b-270">制限なしと呼ばれる音声ルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e210b-270">Create a voice routing policy called No Restrictions</span></span>
- <span data-ttu-id="e210b-271">ユーザー John 森にポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e210b-271">Assign the policy to user John Woods</span></span>


<span data-ttu-id="e210b-272">**手順 1**: PSTN 使用量「国際」を作成します。</span><span class="sxs-lookup"><span data-stu-id="e210b-272">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="e210b-273">Skype for Business Online のリモート PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e210b-273">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="e210b-274">**手順 2**: 新しいボイスルート "国際" を作成します。</span><span class="sxs-lookup"><span data-stu-id="e210b-274">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="e210b-275">戻り値:</span><span class="sxs-lookup"><span data-stu-id="e210b-275">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="e210b-276">**手順 3**: 音声ルーティングポリシーを作成する "制限なし"。</span><span class="sxs-lookup"><span data-stu-id="e210b-276">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="e210b-277">PSTN の利用状況 "レドモンド 1" と "Redmond" は、電話番号 "+ 1 425 XXX XX XX" と "+ 1 206 XXX XX XX" への通話に対する特別な処理を、ローカルまたはオンプレミスの通話として維持するために、この音声ルーティングポリシーで再利用されています。</span><span class="sxs-lookup"><span data-stu-id="e210b-277">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="e210b-278">PSTN の使用順序に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e210b-278">Take note of the order of PSTN Usages:</span></span>

  <span data-ttu-id="e210b-279">a.</span><span class="sxs-lookup"><span data-stu-id="e210b-279">a.</span></span> <span data-ttu-id="e210b-280">次の例のように、利用状況を設定して、"+ 1 425 XXX XX XX" という数値を指定した場合は、通話は "US およびカナダ" の使用に設定され、特殊なルーティングロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-280">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="e210b-281">つまり、sbc1.contoso.biz と sbc2.contoso.biz を使用して通話がルーティングされ、次にバックアップルートとして sbc3.contoso.biz と sbc4.contoso.biz が送信されます。</span><span class="sxs-lookup"><span data-stu-id="e210b-281">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  <span data-ttu-id="e210b-282">b.</span><span class="sxs-lookup"><span data-stu-id="e210b-282">b.</span></span> <span data-ttu-id="e210b-283">"国際" という PSTN の使用が "US とカナダ" よりも前にある場合は、ルーティングロジックの一部として、+ 1 425 XXX XX XX への通話が sbc2.contoso.biz と sbc5.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e210b-283">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="e210b-284">コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e210b-284">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="e210b-285">戻り値:</span><span class="sxs-lookup"><span data-stu-id="e210b-285">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

<span data-ttu-id="e210b-286">**手順 4**: 次のコマンドを使用して、ボイスルーティングポリシーをユーザーの "John 森" に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e210b-286">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="e210b-287">次に、コマンドを使用して課題を確認します。</span><span class="sxs-lookup"><span data-stu-id="e210b-287">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="e210b-288">戻り値:</span><span class="sxs-lookup"><span data-stu-id="e210b-288">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="e210b-289">結果として、John 森の通話に適用されるボイスポリシーは無制限であり、米国、カナダ、国際通話で利用可能な通話ルーティングのロジックに従うことになります。</span><span class="sxs-lookup"><span data-stu-id="e210b-289">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>



## <a name="see-also"></a><span data-ttu-id="e210b-290">関連項目</span><span class="sxs-lookup"><span data-stu-id="e210b-290">See also</span></span>

[<span data-ttu-id="e210b-291">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="e210b-291">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="e210b-292">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="e210b-292">Configure Direct Routing</span></span>](direct-routing-configure.md)
