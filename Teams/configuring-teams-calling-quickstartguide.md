---
title: 'クイック スタート ガイド: Microsoft Teams での通話プランの設定'
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Microsoft Teams で通話プランを設定するためのクイック スタート ガイドです。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86a4862a547df6f50d0831616a42824d9f8c3287
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882099"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="6cf71-103">クイック スタート ガイド: Microsoft Teams での通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="6cf71-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="6cf71-104">このガイドでは、ユーザーが Teams で通話プランを利用できるように設定する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6cf71-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="6cf71-105">Teams の通話プランに関する 2017 年 12 月 12 日付けの発表「[Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)」(英語) をお読みください。</span><span class="sxs-lookup"><span data-stu-id="6cf71-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="6cf71-106">ロールアウトを成功させるため、このクイック スタート ガイドとともに、[実践的なガイダンス](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)と [FastTrack](https://aka.ms/cloudvoice) をご覧になることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6cf71-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="6cf71-107">Skype for Business が提供する Office 365 の機能の 1 つである通話プランを追加することで、Teams で公衆交換電話網 (PSTN) を介して固定電話や携帯電話に対する通話の発信および受信を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="6cf71-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Teams での通話](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="6cf71-109">Teams の [**通話**] タブを有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="6cf71-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="6cf71-110">Teams の [**通話**] タブを有効にして、ユーザーが PSTN 通話の発信と受信を行えるようにするには、電話システムと通話プランの利用に向けてユーザーをプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cf71-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="6cf71-111">この設定方法については、「[通話プランの設定](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6cf71-111">To learn how to set this up, read [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="6cf71-112">Teams の相互運用ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="6cf71-112">Teams interop policy configuration</span></span>
<span data-ttu-id="6cf71-113">Teams を有効にして通話を受けられるようにするには、通話を Teams にリダイレクトするために、[Microsoft Teams と Skype for Business の管理センター](https://aka.ms/teamsadmincenter)を使用するか、Skype for Business [`*-CsTeamsUpgradePolicy` と `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) コマンドレットでリモートの Windows PowerShell セッションを使用して、Teams のアップグレード ポリシーと Teams の相互運用ポリシー更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cf71-113">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="6cf71-114">Teams のアップグレード ポリシーと Teams の相互運用ポリシーの詳細については、「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス)](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6cf71-114">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="6cf71-115">必要な PowerShell コマンドレットを検索するには、[Skype for Business PowerShell コマンドレットに関するドキュメント](https://docs.microsoft.com/powershell/module/skype)で [**フィルター**] ボックスに「CsTeamsUpgradePolicy」または「CsTeamsInteropPolicy」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6cf71-115">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="6cf71-116">既定の Teams のアップグレード ポリシーと相互運用ポリシー</span><span class="sxs-lookup"><span data-stu-id="6cf71-116">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="6cf71-117">Teams の既定のポリシーは、Teams の展開時に既存のビジネス ワークフローが中断されることがないように構成されています。</span><span class="sxs-lookup"><span data-stu-id="6cf71-117">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="6cf71-118">既定では、ユーザーへの VoIP 通話、PSTN 通話、フェデレーション通話は、ポリシーを更新して Teams への着信通話を有効にするまで、Skype for Business にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="6cf71-118">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="6cf71-119">このメカニズムにより、Teams のパイロットや展開を開始したときに、音声サービスに意図しない中断が発生するのが回避されます。</span><span class="sxs-lookup"><span data-stu-id="6cf71-119">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="6cf71-120">Teams のアップグレード ポリシーは、既定では、Teams または Skype for Business のどちらにチャットや通話がルーティングされるかを決める、Teams の相互運用ポリシーを受け継ぐレガシー モードで維持されます。</span><span class="sxs-lookup"><span data-stu-id="6cf71-120">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="6cf71-121">Teams のアップグレード ポリシーと Teams の相互運用ポリシーの動作は、すぐに「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス)](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)」に記載されているとおりに変わります。</span><span class="sxs-lookup"><span data-stu-id="6cf71-121">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="6cf71-122">Teams の相互運用ポリシーでは、次のように既定の設定が構成されています。</span><span class="sxs-lookup"><span data-stu-id="6cf71-122">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="6cf71-123">既定の設定の動作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6cf71-123">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="6cf71-124">**Skype for Business をすでに利用しているお客様の場合**、このポリシーは Skype for Business の通話を Skype for Business に移動させ、Teams の通話を Teams に移動させるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="6cf71-124">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="6cf71-125">このポリシーが有効な場合、PSTN 通話とフェデレーション通話は Skype for Business に移動されます。</span><span class="sxs-lookup"><span data-stu-id="6cf71-125">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="6cf71-126">**Skype for Business を利用していないお客様の場合**、このポリシーが有効であるときに、Teams では Teams ユーザー間の通話に加えて、PSTN 発信通話のみを利用できます。</span><span class="sxs-lookup"><span data-stu-id="6cf71-126">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="6cf71-127">Teams で PSTN 通話を受信するには、ユーザーに割り当てられている Teams の相互運用ポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cf71-127">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="6cf71-128">Skype for Business Online で使用する電話システムと通話プランのライセンスでプロビジョニングされ、Teams の相互運用のグローバル ポリシーが設定されているユーザーには、Teams で [通話] タブが有効化されます。こうしたユーザーは、管理者による管理操作なしで Teams から PSTN 通話の発信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6cf71-128">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="6cf71-129">PSTN 着信通話を受信するように Teams を設定する</span><span class="sxs-lookup"><span data-stu-id="6cf71-129">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="6cf71-130">Teams で PSTN 着信通話を受信するには、`CallingDefaultClient` パラメーターを Teams に設定する、対応する Teams の相互運用ポリシーとともに Teams のアップグレード ポリシーを適用して、Teams を既定の通話アプリケーションとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cf71-130">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cf71-131">広い範囲または組織レベルで変更を実施する前に、この設定を特定のユーザーのみに適用して、Teams のこの新しい通話機能を試してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6cf71-131">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="6cf71-132">レガシーの Teams のアップグレード ポリシーを使い続ける選択をする場合は、次の事前設定済の Teams 相互運用ポリシーを使用して、PSTN 着信通話を Teams にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="6cf71-132">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="6cf71-133">更新された Teams のアップグレード ポリシーを使うことを選んだ場合、TeamsOnly モードを自分のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cf71-133">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="6cf71-134">上記のポリシーの動作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6cf71-134">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="6cf71-135">**Skype for Business をすでに利用しているお客様の場合**、このポリシーは着信通話を Teams にリダイレクトするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="6cf71-135">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="6cf71-136">この場合、着信通話には VoIP (Teams と Skype for Business からの通話) と PSTN 通話が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6cf71-136">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="6cf71-137">**Skype for Business を利用していないお客様の場合**、このポリシーが有効であるときは、PSTN 通話は Teams で受信されます。</span><span class="sxs-lookup"><span data-stu-id="6cf71-137">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="6cf71-138">現時点では、`CallingDefaultClient` を Teams に変更すると、Skype for Business IP 電話への通話にも影響がおよびます。</span><span class="sxs-lookup"><span data-stu-id="6cf71-138">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="6cf71-139">Skype for Business IP 電話で着信通話を受信できなくなり、Teams クライアントでのみ着信音が鳴ります。</span><span class="sxs-lookup"><span data-stu-id="6cf71-139">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="6cf71-140">既存の認定済み SIP 電話のサポートについては、「[Skype for Business から Microsoft Teams へ: 機能のロードマップ](https://aka.ms/skype2teamsroadmap)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6cf71-140">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="6cf71-141">Teams でユーザーが PSTN 通話を受信する用に設定する方法</span><span class="sxs-lookup"><span data-stu-id="6cf71-141">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="6cf71-142">レガシーの Teams のアップグレード ポリシーを使用しているときに、Teams に通話をリダイレクトするには、上記の説明に従って Skype for Business の Windows PowerShell リモート セッションを介して Teams の相互運用ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="6cf71-142">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="6cf71-143">TeamsOnly モードを使うことを選ぶと、Microsoft Teams と Skype for Business の管理センターを介して、または Skype for Business のリモート Windows PowerShell セッションを介して、Teams に通話をリダイレクトするためにユーザーの共存モードを TeamsOnly に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6cf71-143">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="6cf71-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cf71-144">See also</span></span>
[<span data-ttu-id="6cf71-145">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="6cf71-145">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="6cf71-146">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="6cf71-146">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="6cf71-147">Microsoft Teams の通話プランが設定された電話システムの実践的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="6cf71-147">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="6cf71-148">Skype for Business PowerShell cmdlet reference (英語)</span><span class="sxs-lookup"><span data-stu-id="6cf71-148">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

<span data-ttu-id="6cf71-149">[Teams PowerShell cmdlet reference](https://docs.microsoft.com/powershell/module/teams) (英語)</span><span class="sxs-lookup"><span data-stu-id="6cf71-149">[Teams PowerShell cmdlet reference](https://docs.microsoft.com/powershell/module/teams)</span></span>
