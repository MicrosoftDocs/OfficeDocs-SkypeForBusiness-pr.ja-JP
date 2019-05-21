---
title: 'クイック スタート ガイド: Microsoft Teams での通話プランの設定'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Microsoft Teams で通話プランを構成するためのクイックスタートガイドです。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd1e9484b522a657a92916815c1ae8940dcc2117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898524"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="17c4b-103">クイック スタート ガイド: Microsoft Teams での通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="17c4b-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="17c4b-104">このガイドは、チームの通話プランを調査できるように、一連のユーザーを準備し、実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="17c4b-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="17c4b-105">2017年12月12日、Teams での通話プランのお知らせ:[インテリジェントコミュニケーションは、teams での通話の次の手順を実行し](https://aka.ms/ipyqus)ます。</span><span class="sxs-lookup"><span data-stu-id="17c4b-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="17c4b-106">このクイックスタートガイドと並行して、[通話プランを使って電話システム](calling-plan-landing-page.md)を読み、ロールアウトを計画して成功させるために[fasttrack](https://aka.ms/cloudvoice)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="17c4b-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="17c4b-107">通話プランを追加することにより、Skype for Business を使用した Office 365 機能を利用できるようになりました。これで、チームを使って、市内電話網 (PSTN) 経由で、職場や携帯電話との通話を発信および受信することができます。</span><span class="sxs-lookup"><span data-stu-id="17c4b-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Teams での通話](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="17c4b-109">Teams で「**通話**」タブを有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="17c4b-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="17c4b-110">Teams ユーザーの [**通話**] タブを有効にするには、teams で1:1 通話を有効にし、1:1 teams の通話をサポートするチームクライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17c4b-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="17c4b-111">Teams で1:1 通話を管理する方法については、「 [Set-Csteamのポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17c4b-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="17c4b-112">通話をサポートしているクライアントの詳細については、 [Microsoft Teams の制限事項と仕様](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17c4b-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="17c4b-113">現時点では、ユーザーが PSTN 通話を有効にしていない限り、[通話] タブでボイスメールを利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="17c4b-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="17c4b-114">Teams で**ダイヤルパッド**を有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="17c4b-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="17c4b-115">Teams で [**ダイヤルパッド**] タブを有効にして、ユーザーが PSTN 通話を発信および受信できるようにするには、電話システムと通話プランのユーザーをプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="17c4b-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="17c4b-116">通話プランの設定方法については、「[通話プラン](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17c4b-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="17c4b-117">また、直接ルーティングを使用して、ユーザーが PSTN 通話を発信および受信できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="17c4b-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="17c4b-118">ダイレクトルーティングを設定する方法については、「 [Direct ルーティングを構成](https://docs.microsoft.com/microsoftteams/direct-routing-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17c4b-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="17c4b-119">TeamsUpgradePolicy を使用して、通話の陸地を制御する</span><span class="sxs-lookup"><span data-stu-id="17c4b-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="17c4b-120">チームまたは Skype for business で着信通話 (およびチャット) が着陸するかどうかを制御するには、 [Microsoft Teams 管理センター](https://aka.ms/teamsadmincenter)を使用するか、または[skype for Business](https://docs.microsoft.com/powershell/module/skype)でリモート Windows PowerShell セッションを使用して、管理者が TeamsUpgradePolicy を使用します。cmdlet.</span><span class="sxs-lookup"><span data-stu-id="17c4b-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="17c4b-121">TeamsUpgradePolicy の既定の構成は諸島モードであり、チームの展開時に既存のビジネスワークフローが中断されないように設計されています。</span><span class="sxs-lookup"><span data-stu-id="17c4b-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="17c4b-122">既定では、ユーザーへの VoIP、PSTN、およびフェデレーションされた通話は、ポリシーを更新してチームへの着信通話を有効にするまで、引き続き Skype for Business にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="17c4b-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="17c4b-123">受信者が諸島モードの場合:</span><span class="sxs-lookup"><span data-stu-id="17c4b-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="17c4b-124">Skype for Business で発生した着信 VOIP 通話は、常に受信者の Skype for business クライアントに着陸します。</span><span class="sxs-lookup"><span data-stu-id="17c4b-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="17c4b-125">*送信者と受信者が同じテナントにある場合*、teams で発生した着信 VOIP 通話。</span><span class="sxs-lookup"><span data-stu-id="17c4b-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="17c4b-126">受信したフェデレーション VOIP (クライアントの種類に関係なく) と PSTN 通話は、常に受信者の Skype for Business クライアントにあります。</span><span class="sxs-lookup"><span data-stu-id="17c4b-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="17c4b-127">受信した VOIP と PSTN の通話が常にユーザーのチームクライアントに確実に含まれるようにするには、ユーザーの共存モードを [チームのみ] に更新します (つまり、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てます)。</span><span class="sxs-lookup"><span data-stu-id="17c4b-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="17c4b-128">共存モードと TeamsUpgradePolicy の詳細については、「[チームと Skype For business を併用する組織向けの移行と相互運用性に関するガイダンス](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17c4b-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="17c4b-129">**記録**</span><span class="sxs-lookup"><span data-stu-id="17c4b-129">**NOTES**</span></span>
 - <span data-ttu-id="17c4b-130">Skype for Business の IP 電話では、ユーザーが teams モードのみを使用している場合でも、通話が受信されます。</span><span class="sxs-lookup"><span data-stu-id="17c4b-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="17c4b-131">Skype for Business Online で使用するために、電話システムと通話プランを使ってプロビジョニングされたユーザー (OnlineVoiceRoutingPolicy の値が割り当てられている場合) は、Teams で [通話] タブが有効になり、送信 PSTN 通話を発信できます。管理者がいないチームで、管理者の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="17c4b-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="17c4b-132">Teams でのすべての受信 VOIP および PSTN 通話を受信するようにユーザーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="17c4b-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="17c4b-133">ユーザーが受信した VOIP および PSTN 通話をすべて Teams で確実に受信できるようにするには、Microsoft Teams 管理センターでユーザーの共存モードを Teams に設定するか、Skype for Business リモート Windows PowerShell セッションを使用して、次のように TeamsUpgradePolicy を更新します。</span><span class="sxs-lookup"><span data-stu-id="17c4b-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="17c4b-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="17c4b-134">See also</span></span>
[<span data-ttu-id="17c4b-135">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="17c4b-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="17c4b-136">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="17c4b-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="17c4b-137">通話プランを使用した電話システム</span><span class="sxs-lookup"><span data-stu-id="17c4b-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="17c4b-138">Skype for Business PowerShell コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="17c4b-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

