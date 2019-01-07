---
title: Office 365 を使用する組織で Microsoft Teams の機能を管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Office 365 を使用する組織での、タブ、コネクタ、ボット、またはそれらの組み合わせを含む、Microsoft Teams のアプリをオンまたはオフに切り替える方法について説明します。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a36c0a23076c5aa172824fe85103c57a8494dbf
ms.sourcegitcommit: a378848c5aeb8e2b25300024318de792454d905b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/28/2018
ms.locfileid: "27458479"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="781f5-103">Office 365 を使用する組織で Microsoft Teams の機能を管理する</span><span class="sxs-lookup"><span data-stu-id="781f5-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

<span data-ttu-id="781f5-p101">すべての Teams の設定は、新しい Microsoft Teams および Skype for Business 管理センターに間もなく移行されます。Teams の機能のうち、アプリのみが Office 365 管理センターで管理されます。</span><span class="sxs-lookup"><span data-stu-id="781f5-p101">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center. The only Teams feature that is managed in the Office 365 admin center is Apps.</span></span> 

<span data-ttu-id="781f5-106">特に明記されていない限り、オプションの既定値は [**オン**] です。</span><span class="sxs-lookup"><span data-stu-id="781f5-106">Unless otherwise noted, the default value for an option is **On**.</span></span>

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="781f5-107">Office 365 テナント全体の設定</span><span class="sxs-lookup"><span data-stu-id="781f5-107">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="781f5-108">[**テナント全体の設定**] で、アプリをオンまたはオフに切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="781f5-108">In **Tenant-wide settings**, you can turn on or turn off Apps.</span></span>

<span data-ttu-id="781f5-p102">Teams の [**テナント全体の設定**] を編集するには、Microsoft Teams および Skype for Business 管理センターに移動して、[**Legacy portal (従来のポータル)**] を選択します。[**設定**]  >  [**サービスとアドイン**]  >  [**Microsoft Teams**] の順に選択します。Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。</span><span class="sxs-lookup"><span data-stu-id="781f5-p102">To edit **Tenant-wide settings** for Teams, go to the Microsoft Teams & Skype for Business Admin Center, and select **Legacy portal**. Choose **Settings** > **Services & add-ins** > **Microsoft Teams**. If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a><span data-ttu-id="781f5-112">アプリ</span><span class="sxs-lookup"><span data-stu-id="781f5-112">Apps</span></span>

<span data-ttu-id="781f5-p103">アプリとは、サードパーティのサービスによって提供されるタブ、コネクタ、ボットという 3 つの要素のあらゆる組み合わせで構成されているものです。Office 365 管理センターで構成可能な Teams 管理ポリシーを使用すると、許可する外部サードパーティ アプリを制御することができます。このポリシーでは、許可または禁止するアプリ、新しい外部アプリの動作、アプリのサイドロードを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="781f5-p103">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="781f5-116">[**アプリ**] の下で、組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="781f5-116">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![[アプリ] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="781f5-118">**Microsoft Teams の外部アプリを許可する**: このスイッチがオンになると、ユーザーは Office 365 テナントで利用できるタブやボットを 追加することができます。</span><span class="sxs-lookup"><span data-stu-id="781f5-118">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![[アプリ] セクションの外部アプリの許可コントロールのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="781f5-p104">**既定で新しい外部アプリを有効にする**: このスイッチがオンになると、ユーザーは Teams アプリ カタログに新しいアプリが追加されるとそれをすぐにアクティブ化することができます。新しいアプリに対する制御を行う場合はこのスイッチをオフにします。これをオフにする場合は、自分の組織で優れた新しいアプリを利用する機会を失うことがないように、新しいアプリについて忘れずに定期的に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="781f5-p104">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog. Turn off this switch if you want to control new apps. Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="781f5-123">**外部アプリのサイドロードを許可する:** このスイッチがオンになると、ユーザーはカスタムのボットやタブをインストールして有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="781f5-123">**Allow sideloading of external apps**: When this switch is turned on, users can install and turn on custom bots and tabs.</span></span> 

<span data-ttu-id="781f5-124">詳細については、「[Teams でのアプリの管理設定](admin-settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="781f5-124">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

## <a name="teams-org-wide-settings"></a><span data-ttu-id="781f5-125">Teams の組織全体の設定</span><span class="sxs-lookup"><span data-stu-id="781f5-125">Teams org-wide settings</span></span>

<span data-ttu-id="781f5-126">Microsoft Teams および Skype for Business 管理センターで組織全体のユーザー設定を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="781f5-126">You can control organization-wide user settings in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="781f5-127">組織全体の設定を編集するには、Microsoft Teams および Skype for Business 管理センターに移動して、[**Org-wide settings (組織全体の設定)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="781f5-127">To edit org-wide settings, go to the Microsoft Skype for Business Admin Center, and then select **Org-wide settings**.</span></span> <span data-ttu-id="781f5-128">次の設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="781f5-128">You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="781f5-129">外部アクセス</span><span class="sxs-lookup"><span data-stu-id="781f5-129">External access</span></span>

<span data-ttu-id="781f5-p106">**外部アクセス**では、Teams および Skype for Business のユーザーが、組織の外部ユーザーと通信するように設定することができます。外部アクセスを構成するには、[[Let your Teams users chat and communicate with users in another Teams organization (Teams ユーザーが別の Teams の組織に所属するユーザーと通信することを許可する) ](let-your-teams-users-communicate-with-other-people.md)] に移動します。</span><span class="sxs-lookup"><span data-stu-id="781f5-p106">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization. To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

### <a name="guest-access"></a><span data-ttu-id="781f5-132">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="781f5-132">Guest access</span></span>

<span data-ttu-id="781f5-p107">Microsoft Teams での**ゲスト アクセス**により、組織内のチームは組織外のユーザーにチームおよびチャネルへのアクセス権を付与することで、それらのユーザーと共同作業することができるようになります。Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、チーム チャット、会議、ファイルに完全なアクセス権を持つゲストとして Teams に参加することができます。詳細については、「[Guest access in Microsoft Teams (Microsoft Teams でのゲスト アクセス)](guest-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="781f5-p107">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="781f5-136">Teams の設定</span><span class="sxs-lookup"><span data-stu-id="781f5-136">Teams settings</span></span>

<span data-ttu-id="781f5-137">**Teams の設定**で、電子メール統合、クラウド ストレージのオプション、Skype for Business の相互運用性、およびデバイスをセットアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="781f5-137">In **Teams settings**, you can set up email integration, cloud storage options, Skype for Business interoperability, and devices.</span></span>

#### <a name="email-integration"></a><span data-ttu-id="781f5-138">電子メール統合</span><span class="sxs-lookup"><span data-stu-id="781f5-138">Email integration</span></span>

<span data-ttu-id="781f5-p108">この機能をオンにすると、ユーザーはチャネル電子メール アドレスを使用して、Teams のチャネルにメールを送信できるようなります。この操作は、ユーザーが所有するチームに属しているどのチャネルに対しても行えます。ユーザーのメールは、チーム メンバーに対してオンになっている追加のコネクタがあるチーム内の任意のチャネルにも送信できます。電子メール統合をオンにするには、[**Allow users to send emails to a channel email address (ユーザーがメールをチャネルの電子メール アドレスに送信できるようにする)**] が [**オン**] であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="781f5-p108">Turn on this feature so users can send email to a channel in Teams, using the channel email address. Users can do this for any channel belonging to a team they own. Users can also send emails to any channel in a team that has adding connectors turned on for team members. To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span> 

#### <a name="files"></a><span data-ttu-id="781f5-143">ファイル</span><span class="sxs-lookup"><span data-stu-id="781f5-143">Files</span></span>

<span data-ttu-id="781f5-144">ファイル共有オプションおよびファイル保存オプションをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="781f5-144">Here you can turn on or turn off file sharing and cloud file storage options.</span></span> 

<span data-ttu-id="781f5-p109">ユーザーは Teams のチャネルやチャットでクラウド ストレージ サービスを介して、ファイルのアップロードや共有を行うことができます。現時点では、Teams のクラウド ストレージ オプションには、Box、Dropbox、Google ドライブ、ShareFile があります。自分の組織で使用することになるクラウド ストレージ プロバイダのスイッチをオンにします。</span><span class="sxs-lookup"><span data-stu-id="781f5-p109">Users can upload and share files from cloud storage services in Teams channels and chats. Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive. Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="781f5-148">組織</span><span class="sxs-lookup"><span data-stu-id="781f5-148">Organization</span></span>

<span data-ttu-id="781f5-p110">ユーザーの組織について詳細な組織図を示す、[**組織**] タブをオンにすることができます。詳細については、「[Teams で組織タブを使用する](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="781f5-p110">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization. For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="skype-for-business-interop"></a><span data-ttu-id="781f5-151">Skype for Business の相互運用性</span><span class="sxs-lookup"><span data-stu-id="781f5-151">Skype for Business interop</span></span>

<span data-ttu-id="781f5-p111">この設定を使用して、Teams のユーザーが Skype for Business ユーザーとチャットするようにすることができますTeams と Skype for Business との相互運用性については、「[Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="781f5-p111">Use this setting to let Teams users chat with Skype for Business users. For detailed information about interoperability between Teams and Skype for Business, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="devices"></a><span data-ttu-id="781f5-154">デバイス</span><span class="sxs-lookup"><span data-stu-id="781f5-154">Devices</span></span>

<span data-ttu-id="781f5-p112">これらの設定により、Microsoft Teams 会議に参加している Surface Hub デバイスのリソース アカウントの動作を制御します。これらの設定を使用して、認証の要件を構成し、コンテンツ PIN を要求し、Surface Hub リソース アカウントをオンにしてメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="781f5-p112">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings. Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="781f5-157">**Require a secondary form of authentication to access meeting content (会議のコンテンツにアクセスするための認証のセカンダリ フォームを要求する)** – コンテンツ PIN を入力するときにユーザーが持つアクセスのレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="781f5-157">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="781f5-p113">**Set content PIN (コンテンツ PIN を設定する)** – ドキュメントに対する未承認のアクセスを防ぐためにこの PIN を入力するようにユーザーに要求します。これにより、未承認のユーザーが今後の会議に参加したり、添付ファイルを参照したりすることを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="781f5-p113">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents. This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="781f5-160">**Resource accounts can send messages (リソース アカウントがメッセージを送信することができる)** – この設定を [**オン**] にすると、メッセージが Surface Hub リソース アカウントから送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="781f5-160">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search"></a><span data-ttu-id="781f5-161">検索</span><span class="sxs-lookup"><span data-stu-id="781f5-161">Search</span></span>

<span data-ttu-id="781f5-p114">Microsoft Teams の範囲指定ディレクトリ検索では、アドレス帳ポリシー (APB) を使用して、組織がどのように組織内のユーザーを検索するか、およびそれらのユーザーと通信するかを制御するために、仮想の境界を作成することができます。範囲指定ディレクトリ検索を使用することが考えられる状況は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="781f5-p114">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization. You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="781f5-164">所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。</span><span class="sxs-lookup"><span data-stu-id="781f5-164">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="781f5-165">所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="781f5-165">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="781f5-166">範囲指定ディレクトリ検索をオンにするには、この設定を [**オン**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="781f5-166">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="781f5-167">Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="781f5-167">Teams upgrade</span></span>

<span data-ttu-id="781f5-168">これらの設定を使用して、自分たちのユーザーがどのように Skype for Business から Microsoft Teams にアップグレードするかを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="781f5-168">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="781f5-169">共存モード</span><span class="sxs-lookup"><span data-stu-id="781f5-169">Coexistence mode</span></span>
<span data-ttu-id="781f5-p115">共存モードを指定することができます。**Teams のみ**、**Islands (アイランド)** (Teams と Skype for Business が共存) または **Skype for Business のみ**を選択することができます。選択した共存モードにより、着信通話およびチャットのルーティングと、ユーザーによってチャットや通話を開始したり会議をスケジュールするために使用されるアプリが決まります。Teams と Skype for Business との相互運用性については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="781f5-p115">You can specify a coexistence mode: **Teams only**, **Islands** (Teams and Skype for Business will coexist), or **Skype for Business only**. The Coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings. For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="781f5-173">アプリの基本設定</span><span class="sxs-lookup"><span data-stu-id="781f5-173">App preferences</span></span>

<span data-ttu-id="781f5-p116">ユーザーが Skype for Business の会議に参加するために使用するアプリを選ぶことができます (Skype for Business または [Skype 会議アプリ](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5))。この設定は、共存モードの設定に依存しません。</span><span class="sxs-lookup"><span data-stu-id="781f5-p116">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). This setting isn't dependent on the coexistence mode setting.</span></span>

## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="781f5-176">利用可能な機能を知る方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="781f5-176">How can I tell which features are available?</span></span>

<span data-ttu-id="781f5-p117">新しい Teams の機能の詳細については、[Office 365 ロードマップ](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)をご覧ください。新機能および今後導入される機能については、Teams の[新機能](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US)ページと、Teams に関する[技術コミュニティの Microsoft Teams ブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="781f5-p117">See the [Office 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features. For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 

## <a name="more-information"></a><span data-ttu-id="781f5-179">詳細情報</span><span class="sxs-lookup"><span data-stu-id="781f5-179">More information</span></span>

<span data-ttu-id="781f5-180">管理機能を実行できる役割については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="781f5-180">For information about which roles can perform admin functions, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>
