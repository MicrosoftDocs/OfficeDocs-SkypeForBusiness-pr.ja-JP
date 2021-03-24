---
title: クイック スタート ガイド - 通話プランの構成
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 一連のユーザーを起動して実行できるよう、Microsoft Teams で通話プランを構成するためのクイック スタート ガイド。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101183"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="55cc5-103">クイック スタート ガイド: Microsoft Teams での通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="55cc5-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="55cc5-104">このガイドでは、ユーザーが Teams で通話プランを利用できるように設定する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="55cc5-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="55cc5-105">Teams の通話プランに関する 2017 年 12 月 12 日付けの発表「[Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)」(英語) をお読みください。</span><span class="sxs-lookup"><span data-stu-id="55cc5-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="55cc5-106">展開を成功させるため、このクイック スタート ガイドとともに、「[通話プランが設定された電話システム](calling-plan-landing-page.md)」と「[FastTrack](https://aka.ms/cloudvoice)」をご覧になることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="55cc5-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="55cc5-107">Skype for Business を利用した Microsoft 365 および Office 365 の機能である通話プランを追加すると、Teams を使用して、公衆交換電話網 (PSTN) を介して、固定電話と携帯電話の間で通話を発信および受信できます。</span><span class="sxs-lookup"><span data-stu-id="55cc5-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Teams の [連絡先] ページを示すスクリーンショット](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="55cc5-109">Teams の [**通話**] タブを有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="55cc5-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="55cc5-110">Teams の [**通話**] を有効にするには、Teams で 1:1 の通話を有効にする必要があります。また、Teams の 1:1 の通話をサポートする Teams クライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55cc5-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="55cc5-111">Teams で 1:1 の通話を管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55cc5-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="55cc5-112">通話をサポートしているクライアントの詳細については、「[Microsoft Teams の制限事項と仕様](./limits-specifications-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55cc5-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="55cc5-113">現在、ボイスメールは、ユーザーが PSTN 通話を有効にしていない限り、[通話] タブには表示されません。</span><span class="sxs-lookup"><span data-stu-id="55cc5-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="55cc5-114">Teams の [**ダイヤル パッド**] タブを有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="55cc5-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="55cc5-115">Teams の [**ダイヤル パッド**] タブを有効にして、ユーザーが PSTN 通話の発信と受信を行えるようにするには、電話システムと通話プランの利用に向けてユーザーをプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55cc5-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="55cc5-116">通話プランの設定方法については、「[通話プランの設定](./set-up-calling-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55cc5-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="55cc5-117">また、Teams のみのユーザーについては、Teams 通話ポリシーで「プライベート通話を許可します」が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55cc5-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="55cc5-118">詳細については、「[新しい Microsoft Teams 管理センターへの移行中に Teams を管理する](./manage-teams-skypeforbusiness-admin-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55cc5-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="55cc5-119">また、ダイレクト ルーティングを使用して、ユーザーが PSTN 通話を発信および受信できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="55cc5-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="55cc5-120">ダイレクト ルーティングの設定方法については、「[ダイレクト ルーティングを構成する](./direct-routing-configure.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55cc5-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="55cc5-121">TeamsUpgradePolicy を使用した通話の着信先の制御</span><span class="sxs-lookup"><span data-stu-id="55cc5-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="55cc5-122">着信先 （およびチャット） が Teams または Skype for Business になるように制御するには、管理者は [MicrosoftTeams 管理センター](https://aka.ms/teamsadmincenter)を使用するか、[Skype for Business](/powershell/module/skype) コマンドレットでリモート Windows PowerShell セッションを使用して TeamsUpgradePolicy を使用します。</span><span class="sxs-lookup"><span data-stu-id="55cc5-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="55cc5-123">TeamsUpgradePolicy の既定の構成は、アイランド モードです。これは Teams の展開時に既存のビジネス ワークフローが中断されることがないように構成されています。</span><span class="sxs-lookup"><span data-stu-id="55cc5-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="55cc5-124">既定では、ユーザーへの VoIP 通話、PSTN 通話、フェデレーション通話は、ポリシーを更新して Teams への着信通話を有効にするまで、Skype for Business にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="55cc5-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="55cc5-125">受信者がアイランド モードの場合の動作は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="55cc5-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="55cc5-126">Skype for Business で発信された着信 VOIP 通話は、常に受信者の Skype for Business クライアントに着信します。</span><span class="sxs-lookup"><span data-stu-id="55cc5-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="55cc5-127">*送信者と受信者が同じテナント内にある場合は*、Teams 内で発信された着信 VOIP 通話は Teams に着信します。</span><span class="sxs-lookup"><span data-stu-id="55cc5-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="55cc5-128">着信フェデレーション VOIP (クライアントの発信元に関係なく) および PSTN 通話は、常に受信者の Skype for Business クライアントに着信します。</span><span class="sxs-lookup"><span data-stu-id="55cc5-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="55cc5-129">着信 VOIP 通話と PSTN 通話が常にユーザーの Teams クライアントに着信できるようにするには、ユーザーの共存モードを TeamsOnly に更新します (つまり、TeamsUpgradePolicy の「UpgradeToTeams」インスタンスを割り当てます)。</span><span class="sxs-lookup"><span data-stu-id="55cc5-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="55cc5-130">共存モードと TeamsUpgradePolicy の詳細については、「[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](./migration-interop-guidance-for-teams-with-skype.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55cc5-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="55cc5-131">**注**</span><span class="sxs-lookup"><span data-stu-id="55cc5-131">**NOTES**</span></span>
 - <span data-ttu-id="55cc5-132">ユーザーが TeamsOnly モードを使用している場合でも、Skype for Business IP 電話は通話を受信します。</span><span class="sxs-lookup"><span data-stu-id="55cc5-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="55cc5-133">Skype for Business Online で使用する電話システムと通話プランのライセンスでプロビジョニングされた (たとえば、OnlineVoiceRoutingPolicy の値が割り当てられている) ユーザーには、Teams で [通話] タブが有効化されているため、管理者による管理操作なしで Teams から PSTN 通話の発信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="55cc5-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="55cc5-134">Teams 内のすべての着信 VOIP および PSTN 通話を受信するようにユーザを設定する方法</span><span class="sxs-lookup"><span data-stu-id="55cc5-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="55cc5-135">ユーザーがすべての着信 VOIP と PSTN 通話を Teams で確実に受信できるようにするには、Microsoft Teams 管理センターでユーザーの共存モードを TeamsOnly に設定するか、Skype for Business のリモート Windows PowerShell セッションを使用して、次のように TeamsUpgradePolicy を更新します。</span><span class="sxs-lookup"><span data-stu-id="55cc5-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="55cc5-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="55cc5-136">See also</span></span>
[<span data-ttu-id="55cc5-137">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="55cc5-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="55cc5-138">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="55cc5-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="55cc5-139">通話プランが設定された電話システム</span><span class="sxs-lookup"><span data-stu-id="55cc5-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="55cc5-140">Skype for Business PowerShell のコマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="55cc5-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)