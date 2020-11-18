---
title: Microsoft Teams にようこそ
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: serdars
description: Microsoft Teams を組織に展開するための正しい経路を見つけます。 Teams のインフラストラクチャと、Microsoft 365 または Office 365 での Teams の使用について説明します。
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.allteamsdocuments
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b7fe540134ae273e74dd445f1c822c1c43fe645
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030983"
---
# <a name="welcome-to-microsoft-teams"></a><span data-ttu-id="aeae6-104">Microsoft Teams にようこそ</span><span class="sxs-lookup"><span data-stu-id="aeae6-104">Welcome to Microsoft Teams</span></span>
<span data-ttu-id="aeae6-105">所属する組織での Microsoft Teams の管理者である場合は、このページの内容をよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-105">If you're the admin for Microsoft Teams in your organization, you're in the right place.</span></span> <span data-ttu-id="aeae6-106">Teams を使用する準備が整っている場合は、「[Teams の展開方法](How-to-roll-out-teams.md)」から始めてください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-106">When you're ready to get going with Teams, start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="aeae6-107">Teams を使うのが初めてで、詳細を知りたい場合は、「[Teams へようこそ](https://www.youtube.com/embed/s3aQV3T0D6c)」のビデオ (55 秒) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-107">If you're new to Teams and want to learn more, check out our short [Welcome to Teams](https://www.youtube.com/embed/s3aQV3T0D6c) video (55 seconds).</span></span>

<span data-ttu-id="aeae6-108">Teams の管理者向けビデオの「Teams へようこそ」をお見逃しなく (3 分強):</span><span class="sxs-lookup"><span data-stu-id="aeae6-108">Don't miss our Welcome to Teams for the Teams admin video (just over 3 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vxWd]

<span data-ttu-id="aeae6-109">エンド ユーザー向けの Teams のヘルプを探している場合は、アプリの左側にある **[ヘルプ]** をクリックするか、 [Microsoft Teams ヘルプ センター](https://support.office.com/teams)に移動します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-109">If you're looking for end user Teams Help, click **Help** on the left side of the app, or go to the [Microsoft Teams help center](https://support.office.com/teams).</span></span> <span data-ttu-id="aeae6-110">トレーニングについては、「[Microsoft Teams のトレーニング](training-microsoft-teams-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-110">For training, go to [Microsoft Teams Training](training-microsoft-teams-landing-page.md).</span></span> 

## <a name="teams-architecture"></a><span data-ttu-id="aeae6-111">Teams のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="aeae6-111">Teams architecture</span></span>

<span data-ttu-id="aeae6-112">Teams は Microsoft 365 グループ、Microsoft Graph、および他の Microsoft 365 および Office 365 と同じエンタープライズ レベルのセキュリティ、コンプライアンス、管理容易性で構築されています。</span><span class="sxs-lookup"><span data-stu-id="aeae6-112">Teams is built on Microsoft 365 groups, Microsoft Graph, and the same enterprise-level security, compliance, and manageability as the rest of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="aeae6-113">Teams は Azure Active Directory (Azure AD) に保存された ID を活用します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-113">Teams leverages identities stored in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="aeae6-114">Teams は、オフラインの場合やネットワークの状態が不安定な場合でも作業を続けます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-114">Teams keeps working even when you're offline or experiencing spotty network conditions.</span></span>

<span data-ttu-id="aeae6-115">Microsoft 365 全体の中での Teams の位置を確認するには、次のアーキテクチャ ポスターを参照してください: [Microsoft 365 の一部としての Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="aeae6-115">To see where Teams fits in the context of Microsoft 365, check out this architecture poster:  [Teams as part of Microsoft 365](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)</span></span>

<span data-ttu-id="aeae6-116">チームを作成すると、次のものが作成されることになります。</span><span class="sxs-lookup"><span data-stu-id="aeae6-116">When you create a team, here's what gets created:</span></span>
- <span data-ttu-id="aeae6-117">新しい [Microsoft 365 グループ](office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="aeae6-117">A new [Microsoft 365 group](office-365-groups.md)</span></span>
- <span data-ttu-id="aeae6-118">チームのファイルを保存するための [SharePoint Online](sharepoint-onedrive-interact.md) サイトとドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="aeae6-118">A [SharePoint Online](sharepoint-onedrive-interact.md) site and document library to store team files</span></span>
- <span data-ttu-id="aeae6-119">[Exchange Online](exchange-teams-interact.md) の共有メールボックスとカレンダー</span><span class="sxs-lookup"><span data-stu-id="aeae6-119">An [Exchange Online](exchange-teams-interact.md) shared mailbox and calendar</span></span>
- <span data-ttu-id="aeae6-120">OneNote ノートブック</span><span class="sxs-lookup"><span data-stu-id="aeae6-120">A OneNote notebook</span></span>
- <span data-ttu-id="aeae6-121">Planner や Power BI などのその他の Microsoft 365 および Office 365 アプリとの連動</span><span class="sxs-lookup"><span data-stu-id="aeae6-121">Ties into other Microsoft 365 and Office 365 apps such as Planner and Power BI</span></span>

<span data-ttu-id="aeae6-122">既存のグループからチームを作成する場合は、グループのメンバーシップ、サイト、メールボックス、ノートブックが Teams に表示されます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-122">When you create a team from an existing group, that group's membership, site, mailbox, and notebook are surfaced in Teams.</span></span> <span data-ttu-id="aeae6-123">詳細については、こちらのポスターをご覧ください: [ITアーキテクト向けMicrosoft 365のグループ](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="aeae6-123">To learn more, check out this poster: [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span></span>

<span data-ttu-id="aeae6-124">Teams をカスタマイズおよび拡張するには、[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を使用してサードパーティ アプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-124">To customize and extend Teams, add third-party apps through [apps, bots, and connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="aeae6-125">Teams では、組織の外部のユーザーを[ゲストとして追加する](guest-access.md)ことで、チームまたはチャネルに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-125">With Teams, you can include people from outside your organization by [adding them as a guest](guest-access.md) to a team or channel.</span></span> <span data-ttu-id="aeae6-126">Microsoft 365 および Office 365 の一部として、Teams は強力な[開発プラットフォーム](https://docs.microsoft.com/microsoftteams/platform)を提供します。これにより、ユーザーは組織に必要なチームワーク ハブを構築できます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-126">As part of Microsoft 365 and Office 365, Teams offers a robust [development platform](https://docs.microsoft.com/microsoftteams/platform) so you can build the teamwork hub you need for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="aeae6-127">Teams のアーキテクチャの詳細については、[Teams Platform Academy (Teams プラットフォーム アカデミー)](https://aka.ms/TeamsPlatformAcademy) にある動画を視聴してください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-127">For a deep dive into Teams architecture, watch the videos on the [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy).</span></span>


## <a name="managing-teams"></a><span data-ttu-id="aeae6-128">Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="aeae6-128">Managing Teams</span></span>

<span data-ttu-id="aeae6-129">ユーザーは管理者として、Microsoft Teams 管理センター経由で Teams を管理します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-129">As the admin, you'll manage Teams through the Microsoft Teams admin center.</span></span> <span data-ttu-id="aeae6-130">「Teams 管理センターを使用して Teams を管理する」のビデオ (3:03 分) で、簡潔なオリエンテーションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-130">For a quick orientation, watch the Manage Teams using the Teams admin center video (3:03 min):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yi]

<span data-ttu-id="aeae6-131">詳細情報:</span><span class="sxs-lookup"><span data-stu-id="aeae6-131">To learn more:</span></span>

- [<span data-ttu-id="aeae6-132">Teams 管理者ロールを使用してTeams を管理します</span><span class="sxs-lookup"><span data-stu-id="aeae6-132">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="aeae6-133">Teams 管理センターで Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="aeae6-133">Manage Teams in the Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="aeae6-134">新しい Teams 管理センターへの移行中に Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="aeae6-134">Manage Teams during the transition to the new Teams admin center</span></span>](manage-teams-in-modern-portal.md)
- [<span data-ttu-id="aeae6-135">Microsoft 365 または Office 365 の Teams 機能を管理する</span><span class="sxs-lookup"><span data-stu-id="aeae6-135">Manage Teams features in your Microsoft 365 or Office 365</span></span>](enable-features-office-365.md)

<span data-ttu-id="aeae6-136">Teams およびその他の Microsoft 365 および Office 365 製品とサービスに今後導入される機能についての最新情報を常に取得するには、必ず「[メッセージ センター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)」と「[Teams ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-136">To stay on top of what's coming for Teams and all other Microsoft 365 or Office 365 products and services in your organization, be sure to check [Message center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) and the [Teams roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams).</span></span> <span data-ttu-id="aeae6-137">新機能および更新された機能、計画済みの変更、および問題についての通知を取得して、常に情報を把握して準備を整えられるようになります。</span><span class="sxs-lookup"><span data-stu-id="aeae6-137">You'll get announcements about new and updated features, planned changes, and issues to help keep you informed and prepared.</span></span> 

## <a name="upgrade-from-skype-for-business-to-teams"></a><span data-ttu-id="aeae6-138">Skype for Business から Teams へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="aeae6-138">Upgrade from Skype for Business to Teams</span></span>
<span data-ttu-id="aeae6-139">Teams は Microsoft 365 および Office 365 でのインテリジェント コミュニケーションの中心的なクライアントで、最終的に Skype for Business Online に取って代わります。</span><span class="sxs-lookup"><span data-stu-id="aeae6-139">Teams is the primary client for intelligent communications in Microsoft 365 and Office 365, and it'll eventually replace Skype for Business Online.</span></span> <span data-ttu-id="aeae6-140">Teams に導入される新機能の最新情報を入手するには、「[Microsoft 365 ロードマップ](https://aka.ms/O365Roadmap)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-140">To stay on top of new features coming to Teams, see the [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap).</span></span> <span data-ttu-id="aeae6-141">常設チャットおよびメッセージの機能を補完するために、Teams では内蔵され完全に統合された音声とビデオによる、包括的な会議および通話のエクスペリエンスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="aeae6-141">To complement persistent chat and messaging capabilities, Teams offers a comprehensive meeting and calling experience, with built in, fully integrated voice and video.</span></span> <span data-ttu-id="aeae6-142">Microsoft Teams ブログの「[完全な会議および通話ソリューションとなった Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-142">Check out [Teams is now a complete meeting and calling solution](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042) in the Microsoft Teams Blog.</span></span>

<span data-ttu-id="aeae6-143">Skype for Business を実行していて、Teams にアップグレードする準備が整っている場合、または Skype for Business と Teams を共存させて実行していて、完全に Teams に移動する準備が整っている場合、その移行作業を正常に完了させるために役に立つツール、ヒント、ガイダンスを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-143">If you're running Skype for Business and are ready to upgrade to Teams, or if you're running Skype for Business and Teams side-by-side and are ready to fully move to Teams, we have the tools, tips, and guidance to help make your transition successful.</span></span> <span data-ttu-id="aeae6-144">詳細については、「[Teams へのアップグレード](upgrade-start-here.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-144">To learn more, see [Upgrade to Teams](upgrade-start-here.md).</span></span>

## <a name="teamwork"></a><span data-ttu-id="aeae6-145">チームワーク</span><span class="sxs-lookup"><span data-stu-id="aeae6-145">Teamwork</span></span>
<span data-ttu-id="aeae6-146">すべてのチームはそれぞれ異なります。コラボレーションを行うための万能の手段はありません。</span><span class="sxs-lookup"><span data-stu-id="aeae6-146">Every team is different; there's no one-size-fits-all approach to collaboration.</span></span> <span data-ttu-id="aeae6-147">Microsoft 365 および Office 365 は各チームの固有のニーズを満たすよう設計されていて、ユーザーが通信、共同作業などより多くのことを専用の統合アプリで成し遂げられる能力を強化します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-147">Microsoft 365 and Office 365 are designed to meet the unique needs of every team, empowering people to communicate, collaborate, and achieve more with purpose-built, integrated applications.</span></span>

<span data-ttu-id="aeae6-148">どの Microsoft 365 または Office 365 アプリおよびサービスを使用するかを決めるときに、自分の組織で行われる作業や、所属するチームで行う必要がある会話の種類について考えます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-148">When deciding which Microsoft 365 or Office 365 apps and services to use, think about the work your organization does and the types of conversations your teams need to have.</span></span> 

- <span data-ttu-id="aeae6-149">**Teams** は、チームワークのハブとして、組織内外のユーザーが積極的にリアルタイムでつながり、共同作業を完了できる場所です。</span><span class="sxs-lookup"><span data-stu-id="aeae6-149">**Teams** , as the hub for teamwork, is where people - including people outside your organization - can actively connect and collaborate in real time to get things done.</span></span> <span data-ttu-id="aeae6-150">ドキュメントの共同作成や、会議の開催や、他のアプリやサービスでの共同作業など、作業が発生したその場で会話を交わします。</span><span class="sxs-lookup"><span data-stu-id="aeae6-150">Have a conversation right where the work is happening, whether coauthoring a document, having a meeting, or working together in other apps and services.</span></span> <span data-ttu-id="aeae6-151">Teams は、くだけたチャットを行ったり、プロジェクトに対して速やかに反復作業を行ったり、チームのファイルで作業したり、共有された成果物でコラボレーションを行ったりするための場所となります。</span><span class="sxs-lookup"><span data-stu-id="aeae6-151">Teams is the place to have informal chats, iterate quickly on a project, work with team files, and collaborate on shared deliverables.</span></span> 

- <span data-ttu-id="aeae6-152">**Outlook** は、使い慣れた電子メール環境や、より丁寧で真面目な方法でコラボレーションを行うために、またはターゲットを絞って直接コミュニケーションをとる場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-152">**Outlook** for collaborating in the familiar environment of email and in a more formal, structured manner or when targeted and direct communication is required.</span></span>

- <span data-ttu-id="aeae6-153">**SharePoint** は、サイト、ポータル、インテリジェント コンテンツ サービス、ビジネス プロセスの自動化、およびエンタープライズ検索で活用されます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-153">**SharePoint** for sites, portals, intelligent content services, business process automation, and enterprise search.</span></span> <span data-ttu-id="aeae6-154">SharePoint はコンテンツをフレームワークの中心で保持して、あらゆる種類のコンテンツをチーム全体で簡単に共有可能およびアクセス可能にします。</span><span class="sxs-lookup"><span data-stu-id="aeae6-154">SharePoint keeps content at the center of teamwork, making all types of content easily shareable and accessible across teams.</span></span> <span data-ttu-id="aeae6-155">Outlook、Yammer、および Teams との緊密な統合により、会話のクスぺリエンス全体にわたって、シームレスなコンテンツのコラボレーションを実現します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-155">Tight integration with Outlook, Yammer, and Teams enables seamless content collaboration across conversation experiences.</span></span>

- <span data-ttu-id="aeae6-156">**OneDrive for Business** は、ファイルを保管したり、招待した他のユーザーと共有するために利用できます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-156">**OneDrive for Business** for storing files and sharing them with people that a user invites.</span></span> <span data-ttu-id="aeae6-157">ユーザーが OneDrive for Business に保存するコンテンツは、ユーザーが他の人と共有するまで、プライベートとなります。これは、共有するつもりがない、または共有するための準備が整っていない個人のドキュメントや下書きのドキュメントを保管するためには最良のオプションです。</span><span class="sxs-lookup"><span data-stu-id="aeae6-157">Content that a user saves to OneDrive for Business is private until the user shares it with others, making it the best option for storing personal and draft documents that are not intended to be shared or not ready to be shared.</span></span>

- <span data-ttu-id="aeae6-158">**Yammer** は、組織全体にわたるユーザーを接続するために使用します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-158">**Yammer** to connect people across the organization.</span></span> <span data-ttu-id="aeae6-159">会社全体の取り組みを推進したり、ベスト プラクティスを共有したり、一般的な領域または関心のある話題や実践に関するコミュニティを構築したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-159">Drive company-wide initiatives, share best practices, and build communities around common topics of interest or areas of practice.</span></span> <span data-ttu-id="aeae6-160">クラウドソーシングのアイデアで、会社全体にわたるユーザーとのオープンなディスカッションを促進します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-160">Crowdsource ideas to foster open discussions with people across the company.</span></span>

- <span data-ttu-id="aeae6-161">**Office アプリ** は、Word、Excel、 PowerPoint、OneNote などを含む、すべてユーザーが良く知っていて、恒常的に使用している、慣れ親しんだツールです。</span><span class="sxs-lookup"><span data-stu-id="aeae6-161">**Office apps** are all the familiar tools that people know and use regularly, including Word, Excel, PowerPoint, and OneNote.</span></span> 

## <a name="teams-content-updates"></a><span data-ttu-id="aeae6-162">Teams のコンテンツ アップデート</span><span class="sxs-lookup"><span data-stu-id="aeae6-162">Teams content updates</span></span>

<span data-ttu-id="aeae6-163">「[更新された Teams のトピックの週間リスト](teams-updates.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-163">See a [weekly list of Teams topics that have been updated](teams-updates.md).</span></span>

## <a name="teams-known-issues"></a><span data-ttu-id="aeae6-164">Teams の既知の問題</span><span class="sxs-lookup"><span data-stu-id="aeae6-164">Teams known issues</span></span>

<span data-ttu-id="aeae6-165">こちらを参照してください[Teams トラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)。</span><span class="sxs-lookup"><span data-stu-id="aeae6-165">See [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams).</span></span>

## <a name="teams-client-release-notes"></a><span data-ttu-id="aeae6-166">Teams クライアントのリリース ノート</span><span class="sxs-lookup"><span data-stu-id="aeae6-166">Teams client release notes</span></span>

<span data-ttu-id="aeae6-167">「[ Teams の新機能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-167">See [What's new in Teams](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).</span></span>

