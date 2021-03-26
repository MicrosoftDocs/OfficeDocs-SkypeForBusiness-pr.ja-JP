---
title: 直接ルーティング、GCCH、DoD を使用した電話会議
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: 管理者は、GCCH および DoD 環境での直接ルーティングで電話会議を使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 577a9fe106cb5dae23049404b54433288e350b78
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262622"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="aba39-103">GCC High および DoD のダイレクト ルーティングを使用する電話会議</span><span class="sxs-lookup"><span data-stu-id="aba39-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="aba39-104">GCC High および DoD の直接ルーティングを使用した電話会議では、参加者は電話デバイスを使用して GCC High または DoD 組織の Teams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="aba39-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="aba39-105">会議の参加者は、インターネット接続が制限されている場合や、ユーザーが道を行き、Teams にアクセスできない場合などのシナリオで、電話デバイスを使用して Teams 会議に参加することを好む場合があります。</span><span class="sxs-lookup"><span data-stu-id="aba39-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="aba39-106">参加者は、組織のダイヤルイン電話番号にダイヤルインするか、会議を自分の電話デバイスにダイヤルアウトすることで、会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="aba39-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="aba39-107">GCC High および DoD の直接ルーティングを使用した電話会議では、組織はダイヤルイン電話番号として独自の番号を使用し、電話デバイスへの会議のすべてのダイヤルアウトは直接ルーティングを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="aba39-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="aba39-108">サービスを有効にするには、組織はダイレクト ルーティングを設定し、ダイヤルイン電話番号として使用できる電話番号を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aba39-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="aba39-109">直接ルーティングを使用する要件は、ダイヤルイン電話番号が Microsoft によって提供される GCC High 以外の組織および DoD 以外の組織に提供される電話会議サービスとは異なります。</span><span class="sxs-lookup"><span data-stu-id="aba39-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="aba39-110">GCC High および DoD の直接ルーティングを使用して電話会議を展開する</span><span class="sxs-lookup"><span data-stu-id="aba39-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="aba39-111">手順 1: GCC High または DoD ライセンスの直接ルーティングを使用して電話会議を取得する</span><span class="sxs-lookup"><span data-stu-id="aba39-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="aba39-112">GCC High または DoD で電話会議を使用するには、組織と組織内のユーザーに直接ルーティング ライセンスが割り当てられた電話会議が必要です。</span><span class="sxs-lookup"><span data-stu-id="aba39-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="aba39-113">GCC High または DoD の直接ルーティングを使用して電話会議を有効にするために必要なライセンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="aba39-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="aba39-114">GCC High: 電話会議 - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span><span class="sxs-lookup"><span data-stu-id="aba39-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="aba39-115">DoD: 電話会議 - 組織の DoD テナント ライセンスと電話会議 - ユーザーの DoD ライセンス。</span><span class="sxs-lookup"><span data-stu-id="aba39-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="aba39-116">サービスを有効にするには、テナント ライセンスと少なくとも 1 つのユーザー ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="aba39-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="aba39-117">テナント ライセンスのみ、またはユーザー ライセンスのみを使用してサービスを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="aba39-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="aba39-118">テナントと組織内のユーザーのサービス ライセンスを取得するには、アカウント チームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="aba39-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aba39-119">ダイヤルイン電話番号が設定されるまで、ユーザーは直接ルーティングを使用して電話会議を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="aba39-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="aba39-120">この記事で説明するダイヤルイン電話番号を設定するまで、GCC High ライセンスまたは DoD ライセンスのダイレクト ルーティングを使用する電話会議をユーザーに割り当てないでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aba39-120">We recommend that you do not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>  <span data-ttu-id="aba39-121">このガイダンスに従う必要が生じ、Teams クライアントでダイヤル パッドが完全に見つからない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aba39-121">Failure to follow this guidance may cause the dial pad to be completely missing in the Teams client.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="aba39-122">手順 2: ダイレクト ルーティングを設定する</span><span class="sxs-lookup"><span data-stu-id="aba39-122">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="aba39-123">ダイレクト ルーティングを設定するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aba39-123">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="aba39-124">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="aba39-124">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="aba39-125">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="aba39-125">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="aba39-126">ダイレクト ルーティングを設定する場合は、これら 2 つの記事で説明されている GCC High または DoD 固有の FQDN とポートを使用してください。</span><span class="sxs-lookup"><span data-stu-id="aba39-126">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="aba39-127">手順 3: ダイヤルイン電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="aba39-127">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="aba39-128">ダイヤルイン電話番号は、電話会議ブリッジに関連付けられている電話番号です。</span><span class="sxs-lookup"><span data-stu-id="aba39-128">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="aba39-129">これらの番号は、組織内のユーザーがスケジュールした会議に参加するために参加者が使用します。</span><span class="sxs-lookup"><span data-stu-id="aba39-129">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="aba39-130">これらの番号は、組織内の会議をスケジュールするユーザーの会議の招待と [電話番号の検索] ページにも含まれます。</span><span class="sxs-lookup"><span data-stu-id="aba39-130">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="aba39-131">テナントでサービス電話番号を定義する</span><span class="sxs-lookup"><span data-stu-id="aba39-131">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="aba39-132">New-csHybridTelephoneNumber PowerShell コマンドレットを使用して、直接ルーティングを使用して電話会議サービスに通話をルーティングするために使用できる、テナントのサービス電話番号を定義できます。</span><span class="sxs-lookup"><span data-stu-id="aba39-132">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="aba39-133">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="aba39-133">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="aba39-134">組織の電話会議ブリッジにサービス電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="aba39-134">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="aba39-135">Register-csOnlineDialInConferencingServiceNumber PowerShell コマンドレットを使用して、組織の電話会議ブリッジにサービス電話番号を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="aba39-135">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="aba39-136">Get-CsOnlineDialInConferencingBridge を使用して、電話会議ブリッジの ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="aba39-136">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="aba39-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="aba39-137">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="aba39-138">手順 4: グローバル音声ルーティング ポリシーを定義して、会議からの送信通話のルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="aba39-138">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="aba39-139">組織内のユーザーによって開催された会議から PSTN に対して行われた発信通話のルーティングは、組織のグローバル音声ルーティング ポリシーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="aba39-139">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="aba39-140">組織でグローバル音声ルーティング ポリシーが定義されている場合は、グローバル音声ルーティング ポリシーで、組織内のユーザーが開催する会議から開始される予定の PSTN への発信通話が許可されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aba39-140">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="aba39-141">組織にグローバル音声ルーティング ポリシーが定義されていない場合は、組織内のユーザーが開催する会議から PSTN への発信通話のルーティングを有効にするグローバル音声ルーティング ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aba39-141">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="aba39-142">組織のグローバル音声ルーティング ポリシーは、組織内のユーザーが PSTN に対して行った 1 対 1 の通話にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="aba39-142">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="aba39-143">PSTN への 1 対 1 の通話が組織内のユーザーに対して有効になっている場合は、グローバル音声ルーティング ポリシーが両方の種類の通話に対する組織のニーズを満たしているか確認します。</span><span class="sxs-lookup"><span data-stu-id="aba39-143">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="aba39-144">Location-Basedルーティングは、Microsoft 365 Government Community Cloud (GCC) の High または DoD 展開では利用できません。</span><span class="sxs-lookup"><span data-stu-id="aba39-144">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="aba39-145">電話会議を有効にする場合は、GCC High または DoD 環境の電話会議ユーザーが電話会議ルーティングに対して有効になっていないことをLocation-Basedしてください。</span><span class="sxs-lookup"><span data-stu-id="aba39-145">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="aba39-146">グローバル 音声ルーティング ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="aba39-146">Defining a global voice routing policy</span></span>

<span data-ttu-id="aba39-147">グローバル音声ルーティング ポリシーは、PSTN の使用状況、音声ルート、音声ルーティング ポリシーを定義し、新しい音声ルーティング ポリシーを組織のグローバル 音声ルーティング ポリシーとして割り当てると定義できます。</span><span class="sxs-lookup"><span data-stu-id="aba39-147">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="aba39-148">次の手順では、組織に新しいグローバル音声ルーティング ポリシーを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aba39-148">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="aba39-149">組織で音声ルーティング ポリシーが既に定義されている場合は、次の構成が組織の既存の音声ルーティング ポリシーと競合しなされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="aba39-149">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="aba39-150">Skype for Business Online のリモート PowerShell セッションで新しい PSTN 使用状況を作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aba39-150">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="aba39-151">詳細については [、「Set-CsOnlinePstnUsage」を参照してください](/powershell/module/skype/set-csonlinepstnusage)。</span><span class="sxs-lookup"><span data-stu-id="aba39-151">For additional information, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="aba39-152">新しい音声ルートを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aba39-152">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="aba39-153">組織の新しい音声ルートを定義する場合は、ダイレクト ルーティングの構成中に組織に定義されている PSTN オンライン PSTN ゲートウェイの 1 つ以上を指定してください。</span><span class="sxs-lookup"><span data-stu-id="aba39-153">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="aba39-154">番号パターンは、呼び出し先の電話番号に基づいて、指定されたゲートウェイのリストを介してルーティングされる通話を指定します。</span><span class="sxs-lookup"><span data-stu-id="aba39-154">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="aba39-155">上記の例では、世界中の任意の宛先への呼び出しが音声ルートと一致します。</span><span class="sxs-lookup"><span data-stu-id="aba39-155">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="aba39-156">組織内のユーザーの会議からダイヤルできる電話番号を制限する場合は、音声ルートが許可されている発信先の番号パターンにのみ一致する番号パターンを変更できます。</span><span class="sxs-lookup"><span data-stu-id="aba39-156">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="aba39-157">特定の通話の宛先電話番号の番号パターンに一致する音声ルートがない場合、通話はルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="aba39-157">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="aba39-158">詳細については [、「New-CsOnlineVoiceRoute」を参照してください](/powershell/module/skype/new-csonlinevoiceroute)。</span><span class="sxs-lookup"><span data-stu-id="aba39-158">For additional information, see [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="aba39-159">新しい音声ルーティング ポリシーを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aba39-159">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="aba39-160">音声ルーティング ポリシーで複数の PSTN 使用状況が定義されている場合、それらは定義された順序で評価されます。</span><span class="sxs-lookup"><span data-stu-id="aba39-160">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="aba39-161">PSTN の使用状況は、PSTN 使用状況に関連付けられている音声ルートの番号パターンに関して、より一般的な順に定義されるのが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="aba39-161">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="aba39-162">たとえば、通話を米国にルーティングするために PSTN 使用状況が定義され、別の PSTN 使用状況が通話を世界の他の場所にルーティングするために定義されている場合、通話を世界の他の場所にルーティングするには、PSTN の使用の前に、米国への通話の PSTN 使用状況を音声ルーティング ポリシーに一覧表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aba39-162">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="aba39-163">詳細については [、「New-CsOnlineVoiceRoutingPolicy」を参照してください](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="aba39-163">For additional information, see [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="aba39-164">新しい音声ルートを組織のグローバル音声ルーティング ポリシーに割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aba39-164">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="aba39-165">詳細については [、「Grant-CsOnlineVoiceRoutingPolicy」を参照してください](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="aba39-165">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="aba39-166">グローバル音声ルーティング ポリシーを定義すると、組織内のユーザーによって開催された会議から発信された通話は、グローバル音声ルーティング ポリシーの PSTN 使用状況に関連付けられている音声ルートに対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="aba39-166">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="aba39-167">発信通話は、ダイヤルされた電話番号の番号パターンに一致する最初の音声ルートに従ってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="aba39-167">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="aba39-168">手順 5: GCC High または DoD ライセンスの直接ルーティングを使用した電話会議をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="aba39-168">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="aba39-169">GCC High ライセンスまたは DoD ライセンスのダイレクト ルーティングを使用した電話会議をユーザーに割り当てるには、「ライセンスをユーザーに割り当てる [」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="aba39-169">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="aba39-170">手順 6: (オプション) Teams の電話会議番号の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="aba39-170">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="aba39-171">組織の電話会議番号の一覧を表示するには [、「Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)の電話会議番号の一覧を表示する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aba39-171">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="aba39-172">手順 7: (オプション) 組織の電話会議ダイヤルイン番号の自動応答言語を設定する</span><span class="sxs-lookup"><span data-stu-id="aba39-172">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="aba39-173">組織の電話会議ダイヤルイン番号の言語を変更するには [、「Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)の電話会議の自動応答言語を設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aba39-173">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="aba39-174">手順 8: (オプション) 組織の電話会議ブリッジの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="aba39-174">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="aba39-175">組織の電話会議ブリッジの設定を変更するには、「電話会議ブリッジの設定を変更する」 [を参照してください](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="aba39-175">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="aba39-176">手順 9: (オプション) 組織内のユーザーの会議出席招待に含まれる電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="aba39-176">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="aba39-177">ユーザーの会議出席招待に含まれる電話番号のセットを変更するには [、「Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)の招待に含まれる電話番号を設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aba39-177">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="aba39-178">GCC High および DoD の直接ルーティングを使用した電話会議でサポートされていない電話会議機能</span><span class="sxs-lookup"><span data-stu-id="aba39-178">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="aba39-179">GCC High および DoD の直接ルーティングを使用した電話会議ではサポートされていない電話会議機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="aba39-179">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="aba39-180">名前の記録を使用して通知を開始および終了します。</span><span class="sxs-lookup"><span data-stu-id="aba39-180">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="aba39-181">直接ルーティングを使用した電話会議の場合、入退出通知はトーンとして会議で再生されます。</span><span class="sxs-lookup"><span data-stu-id="aba39-181">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="aba39-182">電話会議の発信通話制限ポリシー。</span><span class="sxs-lookup"><span data-stu-id="aba39-182">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="aba39-183">発信通話を制限するユーザー レベルのコントロールは、ダイレクト ルーティングを介してルーティングされる会議のダイヤルアウト通話には適用されません。</span><span class="sxs-lookup"><span data-stu-id="aba39-183">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="aba39-184">会議特定の開催者の無料電話番号の使用を無効にします。</span><span class="sxs-lookup"><span data-stu-id="aba39-184">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="aba39-185">組織の会議に参加するために無料電話番号の使用を制限するユーザー レベルのコントロールは、直接ルーティングを介してルーティングされる通話には適用されません。</span><span class="sxs-lookup"><span data-stu-id="aba39-185">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="aba39-186">設定が変更されたユーザーに通知メールを送信する。</span><span class="sxs-lookup"><span data-stu-id="aba39-186">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="aba39-187">GCC High および DoD の直接ルーティングを使用した電話会議では、電話会議の通知メールはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="aba39-187">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>