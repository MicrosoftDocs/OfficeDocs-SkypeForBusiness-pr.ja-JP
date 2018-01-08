---
title: "Office 365 を使用する組織で Microsoft Teams の機能をオンにする"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "テナント全体の設定、電子メール統合、アプリ、クラウド ストレージなど、Office 365 を使用する組織でオンに設定することができるすべての Microsoft Teams 機能について説明します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: d6a4a8d10e20b57df16fac3c7ffeba0bacd64d2e
ms.sourcegitcommit: 19d7af5d60276c0a1ca3e01588b91c34a3fd0f92
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
<a name="turn-on-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="bb57d-103">Office 365 を使用する組織で Microsoft Teams の機能をオンにする</span><span class="sxs-lookup"><span data-stu-id="bb57d-103">Enable Microsoft Teams features in your Office 365 organization</span></span>
======================================================

<span data-ttu-id="bb57d-p101">Teams には、Office 365 テナント レベルでオンまたはオフにすることができる設定が複数あります。テナントで Teams をオンにすると、Teams が有効なすべてのユーザーにもテナント レベルの設定が継承されます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-p101">Microsoft Teams has multiple settings that can be enabled or disabled at the tenant level. With Teams enabled for the tenant, any user that is also enabled for Teams will inherit the settings from the tenant level.</span></span>

<span data-ttu-id="bb57d-106">Teams 内で Office 365 管理者が有効または無効にできる機能のリストを次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb57d-106">Below is the list of features an Office 365 administrator can choose to enable or disable in Teams.</span></span>

<span data-ttu-id="bb57d-107">特に明記されていない場合を除き、オプションの規定値はオンです。</span><span class="sxs-lookup"><span data-stu-id="bb57d-107">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE]
> <span data-ttu-id="bb57d-p102">Office 365 管理者はいつでも Office 365 管理センターを介して Microsoft Teams をオフにすることができます。Teams をオフにした場合でも、Microsoft Teams の有効なライセンスを所有するユーザーには Teams アプリ タイルがそのまま表示され続けます。ユーザーからライセンスを削除する方法について詳しくは、「[Microsoft Teams へのユーザー アクセスを管理する](user-access.md)」をご覧ください。Teams を無効にすると、Teams クライアントからのアクセスが遮断されます。ただし、SharePoint や OneDrive を介したファイルなど、その他のクライアントやサービスから利用できるデータには継続的に利用できます。チームを明示的に削除しない限り、すべてのデータはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="bb57d-p102">An Office 365 admin can turn off Microsoft Teams at any time in the Office 365 Admin center. Be aware that users with active Microsoft Teams licenses will continue to see the Teams app tile even if you turn off Teams. For details about how to remove licenses from users, see [Manage user access to Microsoft Teams](user-access.md). After Teams is disabled, access from the Teams client is blocked, but data available through other clients and services is still available, such as files via SharePoint and OneDrive. All data remains in place unless the teams are explicitly deleted.</span></span>

<a name="office-365-tenant-wide-settings"></a><span data-ttu-id="bb57d-113">Office 365 テナント全体の設定</span><span class="sxs-lookup"><span data-stu-id="bb57d-113">Office 365 tenant-wide settings</span></span> 
---------------------

<span data-ttu-id="bb57d-114">[**テナント全体の設定**] で、[全般]、[電子メール統合]、[アプリ]、[Custom cloud storage (カスタム クラウド ストレージ)] のオプションをオンまたはオフに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-114">In **Tenant-wide settings**, you can turn on or turn off options in General, Email integration, Apps, and Custom cloud storage.</span></span>

<span data-ttu-id="bb57d-115">Teams の**テナント全体の設定**を編集するには、Office 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="bb57d-115">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="bb57d-116">[**設定**]  >  [**サービスとアドイン**]  >  [**Microsoft Teams**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bb57d-116">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

### <a name="general"></a><span data-ttu-id="bb57d-117">全般</span><span class="sxs-lookup"><span data-stu-id="bb57d-117">General</span></span>

<span data-ttu-id="bb57d-118">[全般] セクションでは組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-118">The General section lets you configure the following settings for your organization:</span></span>

> ![テナント全体にわたる設定の [全般] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   <span data-ttu-id="bb57d-120">**個人プロファイルに組織図を表示する:** この設定を有効にすると、組織図アイコンがユーザーの連絡先カードに表示されます。このアイコンをクリックすると、詳細な組織図が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-120">**Show organizational chart in personal profile:** When this setting is enabled, it shows the organizational chart icon in the user’s contact card and when clicked, it displays the detailed organizational chart.</span></span>

    ![ユーザーの連絡先カードの [組織図] アイコンのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![組織図のスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-   <span data-ttu-id="bb57d-123">**Teams を所有していない受信者に対して Skype for Business を使用する:** この設定を有効にすると、Teams のユーザーは組織内で Teams が有効でないユーザーに対して Skype for Business 経由で連絡することができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-123">**Use Skype for Business for recipients who don’t have Microsoft Teams:** When this setting is enabled, it allows Microsoft Teams users to contact other users in the organization that are not enabled for Microsoft Teams via Skype for Business.</span></span>

-   <span data-ttu-id="bb57d-124">**T-Bot がプロアクティブにヘルプ メッセージに送るのを許可する:** この設定を有効にすると、T-Bot はプライベート チャット セッションを開始し、Teams の使用に関するガイドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bb57d-124">**Allow T-bot proactive help messages:** When this setting is enabled, T-bot will initiate a private chat session with users to guide them in using Microsoft Teams.</span></span>

    ![Teams インターフェイスの T-Bot セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a><span data-ttu-id="bb57d-126">電子メール統合</span><span class="sxs-lookup"><span data-stu-id="bb57d-126">Email integration</span></span>
-----------------

<span data-ttu-id="bb57d-127">この機能をオンにすると、ユーザーはチャネル電子メール アドレスを使用して、Teams のチャネルにメールを送信できるようなります。</span><span class="sxs-lookup"><span data-stu-id="bb57d-127">Turn on this feature so users can send email to a channel in Teams, using the channel email address.</span></span> <span data-ttu-id="bb57d-128">この操作は、ユーザーが所有するチームに属しているどのチャネルに対しても行えます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-128">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="bb57d-129">ユーザーのメールは、チーム メンバーに対して有効になっている追加のコネクタがあるチーム内の任意のチャネルにも送信できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-129">Users can also send emails to any channel in a team that has adding connectors enabled for team members.</span></span> <span data-ttu-id="bb57d-130">また、ユーザーにチャネル電子メール アドレスを作成するためのアクセス許可がない場合でも、権限のある他のユーザーがアドレスを作成すれば、そのアドレスに該当チャネルの \<その他アイコン\> メニューからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-130">And, even if a user doesn’t have permission to create a channel email address, if someone who does have permission creates that address, the user can access it from the \<more icon\> menu for that channel.</span></span>

<span data-ttu-id="bb57d-131">[電子メール統合] セクションでは組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-131">The Email integration section lets you configure the following settings for your organization:</span></span>

   ![テナント全体の設定の [電子メール統合] セクションのスクリーンショット。](media/QS-edu-email-integration.png)

-   <span data-ttu-id="bb57d-133">**ユーザーがチャネルにメールを送信するのを許可する:** 有効にすると、メール フックが有効に設定されます。ユーザーは Teams のチャネルの電子メール アドレス宛に電子メールを送信することでチャネルにメッセージを投稿できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bb57d-133">**Allow users to send emails to channels:** When enabled, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of Microsoft Teams channel.</span></span>

> <span data-ttu-id="bb57d-134">チャネルの電子メール アドレスを見つけるには、チャネル名の隣にある [**その他のオプション**] をクリックしてから [**電子メール アドレスの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb57d-134">To find the channel’s e-mail address, click **More options** next to the channel name and then select **Get email address**.</span></span>

-   <span data-ttu-id="bb57d-135">**送信者の制限一覧:** 送信者のドメインをさらに制限して、SMTP ドメインのみが Teams チャネルに電子メールを送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bb57d-135">**Restricted Senders List:** Senders domains can be further restricted to ensure that only allowed SMTP domains can send emails to the Microsoft Teams channels.</span></span>

<a name="apps"></a><span data-ttu-id="bb57d-136">アプリ</span><span class="sxs-lookup"><span data-stu-id="bb57d-136">Apps</span></span>
----

<span data-ttu-id="bb57d-137">Teams の [アプリ] は、チームが関心を持つツールとサービスをチャネルやチャットに統合するための優れたツールです。</span><span class="sxs-lookup"><span data-stu-id="bb57d-137">Apps in Microsoft Teams are a terrific way to integrate the tools and services your team cares about, right into any channel or chat.</span></span>

<span data-ttu-id="bb57d-138">[**アプリ**] セクションでは、組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-138">The **Apps** section lets you configure the following settings for your organization:</span></span>

![[アプリ] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

-   <span data-ttu-id="bb57d-140">**Microsoft Teams の外部アプリを許可する:** 有効にすると、ユーザーは Office 365 テナントで利用できるタブやボットを 追加することができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-140">**Allow external apps in Microsoft Teams:** When enabled, users can add tabs and bots that are available to the Office 365 tenant.</span></span>
<span data-ttu-id="bb57d-141">![[アプリ] セクションの外部アプリの許可コントロールのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)</span><span class="sxs-lookup"><span data-stu-id="bb57d-141">![Screenshot of the Allow external apps control in the Apps section.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)</span></span>

-   <span data-ttu-id="bb57d-142">**外部アプリのサイドロードを許可する:** 有効にすると、ユーザーはカスタムのボットやタブをインストールして有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-142">**Allow sideloading of external apps:** When enabled, users can install and enable custom bots and tabs.</span></span>

<a name="custom-cloud-storage"></a><span data-ttu-id="bb57d-143">カスタム クラウド ストレージ</span><span class="sxs-lookup"><span data-stu-id="bb57d-143">Custom cloud storage</span></span>
--------------------

<span data-ttu-id="bb57d-144">現時点では、Teams のクラウド ストレージ オプションには、Box、Dropbox、Google ドライブ、ShareFile があります。</span><span class="sxs-lookup"><span data-stu-id="bb57d-144">Cloud storage options in Teams currently include Box, Dropbox, Google Drive, and ShareFile.</span></span> <span data-ttu-id="bb57d-145">ユーザーは Teams チャネルやチャットでクラウド ストレージ サービスを介してファイルをアップロード、共有できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-145">Users can upload and share files from cloud storage services in Teams channels and chats.</span></span> <span data-ttu-id="bb57d-146">組織が使用するクラウド ストレージ プロバイダの横にあるトグル スイッチをクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="bb57d-146">Click or tap the toggle switch next to the cloud storage providers that your organization wants to use.</span></span>

![[カスタム クラウド ストレージ] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a><span data-ttu-id="bb57d-148">ライセンスでのユーザー設定</span><span class="sxs-lookup"><span data-stu-id="bb57d-148">User settings by license</span></span>
------------------------

<span data-ttu-id="bb57d-149">[**ライセンスでのユーザー設定**] で、[チームとチャネル]、[通話と会議]、[メッセージング] でオプションをオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-149">In **User settings by license**, you can turn on or turn off options in Teams and channels, Calls and meetings, and Messaging.</span></span>

<a name="teams-and-channels"></a><span data-ttu-id="bb57d-150">チームとチャネル</span><span class="sxs-lookup"><span data-stu-id="bb57d-150">Teams and channels</span></span>
------------------

<span data-ttu-id="bb57d-p107">チームは、業務遂行のために緊密に連携するグループ メンバーをまとめるように設計されています。チームは、プロジェクト ベースの作業向けで動的です (製品の立ち上げや、デジタル作戦指令室を作るなど)。また、組織の内部構造を反映して、随時変化していきます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-p107">A team is designed to bring together a group of people who work closely to get things done. Teams can be dynamic for project-based work (for example, launching a product or creating a digital war room). Or, teams can be ongoing, to reflect the internal structure of your organization.</span></span>

<span data-ttu-id="bb57d-p108">管理者として、ポータルの [グループ] ダッシュボードを使用して、チームの所有者とメンバーを管理することができます。[チームとチャネル] セクションで、[**Office 365 管理センターの [グループ] ダッシュボードを使用してチームを管理する**] のリンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="bb57d-p108">As an admin, you can manage team owners and members by using the Groups dashboard in the Office 365 admin center portal. In the Teams and channels section, click the link for **Use the Groups dashboard in the Office 365 admin center to manage teams**.</span></span>

<span data-ttu-id="bb57d-156">Teams でチームを作成できる組織のユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-156">You can control which users in your organization can create teams in Teams.</span></span> <span data-ttu-id="bb57d-157">Office 365 グループで定義した作成設定が Microsoft Teams にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-157">The same creation settings defined by Office 365 groups apply to Teams.</span></span> <span data-ttu-id="bb57d-158">Office 365 グループの管理の詳細については、「[Office 365 グループを作成する](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f)」および「[Office 365 グループを作成できるユーザーを管理する](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bb57d-158">You can control which users in your organization can create teams in Microsoft Teams. The same creation settings defined by Office 365 groups apply to Microsoft Teams. For more information about managing Office 365 groups, see [Create Office 365 groups](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) and [Control who can create Office 365 Groups](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

> [!NOTE]
> <span data-ttu-id="bb57d-159">[グループ] ダッシュボードでチームを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb57d-159">You can't create teams from the Groups dashboard.</span></span> <span data-ttu-id="bb57d-160">チームは、Teams デスクトップ クライアントまたは Web アプリを使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb57d-160">NOTE: You can't create teams from the Groups dashboard. Teams must be created by using the Microsoft Teams desktop client or web app.</span></span>

<span data-ttu-id="bb57d-161">既定では、どのユーザーもチームやグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-161">By default, every user can create a team or group.</span></span> <span data-ttu-id="bb57d-162">Teams クライアント (デスクトップ クライアントまたは Web アプリ) の左側にある [**チーム**] を選択し、クライアントの下部のチーム リストの下にある [**チームを作成**] を選択して、チームを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-162">By default, every user can create a team or group. Users can create teams by choosing Teams on the left side in the Microsoft Teams client (desktop client or web app), and then choosing Create team at the bottom of the client, below the team list.</span></span>

<span data-ttu-id="bb57d-p112">現在、Office 365 テナントが所有できるチームの既定の最大数は 500,000 です。グローバル管理者はチームを無制限に作成できます。1 人のユーザーが作成できるチームの数は 250 です。チーム所有者は 2500 人のメンバーをチームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-p112">The default maximum number of teams that an Office 365 tenant can have is currently 500,000. A global admin can create an unlimited number of teams. A user can create 250 teams. A team owner can add 2500 members to a team.</span></span>

![[ライセンスでのユーザー設定] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

<span data-ttu-id="bb57d-p113">チャネルは、チームのサブカテゴリーです。チームの誰もがチャネルを追加したり、チャネル内の会話に参加できます。チャネルは、アクティビティや部署用に作成します。会話、ファイル、Wiki は、各チャネルに固有ですが、チーム内の全メンバーが見ることができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-p113">Channels are subcategories of teams. Anyone on the team can add a channel and participate in the conversations in a channel. You might create a channel for an activity or for a department. Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

### <a name="calls-and-meetings"></a><span data-ttu-id="bb57d-172">通話と会議</span><span class="sxs-lookup"><span data-stu-id="bb57d-172">Calls and meetings</span></span>

<span data-ttu-id="bb57d-173">[**通話と会話**] セクションでは、組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-173">The **Calls and meetings** section lets you configure the following settings for your organization:</span></span>

> ![[通話と会話] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

-   <span data-ttu-id="bb57d-175">**Allow scheduling for private meetings (プライベート会議の予約を許可する):** 有効の場合、ユーザーはいずれのチャネルにもリストされていないプライベート会議を予約できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-175">**Allow scheduling for private meetings:** When enabled, users can schedule private meetings that are not listed in any channel.</span></span>

-   <span data-ttu-id="bb57d-176">**Allow ad-hoc channel meetup (臨時のチャネル会合を許可する):**</span><span class="sxs-lookup"><span data-stu-id="bb57d-176">**Allow ad-hoc channel meetup:**</span></span>

-   <span data-ttu-id="bb57d-177">**Allow scheduling for channel meetings (チャネル会議の予約を許可する):** 有効の場合、ユーザーは、すべてのチャネル メンバーが 1 回のクリックで簡単に参加できるチャネルの会議を予約することができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-177">**Allow scheduling for channel meetings:** When enabled, users can schedule a meeting for a channel that all channel members can easily join with a single click.</span></span>

-   <span data-ttu-id="bb57d-178">**会議のビデオを許可:** 会議でビデオの使用を許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb57d-178">**Allow videos in meetings:** Specifies whether the use of video is allowed within the meetings.</span></span>

-   <span data-ttu-id="bb57d-179">**会議の画面共有を許可:** 会議で画面共有を許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb57d-179">**Allow screen sharing in meetings:** Specifies whether screen sharing is allowed within the meetings.</span></span>

-   <span data-ttu-id="bb57d-180">**プライベート通話を許可:** 有効の場合、ユーザーはプライベート通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-180">**Allow private calling:** When enabled, users can make private calls.</span></span>

<span data-ttu-id="bb57d-p114">会議に参加できる人の最大数は 80人です。プライベート チャットでは、チャットの作成者を含め、最大 20 人です。</span><span class="sxs-lookup"><span data-stu-id="bb57d-p114">The maximum number of people in a meeting is 80. There can be 20 members in a private chat, including the user who created the chat.</span></span>

### <a name="messaging"></a><span data-ttu-id="bb57d-183">メッセージング</span><span class="sxs-lookup"><span data-stu-id="bb57d-183">Messaging</span></span> 

<span data-ttu-id="bb57d-184">[メッセージング] セクションでは組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-184">The Messaging section lets you configure the following settings for your organization:</span></span>

![[メッセージング] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   <span data-ttu-id="bb57d-186">**Giphy を有効にして会話に gif を追加できるようにする:** 有効の場合、ユーザーは会話内でアニメーション画像を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-186">**Enable Giphy so users can add gifs to conversations:** When enabled, users can use animated pictures within the conversations.</span></span>

    -   <span data-ttu-id="bb57d-p115">**コンテンツ評価:** アニメーション画像がオンの場合は、コンテンツ評価を適用して、会話に表示できるアニメーション画像の種類を制限することができます。利用可能なコンテンツ評価は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bb57d-p115">**Content Rating:** When animated images are turned on, content rating can be applied to restrict the type of animated images that can be displayed in conversations. Available content rating options are:</span></span>

        -   <span data-ttu-id="bb57d-189">制限なし</span><span class="sxs-lookup"><span data-stu-id="bb57d-189">No restriction</span></span>

        -   <span data-ttu-id="bb57d-190">中レベル (規定値)</span><span class="sxs-lookup"><span data-stu-id="bb57d-190">Moderate (the default value)</span></span>

        -   <span data-ttu-id="bb57d-191">厳密</span><span class="sxs-lookup"><span data-stu-id="bb57d-191">Strict</span></span>

-   <span data-ttu-id="bb57d-192">**Enable memes that users can edit and add to conversations (ミームを編集したり会話に追加できようにする):** 有効の場合、ユーザーはインターネット ミームを使用してユーモアのあるメッセージを投稿できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-192">**Enable memes that users can edit and add to conversations:** When enabled, users can use internet memes to make humorous posts.</span></span>

-   <span data-ttu-id="bb57d-193">**Enable stickers that users can edit and add to conversations (ステッカーを編集したり会話に追加できようにする):** 有効の場合、ユーザーは編集可能なテキストを含む画像を投稿して、チャネル メンバーに注目させることができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-193">**Enable stickers that users can edit and add to conversations:** When enabled, users can post images with editable text to get channel members attention.</span></span>

-   <span data-ttu-id="bb57d-194">**所有者がすべてのメッセージを削除することを許可する:** 有効の場合、チャネルの所有者はチャネルのすべてのメッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-194">**Allow owners to delete all messages:** When enabled, channel owners can remove all messages in a channel.</span></span>

-   <span data-ttu-id="bb57d-195">**ユーザーが自分のメッセージを編集することを許可する:** 有効の場合、ユーザーは自分のメッセージを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-195">**Allow users to edit their own messages:** When enabled, users can edit their own messages.</span></span>

-   <span data-ttu-id="bb57d-196">**ユーザーが自分のメッセージを削除することを許可する:** 有効の場合、ユーザーは自分のメッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-196">**Allow users to delete their own messages:** When enabled, users can delete their own messages.</span></span>

-   <span data-ttu-id="bb57d-197">**Allow users to chat privately (ユーザーがプライベートでチャットすることを許可する):** 有効の場合、ユーザーは、チーム メンバー全員ではなく、チャット内のユーザーにのみ表示されるプライベート チャットに参加できます。</span><span class="sxs-lookup"><span data-stu-id="bb57d-197">**Allow users to chat privately:** When enabled, users can engage in private chats that are visible only to the people in the chat, instead of everyone on the team.</span></span>


| |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |<span data-ttu-id="bb57d-199">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="bb57d-199">Decision Point</span></span>         |<span data-ttu-id="bb57d-200">組織で有効にする Microsoft Teams の設定を教えてください。</span><span class="sxs-lookup"><span data-stu-id="bb57d-200">What settings for Microsoft Teams will your organization enable?</span></span>         |
|![次のステップ アイコン。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |<span data-ttu-id="bb57d-202">次のステップ</span><span class="sxs-lookup"><span data-stu-id="bb57d-202">Next Steps</span></span>        |<span data-ttu-id="bb57d-203">[Microsoft Teams で役割と権限を割り当てる](assign-roles-permissions.md)の表における、これらの決定を文書化します。</span><span class="sxs-lookup"><span data-stu-id="bb57d-203">Document these decisions in the table in [Assign roles and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>         |

