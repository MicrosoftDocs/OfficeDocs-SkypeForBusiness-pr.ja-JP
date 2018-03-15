---
title: "Office 365 を使用する組織で Microsoft Teams の機能をオンにする"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "テナント全体の設定、電子メール統合、アプリ、クラウド ストレージなど、Office 365 を使用する組織でオンまたはオフに設定することができるすべての Microsoft Teams 機能について説明します。"
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87871cb46c1b9e584308b75376622473a3131888
ms.sourcegitcommit: 50446359cd7c359eb2536176545291c723392e47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2018
---
<a name="turn-on-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="5e118-103">Office 365 を使用する組織で Microsoft Teams の機能をオンにする</span><span class="sxs-lookup"><span data-stu-id="5e118-103">Turn on Microsoft Teams features in your Office 365 organization</span></span>
======================================================

<span data-ttu-id="5e118-p101">Teams には、Office 365 テナント レベルでオンまたはオフにすることができる設定が複数あります。テナントで Teams をオンにすると、Teams が有効なすべてのユーザーにもテナント レベルの設定が継承されます。</span><span class="sxs-lookup"><span data-stu-id="5e118-p101">Teams has multiple settings that can be turned on or turned off at the Office 365 tenant level. With Teams turned on for a tenant, any user that is also enabled for Teams will inherit the settings from the tenant level.</span></span>

<span data-ttu-id="5e118-106">Teams 内で Office 365 管理者がオンまたはオフにできる機能のリストを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5e118-106">Below is the list of features an Office 365 administrator can turn on or turn off in Teams.</span></span> 

<span data-ttu-id="5e118-107">特に明記されていない場合を除き、オプションの規定値はオンです。</span><span class="sxs-lookup"><span data-stu-id="5e118-107">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="5e118-108">Teams についての管理設定を管理するには、Office 365 管理センターに移動して、[**設定**] > [**サービスとアドイン**] を開いて、[**Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e118-108">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="5e118-109">Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-109">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> <span data-ttu-id="5e118-110">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="5e118-110">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="5e118-p103">Office 365 管理者はいつでも Office 365 管理センターを介して Microsoft Teams をオフにすることができます。Teams をオフにした場合でも、Microsoft Teams の有効なライセンスを所有するユーザーには Teams アプリ タイルがそのまま表示され続けます。ユーザーからライセンスを削除する方法について詳しくは、「[Microsoft Teams へのユーザー アクセスを管理する](user-access.md)」をご覧ください。Teams を無効にすると、Teams クライアントからのアクセスが遮断されます。ただし、SharePoint や OneDrive を介したファイルなど、その他のクライアントやサービスから利用できるデータには継続的に利用できます。チームを明示的に削除しない限り、すべてのデータはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="5e118-p103">An Office 365 admin can turn off Microsoft Teams at any time in the Office 365 admin center. Be aware that users with active Microsoft Teams licenses will continue to see the Teams app tile even if you turn off Teams. For details about how to remove licenses from users, see [Manage user access to Microsoft Teams](user-access.md). After Teams is disabled, access from the Teams client is blocked, but data available through other clients and services is still available, such as files via SharePoint and OneDrive. All data remains in place unless the teams are explicitly deleted.</span></span>

<a name="office-365-tenant-wide-settings"></a><span data-ttu-id="5e118-116">Office 365 テナント全体の設定</span><span class="sxs-lookup"><span data-stu-id="5e118-116">Office 365 tenant-wide settings</span></span> 
---------------------

<span data-ttu-id="5e118-117">[**テナント全体の設定**] で、[全般]、[電子メール統合]、[アプリ]、[Custom cloud storage (カスタム クラウド ストレージ)] のオプションをオンまたはオフに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="5e118-117">In **Tenant-wide settings**, you can turn on or turn off options in General, Email integration, Apps, and Custom cloud storage.</span></span>

<span data-ttu-id="5e118-118">Teams の**テナント全体の設定**を編集するには、Office 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="5e118-118">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="5e118-119">[**設定**]  >  [**サービスとアドイン**]  >  [**Microsoft Teams**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5e118-119">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

### <a name="general"></a><span data-ttu-id="5e118-120">全般</span><span class="sxs-lookup"><span data-stu-id="5e118-120">General</span></span>

<span data-ttu-id="5e118-121">[全般] セクションでは組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-121">The General section lets you configure the following settings for your organization:</span></span>

> ![テナント全体にわたる設定の [全般] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   <span data-ttu-id="5e118-123">**個人プロファイルに組織図を表示する:** この設定をオンにすると、組織図アイコンがユーザーの連絡先カードに表示されます。このアイコンをクリックすると、詳細な組織図が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e118-123">**Show organizational chart in personal profile:** When this setting is turned on, it shows the organizational chart icon in the user’s contact card, and when clicked, it displays the detailed organizational chart.</span></span>

    ![ユーザーの連絡先カードの [組織図] アイコンのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![組織図のスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-  <span data-ttu-id="5e118-126">**Teams を所有していない受信者に対して Skype for Business を使用する:** この設定をオンにすると、Teams が有効になっていないユーザー向けに Teams の会話が自動的に Skype for Business に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e118-126">**Use Skype for Business for recipients who don’t have Teams:** When this setting is turned on, Teams conversations automatically show up in Skype for Business for users that aren't enabled for Teams.</span></span>  

-   <span data-ttu-id="5e118-127">**T-Bot がプロアクティブにヘルプ メッセージに送るのを許可する:** この設定をオンにすると、T-Bot はプライベート チャット セッションを開始し、ユーザーに Teams の使用に関するガイドを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e118-127">**Allow T-bot proactive help messages:** When this setting is turned on, T-bot will initiate a private chat session with users to help them use Teams.</span></span>

    ![Teams インターフェイスの T-Bot セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a><span data-ttu-id="5e118-129">電子メール統合</span><span class="sxs-lookup"><span data-stu-id="5e118-129">Email integration</span></span>
-----------------

<span data-ttu-id="5e118-130">この機能をオンにすると、ユーザーはチャネル電子メール アドレスを使用して、Teams のチャネルにメールを送信できるようなります。</span><span class="sxs-lookup"><span data-stu-id="5e118-130">Turn on this feature so users can send email to a channel in Teams, using the channel email address.</span></span> <span data-ttu-id="5e118-131">この操作は、ユーザーが所有するチームに属しているどのチャネルに対しても行えます。</span><span class="sxs-lookup"><span data-stu-id="5e118-131">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="5e118-132">ユーザーのメールは、チーム メンバーに対して有効になっている追加のコネクタがあるチーム内の任意のチャネルにも送信できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-132">Users can also send emails to any channel in a team that has adding connectors enabled for team members.</span></span> <span data-ttu-id="5e118-133">また、ユーザーにチャネル電子メール アドレスを作成するためのアクセス許可がない場合でも、アクセス許可を持つ他のユーザーがアドレスを作成すれば、そのアドレスに該当チャネルの [**その他のオプション**] メニューからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5e118-133">And, even if a user doesn’t have permission to create a channel email address, if someone who does have permission creates that address, the user can access it from the **More options** menu for that channel.</span></span>

<span data-ttu-id="5e118-134">組織のために次の [**電子メール統合**] 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5e118-134">Configure the following **Email integration** settings for your organization:</span></span> 

   ![テナント全体の設定の [電子メール統合] セクションのスクリーンショット。](media/QS-edu-email-integration.png)

-   <span data-ttu-id="5e118-136">**ユーザーがチャネルにメールを送信するのを許可する:** オンにすると、メール フックが有効に設定されます。ユーザーは Teams のチャネルの電子メール アドレス宛に電子メールを送信することでチャネルにメッセージを投稿できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5e118-136">**Allow users to send emails to channels:** When turned on, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of a Teams channel.</span></span> 

 
-   <span data-ttu-id="5e118-137">**ユーザーがチャネルにメールを送信するのを許可する:** オンにすると、メール フックが有効に設定されます。ユーザーは Teams のチャネルの電子メール アドレス宛に電子メールを送信することでチャネルにメッセージを投稿できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5e118-137">**Allow users to send emails to channels:** When turned on, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of Teams channel.</span></span> 

    <span data-ttu-id="5e118-138">チャネルの電子メール アドレスを見つけるには、そのチャネルの [**その他のオプション**] メニューをクリックしてから [**電子メール アドレスの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e118-138">To find the email address for a channel, click the **More options** menu for the channel and then select **Get email address**.</span></span> 

-   <span data-ttu-id="5e118-139">**送信者の制限一覧:** 送信者のドメインをさらに制限して、SMTP ドメインのみが Teams チャネルに電子メールを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5e118-139">**Restricted Senders List:** Senders domains can be further restricted to ensure that only allowed SMTP domains can send emails to the Teams channels.</span></span>

<a name="apps"></a><span data-ttu-id="5e118-140">アプリ</span><span class="sxs-lookup"><span data-stu-id="5e118-140">Apps</span></span>
----

<span data-ttu-id="5e118-p106">アプリとは、単一のサードパーティ サービスによって提供されるタブ、コネクタ、ボットという 3 つの要素のあらゆる組み合わせで構成されているものです。Office 365 管理センターで構成可能な Teams 管理ポリシーを使用すると、許可する外部サードパーティ アプリを制御することができます。このポリシーでは、許可または禁止するアプリ、新しい外部アプリの動作、アプリのサイドロードを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-p106">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="5e118-144">[**アプリ**] の下で、組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-144">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![[アプリ] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="5e118-146">**Microsoft Teams の外部アプリを許可する**: このスイッチがオンになると、ユーザーは Office 365 テナントで利用できるタブやボットを 追加することができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-146">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![[アプリ] セクションの外部アプリの許可コントロールのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="5e118-148">**既定で新しい外部アプリを有効にする**: このスイッチがオンになると、ユーザーは Teams アプリ カタログに新しいアプリが追加されるとそれをすぐにアクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-148">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="5e118-149">新しいアプリに対する制御を行う場合はこのスイッチをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5e118-149">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="5e118-150">これをオフにする場合は、自分の組織で優れた新しいアプリを利用する機会を失うことがないように、新しいアプリについて忘れずに定期的に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e118-150">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="5e118-151">**外部アプリのサイドロードを許可する:** このスイッチがオンになると、ユーザーはカスタムのボットやタブをインストールして有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-151">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="5e118-152">詳細については、[Teams でのアプリの管理設定](admin-settings.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e118-152">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 



<a name="custom-cloud-storage"></a><span data-ttu-id="5e118-153">カスタム クラウド ストレージ</span><span class="sxs-lookup"><span data-stu-id="5e118-153">Custom cloud storage</span></span>
--------------------

<span data-ttu-id="5e118-154">現時点では、Teams のクラウド ストレージ オプションには、Box、Dropbox、Google ドライブ、ShareFile があります。</span><span class="sxs-lookup"><span data-stu-id="5e118-154">Cloud storage options in Teams currently include Box, Dropbox, Google Drive, and ShareFile.</span></span> <span data-ttu-id="5e118-155">ユーザーは Teams チャネルやチャットでクラウド ストレージ サービスを介してファイルをアップロード、共有できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-155">Users can upload and share files from cloud storage services in Teams channels and chats.</span></span> <span data-ttu-id="5e118-156">組織で使用することになるクラウド ストレージ プロバイダのスイッチをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5e118-156">Turn on the switch for the cloud storage providers that your organization wants to use.</span></span> 

![[カスタム クラウド ストレージ] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a><span data-ttu-id="5e118-158">ライセンスでのユーザー設定</span><span class="sxs-lookup"><span data-stu-id="5e118-158">User settings by license</span></span>
------------------------

<span data-ttu-id="5e118-159">[**ライセンスでのユーザー設定**] で、[チームとチャネル]、[通話と会議]、[メッセージング] でオプションをオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="5e118-159">In **User settings by license**, you can turn on or turn off options in Teams and channels, Calls and meetings, and Messaging.</span></span>

<a name="teams-and-channels"></a><span data-ttu-id="5e118-160">チームとチャネル</span><span class="sxs-lookup"><span data-stu-id="5e118-160">Teams and channels</span></span>
------------------

<span data-ttu-id="5e118-p109">チームは、業務遂行のために緊密に連携するグループ メンバーをまとめるように設計されています。チームは、プロジェクト ベースの作業向けで動的です (製品の立ち上げや、デジタル作戦指令室を作るなど)。また、組織の内部構造を反映して、随時変化していきます。</span><span class="sxs-lookup"><span data-stu-id="5e118-p109">A team is designed to bring together a group of people who work closely to get things done. Teams can be dynamic for project-based work (for example, launching a product or creating a digital war room). Or, teams can be ongoing, to reflect the internal structure of your organization.</span></span>

<span data-ttu-id="5e118-164">Office 365 テナントが所有できるチームの最大数は現在 500,000 です。</span><span class="sxs-lookup"><span data-stu-id="5e118-164">The maximum number of teams that an Office 365 tenant can have is currently 500,000.</span></span> <span data-ttu-id="5e118-165">グローバル管理者はチームを無制限に作成できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-165">A global admin can create an unlimited number of teams.</span></span> <span data-ttu-id="5e118-166">ユーザーは 250 個のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-166">A user can create 250 teams.</span></span> <span data-ttu-id="5e118-167">チーム所有者はチームに 2500 人のメンバーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-167">A team owner can add 2500 members to a team.</span></span>

<span data-ttu-id="5e118-168">管理者として、Office 365 管理センターの [グループ] ダッシュボードを使用して、チームの所有者とメンバーを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-168">As an admin, you can manage team owners and members by using the Groups dashboard in the Office 365 admin center.</span></span> <span data-ttu-id="5e118-169">詳細については、[**チームとチャネル**] の [**Office 365 管理センターの [グループ] ダッシュボードを使用してチームを管理する**] をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="5e118-169">To learn more, click **Use the Groups dashboard in the Office 365 admin center to manage teams** under **Teams and channels**.</span></span>

<span data-ttu-id="5e118-170">Teams でチームを作成できる組織のユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-170">You can control which users in your organization can create teams in Teams.</span></span> <span data-ttu-id="5e118-171">Office 365 グループで定義した作成設定が Microsoft Teams にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e118-171">The same creation settings defined by Office 365 groups apply to Teams.</span></span> <span data-ttu-id="5e118-172">Office 365 グループの管理の詳細については、「[Office 365 グループを作成する](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f)」および「[Office 365 グループを作成できるユーザーを管理する](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e118-172">For more information about managing Office 365 groups, see [Create Office 365 groups](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) and [Control who can create Office 365 Groups](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

> [!NOTE]
> <span data-ttu-id="5e118-173">[グループ] ダッシュボードでチームを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="5e118-173">You can't create teams from the Groups dashboard.</span></span> <span data-ttu-id="5e118-174">チームは、Teams デスクトップ クライアントまたは Web アプリを使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e118-174">Teams must be created by using the Teams desktop client or web app.</span></span>

<span data-ttu-id="5e118-175">既定では、どのユーザーもチームやグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-175">By default, every user can create a team or group.</span></span> <span data-ttu-id="5e118-176">Teams クライアント (デスクトップ クライアントまたは Web アプリ) の左側にある [**チーム**] を選択し、クライアントの下部のチーム リストの下にある [**チームを作成**] を選択して、チームを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-176">Choose **Teams** on the left side in the Teams client (desktop client or web app), then choose **Create and join team** at the bottom of the client, below the team list.</span></span>

![[ライセンスでのユーザー設定] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

<span data-ttu-id="5e118-p115">チャネルは、チームのサブカテゴリーです。チームの誰もがチャネルを追加したり、チャネル内の会話に参加できます。チャネルは、アクティビティや部署用に作成します。会話、ファイル、Wiki は、各チャネルに固有ですが、チーム内の全メンバーが見ることができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-p115">Channels are subcategories of teams. Anyone on the team can add a channel and participate in the conversations in a channel. You might create a channel for an activity or for a department. Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

## <a name="calls-and-meetings"></a><span data-ttu-id="5e118-182">通話と会議</span><span class="sxs-lookup"><span data-stu-id="5e118-182">Calls and meetings</span></span>

<span data-ttu-id="5e118-183">組織のために次の [**通話と会議**] 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5e118-183">Configure the following **Calls and meetings** settings for your organization:</span></span>

![[通話と会話] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="5e118-p116">会議に参加できる人の最大数は 80人です。プライベート チャットでは、チャットの作成者を含め、最大 20 人です。</span><span class="sxs-lookup"><span data-stu-id="5e118-p116">The maximum number of people in a meeting is 80. There can be 20 members in a private chat, including the user who created the chat.</span></span>

-   <span data-ttu-id="5e118-187">**Allow scheduling for private meetings (プライベート会議の予約を許可する):** オンの場合、ユーザーはいずれのチャネルにもリストされていないプライベート会議を予約できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-187">**Allow scheduling for private meetings**: When turned on, users can schedule private meetings that are not listed in any channel.</span></span>

-   <span data-ttu-id="5e118-188">**Allow ad-hoc channel meetup (臨時のチャネル会合を許可する)**: オンの場合、ユーザーは目前の目的または特定の目的のために作成されたチャネルで会議を速やかに開始することができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-188">**Allow ad-hoc channel meetup**: When turned on, users can quickly start a meeting for a channel that has been created for an immediate or specific purpose.</span></span>

-   <span data-ttu-id="5e118-189">**Allow scheduling for channel meetings (チャネル会議の予約を許可する):** オンの場合、ユーザーは、すべてのチャネル メンバーが 1 回のクリックで簡単に参加できるチャネルの会議を予約することができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-189">**Allow scheduling for channel meetings**: When turned on, users can schedule a meeting for a channel that all channel members can easily join with a single click.</span></span>

-   <span data-ttu-id="5e118-190">**会議のビデオを許可:** 会議でビデオの使用を許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e118-190">**Allow videos in meetings:** Specifies whether the use of video is allowed in meetings.</span></span>

-   <span data-ttu-id="5e118-191">**会議の画面共有を許可:** 会議で画面共有を許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e118-191">**Allow screen sharing in meetings**: Specifies whether screen sharing is allowed in meetings.</span></span>

-   <span data-ttu-id="5e118-192">**プライベート通話を許可:** オンの場合、ユーザーはプライベート通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-192">**Allow private calling**: When turned on, users can make private calls.</span></span>

## <a name="messaging"></a><span data-ttu-id="5e118-193">メッセージング</span><span class="sxs-lookup"><span data-stu-id="5e118-193">Messaging</span></span> 

<span data-ttu-id="5e118-194">[メッセージング] セクションでは組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-194">The Messaging section lets you configure the following settings for your organization:</span></span>

![[メッセージング] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   <span data-ttu-id="5e118-196">**Giphy を有効にして会話に gif を追加できるようにする:** オンの場合、ユーザーは会話内でアニメーション画像を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-196">**Enable Giphy so users can add gifs to conversations**: When turned on, users can use animated pictures within the conversations.</span></span>

-   <span data-ttu-id="5e118-197">**コンテンツ評価:** アニメーション画像がオンの場合は、コンテンツ評価を適用して、会話に表示できるアニメーション画像の種類を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-197">**Content Rating**: When animated images are turned on, content rating can be applied to restrict the type of animated images that can be displayed in conversations.</span></span> <span data-ttu-id="5e118-198">利用可能なコンテンツ評価は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e118-198">Available content rating options are:</span></span>

    -   <span data-ttu-id="5e118-199">制限なし</span><span class="sxs-lookup"><span data-stu-id="5e118-199">No restriction</span></span>
    -   <span data-ttu-id="5e118-200">中レベル (規定値)</span><span class="sxs-lookup"><span data-stu-id="5e118-200">Moderate (the default value)</span></span>
    -   <span data-ttu-id="5e118-201">厳密</span><span class="sxs-lookup"><span data-stu-id="5e118-201">Strict</span></span>

-   <span data-ttu-id="5e118-202">**Enable memes that users can edit and add to conversations (ミームを編集したり会話に追加できようにする):** オンの場合、ユーザーはインターネット ミームを使用してユーモアのあるメッセージを投稿できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-202">**Enable memes that users can edit and add to conversations**: When turned on, users can use internet memes to make humorous posts.</span></span>

-   <span data-ttu-id="5e118-203">**Enable stickers that users can edit and add to conversations (ステッカーを編集したり会話に追加できようにする):** オンの場合、ユーザーは編集可能なテキストを含む画像を投稿して、チャネル メンバーに注目させることができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-203">**Enable stickers that users can edit and add to conversations**: When turned on, users can post images with editable text to get channel members attention.</span></span>

-   <span data-ttu-id="5e118-204">**所有者がすべてのメッセージを削除することを許可する:** オンの場合、チャネルの所有者はチャネルのすべてのメッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-204">**Allow owners to delete all messages**: When turned on, channel owners can remove all messages in a channel.</span></span>

-   <span data-ttu-id="5e118-205">**ユーザーが自分のメッセージを編集することを許可する:** オンの場合、ユーザーは自分のメッセージを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-205">**Allow users to edit their own messages**: When turned on, users can edit their own messages.</span></span>

-   <span data-ttu-id="5e118-206">**ユーザーが自分のメッセージを削除することを許可する:** オンの場合、ユーザーは自分のメッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5e118-206">**Allow users to delete their own messages**: When turned on, users can delete their own messages.</span></span>

-   <span data-ttu-id="5e118-207">**Allow users to chat privately (ユーザーがプライベートでチャットすることを許可する):** オンの場合、ユーザーは、チーム メンバー全員ではなく、チャット内のユーザーにのみ表示されるプライベート チャットに参加できます。</span><span class="sxs-lookup"><span data-stu-id="5e118-207">**Allow users to chat privately**: When turned on, users can engage in private chats that are visible only to the people in the chat, instead of everyone on the team.</span></span>


| |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |<span data-ttu-id="5e118-209">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="5e118-209">Decision Point</span></span>         |<span data-ttu-id="5e118-210">組織で有効にする Microsoft Teams の設定を教えてください。</span><span class="sxs-lookup"><span data-stu-id="5e118-210">What settings for Microsoft Teams will your organization enable?</span></span>         |
|![次のステップ アイコン。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |<span data-ttu-id="5e118-212">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5e118-212">Next Steps</span></span>        |<span data-ttu-id="5e118-213">[Microsoft Teams で役割と権限を割り当てる](assign-roles-permissions.md)の表における、これらの決定を文書化します。</span><span class="sxs-lookup"><span data-stu-id="5e118-213">Document these decisions in the table in [Assign roles and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>         |

