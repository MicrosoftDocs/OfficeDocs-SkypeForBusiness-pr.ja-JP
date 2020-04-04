---
title: クイックスタートガイド-通話プランを設定する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams で通話プランを設定するためのクイック スタート ガイドです。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a81cd7d3481c9c2f6e3e5c8874eef97dc0540431
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137777"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="3ee20-103">クイック スタート ガイド: Microsoft Teams での通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="3ee20-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="3ee20-104">このガイドでは、ユーザーが Teams で通話プランを利用できるように設定する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ee20-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="3ee20-105">Teams の通話プランに関する 2017 年 12 月 12 日付けの発表「[Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)」(英語) をお読みください。</span><span class="sxs-lookup"><span data-stu-id="3ee20-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="3ee20-106">展開を成功させるため、このクイック スタート ガイドとともに、「[通話プランが設定された電話システム](calling-plan-landing-page.md)」と「[FastTrack](https://aka.ms/cloudvoice)」をご覧になることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ee20-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="3ee20-107">Skype for Business が提供する Office 365 の機能の 1 つである通話プランを追加することで、Teams で公衆交換電話網 (PSTN) を介して固定電話や携帯電話に対する通話の発信および受信を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="3ee20-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Teams の [連絡先] ページを示すスクリーンショット](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="3ee20-109">Teams の [**通話**] タブを有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="3ee20-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="3ee20-110">Teams の [**通話**] を有効にするには、Teams で 1:1 の通話を有効にする必要があります。また、Teams の 1:1 の通話をサポートする Teams クライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ee20-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="3ee20-111">Teams で 1:1 の通話を管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ee20-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="3ee20-112">通話をサポートしているクライアントの詳細については、「[Microsoft Teams の制限事項と仕様](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ee20-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="3ee20-113">現在、ボイスメールは、ユーザーが PSTN 通話を有効にしていない限り、[通話] タブには表示されません。</span><span class="sxs-lookup"><span data-stu-id="3ee20-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="3ee20-114">Teams の [**ダイヤル パッド**] タブを有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="3ee20-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="3ee20-115">Teams の [**ダイヤル パッド**] タブを有効にして、ユーザーが PSTN 通話の発信と受信を行えるようにするには、電話システムと通話プランの利用に向けてユーザーをプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ee20-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="3ee20-116">通話プランの設定方法については、「[通話プランの設定](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3ee20-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="3ee20-117">また、Teams のみのユーザーについては、Teams 通話ポリシーで「プライベート通話を許可します」が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ee20-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="3ee20-118">詳細については、「[新しい Microsoft Teams 管理センターへの移行中に Teams を管理する](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3ee20-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="3ee20-119">また、ダイレクト ルーティングを使用して、ユーザーが PSTN 通話を発信および受信できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3ee20-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="3ee20-120">ダイレクト ルーティングの設定方法については、「[ダイレクト ルーティングを構成する](https://docs.microsoft.com/microsoftteams/direct-routing-configure)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3ee20-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="3ee20-121">TeamsUpgradePolicy を使用した通話の着信先の制御</span><span class="sxs-lookup"><span data-stu-id="3ee20-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="3ee20-122">着信先 （およびチャット） が Teams または Skype for Business になるように制御するには、管理者は [MicrosoftTeams 管理センター](https://aka.ms/teamsadmincenter)を使用するか、[Skype for Business](https://docs.microsoft.com/powershell/module/skype) コマンドレットでリモート Windows PowerShell セッションを使用して TeamsUpgradePolicy を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ee20-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="3ee20-123">TeamsUpgradePolicy の既定の構成は、アイランド モードです。これは Teams の展開時に既存のビジネス ワークフローが中断されることがないように構成されています。</span><span class="sxs-lookup"><span data-stu-id="3ee20-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="3ee20-124">既定では、ユーザーへの VoIP 通話、PSTN 通話、フェデレーション通話は、ポリシーを更新して Teams への着信通話を有効にするまで、Skype for Business にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3ee20-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="3ee20-125">受信者がアイランド モードの場合の動作は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3ee20-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="3ee20-126">Skype for Business で発信された着信 VOIP 通話は、常に受信者の Skype for Business クライアントに着信します。</span><span class="sxs-lookup"><span data-stu-id="3ee20-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="3ee20-127">*送信者と受信者が同じテナント内にある場合は*、Teams 内で発信された着信 VOIP 通話は Teams に着信します。</span><span class="sxs-lookup"><span data-stu-id="3ee20-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="3ee20-128">着信フェデレーション VOIP (クライアントの発信元に関係なく) および PSTN 通話は、常に受信者の Skype for Business クライアントに着信します。</span><span class="sxs-lookup"><span data-stu-id="3ee20-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="3ee20-129">着信 VOIP 通話と PSTN 通話が常にユーザーの Teams クライアントに着信できるようにするには、ユーザーの共存モードを TeamsOnly に更新します (つまり、TeamsUpgradePolicy の「UpgradeToTeams」インスタンスを割り当てます)。</span><span class="sxs-lookup"><span data-stu-id="3ee20-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="3ee20-130">共存モードと TeamsUpgradePolicy の詳細については、「[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ee20-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="3ee20-131">**注**</span><span class="sxs-lookup"><span data-stu-id="3ee20-131">**NOTES**</span></span>
 - <span data-ttu-id="3ee20-132">ユーザーが TeamsOnly モードを使用している場合でも、Skype for Business IP 電話は通話を受信します。</span><span class="sxs-lookup"><span data-stu-id="3ee20-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="3ee20-133">Skype for Business Online で使用する電話システムと通話プランのライセンスでプロビジョニングされた (たとえば、OnlineVoiceRoutingPolicy の値が割り当てられている) ユーザーには、Teams で [通話] タブが有効化されているため、管理者による管理操作なしで Teams から PSTN 通話の発信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3ee20-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="3ee20-134">Teams 内のすべての着信 VOIP および PSTN 通話を受信するようにユーザを設定する方法</span><span class="sxs-lookup"><span data-stu-id="3ee20-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="3ee20-135">ユーザーがすべての着信 VOIP と PSTN 通話を Teams で確実に受信できるようにするには、Microsoft Teams 管理センターでユーザーの共存モードを TeamsOnly に設定するか、Skype for Business のリモート Windows PowerShell セッションを使用して、次のように TeamsUpgradePolicy を更新します。</span><span class="sxs-lookup"><span data-stu-id="3ee20-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="3ee20-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ee20-136">See also</span></span>
[<span data-ttu-id="3ee20-137">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="3ee20-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="3ee20-138">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="3ee20-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="3ee20-139">通話プランが設定された電話システム</span><span class="sxs-lookup"><span data-stu-id="3ee20-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="3ee20-140">Skype for Business PowerShell のコマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="3ee20-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

