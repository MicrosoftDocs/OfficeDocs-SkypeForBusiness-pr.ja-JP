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
ms.openlocfilehash: 55efdc0c79f80a2a7b7ca44fd9c80481b163c63f
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868594"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="f028c-103">GCC High および DoD のダイレクト ルーティングを使用する電話会議</span><span class="sxs-lookup"><span data-stu-id="f028c-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="f028c-104">GCC 高と DoD で直接ルーティングを使用した電話会議により、参加者はスマートフォンデバイスを使って、GCC 高または DoD 組織の Teams 会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="f028c-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="f028c-105">会議の参加者は、インターネット接続が制限されている場合や、ユーザーが外出中で、Teams へのアクセス権を持っていない場合などのシナリオで、電話デバイスを使って Teams 会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="f028c-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="f028c-106">参加者は、組織のダイヤルイン電話番号にダイヤルインするか、会議を電話デバイスにダイヤルアウトすることで、会議に参加することを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="f028c-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="f028c-107">スマートフォン高と DoD の直行ルーティングを使用した電話会議を使用する場合、組織では、独自の番号をダイヤルイン電話番号として使用し、電話デバイスへの会議のすべてのダイヤルアウトは、直接ルーティングを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f028c-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="f028c-108">このサービスを有効にするには、組織はダイレクトルーティングを設定し、ダイヤルイン電話番号として使用できる電話番号を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f028c-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="f028c-109">直接ルーティングを使用するための要件は、スマートフォン以外の組織で、Microsoft がダイヤルイン電話番号を提供している非 GCC 高および DoD 以外の組織で提供されている電話会議サービスとは異なります。</span><span class="sxs-lookup"><span data-stu-id="f028c-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="f028c-110">GCC High and DoD のダイレクトルーティングを使用して電話会議を展開する</span><span class="sxs-lookup"><span data-stu-id="f028c-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="f028c-111">手順 1: GCC 高または DoD ライセンスのダイレクトルーティングを使用して電話会議を取得する</span><span class="sxs-lookup"><span data-stu-id="f028c-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="f028c-112">GCC 高または DoD で電話会議を使用するには、組織内の組織とユーザーが、ダイレクトルーティングライセンスを割り当てられた電話会議を利用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f028c-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="f028c-113">GCC 高または DoD のダイレクトルーティングを使用して電話会議を有効にするために必要なライセンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f028c-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="f028c-114">GCC High: 電話会議-組織および電話会議用の GCC 高テナントライセンス-ユーザー向けのスマートな高ライセンス。</span><span class="sxs-lookup"><span data-stu-id="f028c-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="f028c-115">DoD: 組織および電話会議のための電話会議 (DoD テナントライセンス)-ユーザー向けの DoD ライセンス。</span><span class="sxs-lookup"><span data-stu-id="f028c-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="f028c-116">サービスを有効にするには、テナントライセンスと少なくとも1つのユーザーライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="f028c-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="f028c-117">テナントライセンスのみで、またはユーザーライセンスのみを使用してサービスを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f028c-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="f028c-118">テナントと組織内のユーザーのサービスライセンスを取得するには、アカウントチームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f028c-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f028c-119">ダイヤルイン電話番号が設定されるまで、直接ルーティングを使用して電話会議のユーザーを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f028c-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="f028c-120">この記事で説明されているようにダイヤルイン電話番号を設定しない限り、スマートフォンの高または米国のライセンスを直接ルーティングする電話会議をユーザーに割り当てることは禁じられています。</span><span class="sxs-lookup"><span data-stu-id="f028c-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="f028c-121">手順 2: ダイレクトルーティングを設定する</span><span class="sxs-lookup"><span data-stu-id="f028c-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="f028c-122">直接ルーティングを設定するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f028c-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="f028c-123">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="f028c-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="f028c-124">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="f028c-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="f028c-125">直接ルーティングを設定する場合は、以下の2つの記事で説明されている GCC 高または DoD 固有の Fqdn とポートを使用してください。</span><span class="sxs-lookup"><span data-stu-id="f028c-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="f028c-126">手順 3: ダイヤルイン電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="f028c-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="f028c-127">ダイヤルイン電話番号は、電話会議ブリッジに関連付けられている電話番号です。</span><span class="sxs-lookup"><span data-stu-id="f028c-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="f028c-128">これらの番号は、組織内のユーザーによってスケジュールされた会議に参加するために参加者が使用します。</span><span class="sxs-lookup"><span data-stu-id="f028c-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="f028c-129">この番号は、組織で会議をスケジュールするユーザーの会議出席依頼にも含まれています。また、[電話番号の検索] ページでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="f028c-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="f028c-130">テナントのサービス電話番号を定義する</span><span class="sxs-lookup"><span data-stu-id="f028c-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="f028c-131">CsHybridTelephoneNumber PowerShell コマンドレットを使用して、テナント内のサービス電話番号を定義することができます。これにより、直接ルーティングを使用して電話会議サービスへの呼び出しをルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="f028c-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="f028c-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f028c-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="f028c-133">サービスの電話番号を組織の電話会議ブリッジに割り当てる</span><span class="sxs-lookup"><span data-stu-id="f028c-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="f028c-134">Set-csonlinedialinconferencingservicenumber PowerShell コマンドレットを使用して、組織の電話会議ブリッジにサービスの電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f028c-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="f028c-135">Get-csonlinedialinconferencingbridge を使用して、電話会議ブリッジの ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f028c-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="f028c-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f028c-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="f028c-137">手順 4: ユーザーに GCC 高または DoD ライセンスのダイレクトルーティングを使用して電話会議を割り当てる</span><span class="sxs-lookup"><span data-stu-id="f028c-137">Step 4: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="f028c-138">GCC 高または DoD ライセンスのダイレクトルーティングを使用して電話会議をユーザーに割り当てる方法については、「[ユーザーへのライセンスの割り当て](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f028c-138">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="f028c-139">手順 5: (オプション) Teams で電話会議番号のリストを表示する</span><span class="sxs-lookup"><span data-stu-id="f028c-139">Step 5: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="f028c-140">組織の電話会議番号の一覧を表示するには、 [「Microsoft Teams で電話会議番号のリストを表示する」](see-a-list-of-audio-conferencing-numbers-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f028c-140">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="f028c-141">手順 6: (省略可能) 組織の電話会議のダイヤルイン番号用に自動応答言語を設定する</span><span class="sxs-lookup"><span data-stu-id="f028c-141">Step 6: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="f028c-142">組織の電話会議のダイヤルイン番号の言語を変更する方法については、「 [Microsoft Teams で電話会議の自動応答の言語を設定](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f028c-142">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span></span>

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="f028c-143">手順 7: (省略可能) 組織の電話会議ブリッジの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="f028c-143">Step 7: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="f028c-144">組織の電話会議ブリッジの設定を変更するには、「[電話会議ブリッジの設定を変更](change-the-settings-for-an-audio-conferencing-bridge.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f028c-144">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="f028c-145">手順 8: (省略可能) 組織内のユーザーの会議出席依頼に含まれる電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="f028c-145">Step 8: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="f028c-146">ユーザーの会議出席依頼に含まれる電話番号のセットを変更するには、「 [Microsoft Teams の招待に含まれる電話番号を設定](set-the-phone-numbers-included-on-invites-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f028c-146">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="f028c-147">GCC High and DoD のダイレクトルーティングを使用した電話会議でサポートされていない電話会議機能</span><span class="sxs-lookup"><span data-stu-id="f028c-147">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="f028c-148">以下は、GCC High and DoD のダイレクトルーティングを使用した電話会議でサポートされていない電話会議機能です。</span><span class="sxs-lookup"><span data-stu-id="f028c-148">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="f028c-149">名前の記録を使用した入力通知と終了通知。</span><span class="sxs-lookup"><span data-stu-id="f028c-149">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="f028c-150">Direct Routing、entry、出口の通知を使った電話会議では、会議中にトーンが再生されます。</span><span class="sxs-lookup"><span data-stu-id="f028c-150">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="f028c-151">電話会議の発信通話制限ポリシー。</span><span class="sxs-lookup"><span data-stu-id="f028c-151">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="f028c-152">発信通話を制限するユーザーレベルのコントロールは、直接ルーティングによってルーティングされる会議のダイヤルアウト通話には適用されません。</span><span class="sxs-lookup"><span data-stu-id="f028c-152">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="f028c-153">会議固有の開催者の無料電話番号の使用を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f028c-153">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="f028c-154">ユーザーレベルの制御。組織の会議に参加するための無料電話番号の使用を制限するには、直接ルーティングを使ってルーティングする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f028c-154">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="f028c-155">ユーザー設定が変更された場合に通知メールをユーザーに送信する。</span><span class="sxs-lookup"><span data-stu-id="f028c-155">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="f028c-156">電話会議の通知メールは、GCC 高と DoD のダイレクトルーティングを使用した電話会議ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f028c-156">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
