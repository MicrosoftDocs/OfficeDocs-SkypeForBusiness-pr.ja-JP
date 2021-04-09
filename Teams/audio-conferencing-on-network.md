---
title: 電話会議のオンネットワーク会議
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
description: 次に、電話会議用のオンネットワークの Open Preview 機能について説明します。
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637839"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="79619-103">電話会議用のネットワーク上会議のプレビューを開く</span><span class="sxs-lookup"><span data-stu-id="79619-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="79619-104">オンネットワーク会議のオープン プレビューは、すべてのお客様が利用できます。</span><span class="sxs-lookup"><span data-stu-id="79619-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="79619-105">オンネットワーク会議を使用すると、組織は直接ルーティングを通じて Microsoft ダイヤルイン番号に電話会議の受信および発信を送信できます。</span><span class="sxs-lookup"><span data-stu-id="79619-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="79619-106">この機能は、電話会議のサポートをサードパーティのダイヤルイン番号に拡張することを目的とした機能ではありません。</span><span class="sxs-lookup"><span data-stu-id="79619-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="79619-107">着信通話を電話会議サービスに第三者のダイヤルイン電話番号または発信通話を経由して Microsoft 電話会議ブリッジから PSTN にルーティングするために使用される場合、ネットワーク上会議はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="79619-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="79619-108">この記事では、組織でネットワーク上会議を有効にするために必要な前提条件と構成手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="79619-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79619-109">インドでは、電話会議をテレフォニー機器と一緒に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79619-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="79619-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="79619-110">Prerequisites</span></span>

<span data-ttu-id="79619-111">ネットワーク上会議を構成する前に、組織が次の前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79619-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="79619-112">組織内で電話会議が有効になっているか、有効になるすべてのユーザーが、すべての会議に Teams を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="79619-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="79619-113">オンネットワーク会議を介した受信および送信の電話会議のルーティングは、Teams 会議でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="79619-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="79619-114">電話会議ライセンスを、オンネットワーク会議を使用するすべてのユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="79619-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="79619-115">電話会議サービスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="79619-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="79619-116">詳細については [、「Microsoft Teams の電話会議をセットアップする」を参照してください](set-up-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="79619-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="79619-117">直接ルーティング用にセッション ボーダー コントローラー (SBC) をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="79619-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="79619-118">詳細については、「ダイレクト ルーティングを計画 [する」および「](direct-routing-plan.md) ダイレクト ルーティング [を構成する」を参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="79619-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="79619-119">電話会議の目的でのみ直接ルーティングを設定する場合は、"手順 1: SBC を接続する" をオンネットワーク会議用に完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79619-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="79619-120">直接ルーティングを使用して Microsoft 電話会議へのダイヤルイン通話のルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="79619-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="79619-121">オンプレミス ユーザーが行ったダイヤルイン通話を直接ルーティングを通じて電話会議サービスにルーティングするには、SBC と Private Branch Exchange (PBX) に適切なルーティング ルールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79619-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="79619-122">直接ルーティング トランクを介して組織の会議ブリッジの任意のサービス番号に通話をルーティングするには、サイトのテレフォニー機器を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79619-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="79619-123">Teams 管理センターの [会議 - **>** 会議ブリッジ] または Skype for Business Online PowerShell コマンドレット Get-CsOnlineDialInConferencingBridge を使用して、サービス番号を確認できます。</span><span class="sxs-lookup"><span data-stu-id="79619-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="79619-124">詳細については、Microsoft Teams の電話会議番号 [の一覧を参照してください](see-a-list-of-audio-conferencing-numbers-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="79619-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="79619-125">この機能は、分単位支払い電話会議ライセンスを持つユーザーは使用できません。</span><span class="sxs-lookup"><span data-stu-id="79619-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="79619-126">直接ルーティングを使用して Teams 会議のダイヤルアウト通話のルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="79619-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="79619-127">Teams 会議のダイヤルアウト通話は、組織内の会議内から PSTN 番号に開始されます。この番号には、コール/Me-at 通話や、新しい参加者を会議に追加する通話が含されます。</span><span class="sxs-lookup"><span data-stu-id="79619-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="79619-128">Teams 会議のダイヤルアウト ルーティングを有効にするには、"OnlineAudioConferencingRoutingPolicy" と呼ばれる電話会議ルーティング ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="79619-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="79619-129">OnlineAudioConferencingRoutingPolicy ポリシーは、ダイレクト ルーティングを介した 1 対 1 PSTN 通話の CsOnlineVoiceRoutingPolicy と同等です。</span><span class="sxs-lookup"><span data-stu-id="79619-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="79619-130">OnlineAudioConferencingRoutingPolicy ポリシーは、次のコマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="79619-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="79619-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="79619-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="79619-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="79619-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="79619-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="79619-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="79619-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="79619-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="79619-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="79619-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="79619-136">ダイレクト ルーティングのルーティングの詳細については、「ダイレクト ルーティングの音声ルーティング [を構成する」を参照してください](direct-routing-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="79619-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="79619-137">直接ルーティングを使用して会議のダイヤルアウト通話のルーティングを有効にするには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="79619-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="79619-138">電話会議ルーティング ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="79619-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="79619-139">組織のテレフォニー機器でルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="79619-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="79619-140">(省略可能)ダイヤル プランを構成する</span><span class="sxs-lookup"><span data-stu-id="79619-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="79619-141">Teams 会議からのダイヤルアウト通話は、会議ブリッジの既定のサービス番号から発信されます。</span><span class="sxs-lookup"><span data-stu-id="79619-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="79619-142">電話会議ブリッジの既定のサービス番号の詳細については、「電話会議ブリッジの電話番号を変更する」 [を参照してください](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="79619-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="79619-143">電話会議ルーティング ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="79619-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="79619-144">電話会議ルーティング ポリシー OnlineAudioConferencingRoutingPolicy は、ダイレクト ルーティング トランクにルーティングされる会議ダイヤルアウト通話を決定します。</span><span class="sxs-lookup"><span data-stu-id="79619-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="79619-145">CsOnlineVoiceRoutingPolicy ポリシーをよく知っている場合、このポリシーは非常に似た方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="79619-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="79619-146">電話会議ルーティング ポリシーを設定するには、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="79619-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="79619-147">PSTN 使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="79619-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="79619-148">音声ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="79619-148">Configure voice routes</span></span>
3.  <span data-ttu-id="79619-149">電話会議の音声ルーティング ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="79619-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="79619-150">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="79619-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="79619-151">PSTN 使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="79619-151">Create PSTN usages</span></span>

<span data-ttu-id="79619-152">PSTN の使用状況は、音声ルートのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="79619-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="79619-153">ダイヤルアウト通話が指定の開催者の会議から開始される場合、音声ルートは、ユーザーの音声ルーティング ポリシーを介してユーザーに関連付けられている PSTN 使用状況に基づいて、通話のルーティング パスを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="79619-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="79619-154">"Set-CsOnlinePstnUsage" コマンドレットを使用して PSTN 使用状況を作成できます。</span><span class="sxs-lookup"><span data-stu-id="79619-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="79619-155">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="79619-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="79619-156">音声ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="79619-156">Configure voice routes</span></span>

<span data-ttu-id="79619-157">音声ルートは、Teams 会議からダイヤルされた電話番号に基づいて通話をルーティングするために使用する必要がある PSTN ゲートウェイを決定します。</span><span class="sxs-lookup"><span data-stu-id="79619-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="79619-158">音声ルートは、Teams 会議からダイヤルされた電話番号と正規表現パターンを照合して、特定の通話をルーティングするために使用する PSTN ゲートウェイを決定します。</span><span class="sxs-lookup"><span data-stu-id="79619-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="79619-159">音声ルートを作成する場合、ルートは 1 つ以上の PSTN 使用状況に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79619-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="79619-160">音声ルートを作成し、"New-CsOnlineVoiceRoute" コマンドレットを使用して、音声ルートに関連付けられる正規表現とゲートウェイを定義できます。</span><span class="sxs-lookup"><span data-stu-id="79619-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="79619-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="79619-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="79619-162">電話会議の音声ルーティング ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="79619-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="79619-163">電話会議の音声ルーティング ポリシーは、会議ダイヤルアウト通話の対象電話番号に基づいて、開催者の会議から発信される通話をルーティングするために使用できる可能性があるルートを決定します。</span><span class="sxs-lookup"><span data-stu-id="79619-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="79619-164">電話会議の音声ルーティング ポリシーは、1 つ以上の PSTN 使用状況に関連付けられているので、ポリシーに関連付けられている開催者の会議ダイヤルアウト通話に使用される可能性があるルートを決定します。</span><span class="sxs-lookup"><span data-stu-id="79619-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="79619-165">電話会議の音声ルーティング ポリシーは、"New- CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="79619-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="79619-166">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="79619-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="79619-167">ポリシーがユーザーに割り当てられると、ユーザーの会議の 1 つから会議のダイヤルアウト通話が開始されると、ユーザーの音声ルーティング ポリシーを通じて開催者に関連付けられている PSTN 使用状況の音声ルートが評価されます。</span><span class="sxs-lookup"><span data-stu-id="79619-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="79619-168">会議のダイヤルアウト呼び出し先が、開催者に関連付けられている音声ルートの 1 つの正規表現と一致する場合、会議のダイヤルアウト通話は音声ルートで定義された PSTN ゲートウェイにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="79619-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="79619-169">会議のダイヤルアウト通話先が開催者に関連付けられている音声ルートと一致しない場合、会議のダイヤルアウト通話は Microsoft によってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="79619-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="79619-170">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="79619-170">Assign a policy to your users</span></span>

<span data-ttu-id="79619-171">電話会議ルーティング ポリシーを定義した後、ユーザーに割り当て可能です。</span><span class="sxs-lookup"><span data-stu-id="79619-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="79619-172">ポリシーが割り当てられると、会議のダイヤルアウト通話がポリシーに対して評価され、ルーティング パスが決定されます。</span><span class="sxs-lookup"><span data-stu-id="79619-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="79619-173">電話会議ルーティング ポリシーは、会議のダイヤルアウト通話を開始する会議のユーザーとは独立して、常に会議の開催者に基づいて評価されます。</span><span class="sxs-lookup"><span data-stu-id="79619-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="79619-174">ユーザーに電話会議音声ルーティング ポリシーを割り当てるには、"Grant-CsOnlineAudioConferencingRoutingPolicy" コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="79619-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="79619-175">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="79619-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="79619-176">組織のテレフォニー機器でルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="79619-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="79619-177">組織のテレフォニー機器では、ダイレクト ルーティングを介してルーティングされる会議のダイヤルアウト通話が、意図したネットワーク上の宛先にルーティングされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="79619-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="79619-178">(省略可能)ダイヤル プランを構成する</span><span class="sxs-lookup"><span data-stu-id="79619-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="79619-179">ダイヤル プランは、個別のユーザーによるダイヤルされた電話番号を、通話承認と通話ルーティングの目的で代替形式 (通常は E.164) に変換する正規化ルールのセットです。</span><span class="sxs-lookup"><span data-stu-id="79619-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="79619-180">既定では、Teams ユーザーは E.164 形式 (+) で PSTN 番号にダイヤルアウトできます \<country code\> \<number\> 。</span><span class="sxs-lookup"><span data-stu-id="79619-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="79619-181">ただし、ダイヤル プランを使用すると、ユーザーが他の形式 (4 桁の内線番号など) で電話番号をダイヤルできます。</span><span class="sxs-lookup"><span data-stu-id="79619-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="79619-182">ネットワーク上の会議を通じて内線番号ベースのダイヤルを有効にする場合は、組織の電話番号の電話番号範囲と内線番号のダイヤル パターンを一致するようにダイヤル プランを設定できます。</span><span class="sxs-lookup"><span data-stu-id="79619-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="79619-183">ダイヤル プランを設定するには、「ダイヤル プランを作成 [して管理する」を参照してください](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="79619-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="79619-184">Open Preview の既知の問題</span><span class="sxs-lookup"><span data-stu-id="79619-184">Known issues in Open Preview</span></span>

<span data-ttu-id="79619-185">以下は、オンネットワーク会議の Open Preview リリースに現在存在する既知の問題の一覧です。</span><span class="sxs-lookup"><span data-stu-id="79619-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="79619-186">Microsoft では、これらの問題の解決に取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="79619-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="79619-187">問題</span><span class="sxs-lookup"><span data-stu-id="79619-187">Issue</span></span> | <span data-ttu-id="79619-188">回避策</span><span class="sxs-lookup"><span data-stu-id="79619-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="79619-189">オンネットワーク会議を介してルーティングされる匿名/非表示の発信者 ID を含むダイヤルイン通話は、会議に接続できません。</span><span class="sxs-lookup"><span data-stu-id="79619-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="79619-190">可能であれば、PBX または SBC で構成を設定して、常にオンネットワーク会議経由でルーティングされる通話の発信者番号を送信します。</span><span class="sxs-lookup"><span data-stu-id="79619-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="79619-191">場合によっては、ユーザーがサービスにダイヤルインするときに再生されるウェルカム メッセージ ("電話会議サービスへようこそ...") が切り捨てられ、ユーザーには "ようこそ" という単語が聞こえない場合があります。</span><span class="sxs-lookup"><span data-stu-id="79619-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="79619-192">現時点では、この問題の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="79619-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="79619-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="79619-193">Related topics</span></span>


