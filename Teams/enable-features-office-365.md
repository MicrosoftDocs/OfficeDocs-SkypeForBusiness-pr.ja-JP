---
title: 組織の設定を管理する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: アプリ、外部アクセス、ゲストアクセス、Teams の設定、Teams のアップグレード設定など、Microsoft Teams の組織全体の設定をオンまたはオフにする方法について説明します。
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.teamssettings.targetingintro
- ms.teamsadmincenter.teamssettings.overview
- NewAdminCenter_Update
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d2e334269dd31b876dd18b62a9b61ae1b583c504
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790529"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a><span data-ttu-id="e3728-103">組織の Microsoft Teams の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="e3728-103">Manage Microsoft Teams settings for your organization</span></span>

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e3728-104">Microsoft Teams 管理センターでの Teams アプリの設定</span><span class="sxs-lookup"><span data-stu-id="e3728-104">Teams apps settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="e3728-105">[Microsoft Teams 管理センター](https://admin.teams.microsoft.com)で、 **Teams アプリ** の組織向けアプリを管理します。</span><span class="sxs-lookup"><span data-stu-id="e3728-105">You manage apps for your organization in **Teams apps** in the [Microsoft Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="e3728-106">たとえば、組織全体または特定の Teams ユーザーが使用できるアプリを制御するポリシーを設定したり、ユーザーにとって最も重要なアプリをピン留めして Teams をカスタマイズしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e3728-106">For example, you can set policies to control what apps are available org-wide or to specific Teams users and you can customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="e3728-107">詳細については、「[Teams でのアプリの管理設定](admin-settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e3728-107">To learn more, see [Admin settings for apps in  Teams](admin-settings.md).</span></span>  

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e3728-108">Microsoft Teams 管理センターでの Teams の組織全体の設定</span><span class="sxs-lookup"><span data-stu-id="e3728-108">Teams org-wide settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="e3728-p102">Microsoft Teams 管理センターで、組織全体のユーザー設定を制御することができます。組織全体の設定を編集するには、Microsoft Teams 管理センターに移動して、 **[Org-wide settings (組織全体の設定)]** を選択します。次の設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="e3728-p102">You can control organization-wide user settings in the Microsoft Teams admin center. To edit org-wide settings, go to the Microsoft Teams admin center, and then select **Org-wide settings** . You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="e3728-112">外部アクセス</span><span class="sxs-lookup"><span data-stu-id="e3728-112">External access</span></span>

<span data-ttu-id="e3728-113">**外部アクセス** では、Teams および Skype for Business のユーザーが、組織やドメインの外部ユーザーと通信するように設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e3728-113">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization or domain.</span></span> <span data-ttu-id="e3728-114">外部アクセスを構成するには、「[Teams のユーザーが別の Teams 組織のユーザーとチャットおよび通信できるようにする](let-your-teams-users-communicate-with-other-people.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3728-114">To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

<span data-ttu-id="e3728-115">ドメインを追加またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="e3728-115">To add or block a domain:</span></span>

1. <span data-ttu-id="e3728-116">[ **ドメインの追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3728-116">Select **Add a domain** .</span></span>
2. <span data-ttu-id="e3728-117">[ドメインの追加] ウィンドウで、ドメイン名を入力し、スペース バーをクリックして名前を保存します。</span><span class="sxs-lookup"><span data-stu-id="e3728-117">In the Add a domain pane, enter the domain name, and click the space bar to save the name.</span></span>
3. <span data-ttu-id="e3728-118">[ **許可** ] または [ **禁止** ]を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3728-118">Select **Allowed** or **Blocked** .</span></span>
4. <span data-ttu-id="e3728-119">[ **完了** ] を選んで変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="e3728-119">Select **Done** to save your changes.</span></span> 

### <a name="guest-access"></a><span data-ttu-id="e3728-120">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="e3728-120">Guest access</span></span>

<span data-ttu-id="e3728-p104">Microsoft Teams での **ゲスト アクセス** により、組織内のチームは組織外のユーザーにチームおよびチャネルへのアクセス権を付与することで、それらのユーザーと共同作業することができるようになります。Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、チーム チャット、会議、ファイルに完全なアクセス権を持つゲストとして Teams に参加することができます。詳細については、「 [Guest access in Microsoft Teams (Microsoft Teams でのゲスト アクセス)](guest-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e3728-p104">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="e3728-124">Teams の設定</span><span class="sxs-lookup"><span data-stu-id="e3728-124">Teams settings</span></span>

<span data-ttu-id="e3728-125">**Teams の設定** で、通知とフィード、メールの統合、クラウド ストレージのオプション、デバイスなど、Teams の機能を設定できます。</span><span class="sxs-lookup"><span data-stu-id="e3728-125">In **Teams settings** , you can set up features for teams including notifications and feeds, email integration, cloud storage options, and devices.</span></span>

#### <a name="notifications-and-feeds"></a><span data-ttu-id="e3728-126">通知とフィード</span><span class="sxs-lookup"><span data-stu-id="e3728-126">Notifications and feeds</span></span>

<span data-ttu-id="e3728-127">ここで、サジェストされたフィードを Teams のユーザーのアクティビティ フィードに表示するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="e3728-127">Here you can control whether suggested feeds appear in users' activity feed in Teams.</span></span> <span data-ttu-id="e3728-128">アクティビティ フィードの詳細については、「[Teams でアクティビティ フィードを詳しく見る](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e3728-128">To learn more about the activity feed, see [Explore the Activity feed in Teams](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56).</span></span>

#### <a name="tagging"></a><span data-ttu-id="e3728-129">タグ付け</span><span class="sxs-lookup"><span data-stu-id="e3728-129">Tagging</span></span>

<span data-ttu-id="e3728-130">タグを使用すると、ユーザーはチーム内の一部のユーザーとコミュニケーションをとることができます。</span><span class="sxs-lookup"><span data-stu-id="e3728-130">Tags let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="e3728-131">タグは、1 つまたは複数のチーム メンバーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="e3728-131">Tags can be added to one or more team members.</span></span> <span data-ttu-id="e3728-132">タグを追加した後、そのタグを割り当てられた人のみとコミュニケーションするために、チャネル投稿のチームの誰でもタグを @メンションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3728-132">After a tag is added, it can be used in @mentions by anyone on the team in a channel post to communicate with only those people who are assigned that tag.</span></span> <span data-ttu-id="e3728-133">これらの設定を使用して、組織全体でタグを追加できるユーザーおよびタグの使用方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="e3728-133">Use these settings to control who can add tags and how tags are used across your organization.</span></span> <span data-ttu-id="e3728-134">詳細については、「[Teams でタグを管理する](manage-tags.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3728-134">To learn more, see [Manage tags in Teams](manage-tags.md).</span></span>

#### <a name="email-integration"></a><span data-ttu-id="e3728-135">電子メールの統合</span><span class="sxs-lookup"><span data-stu-id="e3728-135">Email integration</span></span>

<span data-ttu-id="e3728-p107">この機能をオンにすると、ユーザーはチャネル電子メール アドレスを使用して、Teams のチャネルにメールを送信できるようなります。この操作は、ユーザーが所有するチームに属しているどのチャネルに対しても行えます。ユーザーのメールは、チーム メンバーに対してオンになっている追加のコネクタがあるチーム内の任意のチャネルにも送信できます。電子メール統合をオンにするには、[ **Allow users to send emails to a channel email address (ユーザーがメールをチャネルの電子メール アドレスに送信できるようにする)** ] が [ **オン** ] であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e3728-p107">Turn on this feature so users can send email to a channel in Teams, using the channel email address. Users can do this for any channel belonging to a team they own. Users can also send emails to any channel in a team that has adding connectors turned on for team members. To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On** .</span></span>

#### <a name="files"></a><span data-ttu-id="e3728-140">ファイル</span><span class="sxs-lookup"><span data-stu-id="e3728-140">Files</span></span>

<span data-ttu-id="e3728-141">ファイル共有オプションおよびファイル保存オプションをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e3728-141">Here you can turn on or turn off file sharing and cloud file storage options.</span></span>

<span data-ttu-id="e3728-p108">ユーザーは Teams のチャネルやチャットでクラウド ストレージ サービスを介して、ファイルのアップロードや共有を行うことができます。現時点では、Teams のクラウド ストレージ オプションには、Box、Dropbox、Google ドライブ、Egnyte があります。自分の組織で使用することになるクラウド ストレージ プロバイダのスイッチをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e3728-p108">Users can upload and share files from cloud storage services in Teams channels and chats. Cloud storage options in Teams currently include Dropbox, Box, ShareFile, Google Drive, and Egnyte. Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="e3728-145">組織</span><span class="sxs-lookup"><span data-stu-id="e3728-145">Organization</span></span>

<span data-ttu-id="e3728-p109">ユーザーの組織について詳細な組織図を示す、[ **組織** ] タブをオンにすることができます。詳細については、「 [Teams で組織タブを使用する](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e3728-p109">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user's organization. For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="devices"></a><span data-ttu-id="e3728-148">デバイス</span><span class="sxs-lookup"><span data-stu-id="e3728-148">Devices</span></span>

<span data-ttu-id="e3728-p110">これらの設定により、Microsoft Teams 会議に参加している Surface Hub デバイスのリソース アカウントの動作を制御します。これらの設定を使用して、認証の要件を構成し、コンテンツ PIN を要求し、Surface Hub リソース アカウントをオンにしてメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e3728-p110">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings. Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="e3728-151">**Require a secondary form of authentication to access meeting content (会議のコンテンツにアクセスするための認証のセカンダリ フォームを要求する)** – コンテンツ PIN を入力するときにユーザーが持つアクセスのレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3728-151">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="e3728-p111">**Set content PIN (コンテンツ PIN を設定する)** – ドキュメントに対する未承認のアクセスを防ぐためにこの PIN を入力するようにユーザーに要求します。これにより、未承認のユーザーが今後の会議に参加したり、添付ファイルを参照したりすることを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="e3728-p111">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents. This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="e3728-154">**Resource accounts can send messages (リソース アカウントがメッセージを送信することができる)** – この設定を [ **オン** ] にすると、メッセージが Surface Hub リソース アカウントから送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="e3728-154">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search-by-name"></a><span data-ttu-id="e3728-155">名前で検索</span><span class="sxs-lookup"><span data-stu-id="e3728-155">Search by name</span></span>

<span data-ttu-id="e3728-p112">Microsoft Teams の範囲指定ディレクトリ検索では、アドレス帳ポリシー (APB) を使用して、組織がどのように組織内のユーザーを検索するか、およびそれらのユーザーと通信するかを制御するために、仮想の境界を作成することができます。範囲指定ディレクトリ検索を使用することが考えられる状況は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3728-p112">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization. You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="e3728-158">所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。</span><span class="sxs-lookup"><span data-stu-id="e3728-158">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="e3728-159">所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="e3728-159">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="e3728-160">範囲指定ディレクトリ検索をオンにするには、この設定を [ **オン** ] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e3728-160">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="e3728-161">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e3728-161">Skype for Business</span></span>

<span data-ttu-id="e3728-162">このページを使用して、組織内の Skype for Business ユーザー向けの Skype for Business 機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="e3728-162">Use this page to manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="e3728-163">詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](skype-for-business-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3728-163">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](skype-for-business-settings.md).</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="e3728-164">Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="e3728-164">Teams upgrade</span></span>

<span data-ttu-id="e3728-165">これらの設定を使用して、自分たちのユーザーがどのように Skype for Business から Microsoft Teams にアップグレードするかを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="e3728-165">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="e3728-166">共存モード</span><span class="sxs-lookup"><span data-stu-id="e3728-166">Coexistence mode</span></span>
<span data-ttu-id="e3728-167">次の共存モードを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e3728-167">You can specify a coexistence mode:</span></span> 

- <span data-ttu-id="e3728-168">**Teams のみ**</span><span class="sxs-lookup"><span data-stu-id="e3728-168">**Teams only**</span></span>
- <span data-ttu-id="e3728-169">**アイランド** (Teams と Skype for Business が共存します)</span><span class="sxs-lookup"><span data-stu-id="e3728-169">**Islands** (Teams and Skype for Business will coexist)</span></span>
- <span data-ttu-id="e3728-170">**Skype for Business のみ**</span><span class="sxs-lookup"><span data-stu-id="e3728-170">**Skype for Business only**</span></span>
- <span data-ttu-id="e3728-171">**Skype for Business と Teams のコラボレーション** (ユーザーは Skype for Business でチャット、通話や会議のスケジュールを受信しますが、グループでのコラボレーションには Teams を使用します)</span><span class="sxs-lookup"><span data-stu-id="e3728-171">**Skype for Business with Teams collaboration** (Users receive chats and calls and schedule meetings in Skype for Business but use  Teams for group collaboration)</span></span>
- <span data-ttu-id="e3728-172">**Skype for Business と Teams のコラボレーションと会議** (ユーザーは Skype for Business でチャットや通話を受信しますが、グループでのコラボレーションや会議のスケジュールには Teams を使用します)</span><span class="sxs-lookup"><span data-stu-id="e3728-172">**Skype for Business with Teams collaboration and meetings** (Users receive chats and calls in Skype for Business but use Teams for group collaboration and to schedule meetings)</span></span>

<span data-ttu-id="e3728-173">選択した共存モードにより、着信通話およびチャットのルーティングと、ユーザーによってチャットや通話を開始したり会議をスケジュールしたりするために使用されるアプリが決まります。</span><span class="sxs-lookup"><span data-stu-id="e3728-173">The coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings.</span></span> <span data-ttu-id="e3728-174">共存モードの詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3728-174">For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="e3728-175">アプリの基本設定</span><span class="sxs-lookup"><span data-stu-id="e3728-175">App preferences</span></span>

<span data-ttu-id="e3728-p115">ユーザーが Skype for Business の会議に参加するために使用するアプリを選ぶことができます (Skype for Business または [Skype 会議アプリ](https://support.office.com/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5))。この設定は、共存モードの設定に依存しません。</span><span class="sxs-lookup"><span data-stu-id="e3728-p115">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). This setting isn't dependent on the coexistence mode setting.</span></span>


#### <a name="network-planner"></a><span data-ttu-id="e3728-178">ネットワーク プランナー</span><span class="sxs-lookup"><span data-stu-id="e3728-178">Network Planner</span></span>

<span data-ttu-id="e3728-179">ネットワーク プランナーでは組織全体で Teams ユーザーに接続するためのネットワーク要件を決定し、整理できます。</span><span class="sxs-lookup"><span data-stu-id="e3728-179">Network Planner helps you determine and organize network requirements for connecting Teams users across your organization.</span></span>  <span data-ttu-id="e3728-180">[Microsoft Teams でネットワーク プランナーを使用する方法](https://docs.microsoft.com/microsoftteams/network-planner)について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3728-180">Learn how to [Use the Network Planner for Microsoft Teams](https://docs.microsoft.com/microsoftteams/network-planner).</span></span>

<span data-ttu-id="e3728-181">[Skype for Business 向けにバックグラウンドで Teams アプリをダウンロードする] オプションも選択できます。</span><span class="sxs-lookup"><span data-stu-id="e3728-181">You can also select the "Download the Teams app in the background for Skype for Business users" option as well.</span></span>  <span data-ttu-id="e3728-182">既定では、この設定は [オン] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="e3728-182">By default this setting is set to On.</span></span> <span data-ttu-id="e3728-183">この設定を有効にすると、Windows PC で Skype for Business アプリを実行しているユーザー向けに、バックグラウンドで Teams アプリがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="e3728-183">With this setting enabled it will download the Teams app in the background for users running the Skype for Business app on Windows PCs.</span></span> <span data-ttu-id="e3728-184">この問題が発生するのは、ユーザーの [共存モード] が [チームのみ] になっているか、[保留中のアップグレード通知] が Skype for Business アプリで有効になっている場合です。</span><span class="sxs-lookup"><span data-stu-id="e3728-184">This happens if the Coexistence mode for the user is Teams Only, or if a pending upgrade notification is enabled in the Skype for Business app.</span></span>


## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="e3728-185">利用可能な機能を知る方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="e3728-185">How can I tell which features are available?</span></span>

<span data-ttu-id="e3728-p118">新しい Teams の機能の詳細については、「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)」を参照してください。新機能および今後導入される機能については、Teams の「[新機能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US)」ページと、Teams に関する[技術コミュニティの Microsoft Teams ブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3728-p118">See the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features. For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 

## <a name="more-information"></a><span data-ttu-id="e3728-188">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e3728-188">More information</span></span>

<span data-ttu-id="e3728-189">管理機能を実行できる役割については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e3728-189">For information about which roles can perform admin functions, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>
