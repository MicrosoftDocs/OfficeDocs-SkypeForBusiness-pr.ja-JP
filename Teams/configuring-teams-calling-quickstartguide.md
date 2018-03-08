---
title: "クイック スタート ガイド - Microsoft チームのプランの呼び出しを構成します。"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Microsoft のチームで通話プランを構成するためのクイック スタート ガイド"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: e38317132190b3035f37509d1fa7b2da5e4785c7
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="152bf-103">クイック スタート ガイド: Microsoft チームのプランの呼び出しを構成します。</span><span class="sxs-lookup"><span data-stu-id="152bf-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="152bf-104">このガイドはできる一連の上のユーザーと実行しているので、チームのプランの呼び出しを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="152bf-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="152bf-105">チームのプランの呼び出しの 2017、12 月 12日お知らせを読む:[インテリジェント通信チーム呼び出しには、次の手順を移動します。](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="152bf-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="152bf-106">、このクイック スタート ガイドと並行、使用すること、[実用的なガイダンス](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)や[FastTrack](https://aka.ms/cloudvoice)を計画し、正常に展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="152bf-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="152bf-107">-[Skype for Business で、Office 365 機能 - プランの呼び出しを追加して land 線と公衆交換電話網 (PSTN) を使って携帯電話の電話の発信や受信にチームを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="152bf-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![チーム呼び出し](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="152bf-109">チームでは、[**通話**] タブを有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="152bf-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="152bf-p101">チームでは、[**通話**] タブを有効にし、ユーザーが PSTN 通話を送受信できるようにする、ユーザーのプロビジョニングを電話システムとプランの呼び出しの必要があります。これをセットアップする方法については、[プランの呼び出しを設定する](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="152bf-p101">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans. To learn how to set this up, read [Set up Calling Plans](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="152bf-112">プランの呼び出しを設定する、チームで、前に注意してください次の制限事項。</span><span class="sxs-lookup"><span data-stu-id="152bf-112">Before configuring Calling Plans in Teams, please be aware of the following limitations:</span></span>
> * <span data-ttu-id="152bf-p102">**ハイブリッド音声は、チームでサポートされていない**ハイブリッド ボイスは現在サポートされていませんチームでします。ハイブリッド音声顧客がサービス中断これにより、チームで通話を受信するポリシーのいずれかを変更するのにはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="152bf-p102">**Hybrid Voice is not supported in Teams** - Hybrid Voice is currently not supported in Teams. Hybrid Voice customers are not advised to change any of the policies to receive calls in Teams, as this will cause service interruptions.</span></span>
> * <span data-ttu-id="152bf-p103">**チームでは、フェデレーションの通話はサポートされていない**(テナント/会社間での呼び出し) フェデレーション通話は現在サポートされていませんチームでします。フェデレーションの着信通話、チームでサポートされているまでを構成する方法に関係なく、Skype for Business に常にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="152bf-p103">**Federated calling is not supported in Teams** - Federated calling (calling between tenants/companies) is currently not supported in Teams. Federated calls will always be routed to Skype for Business regardless of how you configure calling, until it's supported in Teams.</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="152bf-117">チームの相互運用ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="152bf-117">Teams interop policy configuration</span></span>
<span data-ttu-id="152bf-p104">チームが着信を受信し始めますを有効にする必要がありますチームの相互運用ポリシーを更新する、skype for Business リモート Windows PowerShell セッションを使用して[`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype)チームに着信をリダイレクトするのには、コマンドレットします。チームの相互運用ポリシーの詳細については、 [Microsoft チーム」と「Skype for Business の相互運用性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="152bf-p104">To enable Teams to begin receiving calls, you'll need to update Teams interop policy, using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams. For more information about Teams interop policy, see [Microsoft Teams and Skype for Business Interoperability](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span></span>

> [!TIP]
> <span data-ttu-id="152bf-120">必要がある PowerShell コマンドレットを検索するには、 [Skype for Business PowerShell コマンドレットのドキュメント](https://docs.microsoft.com/powershell/module/skype)で**フィルター** ] ボックスに"CsTeamsInteropPolicy"を入力します。</span><span class="sxs-lookup"><span data-stu-id="152bf-120">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-interop-policy"></a><span data-ttu-id="152bf-121">チームの既定の相互運用ポリシー</span><span class="sxs-lookup"><span data-stu-id="152bf-121">Default Teams interop policy</span></span>
<span data-ttu-id="152bf-p105">チームが、既定のポリシー設定を既存のビジネス ワークフローがチーム展開中に中断されないように設計されています。既定では、VoIP、PSTN とフェデレーションの呼び出しをユーザーに引き続きチームに着信通話を有効にするポリシーを更新するまでに Skype for Business にルーティングされます。これによりがないこと意図しない音声サービス中断を開始するパイロット チームを展開するとします。</span><span class="sxs-lookup"><span data-stu-id="152bf-p105">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment. By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams. This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="152bf-125">チームの相互運用ポリシーには、次の既定の構成がされています。</span><span class="sxs-lookup"><span data-stu-id="152bf-125">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="152bf-126">既定の構成の動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="152bf-126">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="152bf-p106">**既存の Skype for Business ユーザーに**、このポリシーが対応している、Skype for Business 通話は Skype for Business に転送され、チーム呼び出しはチームに転送されることを確認します。PSTN とフェデレーションの呼び出しが開かれ Skype for Business このポリシーが有効な場合。</span><span class="sxs-lookup"><span data-stu-id="152bf-p106">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams. PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="152bf-p107">**Skype for Business の場合**、チームのユーザーの通話のほか、PSTN 通話の発信のみをチームで使われます。チームで PSTN 通話を受けるには、ユーザーに割り当てられているチームの相互運用ポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="152bf-p107">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams. You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="152bf-131">電話システムとプランの呼び出しライセンスでプロビジョニングされているユーザーと使用する skype for Business Online では、既定のグローバル チーム相互運用ポリシーを使用して構成されたチームで有効になっている [通話] タブが表示されますをチームからの送信の PSTN 電話をかけることができます。管理者が管理の操作を実行することなしです。</span><span class="sxs-lookup"><span data-stu-id="152bf-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a><span data-ttu-id="152bf-132">既定のポリシーを使用してチームを構成する方法</span><span class="sxs-lookup"><span data-stu-id="152bf-132">How to configure Teams to use the default policy</span></span>
<span data-ttu-id="152bf-p108">既定では、テナントのすべてのユーザーにグローバル チームの相互運用ポリシーを適用し、上記の説明に従って、既定の設定で構成します。何らかの理由をユーザーに別のポリシーを与えたいし、考えての既定の設定に戻すには場合、は、リモートの Windows PowerShell セッションをビジネス用 Skype でグローバル チーム相互運用ポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="152bf-p108">By default, global Teams interop policy is applied to all users in your tenant, and it is configured with the default settings as described above. If for some reason you have granted different policies to your users and would like to revert to the default setting, you will need to apply the global Teams interop policy via Skype for Business remote Windows PowerShell session:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> <span data-ttu-id="152bf-135">既定値からグローバル チームの相互運用ポリシーを変更することはできますが、お強く推奨に対してします。</span><span class="sxs-lookup"><span data-stu-id="152bf-135">While it is possible to modify the global Teams interop policy from the default values, we strongly advise against it.</span></span> 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="152bf-136">チームが着信 PSTN 通話を受けるを構成します。</span><span class="sxs-lookup"><span data-stu-id="152bf-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="152bf-137">PSTN 通話の着信を受信するには、チームでに既定値を使用してチームの相互運用ポリシーを適用してアプリケーションを呼び出すとチームを構成する必要があります`CallingDefaultClient`チームにパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="152bf-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="152bf-138">ユーザーをチームで魅力的な新しい通話機能を使ってみるを広げる組織レベルの変更を加えるよりも前の初期セットには、この設定を適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="152bf-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="152bf-139">次事前構成されたチームの相互運用ポリシーを使用してチーム呼び出し着信 PSTN をルーティングすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="152bf-139">Consider using the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="152bf-140">このポリシーの動作、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="152bf-140">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="152bf-p109">**既存の Skype for Business ユーザーに**、このポリシーが対応しているチームの着信通話をリダイレクトします。これには、(チームと Skype for Business) から VoIP と PSTN 通話の両方が含まれます。フェデレーションの通話は引き続き Skype for Business で受信します。</span><span class="sxs-lookup"><span data-stu-id="152bf-p109">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams. This includes both VoIP (from Teams and Skype for Business) and PSTN calls. Federated calls will continue to be received in Skype for Business.</span></span> 
* <span data-ttu-id="152bf-p110">**Skype for Business の場合**と実際には、PSTN 通話が受信するチームでします。フェデレーションの通話は、現在チームでは**サポートされていません**。</span><span class="sxs-lookup"><span data-stu-id="152bf-p110">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams. Federated calling is currently **not supported** in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="152bf-p111">現時点では、変更する`CallingDefaultClient`チームにも影響 skype 通話ビジネス IP 電話用します。着信通話られ、携帯電話に受信できませんが、リング チーム クライアントのみをされます。既存の認定 SIP 電話のサポートについては、 [Skype for Business に Microsoft チーム機能ロードマップ](https://aka.ms/skype2teamsroadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="152bf-p111">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones. Incoming calls will not be received on the phones and will only ring Teams clients. Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a><span data-ttu-id="152bf-149">PSTN 通話を受けるチームを構成する方法</span><span class="sxs-lookup"><span data-stu-id="152bf-149">How to configure Teams to receive PSTN calls</span></span>
<span data-ttu-id="152bf-150">チーム呼び出しをリダイレクトするのには、リモートの Windows PowerShell セッションをビジネス用 Skype で上記のように、チームの相互運用ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="152bf-150">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a><span data-ttu-id="152bf-151">ユーザーに、好みの呼び出しのエクスペリエンスを変更できるようにチームを構成します。</span><span class="sxs-lookup"><span data-stu-id="152bf-151">Configuring Teams to allow users to change their preferred calling experience</span></span>
<span data-ttu-id="152bf-152">有効にするカスタム チーム相互運用ポリシーの作成に必要なチームまたは Skype for Business で通話を受信するかどうかは、好みの呼び出し元エクスペリエンスをユーザーが独自の判断できるように、`AllowEndUserClientOverride`パラメーターします。</span><span class="sxs-lookup"><span data-stu-id="152bf-152">To let users to make their own decision over the preferred calling experience, whether to receive calls in Teams or Skype for Business, you need to create a custom Teams interop policy that enables `AllowEndUserClientOverride` parameter.</span></span>

<span data-ttu-id="152bf-153">次には、好みの呼び出し元エクスペリエンスのユーザーの選択を有効にするチームの相互運用ポリシーの例を示します。</span><span class="sxs-lookup"><span data-stu-id="152bf-153">The following is the example of Teams interop policy to enable user choice of the preferred calling experience:</span></span>

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="152bf-154">このユーザー設定のポリシーを適用するには、ユーザーに、好みの呼び出し元のアプリケーションを変更するオプションは自体を変更するユーザーのチーム クライアントでは使用されます。</span><span class="sxs-lookup"><span data-stu-id="152bf-154">Once this custom policy is applied to the users, the option to change the preferred calling application will be available in Teams client for users to make the changes themselves.</span></span>

![好みの呼び出し元アプリケーション オプション](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> <span data-ttu-id="152bf-156">幅または組織レベルを変更する前にユーザーの初期セットには、この設定を適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="152bf-156">It is recommended that you apply this configuration to an initial set of users prior to making wider or organization level changes.</span></span>

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a><span data-ttu-id="152bf-157">作成してチームのユーザー設定の相互運用ポリシーを適用する方法</span><span class="sxs-lookup"><span data-stu-id="152bf-157">How to create and apply the custom Teams interop policy</span></span>
<span data-ttu-id="152bf-158">チームのユーザー設定の相互運用ポリシーを作成するには、リモートの Windows PowerShell セッションをビジネス用 Skype で上記のように、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="152bf-158">To create the custom Teams interop policy as described above via Skype for Business remote Windows PowerShell session, perform the following:</span></span>

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a><span data-ttu-id="152bf-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="152bf-159">See also</span></span>
[<span data-ttu-id="152bf-160">プランの呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="152bf-160">Set up Calling Plans</span></span>](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[<span data-ttu-id="152bf-161">Microsoft チーム」と「Skype for Business の相互運用性</span><span class="sxs-lookup"><span data-stu-id="152bf-161">Microsoft Teams and Skype for Business Interoperability</span></span>](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[<span data-ttu-id="152bf-162">電話システムで Microsoft チームで通話プランに関する実用的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="152bf-162">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="152bf-163">Skype for Business PowerShell コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="152bf-163">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="152bf-164">チームの PowerShell コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="152bf-164">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
