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
- m365initiative-externalcollab
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
ms.openlocfilehash: 9739c35fcd22229f3f1115edf029535f9b23e8f9
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031783"
---
<a name="manage-external-access-in-microsoft-teams"></a><span data-ttu-id="c9330-103">Microsoft Teams での外部アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="c9330-103">Manage external access in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="c9330-104">外部アクセスは、teams ユーザーが Teams で自分との会議を検索、通話、チャット、セットアップできるようにするための手段です。</span><span class="sxs-lookup"><span data-stu-id="c9330-104">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with you in Teams.</span></span> <span data-ttu-id="c9330-105">また、外部アクセスを使用して、まだ Skype for Business (オンラインとオンプレミス) および Skype (プレビュー版) を使用している外部ユーザーと通信することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9330-105">You can also use external access to communicate with external users who are still using Skype for Business (online and on-premises) and Skype (in preview).</span></span>

> [!NOTE]
> <span data-ttu-id="c9330-106">許可または禁止されたドメインは、会議への匿名アクセスが "オフ" の場合にのみ、会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9330-106">The allowed or blocked domains only apply to meetings if anonymous access to meetings is "off".</span></span>

<span data-ttu-id="c9330-107">外部のユーザーがチームとチャネルにアクセスできるようにする場合に適した方法は、ゲスト アクセスです。</span><span class="sxs-lookup"><span data-stu-id="c9330-107">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="c9330-108">外部アクセスとゲスト アクセスの違いの詳細については、「[外部アクセスとゲスト アクセスの比較](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9330-108">For more information about the differences between external access and guest access, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span> 

<span data-ttu-id="c9330-109">以下のような場合に外部アクセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9330-109">Use external access when:</span></span>
  
- <span data-ttu-id="c9330-110">別ドメインに共同作業が必要なユーザーがいる場合。</span><span class="sxs-lookup"><span data-stu-id="c9330-110">You have users in different domains who need to collaborate.</span></span> <span data-ttu-id="c9330-111">たとえば、Rob@contoso.com と Ann@northwindtraders.com が、contoso.com ドメインおよび northwindtraders.com ドメインの他のユーザーと一緒にプロジェクトの共同作業を行う場合です。</span><span class="sxs-lookup"><span data-stu-id="c9330-111">For example, Rob@contoso.com and Ann@northwindtraders.com are working on a project together along with some others in the contoso.com and northwindtraders.com domains.</span></span>

- <span data-ttu-id="c9330-112">組織内のユーザーが、Teams を使用して組織外の特定の会社のユーザーに連絡する必要場ある場合。</span><span class="sxs-lookup"><span data-stu-id="c9330-112">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="c9330-113">ユーザーのメール アドレスを使用して、世界中の Teams のユーザーは誰でもそのユーザーを検索して連絡を取れるようにする場合。</span><span class="sxs-lookup"><span data-stu-id="c9330-113">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c9330-114">Teams クライアントを使って外部ユーザーと通信するには (ユーザーが Teams または Skype for Business を使用しているかどうかにかかわらず)、Teams ユーザーが Skype for Business Online を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9330-114">To use the Teams client to communicate with an external user (whether that user is using Teams or Skype for Business), the Teams user must be homed in Skype for Business Online.</span></span>

## <a name="plan-for-external-access"></a><span data-ttu-id="c9330-115">外部アクセスの計画</span><span class="sxs-lookup"><span data-stu-id="c9330-115">Plan for external access</span></span>

<span data-ttu-id="c9330-116">Teams では既定で外部アクセスが有効になっています。つまり、組織はすべての外部ドメインと通信できます。</span><span class="sxs-lookup"><span data-stu-id="c9330-116">By default, external access is turned on in Teams, which means that your organization can communicate with all external domains.</span></span> <span data-ttu-id="c9330-117">禁止ドメインを追加すると、他のすべてのドメインが許可され、許可ドメインを追加すると、他のすべてのドメインが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="c9330-117">If you add blocked domains, all other domains will be allowed; and if you add allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="c9330-118">このルールの例外は、会議で匿名参加者が許可されている場合です。</span><span class="sxs-lookup"><span data-stu-id="c9330-118">The exception to this rule is if anonymous participants are allowed in meetings.</span></span> <span data-ttu-id="c9330-119">Teams 管理センターで外部アクセスを設定するには、次の 3 つのシナリオがあります ( **[組織全体の設定]**  >  **[外部アクセス]** )。</span><span class="sxs-lookup"><span data-stu-id="c9330-119">There are three scenarios for setting up external access in the Teams admin center ( **Org-wide settings** > **External access** ):</span></span>

- <span data-ttu-id="c9330-120">**開いているフェデレーション** : これは Teams の既定の設定です。組織内のユーザーが任意のドメインの組織外ユーザーとの会議の検索、呼び出し、チャット、設定を行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="c9330-120">**Open federation** : This is the default setting in Teams, and it lets people in your organization find, call, chat, and set up meetings with people external to your organization in any domain.</span></span>

    <span data-ttu-id="c9330-121">このシナリオでは、ユーザーはすべての外部ドメインと通信することができます。この外部ドメインは、Teams または Skype for Business を実行しており、開いているフェデレーションを使用しているか、ユーザーのドメインを許可リストに追加しています。</span><span class="sxs-lookup"><span data-stu-id="c9330-121">In this scenario, your users can communicate with all external domains that are running Teams or Skype for Business AND are using open federation OR have added your domain to their allow list.</span></span>

- <span data-ttu-id="c9330-122">**特定のドメインを許可する** : **[許可]** リストにドメインを追加して、外部アクセスを許可ドメインのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="c9330-122">**Allow specific domains** : By adding domains to an **Allow** list, you limit external access to only the allowed domains.</span></span> <span data-ttu-id="c9330-123">許可ドメインのリストを設定すると、他のすべてのドメインが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="c9330-123">Once you set up a list of allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="c9330-124">特定のドメインを許可するには、 **[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、 **[このドメインで実行するアクション]** をクリックし、 **[許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9330-124">To allow specific domains, click **Add a domain** , add the domain name, click **Action to take on this domain** , and then select **Allowed**.</span></span>

- <span data-ttu-id="c9330-125">**特定のドメインを禁止する** - **[禁止]** リストにドメインを追加すると、禁止したもの *以外の* すべての外部ドメインと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="c9330-125">**Block specific domains** - By adding domains to a **Block** list, you can communicate with all external domains *except* the ones you've blocked.</span></span> <span data-ttu-id="c9330-126">特定のドメインを禁止するには、 **[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、 **[このドメインで実行するアクション]** をクリックし、 **[禁止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9330-126">To block specific domains, click **Add a domain** , add the domain name, click **Action to take on this domain** , and then select **Blocked**.</span></span> <span data-ttu-id="c9330-127">禁止ドメインのリストを設定すると、他のすべてのドメインが許可されます。</span><span class="sxs-lookup"><span data-stu-id="c9330-127">Once you set up a list of blocked domains, all other domains will be allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="c9330-128">組織の外部アクセスを無効にしても、外部ユーザーは匿名の参加を通じて会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="c9330-128">If you turn off external access in your organization, external users can still join meetings through anonymous join.</span></span> <span data-ttu-id="c9330-129">詳細については、「 [Teams で会議の設定を管理](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9330-129">To learn more, see [Manage meeting settings in Teams](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams).</span></span>

## <a name="allow-or-block-domains"></a><span data-ttu-id="c9330-130">ドメインの許可または禁止</span><span class="sxs-lookup"><span data-stu-id="c9330-130">Allow or block domains</span></span>

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a><span data-ttu-id="c9330-131">手順 1-組織が別のチームまたは Skype for Business 組織と通信できるようにする</span><span class="sxs-lookup"><span data-stu-id="c9330-131">Step 1 - Enable your organization to communicate with another Teams or Skype for Business organizations</span></span>

<span data-ttu-id="c9330-132">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="c9330-132">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c9330-133">左側のナビゲーションで、 **[組織全体の設定]**  >  **[外部アクセス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9330-133">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="c9330-134">**[Users can communicate with other Skype for Business and Teams users]** (ユーザーは他の Skype for Business および Teams ユーザーと通信できます) 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="c9330-134">Turn on the **Users can communicate with other Skype for Business and Teams users** setting.</span></span>

     ![[ユーザーは他の Skype for Business および Teams ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-2.png)<span data-ttu-id="c9330-136">.</span><span class="sxs-lookup"><span data-stu-id="c9330-136">.</span></span>

3. <span data-ttu-id="c9330-137">すべての Teams の組織に対して、組織内のユーザーとの通信を許可する場合は、手順 5 に進みます。</span><span class="sxs-lookup"><span data-stu-id="c9330-137">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span>

4. <span data-ttu-id="c9330-138">組織内のユーザーと通信できる組織を制限するには、特定のドメイン以外のすべてを許可する方法と、特定のドメインのみを許可する方法があります。</span><span class="sxs-lookup"><span data-stu-id="c9330-138">If you want to limit the organizations that can communicate with users in your organization, you can either allow all except some domains, or you can allow only specific domains.</span></span> 

    - <span data-ttu-id="c9330-139">特定のドメイン以外のすべてを許可するには、 **[ドメインの追加]** をクリックして禁止するドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="c9330-139">To allow all except some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="c9330-140">**[ドメインの追加]** ウィンドウで、ドメイン名を入力して **[禁止]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9330-140">In the **Add a domain** pane, type the domain name, click **Blocked** , and then click **Done**.</span></span> 
    - <span data-ttu-id="c9330-141">通信を特定の組織に制限するには、それらの組織のドメインを **[許可]** の状態でリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="c9330-141">To limit communications to specific organizations, add those domains to the list with a status of **Allowed**.</span></span> <span data-ttu-id="c9330-142">[許可] リストにいずれかのドメインを追加すると、他の組織との通信は、[許可] リストにドメインが表示される組織との通信のみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="c9330-142">Once you have added any domain to the Allow list, communications with other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 

5. <span data-ttu-id="c9330-143">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9330-143">Click **Save**.</span></span>

6. <span data-ttu-id="c9330-144">他の Teams の組織の管理者も同じ手順を実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9330-144">Make sure the admin in the other Teams organization completes these same steps.</span></span> <span data-ttu-id="c9330-145">たとえば、他のある組織でその組織のユーザーと通信できる組織を制限している場合は、その組織の管理者は、 **許可ドメイン** のリストにお客様の会社のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9330-145">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit the organizations that can communicate with their users.</span></span>

### <a name="step-2---test-it"></a><span data-ttu-id="c9330-146">手順 2 - テスト</span><span class="sxs-lookup"><span data-stu-id="c9330-146">Step 2 - Test it</span></span>

<span data-ttu-id="c9330-147">設定をテストするには、組織のファイアウォールの外側にいる Teams ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="c9330-147">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
1. <span data-ttu-id="c9330-148">お客様ともう 1 つの組織の管理者が [ **外部アクセス** ] 設定の変更をそれぞれ完了すると、テストを開始できます。</span><span class="sxs-lookup"><span data-stu-id="c9330-148">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>

2. <span data-ttu-id="c9330-149">Teams アプリで、メール アドレスを使用してユーザーを検索し、チャットの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="c9330-149">In the Teams app, search for the person by email address, and send a request to chat.</span></span>

3. <span data-ttu-id="c9330-150">お客様宛にチャットの要求を送信するよう、Teams の連絡先に依頼します。</span><span class="sxs-lookup"><span data-stu-id="c9330-150">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="c9330-151">相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。</span><span class="sxs-lookup"><span data-stu-id="c9330-151">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="c9330-152">ファイアウォールに問題があるかどうかをテストする別の方法は、ファイアウォールの外側の WiFi 環境に移動することです。</span><span class="sxs-lookup"><span data-stu-id="c9330-152">Another way to test whether the problem is your firewall is to go to a WiFi location not behind your firewall.</span></span> <span data-ttu-id="c9330-153">コーヒー ショップなどから、Teams を使用して連絡先にチャットの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="c9330-153">such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="c9330-154">メッセージを WiFi 環境からは送信できるが、職場からは送信できない場合、問題の原因は職場のファイアウォールであることが特定できます。</span><span class="sxs-lookup"><span data-stu-id="c9330-154">If the message goes through at the WiFi location, but does not when you're at work, then you know the problem is your firewall.</span></span>

> [!NOTE]
> <span data-ttu-id="c9330-155">これは、ユーザーともう 1 人のユーザーの両方が外部アクセスを有効にしてお互いのドメインを許可している場合に可能になります。</span><span class="sxs-lookup"><span data-stu-id="c9330-155">If you and another user both turn on external access and allow one another's domains, this will work.</span></span> <span data-ttu-id="c9330-156">正常に動作しない場合は、もう 1 人のユーザーの構成でユーザーのドメインが禁止されていないかを確認してもらいます。</span><span class="sxs-lookup"><span data-stu-id="c9330-156">If it doesn't work, the other user should make sure their configuration isn't blocking your domain.</span></span>


## <a name="communicate-with-skype-users-in-preview"></a><span data-ttu-id="c9330-157">Skype ユーザーとの通信 (プレビュー段階)</span><span class="sxs-lookup"><span data-stu-id="c9330-157">Communicate with Skype users (in preview)</span></span>

<span data-ttu-id="c9330-158">組織内の Teams ユーザーが Skype ユーザーとチャットや通話をできるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9330-158">Follow these steps to let Teams users in your organization chat with and call Skype users.</span></span> <span data-ttu-id="c9330-159">この手順を実行すると、Teams ユーザーと Skype ユーザーとが、互いを検索したり、1 対 1 のテキストのみの会話や音声/ビデオ通話を開始したりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c9330-159">Teams users can then search for and start a one-on-one text-only conversation or an audio/video call with Skype users and vice versa.</span></span>

<span data-ttu-id="c9330-160">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="c9330-160">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c9330-161">左側のナビゲーションで、 **[組織全体の設定]**  >  **[外部アクセス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9330-161">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="c9330-162">**[ユーザーは Skype ユーザーと通信できます]** 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="c9330-162">Turn on the **Users can communicate with Skype users** setting.</span></span>

    ![[ユーザーは Skype ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-5.png)<span data-ttu-id="c9330-164">.</span><span class="sxs-lookup"><span data-stu-id="c9330-164">.</span></span>

<span data-ttu-id="c9330-165">Teams ユーザーと Skype ユーザーが通信できるようにする方法、および適用される制限事項の詳細については、「[Teams と Skype の相互運用性](teams-skype-interop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9330-165">To learn more about the ways that Teams users and Skype users can communicate, including limitations that apply, see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>

## <a name="common-external-access-scenarios"></a><span data-ttu-id="c9330-166">一般的な外部アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c9330-166">Common external access scenarios</span></span>

<span data-ttu-id="c9330-167">以下のセクションでは、一般的な外部アクセスシナリオに対してフェデレーションを有効にする方法と、TeamsUpgradePolicy での着信チャットと通話の配信を決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9330-167">The following sections describe how to enable federation for common external access scenarios, and how the TeamsUpgradePolicy determines delivery of incoming chats and calls.</span></span>

### <a name="enable-federation"></a><span data-ttu-id="c9330-168">フェデレーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="c9330-168">Enable federation</span></span>

<span data-ttu-id="c9330-169">組織内のユーザーが別の組織のユーザーと通信できるようにするには、両方の組織がフェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9330-169">To enable users in your organization to communicate with users in another organization, both organizations must enable federation.</span></span> <span data-ttu-id="c9330-170">特定の組織に対してフェデレーションを有効にする手順は、組織が純粋にオンライン、ハイブリッド、純粋にオンプレミスのいずれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c9330-170">The steps to enable federation for a given organization depend on whether the organization is purely online, hybrid, or purely on-premises.</span></span>

|<span data-ttu-id="c9330-171">**組織の場合**</span><span class="sxs-lookup"><span data-stu-id="c9330-171">**If your organization is**</span></span> |<span data-ttu-id="c9330-172">**次のようにフェデレーションを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="c9330-172">**Enable federation as follows**</span></span>  |
|:---------|:-----------------------|
|<span data-ttu-id="c9330-173">オンプレミスの Skype for Business がないオンライン。</span><span class="sxs-lookup"><span data-stu-id="c9330-173">Online with no Skype for Business on-premises.</span></span> <span data-ttu-id="c9330-174">これには、チームのユーザーまたは Skype for Business Online ユーザーがいる組織も含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9330-174">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span>| <span data-ttu-id="c9330-175">Teams 管理センターを使用している場合:</span><span class="sxs-lookup"><span data-stu-id="c9330-175">If using Teams Admin Center:</span></span> <br><span data-ttu-id="c9330-176">-[外部アクセス] で [ **ユーザーが他の Skype For business および Teams ユーザーと通信できる** ようにする] 設定が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9330-176">-   Make sure the **Users can communicate with other Skype for Business and Teams users** setting is enabled in External Access.</span></span><br><span data-ttu-id="c9330-177">-開いているフェデレーション (他のドメインとのフェデレーションを可能にする) を使用していない場合は、許可リストに外部ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="c9330-177">- If you are not using open federation (which allows federation with any other domain), then add the external domain to the Allowed list.</span></span><br><br><span data-ttu-id="c9330-178">PowerShell を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="c9330-178">If using PowerShell:</span></span><br><span data-ttu-id="c9330-179">-テナントがフェデレーションに対して有効になっていることを確認します。 `Get-CsTenantFederationConfiguration` 表示する必要があり `AllowFederatedUsers=true` ます。</span><span class="sxs-lookup"><span data-stu-id="c9330-179">- Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowFederatedUsers=true`.</span></span> <br><span data-ttu-id="c9330-180">-ユーザーの有効な値がにあることを確認し `CsExternalAccessPolicy` `EnableFederationAccess=true` ます。</span><span class="sxs-lookup"><span data-stu-id="c9330-180">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnableFederationAccess=true`.</span></span><br><span data-ttu-id="c9330-181">-オープンフェデレーションを使用していない場合は、ターゲットドメインがに表示されていることを確認し `AllowedDomains` `CsTenantFederationConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="c9330-181">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains` of `CsTenantFederationConfiguration`.</span></span> |
|<span data-ttu-id="c9330-182">純粋なオンプレミス</span><span class="sxs-lookup"><span data-stu-id="c9330-182">Pure on-premises</span></span> | <span data-ttu-id="c9330-183">オンプレミスツールでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c9330-183">In on-premises tools:</span></span> <br><span data-ttu-id="c9330-184">-でフェデレーションが有効になっていることを確認 `CsAccessEdgeConfiguration` します。</span><span class="sxs-lookup"><span data-stu-id="c9330-184">- Ensure federation is enabled in `CsAccessEdgeConfiguration`.</span></span><br><span data-ttu-id="c9330-185">- `ExternalAccessPolicy` (グローバルポリシー、サイトポリシー、またはユーザーが割り当てられたポリシーのいずれかを通じて) ユーザーのフェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c9330-185">- Ensure federation for the user is enabled through `ExternalAccessPolicy` (either through the global policy, site policy, or user assigned policy).</span></span> <br> <span data-ttu-id="c9330-186">-オープンフェデレーションを使用していない場合は、ターゲットドメインがに表示されていることを確認し `AllowedDomains` ます。</span><span class="sxs-lookup"><span data-stu-id="c9330-186">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains`.</span></span> |
|<span data-ttu-id="c9330-187">一部のユーザー (Skype for Business または Teams のいずれか) とオンプレミスの一部のユーザーとのハイブリッド。</span><span class="sxs-lookup"><span data-stu-id="c9330-187">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span> | <span data-ttu-id="c9330-188">オンラインとオンプレミスの両方の組織に対して、上記の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9330-188">Follow above steps for both online and on-premises organizations.</span></span> |

### <a name="delivery-of-incoming-chats-and-calls"></a><span data-ttu-id="c9330-189">チャットと通話の着信の配信</span><span class="sxs-lookup"><span data-stu-id="c9330-189">Delivery of incoming chats and calls</span></span> 

<span data-ttu-id="c9330-190">フェデレーション組織からの着信チャットと通話は、TeamsUpgradePolicy の受信者ユーザーモードに応じて、ユーザーのチームまたは Skype for Business クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9330-190">Incoming chats and calls from a federation organization will land in the user’s Teams or Skype for Business client depending on the recipient user’s mode in TeamsUpgradePolicy.</span></span>

|<span data-ttu-id="c9330-191">**目的**</span><span class="sxs-lookup"><span data-stu-id="c9330-191">**If you want to**</span></span> |<span data-ttu-id="c9330-192">**手順:**</span><span class="sxs-lookup"><span data-stu-id="c9330-192">**Do this:**</span></span>  |
|:---------|:-----------------------|
| <span data-ttu-id="c9330-193">フェデレーションされたチャットの着信と、ユーザーのチームクライアントで通話を受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c9330-193">Ensure incoming federated chats and calls arrive in the user’s Teams client:</span></span> | <span data-ttu-id="c9330-194">ユーザーをチームのみに設定します。</span><span class="sxs-lookup"><span data-stu-id="c9330-194">Configure your users to be TeamsOnly.</span></span>
| <span data-ttu-id="c9330-195">フェデレーションされたチャットの着信と、ユーザーの Skype for Business クライアントで通話を受信できるようにする</span><span class="sxs-lookup"><span data-stu-id="c9330-195">Ensure incoming federated chats and calls arrive in the user’s Skype for Business client</span></span> | <span data-ttu-id="c9330-196">ユーザーは、TeamsOnly 以外のモードに設定します。</span><span class="sxs-lookup"><span data-stu-id="c9330-196">Configure your users to be in any mode other than TeamsOnly.</span></span> |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a><span data-ttu-id="c9330-197">組織内のユーザーと Skype のコンシューマーユーザーの間のフェデレーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="c9330-197">Enable federation between users in your organization and consumer users of Skype</span></span>

<span data-ttu-id="c9330-198">組織内のユーザーと Skype のコンシューマーユーザーの間でフェデレーションを有効にするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c9330-198">To enable federation between users in your organization and consumer users of Skype:</span></span>

|<span data-ttu-id="c9330-199">**組織の場合**</span><span class="sxs-lookup"><span data-stu-id="c9330-199">**If your organization is**</span></span> |<span data-ttu-id="c9330-200">**次のようにコンシューマーフェデレーションを有効にする**</span><span class="sxs-lookup"><span data-stu-id="c9330-200">**Enable consumer federation as follows**</span></span>  |
|:---------|:-----------------------|
| <span data-ttu-id="c9330-201">オンプレミスの Skype for Business を使用しない純粋なオンライン。</span><span class="sxs-lookup"><span data-stu-id="c9330-201">Pure online with no Skype for Business on-premises.</span></span>  <span data-ttu-id="c9330-202">これには、チームのユーザーまたは Skype for Business Online ユーザーがいる組織も含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9330-202">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span> | <span data-ttu-id="c9330-203">Teams 管理センターを使用している場合:</span><span class="sxs-lookup"><span data-stu-id="c9330-203">If using Teams Admin Center:</span></span> <br><span data-ttu-id="c9330-204">-ユーザが **Skype ユーザとの通信が** 外部アクセスで有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9330-204">-Make sure **Users can communicate with Skype users** is enabled in External Access.</span></span><br><br><span data-ttu-id="c9330-205">PowerShell を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="c9330-205">If using PowerShell:</span></span> <br><span data-ttu-id="c9330-206">-テナントがフェデレーションに対して有効になっていることを確認します。 `Get-CsTenantFederationConfiguration` 表示する必要があり `AllowPublicUsers=true` ます。</span><span class="sxs-lookup"><span data-stu-id="c9330-206">-Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowPublicUsers=true`.</span></span> <br> <span data-ttu-id="c9330-207">-ユーザーの有効な値がにあることを確認し `CsExternalAccessPolicy` `EnablePublicCloudAccess=true` ます。</span><span class="sxs-lookup"><span data-stu-id="c9330-207">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnablePublicCloudAccess=true`.</span></span> |
| <span data-ttu-id="c9330-208">純粋なオンプレミス</span><span class="sxs-lookup"><span data-stu-id="c9330-208">Pure on-premises</span></span> | <span data-ttu-id="c9330-209">オンプレミスツールでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c9330-209">In on-premises tools:</span></span> <br> <span data-ttu-id="c9330-210">-フェデレーションパートナーとして Skype が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9330-210">- Ensure Skype is enabled as a federated partner.</span></span> <br> <span data-ttu-id="c9330-211">- `EnablePublicCloudAccess=true` `ExternalAccessPolicy` (グローバルポリシー、サイトポリシー、またはユーザーによって割り当てられたポリシーを使用して) ユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9330-211">- Ensure `EnablePublicCloudAccess=true` for the user through `ExternalAccessPolicy` (either via global policy, site policy, or user assigned policy).</span></span>|
| <span data-ttu-id="c9330-212">一部のユーザー (Skype for Business または Teams のいずれか) とオンプレミスの一部のユーザーとのハイブリッド。</span><span class="sxs-lookup"><span data-stu-id="c9330-212">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span>| <span data-ttu-id="c9330-213">オンラインとオンプレミスの両方の組織に対して、上記の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9330-213">Follow above steps for both online and on-premises organizations.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c9330-214">Teams または Skype for Business Online ユーザーが組織内外の Skype ユーザーと通信できるようにする際、 **Skype ドメイン** を許可ドメインとして追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c9330-214">You don't have to add any **Skype domains** as allowed domains in order to enable Teams or Skype for Business Online users to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="c9330-215">すべての **Skype ドメイン** はホワイトリストに登録されており、これらのドメインはすべて許可されているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="c9330-215">All **Skype domains** are whitelisted, which means all of these domains are considered ALLOWED.</span></span>

## <a name="how-does-external-access-compare-with-guest-access"></a><span data-ttu-id="c9330-216">ゲスト アクセスと比べて外部アクセスはどう違うのか</span><span class="sxs-lookup"><span data-stu-id="c9330-216">How does external access compare with guest access?</span></span>

<span data-ttu-id="c9330-217">外部アクセスとゲスト アクセスの違いの詳細ついては、「[Microsoft Teams の別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9330-217">To learn about the difference between external access and guest access, read [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c9330-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9330-218">Related topics</span></span>

- [<span data-ttu-id="c9330-219">外部 (フェデレーション) ユーザー向けのネイティブ チャット機能</span><span class="sxs-lookup"><span data-stu-id="c9330-219">Native chat experience for external (federated) users</span></span>](native-chat-for-external-users.md)
