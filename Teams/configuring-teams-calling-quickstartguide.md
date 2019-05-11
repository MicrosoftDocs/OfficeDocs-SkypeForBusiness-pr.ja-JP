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
description: マイクロソフトのチームでの通話プランを構成するためのクイック スタート ガイドです。
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
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="00757-103">クイック スタート ガイド: Microsoft Teams での通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="00757-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="00757-104">一連のユーザーおよびチームの計画を呼び出すを参照できるように実行するを取得する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="00757-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="00757-105">チームの計画を呼び出すの 2017 年 12 月 12日、お知らせを読む:[インテリジェント通信チームでの呼び出しには、次の手順を実行します。](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="00757-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="00757-106">このクイック スタート ガイドとの併用とを参照する[計画を呼び出すと、電話システム](calling-plan-landing-page.md) [fasttrack という](https://aka.ms/cloudvoice)計画とドライブに展開の成功をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="00757-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="00757-107">計画を Office 365 機能により、ビジネスの Skype の呼び出しを追加することによって土地の明細行および公衆交換電話網 (PSTN) 経由で携帯電話からの電話呼び出しを送受信するチームを使用できます。</span><span class="sxs-lookup"><span data-stu-id="00757-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![チームでの通話](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="00757-109">チームでは、[**通話**] タブを有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="00757-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="00757-110">チームでは、[**通話**] タブを有効にするには、ユーザーを呼び出すチームで有効になっていると、1 対 1 のチームを呼び出すことをサポートしているチームのクライアントを使用して 1:1 がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="00757-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="00757-111">1 対 1 のチームで呼び出しを管理する方法については、[一連の CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00757-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="00757-112">通話をサポートするクライアントについては、[制限しマイクロソフトのチームの仕様](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00757-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="00757-113">現在、ボイスメールするには、[通話] タブで使用可能な PSTN の呼び出しに対して、ユーザーが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="00757-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="00757-114">チームでは、**ダイヤル パッド**を有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="00757-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="00757-115">チームで、[**ダイヤル パッド**] タブを有効にして、ユーザーが PSTN 通話を送受信できるようにするのには、電話システムおよび計画を呼び出すユーザーをプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00757-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="00757-116">プランの呼び出しを設定する方法については、[計画を呼び出す設定](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00757-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="00757-117">直接ルーティングを使用して、PSTN 通話を送受信するユーザーを許可することができますもします。</span><span class="sxs-lookup"><span data-stu-id="00757-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="00757-118">直接ルーティングを設定する方法については、[直接ルーティングの構成](https://docs.microsoft.com/microsoftteams/direct-routing-configure)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00757-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="00757-119">呼び出しの着陸場所のコントロールに TeamsUpgradePolicy を使用してください。</span><span class="sxs-lookup"><span data-stu-id="00757-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="00757-120">チームやビジネス用の Skype で着信呼び出し (およびチャット) が着陸するかどうかを制御するには、管理者は TeamsUpgradePolicy、いずれかの[マイクロソフトのチーム管理センター](https://aka.ms/teamsadmincenter)を使用するか、リモートの Windows PowerShell セッションを使用して、[ビジネスの Skype](https://docs.microsoft.com/powershell/module/skype)でを使用します。コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="00757-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="00757-121">TeamsUpgradePolicy の既定の構成は、諸島のモードは、その既存のビジネス ワークフローはチームに展開したときは中断されないことを確認するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="00757-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="00757-122">既定では、VoIP と PSTN、ユーザーにフェデレーションの呼び出しは引き続きチームへの着信通話を有効にするポリシーを更新するまでは、Skype のビジネスにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="00757-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="00757-123">受信者は、島のモードでは。</span><span class="sxs-lookup"><span data-stu-id="00757-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="00757-124">VOIP の着信呼び出しに由来する Skype ビジネスの常にビジネス クライアント用の受信者の Skype での着陸。</span><span class="sxs-lookup"><span data-stu-id="00757-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="00757-125">着信 VOIP 電話の*送信者と受信者は、同じテナントのかどうかは*、チームのチームの土地に由来します。</span><span class="sxs-lookup"><span data-stu-id="00757-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="00757-126">着信の連合 (クライアントに関係なく元の場所) の VOIP と PSTN では常に受信者の Skype の土地ビジネス クライアントです。</span><span class="sxs-lookup"><span data-stu-id="00757-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="00757-127">着信 VOIP と PSTN がように常にユーザーのチームのクライアントでの着陸をするには更新のユーザーの共存のモードを TeamsOnly (これは TeamsUpgradePolicy の"UpgradeToTeams"のインスタンスを割り当てることを意味します。</span><span class="sxs-lookup"><span data-stu-id="00757-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="00757-128">共存モードおよび TeamsUpgradePolicy の詳細については、「[チームとは、ビジネス用 Skype を使用する組織の移行と相互運用性](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)の使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00757-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="00757-129">**メモ**</span><span class="sxs-lookup"><span data-stu-id="00757-129">**NOTES**</span></span>
 - <span data-ttu-id="00757-130">ビジネス IP 電話の Skype ユーザーが TeamsOnly モードである場合でも、呼び出しが表示されます。</span><span class="sxs-lookup"><span data-stu-id="00757-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="00757-131">(例: 割り当てられている OnlineVoiceRoutingPolicy の値)、ビジネス オンラインはチームで有効になっている [通話] タブがありからの発信の PSTN 通話を配置することができますは、Skype で使用するライセンスの電話システムとプランを呼び出すことでプロビジョニングされているユーザー管理者は、管理操作を実行する必要のないチームです。</span><span class="sxs-lookup"><span data-stu-id="00757-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="00757-132">チームでの呼び出しを受信したすべての VOIP と PSTN を受信するユーザーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="00757-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="00757-133">ユーザー チームのすべての着信 VOIP と PSTN の呼び出しを受信することを確認するには、マイクロソフトのチーム管理センターで、ユーザーの共存モードを TeamsOnly に設定またはリモートの Windows PowerShell セッションをビジネス用の Skype を使用して、次のように TeamsUpgradePolicy を更新します。</span><span class="sxs-lookup"><span data-stu-id="00757-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="00757-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="00757-134">See also</span></span>
[<span data-ttu-id="00757-135">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="00757-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="00757-136">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="00757-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="00757-137">通話プランと電話システム</span><span class="sxs-lookup"><span data-stu-id="00757-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="00757-138">Skype のビジネスの PowerShell コマンドレットのリファレンス</span><span class="sxs-lookup"><span data-stu-id="00757-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

