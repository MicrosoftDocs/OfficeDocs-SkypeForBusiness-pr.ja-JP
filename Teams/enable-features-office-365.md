---
title: 組織の Microsoft Teams の設定を管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/18/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: アプリ、外部アクセス、ゲストアクセス、Teams の設定、Teams のアップグレード設定など、あなたの組織に対する Microsoft Teams の組織全体の設定をオンまたはオフにする方法について説明します。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 458e6fc5fc788facb6ee900b9dd40be58428e08b
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "35116026"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a><span data-ttu-id="358ea-103">組織の Microsoft Teams の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="358ea-103">Manage Microsoft Teams settings for your organization</span></span>

<span data-ttu-id="358ea-p101">もうすぐ、すべての Teams の設定が新しい Microsoft Teams 管理センターに移行されます。Teams の機能のうち、アプリのみが Microsoft 365 管理センターで管理されます。</span><span class="sxs-lookup"><span data-stu-id="358ea-p101">All Teams settings will soon be migrated to the new Microsoft Teams admin center. The only Teams feature that's managed in the Microsoft 365 admin center is Apps.</span></span> 

<span data-ttu-id="358ea-106">特に明記されていない限り、オプションの既定値は [**オン**] です。</span><span class="sxs-lookup"><span data-stu-id="358ea-106">Unless otherwise noted, the default value for an option is **On**.</span></span>

## <a name="tenant-wide-settings-in-the-microsoft-365-admin-center"></a><span data-ttu-id="358ea-107">Microsoft 365 管理センターでのテナント全体の設定</span><span class="sxs-lookup"><span data-stu-id="358ea-107">Tenant-wide settings in the Microsoft 365 admin center</span></span>

<span data-ttu-id="358ea-108">Microsoft 365 管理センターの [**テナント全体の設定**] で Teams のアプリをオフにしたりオンにしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="358ea-108">You can turn off or turn on apps for Teams in **Tenant-wide settings** in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="358ea-p102">Teams の [**テナント全体の設定**] を編集するには、Microsoft 365 管理センターに移動して、[**設定**]  >  [**サービスとアドイン**]  >  [**Microsoft Teams**] の順に選択します。Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。</span><span class="sxs-lookup"><span data-stu-id="358ea-p102">To edit **Tenant-wide settings** for Teams, go to the Microsoft 365 admin center, choose **Settings** > **Services & add-ins** > **Microsoft Teams**. If you're signed in as an Office 365 admin, this link should take you there:</span></span> 

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a><span data-ttu-id="358ea-111">アプリ</span><span class="sxs-lookup"><span data-stu-id="358ea-111">Apps</span></span>

<span data-ttu-id="358ea-p103">アプリは、Teams (ファーストパーティ アプリ、または既定のアプリ) によって、またはサードパーティ (外部アプリ) によって提供される、タブ、コネクタ、ボットまたはそれらの 3 つを任意に組み合わせたのものです。**[アプリ]** の下で、既定のアプリを有効または無効にしたり、外部アプリを制御する設定を構成したりすることができます。Teams のアプリ、ボット、コネクタ、およびタブのロールアウトについては、[アプリ、ボット、およびコネクタ](https://docs.microsoft.com/microsoftteams/deploy-apps-microsoft-teams-landing-page) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="358ea-p103">Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, also known as default apps) or by a third-party (also known as external apps). Under Apps, you can enable and disable default apps and configure settings to control external apps. To learn about rolling out apps, bots, connectors, and tabs in Teams, read (Apps, bots, & connectors)[deploy-apps-microsoft-teams-landing-page.md].</span></span>

#### <a name="default-apps"></a><span data-ttu-id="358ea-115">既定のアプリ</span><span class="sxs-lookup"><span data-stu-id="358ea-115">Default apps</span></span>

<span data-ttu-id="358ea-116">プランナー、称賛、天気などのアプリは、Teams によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="358ea-116">These apps, such as Planner, Praise, and Weather, are provided by Teams.</span></span> <span data-ttu-id="358ea-117">アプリをオンにするには、そのアプリのチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="358ea-117">To turn on an app, select the check box for that app.</span></span> <span data-ttu-id="358ea-118">アプリをオフにするには、チェック ボックスをクリアします。</span><span class="sxs-lookup"><span data-stu-id="358ea-118">To turn off an app, clear the check box.</span></span> 

<span data-ttu-id="358ea-119">![[既定のアプリ] セクションのスクリーン ショット。](media/teams-manage-features-in-office365-image1.png "[既定のアプリ] セクションのスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="358ea-119">![Screen shot of the Default Apps section.](media/teams-manage-features-in-office365-image1.png "Screen shot of the Default Apps section")</span></span>

#### <a name="external-apps"></a><span data-ttu-id="358ea-120">外部アプリ</span><span class="sxs-lookup"><span data-stu-id="358ea-120">External apps</span></span>

<span data-ttu-id="358ea-121">これらのアプリはサードパーティによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="358ea-121">These apps are provided by third parties.</span></span> <span data-ttu-id="358ea-122">外部アプリについては、次の設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="358ea-122">You can configure the following settings for external apps.</span></span>

<span data-ttu-id="358ea-123">![[外部アプリ] セクションのスクリーンショット。](media/teams-manage-features-in-office365-image2.png "[外部アプリ] セクションのスクリーンショット。オンまたはオフにすることができる設定")</span><span class="sxs-lookup"><span data-stu-id="358ea-123">![Screenshot of the External Apps section.](media/teams-manage-features-in-office365-image2.png "Screen shot of the External Apps section, showing settings that you can turn on and off")</span></span>

- <span data-ttu-id="358ea-124">**Microsoft Teams の外部アプリを許可する**: この設定がオンになると、ユーザーは自分の組織で利用できる外部アプリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="358ea-124">**Allow external apps in Microsoft Teams**: When this setting is turned on, users can add external apps that are available to your organization.</span></span> 

- <span data-ttu-id="358ea-125">**外部アプリのサイドローディングを利用できるようになります**: 一部の外部アプリをオンにして、その他のアプリをオフにする場合は、この設定をオフにしてから、外部アプリのリストでユーザーがアクセスしないようするアプリをオフにします。</span><span class="sxs-lookup"><span data-stu-id="358ea-125">**Allow sideloading of external apps**: If you want to turn on some external apps and turn off others , turn off this setting, and then in the list of external apps, turn off the apps that you don't want users to access.</span></span> <span data-ttu-id="358ea-126">この設定がオンになっているときは、アクセス権が付与されているチーム所有者およびメンバーは、アプリを Teams にサイドリーディングすることができます。</span><span class="sxs-lookup"><span data-stu-id="358ea-126">When this setting is turned on, team owners and members who are granted permission can sideload apps to Teams.</span></span> 

- <span data-ttu-id="358ea-127">**既定で新しい外部アプリが有効になります**: この設定がオンになると、ユーザーは Teams アプリ カタログに新しいアプリが追加されると、それらをすぐにアクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="358ea-127">**Enable new external apps by default**: When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="358ea-128">新しいアプリに対する制御を行う場合はこの設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="358ea-128">Turn off this setting if you want to control new apps.</span></span> <span data-ttu-id="358ea-129">これをオフにする場合は、自分の組織で新しいアプリを利用する機会を失うことがないように、新しいアプリについて定期的に確認するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="358ea-129">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on new apps.</span></span> 

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="358ea-130">Microsoft Teams 管理センターでの Teams の組織全体の設定</span><span class="sxs-lookup"><span data-stu-id="358ea-130">Teams org-wide settings in the Microsoft Teams admin center</span></span>
<span data-ttu-id="358ea-p108">Microsoft Teams 管理センターで、組織全体のユーザー設定を制御することができます。組織全体の設定を編集するには、Microsoft Teams 管理センターに移動して、**[Org-wide settings (組織全体の設定)]** を選択します。次の設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="358ea-p108">You can control organization-wide user settings in the Microsoft Teams admin center. To edit org-wide settings, go to the Microsoft Teams admin center, and then select **Org-wide settings**. You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="358ea-134">外部アクセス</span><span class="sxs-lookup"><span data-stu-id="358ea-134">External access</span></span>

<span data-ttu-id="358ea-p109">**外部アクセス**では、Teams および Skype for Business のユーザーが、組織の外部ユーザーと通信するように設定することができます。外部アクセスを構成するには、[[Let your Teams users chat and communicate with users in another Teams organization (Teams ユーザーが別の Teams の組織に所属するユーザーと通信することを許可する) ](let-your-teams-users-communicate-with-other-people.md)] に移動します。</span><span class="sxs-lookup"><span data-stu-id="358ea-p109">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization. To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

<span data-ttu-id="358ea-137">ドメインを追加またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="358ea-137">To add or block a domain:</span></span>

1. <span data-ttu-id="358ea-138">[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="358ea-138">Select **Add a domain**.</span></span>
2. <span data-ttu-id="358ea-139">[ドメインの追加] ウィンドウで、ドメイン名を入力し、スペース バーをクリックして名前を保存します。</span><span class="sxs-lookup"><span data-stu-id="358ea-139">In the Add a domain pane, enter the domain name, and click the space bar to save the name.</span></span>
3. <span data-ttu-id="358ea-140">[**許可**] または [**禁止**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="358ea-140">Select **Allowed** or **Blocked**.</span></span>
4. <span data-ttu-id="358ea-141">[**完了**] を選んで変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="358ea-141">Select **Done** to save your changes.</span></span> 

### <a name="guest-access"></a><span data-ttu-id="358ea-142">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="358ea-142">Guest access</span></span>

<span data-ttu-id="358ea-p110">Microsoft Teams での**ゲスト アクセス**により、組織内のチームは組織外のユーザーにチームおよびチャネルへのアクセス権を付与することで、それらのユーザーと共同作業することができるようになります。Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、チーム チャット、会議、ファイルに完全なアクセス権を持つゲストとして Teams に参加することができます。詳細については、「[Guest access in Microsoft Teams (Microsoft Teams でのゲスト アクセス)](guest-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="358ea-p110">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="358ea-146">Teams の設定</span><span class="sxs-lookup"><span data-stu-id="358ea-146">Teams settings</span></span>

<span data-ttu-id="358ea-147">**Teams の設定**で、電子メール統合、クラウド ストレージのオプション、Skype for Business の相互運用性、およびデバイスをセットアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="358ea-147">In **Teams settings**, you can set up email integration, cloud storage options, Skype for Business interoperability, and devices.</span></span>

#### <a name="email-integration"></a><span data-ttu-id="358ea-148">電子メールの統合</span><span class="sxs-lookup"><span data-stu-id="358ea-148">Email integration</span></span>

<span data-ttu-id="358ea-p111">この機能をオンにすると、ユーザーはチャネル電子メール アドレスを使用して、Teams のチャネルにメールを送信できるようなります。この操作は、ユーザーが所有するチームに属しているどのチャネルに対しても行えます。ユーザーのメールは、チーム メンバーに対してオンになっている追加のコネクタがあるチーム内の任意のチャネルにも送信できます。電子メール統合をオンにするには、[**Allow users to send emails to a channel email address (ユーザーがメールをチャネルの電子メール アドレスに送信できるようにする)**] が [**オン**] であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="358ea-p111">Turn on this feature so users can send email to a channel in Teams, using the channel email address. Users can do this for any channel belonging to a team they own. Users can also send emails to any channel in a team that has adding connectors turned on for team members. To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span> 

#### <a name="files"></a><span data-ttu-id="358ea-153">ファイル</span><span class="sxs-lookup"><span data-stu-id="358ea-153">Files</span></span>

<span data-ttu-id="358ea-154">ファイル共有オプションおよびファイル保存オプションをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="358ea-154">Here you can turn on or turn off file sharing and cloud file storage options.</span></span> 

<span data-ttu-id="358ea-p112">ユーザーは Teams のチャネルやチャットでクラウド ストレージ サービスを介して、ファイルのアップロードや共有を行うことができます。現時点では、Teams のクラウド ストレージ オプションには、Box、Dropbox、Google ドライブ、ShareFile があります。自分の組織で使用することになるクラウド ストレージ プロバイダのスイッチをオンにします。</span><span class="sxs-lookup"><span data-stu-id="358ea-p112">Users can upload and share files from cloud storage services in Teams channels and chats. Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive. Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="358ea-158">組織</span><span class="sxs-lookup"><span data-stu-id="358ea-158">Organization</span></span>

<span data-ttu-id="358ea-p113">ユーザーの組織について詳細な組織図を示す、[**組織**] タブをオンにすることができます。詳細については、「[Teams で組織タブを使用する](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="358ea-p113">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization. For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="devices"></a><span data-ttu-id="358ea-161">デバイス</span><span class="sxs-lookup"><span data-stu-id="358ea-161">Devices</span></span>

<span data-ttu-id="358ea-p114">これらの設定により、Microsoft Teams 会議に参加している Surface Hub デバイスのリソース アカウントの動作を制御します。これらの設定を使用して、認証の要件を構成し、コンテンツ PIN を要求し、Surface Hub リソース アカウントをオンにしてメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="358ea-p114">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings. Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="358ea-164">**Require a secondary form of authentication to access meeting content (会議のコンテンツにアクセスするための認証のセカンダリ フォームを要求する)** – コンテンツ PIN を入力するときにユーザーが持つアクセスのレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="358ea-164">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="358ea-p115">**Set content PIN (コンテンツ PIN を設定する)** – ドキュメントに対する未承認のアクセスを防ぐためにこの PIN を入力するようにユーザーに要求します。これにより、未承認のユーザーが今後の会議に参加したり、添付ファイルを参照したりすることを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="358ea-p115">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents. This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="358ea-167">**Resource accounts can send messages (リソース アカウントがメッセージを送信することができる)** – この設定を [**オン**] にすると、メッセージが Surface Hub リソース アカウントから送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="358ea-167">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search-by-name"></a><span data-ttu-id="358ea-168">名前で検索</span><span class="sxs-lookup"><span data-stu-id="358ea-168">Search by name</span></span>

<span data-ttu-id="358ea-p116">Microsoft Teams の範囲指定ディレクトリ検索では、アドレス帳ポリシー (APB) を使用して、組織がどのように組織内のユーザーを検索するか、およびそれらのユーザーと通信するかを制御するために、仮想の境界を作成することができます。範囲指定ディレクトリ検索を使用することが考えられる状況は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="358ea-p116">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization. You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="358ea-171">所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。</span><span class="sxs-lookup"><span data-stu-id="358ea-171">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="358ea-172">所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="358ea-172">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="358ea-173">範囲指定ディレクトリ検索をオンにするには、この設定を [**オン**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="358ea-173">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="358ea-174">Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="358ea-174">Teams upgrade</span></span>

<span data-ttu-id="358ea-175">これらの設定を使用して、自分たちのユーザーがどのように Skype for Business から Microsoft Teams にアップグレードするかを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="358ea-175">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="358ea-176">共存モード</span><span class="sxs-lookup"><span data-stu-id="358ea-176">Coexistence mode</span></span>
<span data-ttu-id="358ea-p117">共存モードを指定することができます。**Teams のみ**、**Islands (アイランド)** (Teams と Skype for Business が共存) または **Skype for Business のみ**を選択することができます。選択した共存モードにより、着信通話およびチャットのルーティングと、ユーザーによってチャットや通話を開始したり会議をスケジュールするために使用されるアプリが決まります。Teams と Skype for Business との相互運用性については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="358ea-p117">You can specify a coexistence mode: **Teams only**, **Islands** (Teams and Skype for Business will coexist), or **Skype for Business only**. The Coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings. For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="358ea-180">アプリの基本設定</span><span class="sxs-lookup"><span data-stu-id="358ea-180">App preferences</span></span>

<span data-ttu-id="358ea-p118">ユーザーが Skype for Business の会議に参加するために使用するアプリを選ぶことができます (Skype for Business または [Skype 会議アプリ](https://support.office.com/ja-JP/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5))。この設定は、共存モードの設定に依存しません。</span><span class="sxs-lookup"><span data-stu-id="358ea-p118">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). This setting isn't dependent on the coexistence mode setting.</span></span>

## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="358ea-183">利用可能な機能を知る方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="358ea-183">How can I tell which features are available?</span></span>

<span data-ttu-id="358ea-p119">新しい Teams の機能の詳細については、「[Microsoft 365 ロードマップ](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)」を参照してください。新機能および今後導入される機能については、Teams の「[新機能](https://support.office.com/ja-JP/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US)」ページと、Teams に関する[技術コミュニティの Microsoft Teams ブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="358ea-p119">See the [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features. For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 

## <a name="more-information"></a><span data-ttu-id="358ea-186">詳細情報</span><span class="sxs-lookup"><span data-stu-id="358ea-186">More information</span></span>

<span data-ttu-id="358ea-187">管理機能を実行できる役割については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="358ea-187">For information about which roles can perform admin functions, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>
