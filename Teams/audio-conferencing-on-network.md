---
title: 電話会議のネットワーク上会議
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 以下では、電話会議のネットワーク上での、オープンなプレビュー機能について説明します。
ms.openlocfilehash: 1ae61034ef083c89e14c67cef0effa1c105de758
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031863"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="759c4-103">電話会議のネットワーク上の会議のプレビューを開く</span><span class="sxs-lookup"><span data-stu-id="759c4-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="759c4-104">ネットワーク上の会議のオープンプレビューは、すべてのユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="759c4-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="759c4-105">ネットワーク上の会議では、組織は、直接ルーティングを介して、着信/発信の電話会議通話を Microsoft ダイヤルイン番号に送信できます。</span><span class="sxs-lookup"><span data-stu-id="759c4-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="759c4-106">この機能は、電話会議のサポートをサードパーティのダイヤルイン番号に拡張するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="759c4-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="759c4-107">ネットワーク上の会議は、サードパーティのダイヤルイン電話番号を使用して着信通話を電話会議サービスにルーティングするために使用されている場合はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="759c4-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="759c4-108">この記事では、組織のネットワーク会議を有効にするために必要な前提条件と構成手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="759c4-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="759c4-109">ネットワーク上の会議は、インドのテレフォニー機器と共に展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="759c4-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="759c4-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="759c4-110">Prerequisites</span></span>

<span data-ttu-id="759c4-111">ネットワーク上の会議を構成する前に、組織が次の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="759c4-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="759c4-112">電話会議について、有効になっている、または有効にする組織内のすべてのユーザーが、すべての会議に対して Teams を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="759c4-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="759c4-113">ネットワーク会議経由での着信通話と発信電話会議のルーティングは、Teams 会議でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="759c4-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="759c4-114">ネットワーク上の会議を使用するすべてのユーザーに電話会議のライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="759c4-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="759c4-115">電話会議サービスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="759c4-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="759c4-116">詳細については、「 [Microsoft Teams の電話会議をセットアップする](set-up-audio-conferencing-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="759c4-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="759c4-117">ダイレクトルーティング用にセッション境界コントローラー (SBC) を設定します。</span><span class="sxs-lookup"><span data-stu-id="759c4-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="759c4-118">詳細については、「 [ダイレクトルーティングを計画](direct-routing-plan.md) し、 [直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="759c4-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="759c4-119">電話会議の目的にのみ直接ルーティングを設定する場合は、「手順 1: お使いのネットワーク会議用に SBC を接続する」を完了してください。</span><span class="sxs-lookup"><span data-stu-id="759c4-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="759c4-120">直接ルーティングによって Microsoft 電話会議へのダイヤルイン通話のルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="759c4-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="759c4-121">オンプレミスのユーザーによって行われたダイヤルイン通話を、直接ルーティングを通じて電話会議サービスにルーティングするには、SBCs とプライベート支店の Exchange (Pbx) に対して適切なルーティングルールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="759c4-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="759c4-122">ダイレクトルーティングトランクを通じて、組織の電話会議ブリッジの任意のサービス番号への通話をルーティングするように、サイトのテレフォニー機器を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="759c4-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="759c4-123">[ **会議-> 会議ブリッジ** ] または [Skype For Business Online PowerShell コマンドレット get-csonlinedialinconferencingbridge を使用して、Teams 管理センターでサービス番号を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="759c4-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="759c4-124">詳細については、 [Microsoft Teams の電話会議番号](see-a-list-of-audio-conferencing-numbers-in-teams.md)の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="759c4-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="759c4-125">この機能は、1分あたりの有料電話会議ライセンスをお持ちのユーザーは利用できません。</span><span class="sxs-lookup"><span data-stu-id="759c4-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="759c4-126">直接ルーティングを使用して、Teams 会議のダイヤルアウト通話のルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="759c4-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="759c4-127">チーム会議のダイヤルアウト通話は、組織内の会議内から、PSTN 番号への通話 (コールイン通話、通話など) に対して開始され、新しい参加者を会議に追加します。</span><span class="sxs-lookup"><span data-stu-id="759c4-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="759c4-128">ネットワーク上のユーザーへの直接ルーティングを通じてチーム会議のダイヤルアウトルーティングを有効にするには、"OnlineAudioConferencingRoutingPolicy" と呼ばれる電話会議ルーティングポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="759c4-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="759c4-129">OnlineAudioConferencingRoutingPolicy ポリシーは、ダイレクトルーティングによる1:1 の PSTN 通話の CsOnlineVoiceRoutingPolicy と同じです。</span><span class="sxs-lookup"><span data-stu-id="759c4-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="759c4-130">OnlineAudioConferencingRoutingPolicy ポリシーは、次のコマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="759c4-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="759c4-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="759c4-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="759c4-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="759c4-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="759c4-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="759c4-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="759c4-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="759c4-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="759c4-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="759c4-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="759c4-136">直接ルーティングのルーティングの詳細については、「 [直接ルーティング用にボイスルーティングを構成する](direct-routing-voice-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="759c4-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="759c4-137">直接ルーティングによって会議のダイヤルアウト通話のルーティングを有効にするには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="759c4-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="759c4-138">電話会議ルーティングポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="759c4-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="759c4-139">組織のテレフォニー機器でルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="759c4-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="759c4-140">省略ダイヤルプランを設定する</span><span class="sxs-lookup"><span data-stu-id="759c4-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="759c4-141">Teams 会議からのダイヤルアウト通話は、会議ブリッジの既定のサービス番号から提供されます。</span><span class="sxs-lookup"><span data-stu-id="759c4-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="759c4-142">電話会議ブリッジの既定のサービス番号の詳細については、「 [電話会議ブリッジの電話番号を変更](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="759c4-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="759c4-143">電話会議ルーティングポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="759c4-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="759c4-144">電話会議ルーティングポリシー OnlineAudioConferencingRoutingPolicy は、ダイレクトルーティング trunks にルーティングされる会議のダイヤルアウト通話を決定します。</span><span class="sxs-lookup"><span data-stu-id="759c4-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="759c4-145">CsOnlineVoiceRoutingPolicy ポリシーに精通している場合、このポリシーはよく似た方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="759c4-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="759c4-146">電話会議のルーティングポリシーをセットアップするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="759c4-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="759c4-147">PSTN の使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="759c4-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="759c4-148">ボイスルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="759c4-148">Configure voice routes</span></span>
3.  <span data-ttu-id="759c4-149">電話会議のボイスルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="759c4-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="759c4-150">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="759c4-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="759c4-151">PSTN の使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="759c4-151">Create PSTN usages</span></span>

<span data-ttu-id="759c4-152">PSTN 使用量は、ボイスルートのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="759c4-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="759c4-153">特定の開催者の会議でダイヤルアウト通話が開始されると、ユーザーのボイスルーティングポリシーによってユーザーに関連付けられている PSTN 経由での通話のルーティングパスが決定されます。</span><span class="sxs-lookup"><span data-stu-id="759c4-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="759c4-154">PSTN の使用状況を作成するには、"CsOnlinePstnUsage" コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="759c4-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="759c4-155">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="759c4-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="759c4-156">ボイスルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="759c4-156">Configure voice routes</span></span>

<span data-ttu-id="759c4-157">音声ルーティングでは、Teams 会議からダイヤルされた電話番号に基づいて通話をルーティングするために使用する PSTN ゲートウェイを決定します。</span><span class="sxs-lookup"><span data-stu-id="759c4-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="759c4-158">ボイスルーティングは、特定の通話をルーティングするために使用する PSTN ゲートウェイを決定します。これは、Teams の会議でダイヤルされた電話番号と regex のパターンを照合することによって決まります。</span><span class="sxs-lookup"><span data-stu-id="759c4-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="759c4-159">ボイスルートを作成する場合は、1つ以上の PSTN 使用状況にルートを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="759c4-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="759c4-160">"CsOnlineVoiceRoute" コマンドレットを使用して、ボイスルートを作成し、その音声ルートに関連付ける regex とゲートウェイを定義できます。</span><span class="sxs-lookup"><span data-stu-id="759c4-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="759c4-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="759c4-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="759c4-162">電話会議のボイスルーティングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="759c4-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="759c4-163">電話会議の音声ルーティングポリシーは、会議のダイヤルアウト通話のターゲットの電話番号に基づいて開催者の会議から発信する通話をルーティングするために使用できるルートの候補を決定します。</span><span class="sxs-lookup"><span data-stu-id="759c4-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="759c4-164">電話会議のボイスルーティングポリシーは、1つ以上の PSTN 使用状況に関連付けられています。これにより、ポリシーに関連付けられた開催者の会議のダイヤルアウト呼び出しに対して使用できるルートを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="759c4-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="759c4-165">"New-CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用して、電話会議の音声ルーティングポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="759c4-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="759c4-166">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="759c4-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="759c4-167">ポリシーがユーザーに割り当てられた後、会議のダイヤルアウト通話がユーザーの会議のいずれかから開始されると、ユーザーのボイスルーティングポリシーを通じて開催者に関連付けられている PSTN の使用状況のボイスルートが評価されます。</span><span class="sxs-lookup"><span data-stu-id="759c4-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="759c4-168">会議のダイヤルアウトの発信先が、開催者に関連付けられているいずれかのボイスルートの regex と一致する場合、会議のダイヤルアウト通話は、ボイスルートで定義された PSTN ゲートウェイにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="759c4-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="759c4-169">会議のダイヤルアウトの発信先が、開催者に関連付けられているボイスルートと一致しない場合、会議のダイヤルアウト通話は Microsoft によってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="759c4-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="759c4-170">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="759c4-170">Assign a policy to your users</span></span>

<span data-ttu-id="759c4-171">電話会議のルーティングポリシーが定義されたら、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="759c4-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="759c4-172">ポリシーが割り当てられると、会議のダイヤルアウト通話がそのルーティングパスを判断するために評価されます。</span><span class="sxs-lookup"><span data-stu-id="759c4-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="759c4-173">電話会議のルーティングポリシーは、会議の開催者に基づいて、会議のダイヤルアウト通話を開始する会議のユーザーから独立して、常に評価されます。</span><span class="sxs-lookup"><span data-stu-id="759c4-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="759c4-174">"Grant-CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用して、電話会議の音声ルーティングポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="759c4-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="759c4-175">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="759c4-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="759c4-176">組織のテレフォニー機器でルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="759c4-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="759c4-177">組織のテレフォニー機器で、直接ルーティングによってルーティングされた会議のダイヤルアウト通話が、ネットワーク上の目的の場所にルーティングされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="759c4-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="759c4-178">省略ダイヤルプランを設定する</span><span class="sxs-lookup"><span data-stu-id="759c4-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="759c4-179">ダイヤルプランとは、個々のユーザーによってダイヤルされた電話番号を、別の形式 (通常は E.i) に変換する正規化ルールのセットです。</span><span class="sxs-lookup"><span data-stu-id="759c4-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="759c4-180">既定では、Teams ユーザーは、164形式の PSTN 番号にダイヤルアウトすることができます。これは、+ \<country code\> \<number\> です。</span><span class="sxs-lookup"><span data-stu-id="759c4-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="759c4-181">ただし、ダイヤルプランを使って、4桁の内線番号など、他の形式で電話番号をダイヤルすることができます。</span><span class="sxs-lookup"><span data-stu-id="759c4-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="759c4-182">ネットワーク上の会議経由の内線番号に基づくダイヤルを有効にするには、ダイヤルプランを、内線番号のダイヤルパターンと組織の電話番号の電話番号の範囲に合わせて設定します。</span><span class="sxs-lookup"><span data-stu-id="759c4-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="759c4-183">ダイヤルプランを設定する方法については、「 [ダイヤルプランを作成して管理](create-and-manage-dial-plans.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="759c4-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="759c4-184">開いているプレビューの既知の問題</span><span class="sxs-lookup"><span data-stu-id="759c4-184">Known issues in Open Preview</span></span>

<span data-ttu-id="759c4-185">次に示すのは、ネットワーク会議のオープンプレビューリリースで現在存在する既知の問題の一覧です。</span><span class="sxs-lookup"><span data-stu-id="759c4-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="759c4-186">Microsoft は、これらの問題の解決に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="759c4-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="759c4-187">問題</span><span class="sxs-lookup"><span data-stu-id="759c4-187">Issue</span></span> | <span data-ttu-id="759c4-188">ところ</span><span class="sxs-lookup"><span data-stu-id="759c4-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="759c4-189">ネットワーク上の会議経由でルーティングされた、匿名/非表示の発信者番号を使用したダイヤルイン通話は、会議に接続できません。</span><span class="sxs-lookup"><span data-stu-id="759c4-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="759c4-190">可能であれば、PBX または SBC の構成を設定して、ネットワーク上の会議経由でルーティングされた通話に対して、常に発信者番号認識を送信します。</span><span class="sxs-lookup"><span data-stu-id="759c4-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="759c4-191">場合によっては、ユーザーがサービスにダイヤルインしたときに再生されるようこそメッセージ ("電話会議へようこそ") が切り捨てられ、ユーザーは "ようこそ" の単語を読み上げません。</span><span class="sxs-lookup"><span data-stu-id="759c4-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="759c4-192">現時点では、この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="759c4-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="759c4-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="759c4-193">Related topics</span></span>


