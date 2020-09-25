---
title: Direct Routing、GCCH、DoD を搭載した電話会議
author: LanaChin
ms.author: v-lanac
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
description: 管理者は、GCCH および DoD 環境で直接ルーティングを使用して電話会議を使用する方法について知ることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262494"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="580d8-103">GCC High および DoD のダイレクト ルーティングを使用する電話会議</span><span class="sxs-lookup"><span data-stu-id="580d8-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="580d8-104">GCC 高と DoD で直接ルーティングを使用した電話会議により、参加者はスマートフォンデバイスを使って、GCC 高または DoD 組織の Teams 会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="580d8-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="580d8-105">会議の参加者は、インターネット接続が制限されている場合や、ユーザーが外出中で、Teams へのアクセス権を持っていない場合などのシナリオで、電話デバイスを使って Teams 会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="580d8-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="580d8-106">参加者は、組織のダイヤルイン電話番号にダイヤルインするか、会議を電話デバイスにダイヤルアウトすることで、会議に参加することを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="580d8-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="580d8-107">スマートフォン高と DoD の直行ルーティングを使用した電話会議を使用する場合、組織では、独自の番号をダイヤルイン電話番号として使用し、電話デバイスへの会議のすべてのダイヤルアウトは、直接ルーティングを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="580d8-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="580d8-108">このサービスを有効にするには、組織はダイレクトルーティングを設定し、ダイヤルイン電話番号として使用できる電話番号を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="580d8-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="580d8-109">直接ルーティングを使用するための要件は、スマートフォン以外の組織で、Microsoft がダイヤルイン電話番号を提供している非 GCC 高および DoD 以外の組織で提供されている電話会議サービスとは異なります。</span><span class="sxs-lookup"><span data-stu-id="580d8-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="580d8-110">GCC High and DoD のダイレクトルーティングを使用して電話会議を展開する</span><span class="sxs-lookup"><span data-stu-id="580d8-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="580d8-111">手順 1: GCC 高または DoD ライセンスのダイレクトルーティングを使用して電話会議を取得する</span><span class="sxs-lookup"><span data-stu-id="580d8-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="580d8-112">GCC 高または DoD で電話会議を使用するには、組織内の組織とユーザーが、ダイレクトルーティングライセンスを割り当てられた電話会議を利用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="580d8-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="580d8-113">GCC 高または DoD のダイレクトルーティングを使用して電話会議を有効にするために必要なライセンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="580d8-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="580d8-114">GCC High: 電話会議-組織および電話会議用の GCC 高テナントライセンス-ユーザー向けのスマートな高ライセンス。</span><span class="sxs-lookup"><span data-stu-id="580d8-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="580d8-115">DoD: 組織および電話会議のための電話会議 (DoD テナントライセンス)-ユーザー向けの DoD ライセンス。</span><span class="sxs-lookup"><span data-stu-id="580d8-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="580d8-116">サービスを有効にするには、テナントライセンスと少なくとも1つのユーザーライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="580d8-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="580d8-117">テナントライセンスのみで、またはユーザーライセンスのみを使用してサービスを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="580d8-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="580d8-118">テナントと組織内のユーザーのサービスライセンスを取得するには、アカウントチームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="580d8-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="580d8-119">ダイヤルイン電話番号が設定されるまで、直接ルーティングを使用して電話会議のユーザーを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="580d8-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="580d8-120">この記事で説明されているようにダイヤルイン電話番号を設定しない限り、スマートフォンの高または米国のライセンスを直接ルーティングする電話会議をユーザーに割り当てることは禁じられています。</span><span class="sxs-lookup"><span data-stu-id="580d8-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="580d8-121">手順 2: ダイレクトルーティングを設定する</span><span class="sxs-lookup"><span data-stu-id="580d8-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="580d8-122">直接ルーティングを設定するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="580d8-123">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="580d8-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="580d8-124">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="580d8-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="580d8-125">直接ルーティングを設定する場合は、以下の2つの記事で説明されている GCC 高または DoD 固有の Fqdn とポートを使用してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="580d8-126">手順 3: ダイヤルイン電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="580d8-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="580d8-127">ダイヤルイン電話番号は、電話会議ブリッジに関連付けられている電話番号です。</span><span class="sxs-lookup"><span data-stu-id="580d8-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="580d8-128">これらの番号は、組織内のユーザーによってスケジュールされた会議に参加するために参加者が使用します。</span><span class="sxs-lookup"><span data-stu-id="580d8-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="580d8-129">この番号は、組織で会議をスケジュールするユーザーの会議出席依頼にも含まれています。また、[電話番号の検索] ページでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="580d8-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="580d8-130">テナントのサービス電話番号を定義する</span><span class="sxs-lookup"><span data-stu-id="580d8-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="580d8-131">CsHybridTelephoneNumber PowerShell コマンドレットを使用して、テナント内のサービス電話番号を定義することができます。これにより、直接ルーティングを使用して電話会議サービスへの呼び出しをルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="580d8-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="580d8-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="580d8-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="580d8-133">サービスの電話番号を組織の電話会議ブリッジに割り当てる</span><span class="sxs-lookup"><span data-stu-id="580d8-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="580d8-134">Set-csonlinedialinconferencingservicenumber PowerShell コマンドレットを使用して、組織の電話会議ブリッジにサービスの電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="580d8-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="580d8-135">Get-csonlinedialinconferencingbridge を使用して、電話会議ブリッジの ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="580d8-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="580d8-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="580d8-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="580d8-137">手順 4: グローバルボイスルーティングポリシーを定義して、会議からの発信通話のルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="580d8-137">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="580d8-138">組織内のユーザーによって開催された会議からの PSTN に対する発信通話のルーティングは、組織のグローバルボイスルーティングポリシーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="580d8-138">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="580d8-139">グローバルボイスルーティングポリシーが定義されている組織の場合は、グローバルボイスルーティングポリシーによって、組織内のユーザーによって開催される会議から開始される可能性がある PSTN への発信通話が許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-139">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="580d8-140">組織にグローバルボイスルーティングポリシーが定義されていない場合は、組織内のユーザーによって開催された会議からの、PSTN への発信通話のルーティングを有効にするように定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="580d8-140">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="580d8-141">組織のグローバルボイスルーティングポリシーは、組織内のユーザーによって PSTN に行われる1対1の通話にも適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-141">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="580d8-142">組織内のユーザーに対して、PSTN への1対1の通話が有効になっている場合は、グローバルボイスルーティングポリシーが両方の種類の通話に対して組織のニーズを満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-142">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="580d8-143">位置情報に基づくルーティングは、Microsoft 365 Government Community Cloud (GCC) 高または DoD の展開では使用できません。</span><span class="sxs-lookup"><span data-stu-id="580d8-143">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="580d8-144">電話会議を有効にする場合は、場所に基づくルーティングで、GCC 高または DoD 環境で電話会議ユーザーが有効になっていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-144">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="580d8-145">グローバルボイスルーティングポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="580d8-145">Defining a global voice routing policy</span></span>

<span data-ttu-id="580d8-146">グローバルボイスルーティングポリシーを定義するには、PSTN 使用状況、音声ルート、音声ルーティングポリシーを定義し、新しいボイスルーティングポリシーを組織のグローバルボイスルーティングポリシーとして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="580d8-146">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="580d8-147">次の手順では、1つの組織に対して新しいグローバルボイスルーティングポリシーを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="580d8-147">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="580d8-148">組織に既に音声ルーティングポリシーが定義されている場合は、次の構成が組織の既存の音声ルーティングポリシーと競合していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="580d8-148">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="580d8-149">Skype for Business Online のリモート PowerShell セッションで新しい PSTN 使用量を作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="580d8-149">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="580d8-150">詳細については、「 [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-150">For additional information, see [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="580d8-151">新しいボイスルートを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="580d8-151">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="580d8-152">組織の新しいボイスルートを定義する場合は、直接ルーティングの構成時に組織に対して定義されている PSTN オンライン PSTN ゲートウェイの1つまたは複数を指定してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-152">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="580d8-153">番号パターンでは、通話の発信先電話番号に基づいて、指定したゲートウェイの一覧を通じてルーティングされる通話を指定します。</span><span class="sxs-lookup"><span data-stu-id="580d8-153">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="580d8-154">上記の例では、世界中のどこにでも通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="580d8-154">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="580d8-155">組織内のユーザーの会議からダイヤルできる電話番号を制限する場合は、番号パターンを変更して、音声ルートが許可されている送信先の番号パターンだけに一致するようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="580d8-155">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="580d8-156">指定した通話の発信先電話番号の番号パターンと一致するボイスルートがない場合、通話はルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="580d8-156">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="580d8-157">詳細については、「 [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-157">For additional information, see [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="580d8-158">新しいボイスルーティングポリシーを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="580d8-158">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="580d8-159">ボイスルーティングポリシーで複数の PSTN の使用が定義されている場合は、それらのユーザーが定義された順序で評価されます。</span><span class="sxs-lookup"><span data-stu-id="580d8-159">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="580d8-160">Pstn の利用状況に関連付けられているボイスルートの番号パターンについては、最も限定的な順番で PSTN を定義することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="580d8-160">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="580d8-161">たとえば、PSTN の使用状況が、米国への通話をルーティングするように定義されていて、別の PSTN 利用状況が世界中の他の場所への通話をルーティングするように定義されている場合、世界中の他の場所への通話をルーティングするために、pstn 使用の前にボイスルーティングポリシーに含まれている必要</span><span class="sxs-lookup"><span data-stu-id="580d8-161">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="580d8-162">詳細については、「 [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-162">For additional information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="580d8-163">組織のグローバルボイスルーティングポリシーに新しいボイスルートを割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="580d8-163">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="580d8-164">詳細については、「 [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-164">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="580d8-165">グローバルボイスルーティングポリシーを定義すると、組織内のユーザーによって開催された会議から発信されたすべての発信通話は、グローバルボイスルーティングポリシーの PSTN 使用状況に関連付けられているボイスルートと照らし合わせて評価されます。</span><span class="sxs-lookup"><span data-stu-id="580d8-165">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="580d8-166">発信通話は、ダイヤルした電話番号の番号パターンと一致する最初のボイスルートに従ってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="580d8-166">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="580d8-167">手順 5: ユーザーに GCC の高または DoD ライセンスのダイレクトルーティングを使用して電話会議を割り当てる</span><span class="sxs-lookup"><span data-stu-id="580d8-167">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="580d8-168">GCC 高または DoD ライセンスのダイレクトルーティングを使用して電話会議をユーザーに割り当てる方法については、「 [ユーザーへのライセンスの割り当て](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-168">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="580d8-169">手順 6: (オプション) Teams で電話会議番号のリストを表示する</span><span class="sxs-lookup"><span data-stu-id="580d8-169">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="580d8-170">組織の電話会議番号の一覧を表示するには、 [「Microsoft Teams で電話会議番号のリストを表示する」](see-a-list-of-audio-conferencing-numbers-in-teams.md)に進みます。</span><span class="sxs-lookup"><span data-stu-id="580d8-170">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="580d8-171">手順 7: (省略可能) 組織の電話会議のダイヤルイン番号用に自動応答言語を設定する</span><span class="sxs-lookup"><span data-stu-id="580d8-171">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="580d8-172">組織の電話会議のダイヤルイン番号の言語を変更する方法については、「 [Microsoft Teams で電話会議の自動応答の言語を設定](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-172">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="580d8-173">手順 8: (省略可能) 組織の電話会議ブリッジの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="580d8-173">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="580d8-174">組織の電話会議ブリッジの設定を変更するには、「 [電話会議ブリッジの設定を変更](change-the-settings-for-an-audio-conferencing-bridge.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-174">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="580d8-175">手順 9: (省略可能) 組織内のユーザーの会議出席依頼に含まれる電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="580d8-175">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="580d8-176">ユーザーの会議出席依頼に含まれる電話番号のセットを変更するには、「 [Microsoft Teams の招待に含まれる電話番号を設定](set-the-phone-numbers-included-on-invites-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580d8-176">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="580d8-177">GCC High and DoD のダイレクトルーティングを使用した電話会議でサポートされていない電話会議機能</span><span class="sxs-lookup"><span data-stu-id="580d8-177">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="580d8-178">以下は、GCC High and DoD のダイレクトルーティングを使用した電話会議でサポートされていない電話会議機能です。</span><span class="sxs-lookup"><span data-stu-id="580d8-178">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="580d8-179">名前の記録を使用した入力通知と終了通知。</span><span class="sxs-lookup"><span data-stu-id="580d8-179">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="580d8-180">Direct Routing、entry、出口の通知を使った電話会議では、会議中にトーンが再生されます。</span><span class="sxs-lookup"><span data-stu-id="580d8-180">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="580d8-181">電話会議の発信通話制限ポリシー。</span><span class="sxs-lookup"><span data-stu-id="580d8-181">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="580d8-182">発信通話を制限するユーザーレベルのコントロールは、直接ルーティングによってルーティングされる会議のダイヤルアウト通話には適用されません。</span><span class="sxs-lookup"><span data-stu-id="580d8-182">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="580d8-183">会議固有の開催者の無料電話番号の使用を無効にします。</span><span class="sxs-lookup"><span data-stu-id="580d8-183">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="580d8-184">ユーザーレベルの制御。組織の会議に参加するための無料電話番号の使用を制限するには、直接ルーティングを使ってルーティングする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="580d8-184">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="580d8-185">ユーザー設定が変更された場合に通知メールをユーザーに送信する。</span><span class="sxs-lookup"><span data-stu-id="580d8-185">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="580d8-186">電話会議の通知メールは、GCC 高と DoD のダイレクトルーティングを使用した電話会議ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="580d8-186">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
