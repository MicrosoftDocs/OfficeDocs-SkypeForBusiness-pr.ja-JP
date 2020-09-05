---
title: 外部アクセスの管理 (フェデレーション)
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: Teams または IT 管理者は、他のドメインの外部アクセス (フェデレーション) を構成して、それらのドメインのユーザーが Teams に参加できるようにすることができます。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 1acc8bea66791c7e8cfc38cae2d394b6360ceec9
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395406"
---
<a name="manage-external-access-in-microsoft-teams"></a><span data-ttu-id="e8c8e-103">Microsoft Teams での外部アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="e8c8e-103">Manage external access in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="e8c8e-104">外部アクセスは、teams ユーザーが Teams で自分との会議を検索、通話、チャット、セットアップできるようにするための手段です。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-104">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with you in Teams.</span></span> <span data-ttu-id="e8c8e-105">また、外部アクセスを使用して、まだ Skype for Business (オンラインとオンプレミス) および Skype (プレビュー版) を使用している外部ユーザーと通信することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-105">You can also use external access to communicate with external users who are still using Skype for Business (online and on-premises) and Skype (in preview).</span></span>

<span data-ttu-id="e8c8e-106">外部のユーザーがチームとチャネルにアクセスできるようにする場合に適した方法は、ゲスト アクセスです。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-106">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="e8c8e-107">外部アクセスとゲスト アクセスの違いの詳細については、「[外部アクセスとゲスト アクセスの比較](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-107">For more information about the differences between external access and guest access, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span> 

<span data-ttu-id="e8c8e-108">以下のような場合に外部アクセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-108">Use external access when:</span></span>
  
- <span data-ttu-id="e8c8e-109">別ドメインに共同作業が必要なユーザーがいる場合。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-109">You have users in different domains who need to collaborate.</span></span> <span data-ttu-id="e8c8e-110">たとえば、Rob@contoso.com と Ann@northwindtraders.com が、contoso.com ドメインおよび northwindtraders.com ドメインの他のユーザーと一緒にプロジェクトの共同作業を行う場合です。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-110">For example, Rob@contoso.com and Ann@northwindtraders.com are working on a project together along with some others in the contoso.com and northwindtraders.com domains.</span></span>

- <span data-ttu-id="e8c8e-111">組織内のユーザーが、Teams を使用して組織外の特定の会社のユーザーに連絡する必要場ある場合。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-111">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="e8c8e-112">ユーザーのメール アドレスを使用して、世界中の Teams のユーザーは誰でもそのユーザーを検索して連絡を取れるようにする場合。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-112">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e8c8e-113">Teams クライアントを使って外部ユーザーと通信するには (ユーザーが Teams または Skype for Business を使用しているかどうかにかかわらず)、Teams ユーザーが Skype for Business Online を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-113">To use the Teams client to communicate with an external user (whether that user is using Teams or Skype for Business), the Teams user must be homed in Skype for Business Online.</span></span>

## <a name="plan-for-external-access"></a><span data-ttu-id="e8c8e-114">外部アクセスの計画</span><span class="sxs-lookup"><span data-stu-id="e8c8e-114">Plan for external access</span></span>

<span data-ttu-id="e8c8e-115">Teams では既定で外部アクセスが有効になっています。つまり、組織はすべての外部ドメインと通信できます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-115">By default, external access is turned on in Teams, which means that your organization can communicate with all external domains.</span></span> <span data-ttu-id="e8c8e-116">禁止ドメインを追加すると、他のすべてのドメインが許可され、許可ドメインを追加すると、他のすべてのドメインが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-116">If you add blocked domains, all other domains will be allowed; and if you add allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="e8c8e-117">Teams 管理センターで外部アクセスを設定するには、次の 3 つのシナリオがあります (**[組織全体の設定]**  >  **[外部アクセス]**)。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-117">There are three scenarios for setting up external access in the Teams admin center (**Org-wide settings** > **External access**):</span></span>

- <span data-ttu-id="e8c8e-118">**開いているフェデレーション**: これは Teams の既定の設定です。組織内のユーザーが任意のドメインの組織外ユーザーとの会議の検索、呼び出し、チャット、設定を行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-118">**Open federation**: This is the default setting in Teams, and it lets people in your organization find, call, chat, and set up meetings with people external to your organization in any domain.</span></span>

    <span data-ttu-id="e8c8e-119">このシナリオでは、ユーザーはすべての外部ドメインと通信することができます。この外部ドメインは、Teams または Skype for Business を実行しており、開いているフェデレーションを使用しているか、ユーザーのドメインを許可リストに追加しています。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-119">In this scenario, your users can communicate with all external domains that are running Teams or Skype for Business AND are using open federation OR have added your domain to their allow list.</span></span>

- <span data-ttu-id="e8c8e-120">**特定のドメインを許可する**: **[許可]** リストにドメインを追加して、外部アクセスを許可ドメインのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-120">**Allow specific domains**: By adding domains to an **Allow** list, you limit external access to only the allowed domains.</span></span> <span data-ttu-id="e8c8e-121">許可ドメインのリストを設定すると、他のすべてのドメインが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-121">Once you set up a list of allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="e8c8e-122">特定のドメインを許可するには、**[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、**[このドメインで実行するアクション]** をクリックし、**[許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-122">To allow specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Allowed**.</span></span>

- <span data-ttu-id="e8c8e-123">**特定のドメインを禁止する** - **[禁止]** リストにドメインを追加すると、禁止したもの*以外の*すべての外部ドメインと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-123">**Block specific domains** - By adding domains to a **Block** list, you can communicate with all external domains *except* the ones you've blocked.</span></span> <span data-ttu-id="e8c8e-124">特定のドメインを禁止するには、**[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、**[このドメインで実行するアクション]** をクリックし、**[禁止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-124">To block specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Blocked**.</span></span> <span data-ttu-id="e8c8e-125">禁止ドメインのリストを設定すると、他のすべてのドメインが許可されます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-125">Once you set up a list of blocked domains, all other domains will be allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="e8c8e-126">組織の外部アクセスを無効にしても、外部ユーザーは匿名の参加を通じて会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-126">If you turn off external access in your organization, external users can still join meetings through anonymous join.</span></span> <span data-ttu-id="e8c8e-127">詳細については、「 [Teams で会議の設定を管理](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-127">To learn more, see [Manage meeting settings in Teams](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams).</span></span>

## <a name="allow-or-block-domains"></a><span data-ttu-id="e8c8e-128">ドメインの許可または禁止</span><span class="sxs-lookup"><span data-stu-id="e8c8e-128">Allow or block domains</span></span>

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a><span data-ttu-id="e8c8e-129">手順 1-組織が別のチームまたは Skype for Business 組織と通信できるようにする</span><span class="sxs-lookup"><span data-stu-id="e8c8e-129">Step 1 - Enable your organization to communicate with another Teams or Skype for Business organizations</span></span>

<span data-ttu-id="e8c8e-130">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="e8c8e-130">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e8c8e-131">左側のナビゲーションで、**[組織全体の設定]**  >  **[外部アクセス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-131">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="e8c8e-132">**[Users can communicate with other Skype for Business and Teams users]**(ユーザーは他の Skype for Business および Teams ユーザーと通信できます) 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-132">Turn on the **Users can communicate with other Skype for Business and Teams users** setting.</span></span>

     ![[ユーザーは他の Skype for Business および Teams ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-2.png)<span data-ttu-id="e8c8e-134">。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-134">.</span></span>

3. <span data-ttu-id="e8c8e-135">すべての Teams の組織に対して、組織内のユーザーとの通信を許可する場合は、手順 5 に進みます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-135">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span>

4. <span data-ttu-id="e8c8e-136">組織内のユーザーと通信できる組織を制限するには、特定のドメイン以外のすべてを許可する方法と、特定のドメインのみを許可する方法があります。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-136">If you want to limit the organizations that can communicate with users in your organization, you can either allow all except some domains, or you can allow only specific domains.</span></span> 

    - <span data-ttu-id="e8c8e-137">特定のドメイン以外のすべてを許可するには、**[ドメインの追加]** をクリックして禁止するドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-137">To allow all except some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="e8c8e-138">**[ドメインの追加]** ウィンドウで、ドメイン名を入力して **[禁止]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-138">In the **Add a domain** pane, type the domain name, click **Blocked**, and then click **Done**.</span></span> 
    - <span data-ttu-id="e8c8e-139">通信を特定の組織に制限するには、それらの組織のドメインを **[許可]** の状態でリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-139">To limit communications to specific organizations, add those domains to the list with a status of **Allowed**.</span></span> <span data-ttu-id="e8c8e-140">[許可] リストにいずれかのドメインを追加すると、他の組織との通信は、[許可] リストにドメインが表示される組織との通信のみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-140">Once you have added any domain to the Allow list, communications with other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 

5. <span data-ttu-id="e8c8e-141">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-141">Click **Save**.</span></span>

6. <span data-ttu-id="e8c8e-142">他の Teams の組織の管理者も同じ手順を実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-142">Make sure the admin in the other Teams organization completes these same steps.</span></span> <span data-ttu-id="e8c8e-143">たとえば、他のある組織でその組織のユーザーと通信できる組織を制限している場合は、その組織の管理者は、**許可ドメイン**のリストにお客様の会社のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-143">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit the organizations that can communicate with their users.</span></span>

### <a name="step-2---test-it"></a><span data-ttu-id="e8c8e-144">手順 2 - テスト</span><span class="sxs-lookup"><span data-stu-id="e8c8e-144">Step 2 - Test it</span></span>

<span data-ttu-id="e8c8e-145">設定をテストするには、組織のファイアウォールの外側にいる Teams ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-145">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
1. <span data-ttu-id="e8c8e-146">お客様ともう 1 つの組織の管理者が [**外部アクセス**] 設定の変更をそれぞれ完了すると、テストを開始できます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-146">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>

2. <span data-ttu-id="e8c8e-147">Teams アプリで、メール アドレスを使用してユーザーを検索し、チャットの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-147">In the Teams app, search for the person by email address, and send a request to chat.</span></span>

3. <span data-ttu-id="e8c8e-148">お客様宛にチャットの要求を送信するよう、Teams の連絡先に依頼します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-148">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="e8c8e-149">相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-149">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="e8c8e-150">ファイアウォールに問題があるかどうかをテストする別の方法は、ファイアウォールの外側の WiFi 環境に移動することです。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-150">Another way to test whether the problem is your firewall is to go to a WiFi location not behind your firewall.</span></span> <span data-ttu-id="e8c8e-151">コーヒー ショップなどから、Teams を使用して連絡先にチャットの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-151">such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="e8c8e-152">メッセージを WiFi 環境からは送信できるが、職場からは送信できない場合、問題の原因は職場のファイアウォールであることが特定できます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-152">If the message goes through at the WiFi location, but does not when you're at work, then you know the problem is your firewall.</span></span>

> [!NOTE]
> <span data-ttu-id="e8c8e-153">これは、ユーザーともう 1 人のユーザーの両方が外部アクセスを有効にしてお互いのドメインを許可している場合に可能になります。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-153">If you and another user both turn on external access and allow one another's domains, this will work.</span></span> <span data-ttu-id="e8c8e-154">正常に動作しない場合は、もう 1 人のユーザーの構成でユーザーのドメインが禁止されていないかを確認してもらいます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-154">If it doesn't work, the other user should make sure their configuration isn't blocking your domain.</span></span>


## <a name="communicate-with-skype-users-in-preview"></a><span data-ttu-id="e8c8e-155">Skype ユーザーとの通信 (プレビュー段階)</span><span class="sxs-lookup"><span data-stu-id="e8c8e-155">Communicate with Skype users (in preview)</span></span>

<span data-ttu-id="e8c8e-156">組織内の Teams ユーザーが Skype ユーザーとチャットや通話をできるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-156">Follow these steps to let Teams users in your organization chat with and call Skype users.</span></span> <span data-ttu-id="e8c8e-157">この手順を実行すると、Teams ユーザーと Skype ユーザーとが、互いを検索したり、1 対 1 のテキストのみの会話や音声/ビデオ通話を開始したりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-157">Teams users can then search for and start a one-on-one text-only conversation or an audio/video call with Skype users and vice versa.</span></span>

<span data-ttu-id="e8c8e-158">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="e8c8e-158">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e8c8e-159">左側のナビゲーションで、**[組織全体の設定]**  >  **[外部アクセス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-159">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="e8c8e-160">**[ユーザーは Skype ユーザーと通信できます]** 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-160">Turn on the **Users can communicate with Skype users** setting.</span></span>

    ![[ユーザーは Skype ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-5.png)<span data-ttu-id="e8c8e-162">.</span><span class="sxs-lookup"><span data-stu-id="e8c8e-162">.</span></span>

<span data-ttu-id="e8c8e-163">Teams ユーザーと Skype ユーザーが通信できるようにする方法、および適用される制限事項の詳細については、「[Teams と Skype の相互運用性](teams-skype-interop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-163">To learn more about the ways that Teams users and Skype users can communicate, including limitations that apply, see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>

## <a name="common-external-access-scenarios"></a><span data-ttu-id="e8c8e-164">一般的な外部アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="e8c8e-164">Common external access scenarios</span></span>

<span data-ttu-id="e8c8e-165">以下のセクションでは、一般的な外部アクセスシナリオに対してフェデレーションを有効にする方法と、TeamsUpgradePolicy での着信チャットと通話の配信を決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-165">The following sections describe how to enable federation for common external access scenarios, and how the TeamsUpgradePolicy determines delivery of incoming chats and calls.</span></span>

### <a name="enable-federation"></a><span data-ttu-id="e8c8e-166">フェデレーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="e8c8e-166">Enable federation</span></span>

<span data-ttu-id="e8c8e-167">組織内のユーザーが別の組織のユーザーと通信できるようにするには、両方の組織がフェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-167">To enable users in your organization to communicate with users in another organization, both organizations must enable federation.</span></span> <span data-ttu-id="e8c8e-168">特定の組織に対してフェデレーションを有効にする手順は、組織が純粋にオンライン、ハイブリッド、純粋にオンプレミスのいずれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-168">The steps to enable federation for a given organization depend on whether the organization is purely online, hybrid, or purely on-premises.</span></span>

|<span data-ttu-id="e8c8e-169">**組織の場合**</span><span class="sxs-lookup"><span data-stu-id="e8c8e-169">**If your organization is**</span></span> |<span data-ttu-id="e8c8e-170">**次のようにフェデレーションを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="e8c8e-170">**Enable federation as follows**</span></span>  |
|:---------|:-----------------------|
|<span data-ttu-id="e8c8e-171">オンプレミスの Skype for Business がないオンライン。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-171">Online with no Skype for Business on-premises.</span></span> <span data-ttu-id="e8c8e-172">これには、チームのユーザーまたは Skype for Business Online ユーザーがいる組織も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-172">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span>| <span data-ttu-id="e8c8e-173">Teams 管理センターを使用している場合:</span><span class="sxs-lookup"><span data-stu-id="e8c8e-173">If using Teams Admin Center:</span></span> <br><span data-ttu-id="e8c8e-174">-[外部アクセス] で [ **ユーザーが他の Skype For business および Teams ユーザーと通信できる** ようにする] 設定が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-174">-   Make sure the **Users can communicate with other Skype for Business and Teams users** setting is enabled in External Access.</span></span><br><span data-ttu-id="e8c8e-175">-開いているフェデレーション (他のドメインとのフェデレーションを可能にする) を使用していない場合は、許可リストに外部ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-175">- If you are not using open federation (which allows federation with any other domain), then add the external domain to the Allowed list.</span></span><br><br><span data-ttu-id="e8c8e-176">PowerShell を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="e8c8e-176">If using PowerShell:</span></span><br><span data-ttu-id="e8c8e-177">-テナントがフェデレーションに対して有効になっていることを確認します。 `Get-CsTenantFederationConfiguration` 表示する必要があり `AllowFederatedUsers=true` ます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-177">- Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowFederatedUsers=true`.</span></span> <br><span data-ttu-id="e8c8e-178">-ユーザーの有効な値がにあることを確認し `CsExternalAccessPolicy` `EnableFederationAccess=true` ます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-178">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnableFederationAccess=true`.</span></span><br><span data-ttu-id="e8c8e-179">-オープンフェデレーションを使用していない場合は、ターゲットドメインがに表示されていることを確認し `AllowedDomains` `CsTenantFederationConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-179">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains` of `CsTenantFederationConfiguration`.</span></span> |
|<span data-ttu-id="e8c8e-180">純粋なオンプレミス</span><span class="sxs-lookup"><span data-stu-id="e8c8e-180">Pure on-premises</span></span> | <span data-ttu-id="e8c8e-181">オンプレミスツールでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-181">In on-premises tools:</span></span> <br><span data-ttu-id="e8c8e-182">-でフェデレーションが有効になっていることを確認 `CsAccessEdgeConfiguration` します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-182">- Ensure federation is enabled in `CsAccessEdgeConfiguration`.</span></span><br><span data-ttu-id="e8c8e-183">- `ExternalAccessPolicy` (グローバルポリシー、サイトポリシー、またはユーザーが割り当てられたポリシーのいずれかを通じて) ユーザーのフェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-183">- Ensure federation for the user is enabled through `ExternalAccessPolicy` (either through the global policy, site policy, or user assigned policy).</span></span> <br> <span data-ttu-id="e8c8e-184">-オープンフェデレーションを使用していない場合は、ターゲットドメインがに表示されていることを確認し `AllowedDomains` ます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-184">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains`.</span></span> |
|<span data-ttu-id="e8c8e-185">一部のユーザー (Skype for Business または Teams のいずれか) とオンプレミスの一部のユーザーとのハイブリッド。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-185">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span> | <span data-ttu-id="e8c8e-186">オンラインとオンプレミスの両方の組織に対して、上記の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-186">Follow above steps for both online and on-premises organizations.</span></span> |

### <a name="delivery-of-incoming-chats-and-calls"></a><span data-ttu-id="e8c8e-187">チャットと通話の着信の配信</span><span class="sxs-lookup"><span data-stu-id="e8c8e-187">Delivery of incoming chats and calls</span></span> 

<span data-ttu-id="e8c8e-188">フェデレーション組織からの着信チャットと通話は、TeamsUpgradePolicy の受信者ユーザーモードに応じて、ユーザーのチームまたは Skype for Business クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-188">Incoming chats and calls from a federation organization will land in the user’s Teams or Skype for Business client depending on the recipient user’s mode in TeamsUpgradePolicy.</span></span>

|<span data-ttu-id="e8c8e-189">**目的**</span><span class="sxs-lookup"><span data-stu-id="e8c8e-189">**If you want to**</span></span> |<span data-ttu-id="e8c8e-190">**手順:**</span><span class="sxs-lookup"><span data-stu-id="e8c8e-190">**Do this:**</span></span>  |
|:---------|:-----------------------|
| <span data-ttu-id="e8c8e-191">フェデレーションされたチャットの着信と、ユーザーのチームクライアントで通話を受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-191">Ensure incoming federated chats and calls arrive in the user’s Teams client:</span></span> | <span data-ttu-id="e8c8e-192">ユーザーをチームのみに設定します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-192">Configure your users to be TeamsOnly.</span></span>
| <span data-ttu-id="e8c8e-193">フェデレーションされたチャットの着信と、ユーザーの Skype for Business クライアントで通話を受信できるようにする</span><span class="sxs-lookup"><span data-stu-id="e8c8e-193">Ensure incoming federated chats and calls arrive in the user’s Skype for Business client</span></span> | <span data-ttu-id="e8c8e-194">ユーザーは、TeamsOnly 以外のモードに設定します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-194">Configure your users to be in any mode other than TeamsOnly.</span></span> |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a><span data-ttu-id="e8c8e-195">組織内のユーザーと Skype のコンシューマーユーザーの間のフェデレーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="e8c8e-195">Enable federation between users in your organization and consumer users of Skype</span></span>

<span data-ttu-id="e8c8e-196">組織内のユーザーと Skype のコンシューマーユーザーの間でフェデレーションを有効にするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-196">To enable federation between users in your organization and consumer users of Skype:</span></span>

|<span data-ttu-id="e8c8e-197">**組織の場合**</span><span class="sxs-lookup"><span data-stu-id="e8c8e-197">**If your organization is**</span></span> |<span data-ttu-id="e8c8e-198">**次のようにコンシューマーフェデレーションを有効にする**</span><span class="sxs-lookup"><span data-stu-id="e8c8e-198">**Enable consumer federation as follows**</span></span>  |
|:---------|:-----------------------|
| <span data-ttu-id="e8c8e-199">オンプレミスの Skype for Business を使用しない純粋なオンライン。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-199">Pure online with no Skype for Business on-premises.</span></span>  <span data-ttu-id="e8c8e-200">これには、チームのユーザーまたは Skype for Business Online ユーザーがいる組織も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-200">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span> | <span data-ttu-id="e8c8e-201">Teams 管理センターを使用している場合:</span><span class="sxs-lookup"><span data-stu-id="e8c8e-201">If using Teams Admin Center:</span></span> <br><span data-ttu-id="e8c8e-202">-ユーザが **Skype ユーザとの通信が** 外部アクセスで有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-202">-Make sure **Users can communicate with Skype users** is enabled in External Access.</span></span><br><br><span data-ttu-id="e8c8e-203">PowerShell を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="e8c8e-203">If using PowerShell:</span></span> <br><span data-ttu-id="e8c8e-204">-テナントがフェデレーションに対して有効になっていることを確認します。 `Get-CsTenantFederationConfiguration` 表示する必要があり `AllowPublicUsers=true` ます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-204">-Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowPublicUsers=true`.</span></span> <br> <span data-ttu-id="e8c8e-205">-ユーザーの有効な値がにあることを確認し `CsExternalAccessPolicy` `EnablePublicCloudAccess=true` ます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-205">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnablePublicCloudAccess=true`.</span></span> |
| <span data-ttu-id="e8c8e-206">純粋なオンプレミス</span><span class="sxs-lookup"><span data-stu-id="e8c8e-206">Pure on-premises</span></span> | <span data-ttu-id="e8c8e-207">オンプレミスツールでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-207">In on-premises tools:</span></span> <br> <span data-ttu-id="e8c8e-208">-フェデレーションパートナーとして Skype が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-208">- Ensure Skype is enabled as a federated partner.</span></span> <br> <span data-ttu-id="e8c8e-209">- `EnablePublicCloudAccess=true` `ExternalAccessPolicy` (グローバルポリシー、サイトポリシー、またはユーザーによって割り当てられたポリシーを使用して) ユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-209">- Ensure `EnablePublicCloudAccess=true` for the user through `ExternalAccessPolicy` (either via global policy, site policy, or user assigned policy).</span></span>|
| <span data-ttu-id="e8c8e-210">一部のユーザー (Skype for Business または Teams のいずれか) とオンプレミスの一部のユーザーとのハイブリッド。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-210">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span>| <span data-ttu-id="e8c8e-211">オンラインとオンプレミスの両方の組織に対して、上記の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-211">Follow above steps for both online and on-premises organizations.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e8c8e-212">Teams または Skype for Business Online ユーザーが組織内外の Skype ユーザーと通信できるようにする際、**Skype ドメイン**を許可ドメインとして追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-212">You don't have to add any **Skype domains** as allowed domains in order to enable Teams or Skype for Business Online users to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="e8c8e-213">すべての **Skype ドメイン**はホワイトリストに登録されており、これらのドメインはすべて許可されているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-213">All **Skype domains** are whitelisted, which means all of these domains are considered ALLOWED.</span></span>

## <a name="how-does-external-access-compare-with-guest-access"></a><span data-ttu-id="e8c8e-214">ゲスト アクセスと比べて外部アクセスはどう違うのか</span><span class="sxs-lookup"><span data-stu-id="e8c8e-214">How does external access compare with guest access?</span></span>

<span data-ttu-id="e8c8e-215">外部アクセスとゲスト アクセスの違いの詳細ついては、「[Microsoft Teams の別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8c8e-215">To learn about the difference between external access and guest access, read [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8c8e-216">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8c8e-216">Related topics</span></span>

- [<span data-ttu-id="e8c8e-217">外部 (フェデレーション) ユーザー向けのネイティブ チャット機能</span><span class="sxs-lookup"><span data-stu-id="e8c8e-217">Native chat experience for external (federated) users</span></span>](native-chat-for-external-users.md)
