---
title: 外部アクセス (フェデレーション) を管理する
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: b5d8bb969725507eec54a66c7ccb20b6eb54ec68
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055749"
---
# <a name="manage-external-access-in-microsoft-teams"></a><span data-ttu-id="b1d5a-103">Microsoft Teams での外部アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="b1d5a-103">Manage external access in Microsoft Teams</span></span>

<span data-ttu-id="b1d5a-104">外部アクセスは、外部ドメイン全体の Teams ユーザーが Teams で自分と会議を検索、通話、チャット、設定するための方法です。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-104">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with you in Teams.</span></span> <span data-ttu-id="b1d5a-105">また、外部アクセスを使用して、Skype for Business (オンラインおよびオンプレミス) および Skype (プレビュー) をまだ使用している他の組織のユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-105">You can also use external access to communicate with people from other organizations who are still using Skype for Business (online and on-premises) and Skype (in preview).</span></span>

> [!NOTE]
> <span data-ttu-id="b1d5a-106">許可されたドメインまたはブロックされたドメインは、会議への匿名アクセスが "オフ" の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-106">The allowed or blocked domains only apply to meetings if anonymous access to meetings is "off".</span></span>

<span data-ttu-id="b1d5a-107">他の組織のユーザーにチームやチャネルへのアクセスを許可する場合は、ゲスト アクセスの方が良い方法である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-107">If you want people from other organizations to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="b1d5a-108">外部アクセスとゲスト アクセスの違いの詳細については、「[外部アクセスとゲスト アクセスの比較](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-108">For more information about the differences between external access and guest access, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span> 

<span data-ttu-id="b1d5a-109">以下のような場合に外部アクセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-109">Use external access when:</span></span>
  
- <span data-ttu-id="b1d5a-110">別ドメインに共同作業が必要なユーザーがいる場合。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-110">You have users in different domains who need to collaborate.</span></span> <span data-ttu-id="b1d5a-111">たとえば、Rob@contoso.com と Ann@northwindtraders.com が、contoso.com ドメインおよび northwindtraders.com ドメインの他のユーザーと一緒にプロジェクトの共同作業を行う場合です。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-111">For example, Rob@contoso.com and Ann@northwindtraders.com are working on a project together along with some others in the contoso.com and northwindtraders.com domains.</span></span>

- <span data-ttu-id="b1d5a-112">組織内のユーザーが、Teams を使用して組織外の特定の会社のユーザーに連絡する必要場ある場合。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-112">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="b1d5a-113">ユーザーのメール アドレスを使用して、世界中の Teams のユーザーは誰でもそのユーザーを検索して連絡を取れるようにする場合。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-113">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b1d5a-114">Teams クライアントを使用して外部ユーザーと通信するには (そのユーザーが Teams または Skype for Business を使用している場合でも)、Teams ユーザーは Skype for Business Online に保存されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-114">To use the Teams client to communicate with an external user (whether that user is using Teams or Skype for Business), the Teams user must be homed in Skype for Business Online.</span></span>

## <a name="plan-for-external-access"></a><span data-ttu-id="b1d5a-115">外部アクセスの計画</span><span class="sxs-lookup"><span data-stu-id="b1d5a-115">Plan for external access</span></span>

<span data-ttu-id="b1d5a-116">Teams では既定で外部アクセスが有効になっています。つまり、組織はすべての外部ドメインと通信できます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-116">By default, external access is turned on in Teams, which means that your organization can communicate with all external domains.</span></span> <span data-ttu-id="b1d5a-117">禁止ドメインを追加すると、他のすべてのドメインが許可され、許可ドメインを追加すると、他のすべてのドメインが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-117">If you add blocked domains, all other domains will be allowed; and if you add allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="b1d5a-118">このルールの例外は、匿名参加者が会議で許可されている場合です。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-118">The exception to this rule is if anonymous participants are allowed in meetings.</span></span> <span data-ttu-id="b1d5a-119">Teams 管理センターで外部アクセスを設定するには、次の 3 つのシナリオがあります (**[組織全体の設定]**  >  **[外部アクセス]**)。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-119">There are three scenarios for setting up external access in the Teams admin center (**Org-wide settings** > **External access**):</span></span>

- <span data-ttu-id="b1d5a-120">**開いているフェデレーション**: これは Teams の既定の設定です。組織内のユーザーが任意のドメインの組織外ユーザーとの会議の検索、呼び出し、チャット、設定を行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-120">**Open federation**: This is the default setting in Teams, and it lets people in your organization find, call, chat, and set up meetings with people external to your organization in any domain.</span></span>

    <span data-ttu-id="b1d5a-121">このシナリオでは、ユーザーはすべての外部ドメインと通信することができます。この外部ドメインは、Teams または Skype for Business を実行しており、開いているフェデレーションを使用しているか、ユーザーのドメインを許可リストに追加しています。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-121">In this scenario, your users can communicate with all external domains that are running Teams or Skype for Business AND are using open federation OR have added your domain to their allow list.</span></span>

- <span data-ttu-id="b1d5a-122">**特定のドメインを許可する**: **[許可]** リストにドメインを追加して、外部アクセスを許可ドメインのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-122">**Allow specific domains**: By adding domains to an **Allow** list, you limit external access to only the allowed domains.</span></span> <span data-ttu-id="b1d5a-123">許可ドメインのリストを設定すると、他のすべてのドメインが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-123">Once you set up a list of allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="b1d5a-124">特定のドメインを許可するには、**[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、**[このドメインで実行するアクション]** をクリックし、**[許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-124">To allow specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Allowed**.</span></span>

- <span data-ttu-id="b1d5a-125">**特定のドメインを禁止する** - **[禁止]** リストにドメインを追加すると、禁止したもの *以外の* すべての外部ドメインと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-125">**Block specific domains** - By adding domains to a **Block** list, you can communicate with all external domains *except* the ones you've blocked.</span></span> <span data-ttu-id="b1d5a-126">特定のドメインを禁止するには、**[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、**[このドメインで実行するアクション]** をクリックし、**[禁止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-126">To block specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Blocked**.</span></span> <span data-ttu-id="b1d5a-127">禁止ドメインのリストを設定すると、他のすべてのドメインが許可されます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-127">Once you set up a list of blocked domains, all other domains will be allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="b1d5a-128">組織で外部アクセスをオフにした場合でも、外部ユーザーは匿名参加を通じて会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-128">If you turn off external access in your organization, external users can still join meetings through anonymous join.</span></span> <span data-ttu-id="b1d5a-129">詳細については、「[Teams での会議設定を管理する](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-129">To learn more, see [Manage meeting settings in Teams](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams).</span></span>

## <a name="allow-or-block-domains"></a><span data-ttu-id="b1d5a-130">ドメインの許可または禁止</span><span class="sxs-lookup"><span data-stu-id="b1d5a-130">Allow or block domains</span></span>

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a><span data-ttu-id="b1d5a-131">手順 1 - 組織が別の Teams または Skype for Business 組織と通信することを有効にする</span><span class="sxs-lookup"><span data-stu-id="b1d5a-131">Step 1 - Enable your organization to communicate with another Teams or Skype for Business organizations</span></span>

<span data-ttu-id="b1d5a-132">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="b1d5a-132">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b1d5a-133">左側のナビゲーションで、**[組織全体の設定]**  >  **[外部アクセス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-133">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="b1d5a-134">**[Users can communicate with other Skype for Business and Teams users]**(ユーザーは他の Skype for Business および Teams ユーザーと通信できます) 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-134">Turn on the **Users can communicate with other Skype for Business and Teams users** setting.</span></span>

     ![[ユーザーは他の Skype for Business および Teams ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-2.png)<span data-ttu-id="b1d5a-136">.</span><span class="sxs-lookup"><span data-stu-id="b1d5a-136">.</span></span>

3. <span data-ttu-id="b1d5a-137">すべての Teams の組織に対して、組織内のユーザーとの通信を許可する場合は、手順 5 に進みます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-137">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span>

4. <span data-ttu-id="b1d5a-138">組織内のユーザーと通信できる組織を制限するには、特定のドメイン以外のすべてを許可する方法と、特定のドメインのみを許可する方法があります。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-138">If you want to limit the organizations that can communicate with users in your organization, you can either allow all except some domains, or you can allow only specific domains.</span></span> 

    - <span data-ttu-id="b1d5a-139">特定のドメイン以外のすべてを許可するには、**[ドメインの追加]** をクリックして禁止するドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-139">To allow all except some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="b1d5a-140">**[ドメインの追加]** ウィンドウで、ドメイン名を入力して **[禁止]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-140">In the **Add a domain** pane, type the domain name, click **Blocked**, and then click **Done**.</span></span> 
    - <span data-ttu-id="b1d5a-141">通信を特定の組織に制限するには、それらの組織のドメインを **[許可]** の状態でリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-141">To limit communications to specific organizations, add those domains to the list with a status of **Allowed**.</span></span> <span data-ttu-id="b1d5a-142">[許可] リストにいずれかのドメインを追加すると、他の組織との通信は、[許可] リストにドメインが表示される組織との通信のみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-142">Once you have added any domain to the Allow list, communications with other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 

5. <span data-ttu-id="b1d5a-143">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-143">Click **Save**.</span></span>

6. <span data-ttu-id="b1d5a-144">他の Teams の組織の管理者も同じ手順を実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-144">Make sure the admin in the other Teams organization completes these same steps.</span></span> <span data-ttu-id="b1d5a-145">たとえば、他のある組織でその組織のユーザーと通信できる組織を制限している場合は、その組織の管理者は、**許可ドメイン** のリストにお客様の会社のドメインを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-145">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit the organizations that can communicate with their users.</span></span>

### <a name="step-2---test-it"></a><span data-ttu-id="b1d5a-146">手順 2 - テスト</span><span class="sxs-lookup"><span data-stu-id="b1d5a-146">Step 2 - Test it</span></span>

<span data-ttu-id="b1d5a-147">設定をテストするには、組織のファイアウォールの外側にいる Teams ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-147">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
1. <span data-ttu-id="b1d5a-148">お客様ともう 1 つの組織の管理者が [**外部アクセス**] 設定の変更をそれぞれ完了すると、テストを開始できます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-148">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>

2. <span data-ttu-id="b1d5a-149">Teams アプリで、メール アドレスを使用してユーザーを検索し、チャットの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-149">In the Teams app, search for the person by email address, and send a request to chat.</span></span>

3. <span data-ttu-id="b1d5a-150">お客様宛にチャットの要求を送信するよう、Teams の連絡先に依頼します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-150">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="b1d5a-151">相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-151">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="b1d5a-152">ファイアウォールに問題があるかどうかをテストする別の方法は、ファイアウォールの外側の WiFi 環境に移動することです。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-152">Another way to test whether the problem is your firewall is to go to a WiFi location not behind your firewall.</span></span> <span data-ttu-id="b1d5a-153">コーヒー ショップなどから、Teams を使用して連絡先にチャットの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-153">such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="b1d5a-154">メッセージを WiFi 環境からは送信できるが、職場からは送信できない場合、問題の原因は職場のファイアウォールであることが特定できます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-154">If the message goes through at the WiFi location, but does not when you're at work, then you know the problem is your firewall.</span></span>

> [!NOTE]
> <span data-ttu-id="b1d5a-155">これは、ユーザーともう 1 人のユーザーの両方が外部アクセスを有効にしてお互いのドメインを許可している場合に可能になります。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-155">If you and another user both turn on external access and allow one another's domains, this will work.</span></span> <span data-ttu-id="b1d5a-156">正常に動作しない場合は、もう 1 人のユーザーの構成でユーザーのドメインが禁止されていないかを確認してもらいます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-156">If it doesn't work, the other user should make sure their configuration isn't blocking your domain.</span></span>


## <a name="communicate-with-skype-users-in-preview"></a><span data-ttu-id="b1d5a-157">Skype ユーザーとの通信 (プレビュー段階)</span><span class="sxs-lookup"><span data-stu-id="b1d5a-157">Communicate with Skype users (in preview)</span></span>

<span data-ttu-id="b1d5a-158">組織内の Teams ユーザーが Skype ユーザーとチャットや通話をできるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-158">Follow these steps to let Teams users in your organization chat with and call Skype users.</span></span> <span data-ttu-id="b1d5a-159">この手順を実行すると、Teams ユーザーと Skype ユーザーとが、互いを検索したり、1 対 1 のテキストのみの会話や音声/ビデオ通話を開始したりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-159">Teams users can then search for and start a one-on-one text-only conversation or an audio/video call with Skype users and vice versa.</span></span>

<span data-ttu-id="b1d5a-160">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="b1d5a-160">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b1d5a-161">左側のナビゲーションで、**[組織全体の設定]**  >  **[外部アクセス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-161">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="b1d5a-162">**[ユーザーは Skype ユーザーと通信できます]** 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-162">Turn on the **Users can communicate with Skype users** setting.</span></span>

    ![[ユーザーは Skype ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-5.png)<span data-ttu-id="b1d5a-164">.</span><span class="sxs-lookup"><span data-stu-id="b1d5a-164">.</span></span>

<span data-ttu-id="b1d5a-165">Teams ユーザーと Skype ユーザーが通信できるようにする方法、および適用される制限事項の詳細については、「[Teams と Skype の相互運用性](teams-skype-interop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-165">To learn more about the ways that Teams users and Skype users can communicate, including limitations that apply, see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>

## <a name="common-external-access-scenarios"></a><span data-ttu-id="b1d5a-166">一般的な外部アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="b1d5a-166">Common external access scenarios</span></span>

<span data-ttu-id="b1d5a-167">次のセクションでは、一般的な外部アクセス シナリオでフェデレーションを有効にする方法、および TeamsUpgradePolicy が着信チャットと通話の配信を決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-167">The following sections describe how to enable federation for common external access scenarios, and how the TeamsUpgradePolicy determines delivery of incoming chats and calls.</span></span>

### <a name="enable-federation"></a><span data-ttu-id="b1d5a-168">フェデレーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="b1d5a-168">Enable federation</span></span>

<span data-ttu-id="b1d5a-169">組織内のユーザーが別の組織のユーザーと通信するには、両方の組織でフェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-169">To enable users in your organization to communicate with users in another organization, both organizations must enable federation.</span></span> <span data-ttu-id="b1d5a-170">特定の組織のフェデレーションを有効にする手順は、組織が完全にオンラインか、ハイブリッドか、または純粋にオンプレミスかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-170">The steps to enable federation for a given organization depend on whether the organization is purely online, hybrid, or purely on-premises.</span></span>

|<span data-ttu-id="b1d5a-171">**組織が**</span><span class="sxs-lookup"><span data-stu-id="b1d5a-171">**If your organization is**</span></span> |<span data-ttu-id="b1d5a-172">**次のようにフェデレーションを有効にする**</span><span class="sxs-lookup"><span data-stu-id="b1d5a-172">**Enable federation as follows**</span></span>  |
|:---------|:-----------------------|
|<span data-ttu-id="b1d5a-173">オンプレミスの Skype for Business がないオンライン。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-173">Online with no Skype for Business on-premises.</span></span> <span data-ttu-id="b1d5a-174">これには、TeamsOnly ユーザーまたは Skype for Business Online ユーザーを持つ組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-174">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span>| <span data-ttu-id="b1d5a-175">Teams 管理センターを使用している場合:</span><span class="sxs-lookup"><span data-stu-id="b1d5a-175">If using Teams Admin Center:</span></span> <br><span data-ttu-id="b1d5a-176">- ユーザーが他の Skype for Business ユーザーと通信可能であり **、Teams** のユーザー設定が外部アクセスで有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-176">-   Make sure the **Users can communicate with other Skype for Business and Teams users** setting is enabled in External Access.</span></span><br><span data-ttu-id="b1d5a-177">- オープン フェデレーション (他のドメインとのフェデレーションを許可する) を使用していない場合は、許可リストに外部ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-177">- If you are not using open federation (which allows federation with any other domain), then add the external domain to the Allowed list.</span></span><br><br><span data-ttu-id="b1d5a-178">PowerShell を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="b1d5a-178">If using PowerShell:</span></span><br><span data-ttu-id="b1d5a-179">- テナントがフェデレーションに対して有効になっている必要があります `Get-CsTenantFederationConfiguration` `AllowFederatedUsers=true` 。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-179">- Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowFederatedUsers=true`.</span></span> <br><span data-ttu-id="b1d5a-180">- ユーザーの有効な価値が `CsExternalAccessPolicy` . `EnableFederationAccess=true`</span><span class="sxs-lookup"><span data-stu-id="b1d5a-180">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnableFederationAccess=true`.</span></span><br><span data-ttu-id="b1d5a-181">- オープン フェデレーションを使用していない場合は、ターゲット ドメインが `AllowedDomains` `CsTenantFederationConfiguration`</span><span class="sxs-lookup"><span data-stu-id="b1d5a-181">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains` of `CsTenantFederationConfiguration`.</span></span> |
|<span data-ttu-id="b1d5a-182">純粋なオンプレミス</span><span class="sxs-lookup"><span data-stu-id="b1d5a-182">Pure on-premises</span></span> | <span data-ttu-id="b1d5a-183">オンプレミス ツールの場合:</span><span class="sxs-lookup"><span data-stu-id="b1d5a-183">In on-premises tools:</span></span> <br><span data-ttu-id="b1d5a-184">- フェデレーションが有効になっているか確認します `CsAccessEdgeConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-184">- Ensure federation is enabled in `CsAccessEdgeConfiguration`.</span></span><br><span data-ttu-id="b1d5a-185">- (グローバル ポリシー、サイト ポリシー、またはユーザーに割り当てられたポリシーを通じて) ユーザーのフェデレーション `ExternalAccessPolicy` が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-185">- Ensure federation for the user is enabled through `ExternalAccessPolicy` (either through the global policy, site policy, or user assigned policy).</span></span> <br> <span data-ttu-id="b1d5a-186">- オープン フェデレーションを使用していない場合は、ターゲット ドメインがリストに表示されるのを確認します `AllowedDomains` 。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-186">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains`.</span></span> |
|<span data-ttu-id="b1d5a-187">オンラインの一部のユーザー (Skype for Business または Teams) とオンプレミスの一部のユーザーとのハイブリッド。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-187">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span> | <span data-ttu-id="b1d5a-188">オンライン組織とオンプレミス組織の両方について、上記の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-188">Follow above steps for both online and on-premises organizations.</span></span> |

### <a name="delivery-of-incoming-chats-and-calls"></a><span data-ttu-id="b1d5a-189">着信チャットと通話の配信</span><span class="sxs-lookup"><span data-stu-id="b1d5a-189">Delivery of incoming chats and calls</span></span> 

<span data-ttu-id="b1d5a-190">フェデレーション組織からの着信チャットと通話は、TeamsUpgradePolicy の受信者ユーザーのモードに応じて、ユーザーの Teams または Skype for Business クライアントに配信されます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-190">Incoming chats and calls from a federation organization will land in the user’s Teams or Skype for Business client depending on the recipient user’s mode in TeamsUpgradePolicy.</span></span>

|<span data-ttu-id="b1d5a-191">**必要な場合は、**</span><span class="sxs-lookup"><span data-stu-id="b1d5a-191">**If you want to**</span></span> |<span data-ttu-id="b1d5a-192">**次の操作を行います。**</span><span class="sxs-lookup"><span data-stu-id="b1d5a-192">**Do this:**</span></span>  |
|:---------|:-----------------------|
| <span data-ttu-id="b1d5a-193">着信フェデレーション チャットと通話がユーザーの Teams クライアントに到着します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-193">Ensure incoming federated chats and calls arrive in the user’s Teams client:</span></span> | <span data-ttu-id="b1d5a-194">ユーザーを TeamsOnly に構成します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-194">Configure your users to be TeamsOnly.</span></span>
| <span data-ttu-id="b1d5a-195">着信フェデレーション チャットと通話がユーザーの Skype for Business クライアントで受信されるのを確認する</span><span class="sxs-lookup"><span data-stu-id="b1d5a-195">Ensure incoming federated chats and calls arrive in the user’s Skype for Business client</span></span> | <span data-ttu-id="b1d5a-196">TeamsOnly 以外のモードでユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-196">Configure your users to be in any mode other than TeamsOnly.</span></span> |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a><span data-ttu-id="b1d5a-197">組織内のユーザーと Skype のコンシューマー ユーザー間のフェデレーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="b1d5a-197">Enable federation between users in your organization and consumer users of Skype</span></span>

<span data-ttu-id="b1d5a-198">組織内のユーザーと Skype のコンシューマー ユーザー間のフェデレーションを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="b1d5a-198">To enable federation between users in your organization and consumer users of Skype:</span></span>

|<span data-ttu-id="b1d5a-199">**組織が**</span><span class="sxs-lookup"><span data-stu-id="b1d5a-199">**If your organization is**</span></span> |<span data-ttu-id="b1d5a-200">**次のようにコンシューマー フェデレーションを有効にする**</span><span class="sxs-lookup"><span data-stu-id="b1d5a-200">**Enable consumer federation as follows**</span></span>  |
|:---------|:-----------------------|
| <span data-ttu-id="b1d5a-201">オンプレミスの Skype for Business がない純粋なオンライン。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-201">Pure online with no Skype for Business on-premises.</span></span>  <span data-ttu-id="b1d5a-202">これには、TeamsOnly ユーザーまたは Skype for Business Online ユーザーを持つ組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-202">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span> | <span data-ttu-id="b1d5a-203">Teams 管理センターを使用している場合:</span><span class="sxs-lookup"><span data-stu-id="b1d5a-203">If using Teams Admin Center:</span></span> <br><span data-ttu-id="b1d5a-204">-外部アクセス **でユーザーが Skype ユーザーと通信** 可能になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-204">-Make sure **Users can communicate with Skype users** is enabled in External Access.</span></span><br><br><span data-ttu-id="b1d5a-205">PowerShell を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="b1d5a-205">If using PowerShell:</span></span> <br><span data-ttu-id="b1d5a-206">-テナントがフェデレーションに対して有効になっている必要があります `Get-CsTenantFederationConfiguration` `AllowPublicUsers=true` 。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-206">-Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowPublicUsers=true`.</span></span> <br> <span data-ttu-id="b1d5a-207">- ユーザーの有効な価値が `CsExternalAccessPolicy` . `EnablePublicCloudAccess=true`</span><span class="sxs-lookup"><span data-stu-id="b1d5a-207">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnablePublicCloudAccess=true`.</span></span> |
| <span data-ttu-id="b1d5a-208">純粋なオンプレミス</span><span class="sxs-lookup"><span data-stu-id="b1d5a-208">Pure on-premises</span></span> | <span data-ttu-id="b1d5a-209">オンプレミス ツールの場合:</span><span class="sxs-lookup"><span data-stu-id="b1d5a-209">In on-premises tools:</span></span> <br> <span data-ttu-id="b1d5a-210">- Skype がフェデレーション パートナーとして有効に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-210">- Ensure Skype is enabled as a federated partner.</span></span> <br> <span data-ttu-id="b1d5a-211">- (グローバル ポリシー、サイト ポリシー、またはユーザー割り当てポリシーを使用して) ユーザー `EnablePublicCloudAccess=true` `ExternalAccessPolicy` を確認します。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-211">- Ensure `EnablePublicCloudAccess=true` for the user through `ExternalAccessPolicy` (either via global policy, site policy, or user assigned policy).</span></span>|
| <span data-ttu-id="b1d5a-212">オンラインの一部のユーザー (Skype for Business または Teams) とオンプレミスの一部のユーザーとのハイブリッド。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-212">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span>| <span data-ttu-id="b1d5a-213">オンライン組織とオンプレミス組織の両方について、上記の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-213">Follow above steps for both online and on-premises organizations.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="b1d5a-214">Teams または Skype for Business Online ユーザーが組織内外の Skype ユーザーと通信できるようにする際、**Skype ドメイン** を許可ドメインとして追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-214">You don't have to add any **Skype domains** as allowed domains in order to enable Teams or Skype for Business Online users to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="b1d5a-215">すべての **Skype ドメイン** が許可されます。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-215">All **Skype domains** are allowed.</span></span>

## <a name="how-does-external-access-compare-with-guest-access"></a><span data-ttu-id="b1d5a-216">ゲスト アクセスと比べて外部アクセスはどう違うのか</span><span class="sxs-lookup"><span data-stu-id="b1d5a-216">How does external access compare with guest access?</span></span>

<span data-ttu-id="b1d5a-217">外部アクセスとゲスト アクセスの違いの詳細ついては、「[Microsoft Teams の別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1d5a-217">To learn about the difference between external access and guest access, read [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1d5a-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1d5a-218">Related topics</span></span>

- [<span data-ttu-id="b1d5a-219">外部 (フェデレーション) ユーザー向けのネイティブ チャット機能</span><span class="sxs-lookup"><span data-stu-id="b1d5a-219">Native chat experience for external (federated) users</span></span>](native-chat-for-external-users.md)
