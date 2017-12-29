---
title: "クイック スタート ガイド: Microsoft Teams での通話プランの設定"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams で通話プランを設定するためのクイック スタート ガイドです。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: bf2aa9b698516882ed5e48b4d9b7b639b74af40e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="1fc21-103">クイック スタート ガイド: Microsoft Teams での通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="1fc21-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="1fc21-104">このガイドでは、ユーザーが Teams で通話プランを利用できるように設定する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="1fc21-105">Teams の通話プランに関する 2017 年 12 月 12 日付けの発表「[Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)」(英語) をお読みください。</span><span class="sxs-lookup"><span data-stu-id="1fc21-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="1fc21-106">ロールアウトを成功させるため、このクイック スタート ガイドとともに、[実践的なガイダンス](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)と [FastTrack](https://aka.ms/cloudvoice) をご覧になることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1fc21-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="1fc21-107">Skype for Business が提供する Office 365 の機能の 1 つである通話プランを追加することで、Teams で公衆交換電話網 (PSTN) を介して固定電話や携帯電話に対する通話の発信および受信を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="1fc21-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Teams での通話](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="1fc21-109">Teams の [**通話**] タブを有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="1fc21-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="1fc21-110">Teams の [**通話**] タブを有効にして、ユーザーが PSTN 通話の発信と受信を行えるようにするには、電話システムと通話プランの利用に向けてユーザーをプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fc21-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="1fc21-111">この設定方法については、「[通話プランの設定](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1fc21-111">To learn how to set this up, read [Set up Calling Plans](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fc21-112">Teams で通話プランを設定する前に、以下の制限に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1fc21-112">Before configuring Calling Plans in Teams, please be aware of the following limitations:</span></span>
> * <span data-ttu-id="1fc21-113">**Teams では Hybrid Voice がサポートされない**: Teams では Hybrid Voice は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1fc21-113">**Hybrid Voice is not supported in Teams** - Hybrid Voice is currently not supported in Teams.</span></span> <span data-ttu-id="1fc21-114">Hybrid Voice をご利用のお客様は、Teams で通話を受信するためのポリシーをそのまま変更しないことをお勧めします。変更するとサービス中断の原因となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1fc21-114">Hybrid Voice customers are not advised to change any of the policies to receive calls in Teams, as this will cause service interruptions.</span></span>
> * <span data-ttu-id="1fc21-115">**Teams ではフェデレーション通話はサポートされない**: Teams ではフェデレーション通話 (テナント/会社間の通話) は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1fc21-115">**Federated calling is not supported in Teams** - Federated calling (calling between tenants/companies) is currently not supported in Teams.</span></span> <span data-ttu-id="1fc21-116">フェデレーション通話は、Teams でサポートされるようになるまで、通話の設定に関係なく常に Skype for Business にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-116">Federated calls will always be routed to Skype for Business regardless of how you configure calling, until it's supported in Teams.</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="1fc21-117">Teams の相互運用ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="1fc21-117">Teams interop policy configuration</span></span>
<span data-ttu-id="1fc21-118">Teams で通話を受信できるようにするには、Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) コマンドレットを使用して Windows PowerShell のリモート セッションを開いて、Teams に通話をリダイレクトするように Teams  の相互運用ポリシーを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fc21-118">To enable Teams to begin receiving calls, you'll need to update Teams interop policy, using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span> <span data-ttu-id="1fc21-119">Teams の相互運用ポリシーの詳細については、「[Microsoft Teams と Skype for Business の相互運用性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1fc21-119">For more information about Teams interop policy, see [Microsoft Teams and Skype for Business Interoperability](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span></span>

> [!TIP]
> <span data-ttu-id="1fc21-120">必要な PowerShell コマンドレットを検索するには、[Skype for Business PowerShell コマンドレットに関するドキュメント](https://docs.microsoft.com/powershell/module/skype)で [**フィルター**] ボックスに「CsTeamsInteropPolicy」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-120">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-interop-policy"></a><span data-ttu-id="1fc21-121">Teams の既定の相互運用ポリシー</span><span class="sxs-lookup"><span data-stu-id="1fc21-121">Default Teams interop policy</span></span>
<span data-ttu-id="1fc21-122">Teams の既定のポリシーは、Teams の展開時に既存のビジネス ワークフローが中断されることがないよう設定されています。</span><span class="sxs-lookup"><span data-stu-id="1fc21-122">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="1fc21-123">既定では、ユーザーへの VoIP 通話、PSTN 通話、フェデレーション通話は、ポリシーを更新して Teams への着信通話を有効にするまで、Skype for Business にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-123">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="1fc21-124">このメカニズムにより、Teams のパイロットや展開を開始したときに発生する可能性のある意図しない中断が回避されます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-124">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="1fc21-125">Teams の相互運用ポリシーでは次の既定の設定が指定されています。</span><span class="sxs-lookup"><span data-stu-id="1fc21-125">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="1fc21-126">既定の設定の動作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-126">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="1fc21-127">**Skype for Business をすでに利用しているお客様の場合**、このポリシーは Skype for Business の通話を Skype for Business に移動させ、Teams の通話を Teams に移動させるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="1fc21-127">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="1fc21-128">このポリシーが有効な場合、PSTN 通話とフェデレーション通話は Skype for Business に移動されます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-128">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="1fc21-129">**Skype for Business を利用していないお客様の場合**、このポリシーが有効であるときに、Teams では Teams ユーザー間の通話に加えて、PSTN 発信通話のみを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-129">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="1fc21-130">Teams で PSTN 通話を受信するには、ユーザーに割り当てられている Teams の相互運用ポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fc21-130">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="1fc21-131">Skype for Business Online で使用する電話システムと通話プランのライセンスでプロビジョニングされ、Teams の相互運用のグローバル ポリシーが設定されているユーザーには、Teams で [通話] タブが有効化されます。こうしたユーザーは、管理者による管理操作なしで Teams から PSTN 通話の発信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a><span data-ttu-id="1fc21-132">既定のポリシーを使用するように Teams を設定する方法</span><span class="sxs-lookup"><span data-stu-id="1fc21-132">How to configure Teams to use the default policy</span></span>
<span data-ttu-id="1fc21-133">既定では、Teams の相互運用のグローバル ポリシーは、テナントのすべてのユーザーに適用されます。このポリシーは上記の既定の設定で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-133">By default, global Teams interop policy is applied to all users in your tenant, and it is configured with the default settings as described above.</span></span> <span data-ttu-id="1fc21-134">何らかの理由により、ユーザーにこれとは異なるポリシーを割り当てている場合に既定の設定に戻すには、Teams の相互運用のグローバル ポリシーを Skype for Business の Windows PowerShell  リモート セッションを介して適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fc21-134">If for some reason you have granted different policies to your users and would like to revert to the default setting, you will need to apply the global Teams interop policy via Skype for Business remote Windows PowerShell session:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> <span data-ttu-id="1fc21-135">Teams の相互運用のグローバル ポリシーで既定の値を変更することもできますが、これらの値は変更しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1fc21-135">While it is possible to modify the global Teams interop policy from the default values, we strongly advise against it.</span></span> 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="1fc21-136">PSTN 着信通話を受信するように Teams を設定する</span><span class="sxs-lookup"><span data-stu-id="1fc21-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="1fc21-137">Teams で PSTN 着信通話を受信するには、`CallingDefaultClient` パラメーターを Teams に設定してある Teams の相互運用ポリシーを適用して、Teams を既定の通話アプリケーションとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fc21-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fc21-138">広い範囲または組織レベルで変更を実施する前に、この設定を特定のユーザーのみに適用して、Teams のこの新しい通話機能を試してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1fc21-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="1fc21-139">PSTN 着信通話を Teams にルーティングするには、次に示す事前に設定された Teams の相互運用ポリシーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-139">Consider using the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="1fc21-140">このポリシーの動作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-140">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="1fc21-141">**Skype for Business をすでに利用しているお客様の場合**、このポリシーは着信通話を Teams にリダイレクトするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="1fc21-141">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="1fc21-142">この場合、着信通話には VoIP (Teams と Skype for Business からの通話) と PSTN 通話が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-142">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> <span data-ttu-id="1fc21-143">フェデレーション通話はこれまでどおり Skype for Business で受信されます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-143">Federated calls will continue to be received in Skype for Business.</span></span> 
* <span data-ttu-id="1fc21-144">**Skype for Business を利用していないお客様の場合**、このポリシーが有効であるときに、PSTN 通話は Teams で受信されます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span> <span data-ttu-id="1fc21-145">現時点では、フェデレーション通話は Teams で**サポートされていません**。</span><span class="sxs-lookup"><span data-stu-id="1fc21-145">Federated calling is currently **not supported** in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="1fc21-146">現時点では、`CallingDefaultClient` を Teams に変更すると、Skype for Business IP 電話への通話にも影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="1fc21-146">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="1fc21-147">Skype for Business IP 電話で着信通話を受信できなくなり、Teams クライアントでのみ着信音が鳴ります。</span><span class="sxs-lookup"><span data-stu-id="1fc21-147">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="1fc21-148">既存の認定済み SIP 電話のサポートについては、「[Skype for Business から Microsoft Teams へ: 機能のロードマップ](https://aka.ms/skype2teamsroadmap)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1fc21-148">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a><span data-ttu-id="1fc21-149">PSTN 通話を受信するように Teams を設定する方法</span><span class="sxs-lookup"><span data-stu-id="1fc21-149">How to configure Teams to receive PSTN calls</span></span>
<span data-ttu-id="1fc21-150">Teams に通話をリダイレクトするには、上記の説明に従って Skype for Business の Windows PowerShell リモート セッションを介して Teams の相互運用ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-150">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a><span data-ttu-id="1fc21-151">通話の優先操作をユーザーが変更できるように Teams を設定する</span><span class="sxs-lookup"><span data-stu-id="1fc21-151">Configuring Teams to allow users to change their preferred calling experience</span></span>
<span data-ttu-id="1fc21-152">通話を Teams または Skype for Business のどちらで受信するかといった通話の優先操作をユーザーが自分で決定できるようにするには、`AllowEndUserClientOverride` パラメーターが有効になっている Teams のカスタムの相互運用ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fc21-152">To let users to make their own decision over the preferred calling experience, whether to receive calls in Teams or Skype for Business, you need to create a custom Teams interop policy that enables `AllowEndUserClientOverride` parameter.</span></span>

<span data-ttu-id="1fc21-153">ユーザーが通話の優先操作を選択できるようにする Teams の相互運用ポリシーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-153">The following is the example of Teams interop policy to enable user choice of the preferred calling experience:</span></span>

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="1fc21-154">このカスタム ポリシーをユーザーに適用すると、Teams クライアントのユーザーは通話の優先アプリケーションを自ら変更するためのオプションを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1fc21-154">Once this custom policy is applied to the users, the option to change the preferred calling application will be available in Teams client for users to make the changes themselves.</span></span>

![優先する通話アプリケーションのオプション](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> <span data-ttu-id="1fc21-156">広い範囲または組織レベルで変更を実施する前に、この設定を特定のユーザーのみに適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1fc21-156">It is recommended that you apply this configuration to an initial set of users prior to making wider or organization level changes.</span></span>

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a><span data-ttu-id="1fc21-157">Teams のカスタムの相互運用ポリシーを作成、適用する方法</span><span class="sxs-lookup"><span data-stu-id="1fc21-157">How to create and apply the custom Teams interop policy</span></span>
<span data-ttu-id="1fc21-158">上記に示した Teams のカスタムの相互運用ポリシーを作成するには、Skype for Business の Windows PowerShell リモート セッションを介して次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1fc21-158">To create the custom Teams interop policy as described above via Skype for Business remote Windows PowerShell session, perform the following:</span></span>

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a><span data-ttu-id="1fc21-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fc21-159">See also</span></span>
[<span data-ttu-id="1fc21-160">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="1fc21-160">Set up Calling Plans</span></span>](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[<span data-ttu-id="1fc21-161">Microsoft Teams と Skype for Business の相互運用性</span><span class="sxs-lookup"><span data-stu-id="1fc21-161">Microsoft Teams and Skype for Business Interoperability</span></span>](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[<span data-ttu-id="1fc21-162">Microsoft Teams の通話プランが設定された電話システムの実践的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="1fc21-162">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="1fc21-163">Skype for Business PowerShell cmdlet reference (英語)</span><span class="sxs-lookup"><span data-stu-id="1fc21-163">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

<span data-ttu-id="1fc21-164">[Teams PowerShell cmdlet reference](https://docs.microsoft.com/powershell/module/teams) (英語)</span><span class="sxs-lookup"><span data-stu-id="1fc21-164">[PowerShell cmdlet reference for Teams](https://docs.microsoft.com/powershell/module/teams)</span></span>
