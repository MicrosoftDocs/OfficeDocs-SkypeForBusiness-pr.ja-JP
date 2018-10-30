---
title: Office 365 組織でマイクロソフトのチーム機能を管理します。
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: 有効または無効のタブ、コネクタ、ボット、または 3 つの任意の組み合わせを含む、Office 365 の組織でアプリケーションをマイクロソフトのチームにする方法を説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f78876064ae50221562bd42b334545f627a02fb
ms.sourcegitcommit: 9138325ba2652a9ee3602d259de811082080e358
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842077"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="92175-103">Office 365 組織でマイクロソフトのチーム機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="92175-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

<span data-ttu-id="92175-104">チームのすべての設定は、新しいマイクロソフトのチームとビジネス管理センターの Skype をすぐに移行されます。</span><span class="sxs-lookup"><span data-stu-id="92175-104">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="92175-105">チームがこの機能を Office 365 の管理センターで管理されているとは、アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="92175-105">The only Teams feature that is managed in the Office 365 admin center is Apps.</span></span> 

<span data-ttu-id="92175-106">特に断らない限り、オプションの既定値は**上**が。</span><span class="sxs-lookup"><span data-stu-id="92175-106">Unless otherwise noted, the default value for an option is **On**.</span></span>

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="92175-107">Office 365 テナント全体の設定</span><span class="sxs-lookup"><span data-stu-id="92175-107">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="92175-108">**テナント全体の設定**] を有効にするまたはアプリケーションを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="92175-108">In **Tenant-wide settings**, you can turn on or turn off Apps.</span></span>

<span data-ttu-id="92175-109">チームの**テナント全体の設定**を編集するには、マイクロソフトのチームとのビジネス管理センターでは、Skype に移動し、**従来のポータル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="92175-109">To edit **Tenant-wide settings** for Teams, go to the Microsoft Teams & Skype for Business Admin Center, and select **Legacy portal**.</span></span> <span data-ttu-id="92175-110">[**設定**]  >  [**サービスとアドイン**]  >  [**Microsoft Teams**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="92175-110">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="92175-111">Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。</span><span class="sxs-lookup"><span data-stu-id="92175-111">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a><span data-ttu-id="92175-112">アプリ</span><span class="sxs-lookup"><span data-stu-id="92175-112">Apps</span></span>

<span data-ttu-id="92175-113">アプリとは、サードパーティのサービスによって提供されるタブ、コネクタ、ボットという 3 つの要素のあらゆる組み合わせで構成されているものです。</span><span class="sxs-lookup"><span data-stu-id="92175-113">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="92175-114">Office 365 管理センターで構成可能な Teams 管理ポリシーを使用すると、許可する外部サードパーティ アプリを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="92175-114">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="92175-115">これらのポリシーでは、読み込み側のアプリケーションを許可するかどうか、どのアプリが許可され、許可されていない外部のアプリケーションの新しい動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="92175-115">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="92175-116">[**アプリ**] の下で、組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="92175-116">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![[アプリ] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="92175-118">**Microsoft Teams の外部アプリを許可する**: このスイッチがオンになると、ユーザーは Office 365 テナントで利用できるタブやボットを 追加することができます。</span><span class="sxs-lookup"><span data-stu-id="92175-118">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![[アプリ] セクションの外部アプリの許可コントロールのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="92175-120">**既定で新しい外部アプリを有効にする**: このスイッチがオンになると、ユーザーは Teams アプリ カタログに新しいアプリが追加されるとそれをすぐにアクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="92175-120">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="92175-121">新しいアプリに対する制御を行う場合はこのスイッチをオフにします。</span><span class="sxs-lookup"><span data-stu-id="92175-121">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="92175-122">これをオフにする場合は、自分の組織で優れた新しいアプリを利用する機会を失うことがないように、新しいアプリについて忘れずに定期的に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92175-122">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="92175-123">**外部アプリケーションの sideloading を許可する**: このスイッチをオンにすると、ユーザーはインストールし、カスタムの bot とタブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="92175-123">**Allow sideloading of external apps**: When this switch is turned on, users can install and turn on custom bots and tabs.</span></span> 

<span data-ttu-id="92175-124">詳細については、[Teams でのアプリの管理設定](admin-settings.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92175-124">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

## <a name="teams-org-wide-settings"></a><span data-ttu-id="92175-125">チームの組織全体の設定</span><span class="sxs-lookup"><span data-stu-id="92175-125">Teams org-wide settings</span></span>

<span data-ttu-id="92175-126">マイクロソフトのチームとビジネス管理センターの Skype で組織全体のユーザー設定を制御できます。</span><span class="sxs-lookup"><span data-stu-id="92175-126">You can control organization-wide user settings in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="92175-127">組織全体の設定を編集するには、ビジネス管理センターでは、Microsoft の Skype に移動し、**組織全体の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="92175-127">To edit org-wide settings, go to the Microsoft Skype for Business Admin Center, and then select **Org-wide settings**.</span></span> <span data-ttu-id="92175-128">次の設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="92175-128">You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="92175-129">外部からのアクセス</span><span class="sxs-lookup"><span data-stu-id="92175-129">External access</span></span>

<span data-ttu-id="92175-130">**外部からのアクセス**では、チームや組織の外部にいるユーザーとの通信、ビジネス ・ ユーザーの Skype を使用できます。</span><span class="sxs-lookup"><span data-stu-id="92175-130">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization.</span></span> <span data-ttu-id="92175-131">外部アクセスを構成するのには[、チームのユーザーのチャットを使用](let-your-teams-users-communicate-with-other-people.md)して別のチームの組織内のユーザーとの通信を移動します。</span><span class="sxs-lookup"><span data-stu-id="92175-131">To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

### <a name="guest-access"></a><span data-ttu-id="92175-132">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="92175-132">Guest access</span></span>

<span data-ttu-id="92175-133">マイクロソフトのチームでは、**ゲスト アクセス**では、組織外のユーザーと共同作業をチームとチャネルへのアクセス権を付与するのには、組織でチームを許可します。</span><span class="sxs-lookup"><span data-stu-id="92175-133">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="92175-134">ビジネスやコンシューマー電子メール アカウントを Outlook、Gmail、またはその他のユーザーなど、すべてのユーザーは、チーム チャット、会議、およびファイルへのフル アクセスを持つチームにゲストとして参加できます。</span><span class="sxs-lookup"><span data-stu-id="92175-134">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="92175-135">詳細については、[マイクロソフトのチームでのゲスト アクセス](guest-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92175-135">For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="92175-136">チームの設定</span><span class="sxs-lookup"><span data-stu-id="92175-136">Teams settings</span></span>

<span data-ttu-id="92175-137">**チームの設定**電子メールの統合、クラウド ・ ストレージ ・ オプションでは、Skype のビジネスの相互運用性、およびデバイスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="92175-137">In **Teams settings**, you can set up email integration, cloud storage options, Skype for Business interoperability, and devices.</span></span>

#### <a name="email-integration"></a><span data-ttu-id="92175-138">電子メール統合</span><span class="sxs-lookup"><span data-stu-id="92175-138">Email integration</span></span>

<span data-ttu-id="92175-139">この機能をオンにすると、ユーザーはチャネル電子メール アドレスを使用して、Teams のチャネルにメールを送信できるようなります。</span><span class="sxs-lookup"><span data-stu-id="92175-139">Turn on this feature so users can send email to a channel in Teams, using the channel email address.</span></span> <span data-ttu-id="92175-140">この操作は、ユーザーが所有するチームに属しているどのチャネルに対しても行えます。</span><span class="sxs-lookup"><span data-stu-id="92175-140">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="92175-141">チーム メンバーに対して、コネクタを有効に追加することがチーム内のすべてのチャネルに電子メールを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="92175-141">Users can also send emails to any channel in a team that has adding connectors turned on for team members.</span></span> <span data-ttu-id="92175-142">電子メールの統合を有効にするのには、**上**の**チャネルの電子メール アドレスに電子メールを送信するユーザーを許可する**になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92175-142">To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span> 

#### <a name="files"></a><span data-ttu-id="92175-143">ファイル</span><span class="sxs-lookup"><span data-stu-id="92175-143">Files</span></span>

<span data-ttu-id="92175-144">ここでオンにするか、ファイルの共有とクラウドのファイル ストレージのオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="92175-144">Here you can turn on or turn off file sharing and cloud file storage options.</span></span> 

<span data-ttu-id="92175-145">ユーザーは Teams チャネルやチャットでクラウド ストレージ サービスを介してファイルをアップロード、共有できます。</span><span class="sxs-lookup"><span data-stu-id="92175-145">Users can upload and share files from cloud storage services in Teams channels and chats.</span></span> <span data-ttu-id="92175-146">現在、チームでのクラウド ・ ストレージ ・ オプションには、ShareFile、ドロップ ボックス、ボックス、および Google のドライブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="92175-146">Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive.</span></span> <span data-ttu-id="92175-147">組織で使用することになるクラウド ストレージ プロバイダのスイッチをオンにします。</span><span class="sxs-lookup"><span data-stu-id="92175-147">Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="92175-148">組織</span><span class="sxs-lookup"><span data-stu-id="92175-148">Organization</span></span>

<span data-ttu-id="92175-149">ここでを有効にできます、[**組織**] タブは、ユーザーの組織の詳細な組織図を示しています。</span><span class="sxs-lookup"><span data-stu-id="92175-149">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization.</span></span> <span data-ttu-id="92175-150">詳細については、[チームの組織のタブを使用する](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92175-150">For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="skype-for-business-interop"></a><span data-ttu-id="92175-151">Skype ビジネスの相互運用機能</span><span class="sxs-lookup"><span data-stu-id="92175-151">Skype for Business interop</span></span>

<span data-ttu-id="92175-152">ビジネス ユーザーの Skype でのチームのユーザーのチャットをできるようにするのにには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="92175-152">Use this setting to let Teams users chat with Skype for Business users.</span></span> <span data-ttu-id="92175-153">チームとビジネス用の Skype との間の相互運用性の詳細については、[マイクロソフト チームの理解とビジネスの共存と相互運用性の Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92175-153">For detailed information about interoperability between Teams and Skype for Business, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="devices"></a><span data-ttu-id="92175-154">デバイス</span><span class="sxs-lookup"><span data-stu-id="92175-154">Devices</span></span>

<span data-ttu-id="92175-155">これらの設定は、マイクロソフトのチーム ミーティングへの参加のサーフェスのハブ デバイスのリソース アカウントの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="92175-155">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings.</span></span> <span data-ttu-id="92175-156">認証の要件を構成して、暗証番号 (pin) をコンテンツを必要とする、メッセージを送信するハブのサーフェス リソースのアカウントを有効にするのには、これらの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="92175-156">Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="92175-157">**ミーティングのコンテンツにアクセスする認証の第 2 のフォームを必要とする**: 選択内容を入力するときにユーザーが持つアクセスのレベルを固定します。</span><span class="sxs-lookup"><span data-stu-id="92175-157">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="92175-158">**暗証番号 (pin) のコンテンツを設定する**– このドキュメントへの不正アクセスを防止するのには暗証番号 (pin) を入力するユーザーを必要とします。</span><span class="sxs-lookup"><span data-stu-id="92175-158">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents.</span></span> <span data-ttu-id="92175-159">これにより、権限のないユーザーからは、今後の会議に参加して、添付ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="92175-159">This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="92175-160">**リソース アカウントがメッセージを送信できます**: サーフェスのハブのリソースのアカウントから送信されるメッセージを許可する**に**は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="92175-160">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search"></a><span data-ttu-id="92175-161">検索</span><span class="sxs-lookup"><span data-stu-id="92175-161">Search</span></span>

<span data-ttu-id="92175-162">マイクロソフト チームのスコープ指定されたディレクトリの検索では、組織がユーザーが検索し、組織内の他のユーザーとの通信方法を制御する仮想境界を作成できるように Exchange アドレス帳ポリシー (APB) を使用します。</span><span class="sxs-lookup"><span data-stu-id="92175-162">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> <span data-ttu-id="92175-163">スコープ指定されたディレクトリ検索を使用して、このような状況にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="92175-163">You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="92175-164">組織には、別に保持する、テナント内の複数の企業がいます。</span><span class="sxs-lookup"><span data-stu-id="92175-164">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="92175-165">学校は、教職員と学生の間でチャットを制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92175-165">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="92175-166">**に**スコープ指定されたディレクトリ検索を有効にするには、この設定を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="92175-166">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="92175-167">チームのアップグレード</span><span class="sxs-lookup"><span data-stu-id="92175-167">Teams upgrade</span></span>

<span data-ttu-id="92175-168">ユーザーにアップグレードする方法ビジネスの Skype からマイクロソフトのチームを構成するのには、これらの設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="92175-168">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="92175-169">共存モード</span><span class="sxs-lookup"><span data-stu-id="92175-169">Coexistence mode</span></span>
<span data-ttu-id="92175-170">共存モードを指定することができます:**チームのみ**、**諸島**(チームとの共存のビジネスは Skype)、または**Skype**です。</span><span class="sxs-lookup"><span data-stu-id="92175-170">You can specify a coexistence mode: **Teams only**, **Islands** (Teams and Skype for Business will coexist), or **Skype for Business only**.</span></span> <span data-ttu-id="92175-171">選択した共存モードでは、着信呼び出しとのチャットとチャットや通話を開始する、または会議をスケジュールするのには、ユーザーによって使用されるアプリケーションのルーティングを決定します。</span><span class="sxs-lookup"><span data-stu-id="92175-171">The Coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings.</span></span> <span data-ttu-id="92175-172">共存モードの詳細については、[マイクロソフト チームの理解とビジネスの共存と相互運用性の Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92175-172">For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="92175-173">アプリケーションの基本設定</span><span class="sxs-lookup"><span data-stu-id="92175-173">App preferences</span></span>

<span data-ttu-id="92175-174">ここで Skype のビジネスに参加するユーザーが使用するアプリケーションを選択できます (ビジネスまたは[Skype 会議アプリケーション](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)の Skype) の会議。</span><span class="sxs-lookup"><span data-stu-id="92175-174">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)).</span></span> <span data-ttu-id="92175-175">このは共存モードの設定に依存します。</span><span class="sxs-lookup"><span data-stu-id="92175-175">This setting isn't dependent on the coexistence mode setting.</span></span>


