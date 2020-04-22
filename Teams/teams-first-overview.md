---
title: Microsoft Teams を最初にロールアウトする
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: このガイダンスを使用して、Microsoft Teams を最初の Office 365 ワークロードとしてロールアウトします。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9db6b2192224e796475c903cf5eeeaa06ecdc8ee
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780376"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="bb4bf-103">Microsoft Teams を最初にロールアウトする</span><span class="sxs-lookup"><span data-stu-id="bb4bf-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="bb4bf-104">Microsoft Teams を使用すると、従業員が世界中の従業員の現実である、現在のかつてない時間帯に、相互に接続して共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="bb4bf-105">チーム内でチャットしたり、ビデオ会議を行ったり、Office ドキュメントの共同作業を行ったりすると、会社の生産性を維持できます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="bb4bf-106">小規模ビジネス、非営利団体、大企業向けのいずれの場合も、他の Office アプリまたはサービスを展開する前に、Office 365 スイート内の最初のワークロードとして Teams を使い始めることができます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="bb4bf-107">この記事では、"Teams First" アプローチで行う必要がある考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb4bf-108">Teams は組織の最初のクラウドに展開されますが、チームの展開は、クラウド展開戦略全体の一部にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="bb4bf-109">他の Office 365 サービスを既にロールアウトしていて、チームが次のワークロード (最初ではなく) である場合は、[チームをロールアウトする方法](How-to-roll-out-teams.md)から開始してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-109">If you have already rolled out other Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out  Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="bb4bf-110">開始するには</span><span class="sxs-lookup"><span data-stu-id="bb4bf-110">Start here</span></span>

<span data-ttu-id="bb4bf-111">チームの最初の展開を始めるには、少なくともいくつかの前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="bb4bf-112">次のリストは、Teams を有効にする前に、組織に必要な場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="bb4bf-113">使用しているドメイン名で構成されている Office 365 組織</span><span class="sxs-lookup"><span data-stu-id="bb4bf-113">An Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="bb4bf-114">Azure Active Directory connectivity (AAD connect) または同様のクラウド id 同期ソリューション–テナントに同期される必須属性がすべて含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="bb4bf-115">AAD 同期と同期される属性について理解するには、「 [AZURE AD Connect sync: 属性が Azure Active Directory に同期](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)されている」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="bb4bf-116">Teams に割り当てられている適切なユーザーライセンス</span><span class="sxs-lookup"><span data-stu-id="bb4bf-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="bb4bf-117">Teams のライセンスについて理解するには、「 [Microsoft teams の Office 365 ライセンス](office-365-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-117">To understand Teams licensing, read [Office 365 licensing for Microsoft Teams](office-365-licensing.md)</span></span>

4.  <span data-ttu-id="bb4bf-118">Teams 用に準備された組織のネットワーク</span><span class="sxs-lookup"><span data-stu-id="bb4bf-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="bb4bf-119">ネットワークの準備について理解するには、「 [Teams 用に組織のネットワークを準備](prepare-network.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="bb4bf-120">Office 365 で Exchange、Sharepoint、OneDrive for Business へのネットワークアクセスを許可する: [office 365 url と IP アドレス範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="bb4bf-121">2019年9月1日以降に作成されたテナントは、Teams 専用モードでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="bb4bf-122">Skype for Business Server を展開していて、テナントが2019年9月1日以降にプロビジョニングされている場合は、プレミアサポートに連絡して、Teams の共存機能を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact premier support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="bb4bf-123">Teams のライセンスをユーザーに割り当てる<span class="underline">前に</span>、"組織全体のアップグレードポリシー" が "アイランドモード" に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="bb4bf-124">移行開始ポイント</span><span class="sxs-lookup"><span data-stu-id="bb4bf-124">Migration Starting points</span></span>

<span data-ttu-id="bb4bf-125">出発点と、オンプレミスの Skype for Business または Lync server の存在に応じて、Teams で利用できる Office 365 および機能への旅。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-125">Your journey to Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="bb4bf-126">以下のセクションでは、上記の前提条件に加え、基本的な機能と構成オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="bb4bf-127">出発点のシナリオは、次のトピックに分類されています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="bb4bf-128">**テナントチームの構成**: テナントとユーザーモードは、受信者の動作を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="bb4bf-129">これらの設定は、テナントレベルまたは組織内のユーザーレベルで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="bb4bf-130">詳細については、「 [Skype For business を使用した共存](coexistence-chat-calls-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="bb4bf-131">**Teams でのチャット/外部通信**: チャットサービスは、組織内外でのピアツーピアまたはグループチャットの会話を指します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="bb4bf-132">外部通信は、Skype for Business のフェデレーションとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="bb4bf-133">**Teams で会議を作成して表示**する: ユーザーがライセンスを取得した後は、常に Outlook Teams アドインと PSTN ダイヤルインを使ってオンライン会議を作成できます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="bb4bf-134">チームと Skype for Business ストアの予定表の情報をユーザーの Exchange メールボックスに保存します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="bb4bf-135">チームクライアントがユーザーのメールボックスを操作できるようにするには、オンプレミスの Exchange server が Exchange Server 2016 CU3 以降で以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="bb4bf-136">Exchange メールボックスにアクセスできない場合、Teams の予定表アイコンは表示されず、ユーザーは Teams クライアントで会議の表示、作成、または変更を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="bb4bf-137">**Teams での通話機能 VoIP/PSTN**: 通話は、ボイスオーバー IP (VoIP) または公衆交換電話網 (PSTN) になります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="bb4bf-138">VoIP 接続は Teams クライアント間でネイティブに実行されますが、ユーザーが外部の電話番号にダイヤルすると、PSTN 接続が発生します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="bb4bf-139">Teams は、2種類の PSTN 接続をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="bb4bf-140">Microsoft が、ユーザーの電話番号などのテレフォニーインフラストラクチャを提供している場合、または直接ルーティング構成である場合は、microsoft の通話プランを利用できます。これは、顧客がチームユーザーのセッションボーダーコントローラー (SBC) 経由でテレフォニー接続を提供する場合です。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="bb4bf-141">詳細については、「[通話プランが適切かどうか](calling-plan-landing-page.md)を確認する」および「[電話システムのダイレクトルーティング](direct-routing-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="bb4bf-142">**Teams でのチームとチャネルの共同作業**: teams では、teams は、仕事、プロジェクト、または一般的な関心事のためにまとめられたユーザーのグループです。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="bb4bf-143">チームはチャネルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-143">Teams are made up of channels.</span></span> <span data-ttu-id="bb4bf-144">各チャネルは、"チームイベント"、"部署名" などのトピック、または楽しいもので構成されています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="bb4bf-145">チャネルでは、会議を開催したり、会話をしたり、ファイルを共同編集したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="bb4bf-146">共同作業中</span><span class="sxs-lookup"><span data-stu-id="bb4bf-146">During collaboration</span></span>

<span data-ttu-id="bb4bf-147">**Teams での onedrive For business (P2P ファイル共有)**: チームとチャネルの外部では、チームユーザーは、OneDrive for business または Citrix のファイル、DropBox、Box、Google ドライブなどの P2P 共有ファイルプログラムを使用して、ピアツーピアファイルを共有できます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="bb4bf-148">OneDrive for business の場合、ユーザーには SharePoint Online ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="bb4bf-149">**アプリケーションプラットフォーム**: アプリでは、チームを最大限に活用できるように、組織のための既定のツールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="bb4bf-150">このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="bb4bf-151">**セキュリティとコンプライアンスの機能:** Teams には、アイテム保持ポリシー、データ損失防止 (DLP)、チャネル、チャット、ファイルの電子情報開示と法的保持、監査ログの検索など、コンプライアンスの領域に役立つさまざまな情報が用意されています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="bb4bf-152">詳細については、「 [Microsoft Teams でセキュリティとコンプライアンス](security-compliance-overview.md)を確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="bb4bf-153">アドバンス eDiscovery 機能には E5 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="bb4bf-154">[ライセンスのオプションを比較](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="bb4bf-155">お客様のシナリオで使用できるコンプライアンス機能については、「 [Exchange と Microsoft Teams の相互作用](exchange-teams-interact.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="bb4bf-156">Skype for Business または Lync server を使用して**<span class="underline">いない</span>** 組織</span><span class="sxs-lookup"><span data-stu-id="bb4bf-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="bb4bf-157">この出発点は、組織が Skype for Business または Lync server を使用していないことを前提としており、Teams は Office 365 の最初のアプリケーションとなります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-157">This starting point assumes that your organization does not utilize Skype for Business or Lync server currently and Teams will be your first application in Office 365.</span></span> <span data-ttu-id="bb4bf-158">次の表では、コアサービスの Teams の高レベルの構成とエンドユーザー向け機能について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="bb4bf-159">項目</span><span class="sxs-lookup"><span data-stu-id="bb4bf-159">Item</span></span></th>
<th><span data-ttu-id="bb4bf-160">メモ</span><span class="sxs-lookup"><span data-stu-id="bb4bf-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bb4bf-161">テナントチームの構成</span><span class="sxs-lookup"><span data-stu-id="bb4bf-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="bb4bf-162">Teams 専用モード、すべてのチャット機能と通話機能が Teams のみに含まれている</span><span class="sxs-lookup"><span data-stu-id="bb4bf-162">Teams Only mode, all chat and calling features are in Teams Only</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb4bf-163">Teams でのチャット/外部通信</span><span class="sxs-lookup"><span data-stu-id="bb4bf-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="bb4bf-164">内部 (Office 365 組織内) および Teams からの外部チャット通信可能</span><span class="sxs-lookup"><span data-stu-id="bb4bf-164">Internal (intra Office 365 organization) and external chat communication possible from Teams</span></span></p>
<p><span data-ttu-id="bb4bf-165"><em>注: DNS エントリは、外部アクセス用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="bb4bf-166">Skype for business DNS レコードは、Lync および Skype for business 環境とのフェデレーションを許可するために、オンプレミスの Skype for Business または Office 365 を使っていない場合でも必要です。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises or in Office 365 to allow federation with Lync and Skype for Business environments.</span></span><br /><span data-ttu-id="bb4bf-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Office 365 の外部ドメインネームシステムレコード</a></em></span><span class="sxs-lookup"><span data-stu-id="bb4bf-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records for Office 365</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb4bf-168"><em>Teams で会議を作成して表示する</em></span><span class="sxs-lookup"><span data-stu-id="bb4bf-168"><em>Create and view Meetings in Teams</em></span></span></td>
<td><p><span data-ttu-id="bb4bf-169"><em>Outlook アドインを使用して会議を作成できる</em></span><span class="sxs-lookup"><span data-stu-id="bb4bf-169"><em>Able to create meetings via Outlook add-in</em></span></span></p>
<p><span data-ttu-id="bb4bf-170"><em>PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-170"><em>PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="bb4bf-171">注: チームの予定表にアクセスするには、exchange ハイブリッドが確立された Exchange 2016 CU3 以降で + オンプレミスの展開が必要:<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">ハイブリッド構成ウィザードを使用したハイブリッド展開の作成</a></span><span class="sxs-lookup"><span data-stu-id="bb4bf-171">Note: Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span><br />
<span data-ttu-id="bb4bf-172">Exchange ハイブリッド構成に加えて、exchange OAuth 認証を確立する: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">exchange と Exchange Online 組織の間の oauth 認証を構成</a>する</em></span><span class="sxs-lookup"><span data-stu-id="bb4bf-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations</a></em></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb4bf-173">通話機能</span><span class="sxs-lookup"><span data-stu-id="bb4bf-173">Calling Features</span></span><br />
<span data-ttu-id="bb4bf-174">Teams での VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="bb4bf-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="bb4bf-175">テナントの内部および外部の VoIP が利用可能</span><span class="sxs-lookup"><span data-stu-id="bb4bf-175">VoIP internally and externally to the tenant is available</span></span></p>
<p><span data-ttu-id="bb4bf-176">PSTN サービスは、Microsoft 電話システムを使って構成できます。さらに、Microsoft 通話プランまたは直接ルーティングを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb4bf-177">Teams でのチームとチャネルのコラボレーション</span><span class="sxs-lookup"><span data-stu-id="bb4bf-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="bb4bf-178">コンプライアンス機能などの完全なエクスペリエンスを実現するには、SharePoint Online ライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="bb4bf-179">既存のオンプレミスの SharePoint サイトの移行は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb4bf-180">OneDrive for Business (P2P ファイル共有)</span><span class="sxs-lookup"><span data-stu-id="bb4bf-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="bb4bf-181">OneDrive for Business では、ユーザーに SharePoint Online ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="bb4bf-182">このライセンスがない場合、ピアツーピアファイル共有はできません。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb4bf-183">アプリケーションプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="bb4bf-183">Application platform</span></span></td>
<td><span data-ttu-id="bb4bf-184">ユーザーは会社のポリシーに従って、利用可能なアプリを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="bb4bf-185">詳細情報: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Teams のアプリの管理設定</a></span><span class="sxs-lookup"><span data-stu-id="bb4bf-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb4bf-186">セキュリティとコンプライアンスの機能</span><span class="sxs-lookup"><span data-stu-id="bb4bf-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="bb4bf-187">アイテム保持ポリシーを使用できます</span><span class="sxs-lookup"><span data-stu-id="bb4bf-187">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="bb4bf-188">チャネルメッセージのコンプライアンスのための電子情報開示と法的保持はサポートされています</span><span class="sxs-lookup"><span data-stu-id="bb4bf-188">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="bb4bf-189">データ損失防止ポリシー (DLP) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-189">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="bb4bf-190">Exchange Online で利用できるすべての機能セット、Exchange オンプレミスは、次の機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-190">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="bb4bf-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange と Teams の連携</a></span><span class="sxs-lookup"><span data-stu-id="bb4bf-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<p><span data-ttu-id="bb4bf-192">すべてのリストの場合</span><span class="sxs-lookup"><span data-stu-id="bb4bf-192">for full list</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="bb4bf-193">Skype for Business または Lync Server を使用していない組織向けの有効化手順</span><span class="sxs-lookup"><span data-stu-id="bb4bf-193">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="bb4bf-194">上の [ここから始めてください] セクションで前提条件を満たす</span><span class="sxs-lookup"><span data-stu-id="bb4bf-194">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="bb4bf-195">テナントを Teams 専用モード (既存のテナントのみ) に切り替える:[共存とアップグレードの設定を設定](setting-your-coexistence-and-upgrade-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-195">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="bb4bf-196">会社のビジネス/会社のポリシーに従ってテナントを構成する:[組織の Microsoft Teams の設定を管理](enable-features-office-365.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-196">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="bb4bf-197">チームクライアントをユーザーに展開する:[チームのクライアントを取得](get-clients.md)する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-197">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="bb4bf-198">導入プログラムを推進する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-198">Drive your adoption program</span></span>  
    [<span data-ttu-id="bb4bf-199">Microsoft Teams を導入する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-199">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="bb4bf-200">Microsoft Teams の導入クイック スタートのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="bb4bf-200">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="bb4bf-201">他のワークロードの Office 365 への移行の計画を開始する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-201">Begin planning moving other workloads to Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="bb4bf-202">Skype for Business または Lync server**<span class="underline">を使用している</span>** 組織</span><span class="sxs-lookup"><span data-stu-id="bb4bf-202">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="bb4bf-203">この出発点は、組織が Skype for Business 2019 または 2015 + または Lync 2013 + server をオンプレミスで利用していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-203">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="bb4bf-204">オンプレミスのサーバーから Teams に移行する組織向けの広範なガイダンスは、これらのシナリオについて説明されています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-204">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="bb4bf-205">このガイダンスは、Teams が Office 365 で初めて利用するアプリケーションであるシナリオに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-205">This guidance is specific to the scenario that Teams is the first application you utilize in Office 365.</span></span> <span data-ttu-id="bb4bf-206">次の表では、コアサービスの Teams の高レベルの構成とエンドユーザー向け機能について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-206">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="bb4bf-207">項目</span><span class="sxs-lookup"><span data-stu-id="bb4bf-207">Item</span></span></th>
<th><span data-ttu-id="bb4bf-208">メモ</span><span class="sxs-lookup"><span data-stu-id="bb4bf-208">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bb4bf-209">テナントチームの構成</span><span class="sxs-lookup"><span data-stu-id="bb4bf-209">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="bb4bf-210">アイランド モード</span><span class="sxs-lookup"><span data-stu-id="bb4bf-210">Islands mode</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb4bf-211">Teams でのチャット/外部通信</span><span class="sxs-lookup"><span data-stu-id="bb4bf-211">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="bb4bf-212">自分のテナント内でのみ内部で利用できる外部通信 (フェデレーション) は、Skype for Business または Lync server の展開を通じて行われます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-212">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb4bf-213">Teams で会議を作成して表示する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-213">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="bb4bf-214">Outlook アドインを使用して会議を作成できる</span><span class="sxs-lookup"><span data-stu-id="bb4bf-214">Able to create meetings via Outlook add-in</span></span></p>
<p><span data-ttu-id="bb4bf-215">PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-215">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="bb4bf-216">チームの予定表へのアクセスには、exchange 2016 CU3 以降で + オンプレミスの展開が必要です。 Exchange ハイブリッドが確立されています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-216">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="bb4bf-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">ハイブリッド構成ウィザードを使ってハイブリッド展開を作成する</a></span><span class="sxs-lookup"><span data-stu-id="bb4bf-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb4bf-218">通話機能</span><span class="sxs-lookup"><span data-stu-id="bb4bf-218">Calling Features</span></span><br />
<span data-ttu-id="bb4bf-219">Teams での VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="bb4bf-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="bb4bf-220">テナントの内部の VoIP が利用可能</span><span class="sxs-lookup"><span data-stu-id="bb4bf-220">VoIP internally to the tenant is available</span></span></p>
<p><span data-ttu-id="bb4bf-221">PSTN または通話プランサービスは、ユーザーが Teams のみに移行されるまでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb4bf-222">Teams でのチームとチャネルのコラボレーション</span><span class="sxs-lookup"><span data-stu-id="bb4bf-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="bb4bf-223">コンプライアンス機能などの完全なエクスペリエンスを実現するには、SharePoint Online ライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="bb4bf-224">既存のオンプレミスの SharePoint サイトの移行は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb4bf-225">OneDrive for Business (P2P ファイル共有)</span><span class="sxs-lookup"><span data-stu-id="bb4bf-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="bb4bf-226">OneDrive for Business では、ユーザーに SharePoint Online ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="bb4bf-227">このライセンスがないと、ピア間でのファイル共有はできません。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb4bf-228">アプリケーションプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="bb4bf-228">Application platform</span></span></td>
<td><span data-ttu-id="bb4bf-229">ユーザーは会社のポリシーに従って、利用可能なアプリを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="bb4bf-230">詳細情報: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Teams のアプリの管理設定</a></span><span class="sxs-lookup"><span data-stu-id="bb4bf-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb4bf-231">セキュリティとコンプライアンスの機能</span><span class="sxs-lookup"><span data-stu-id="bb4bf-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="bb4bf-232">アイテム保持ポリシーを使用できます</span><span class="sxs-lookup"><span data-stu-id="bb4bf-232">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="bb4bf-233">チャネルメッセージのコンプライアンスのための電子情報開示と法的保持はサポートされています</span><span class="sxs-lookup"><span data-stu-id="bb4bf-233">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="bb4bf-234">データ損失防止ポリシー (DLP) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-234">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="bb4bf-235">Exchange Online で利用できるすべての機能セット、Exchange オンプレミスは、次の機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-235">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="bb4bf-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange と Teams の連携</a></span><span class="sxs-lookup"><span data-stu-id="bb4bf-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<ul>
<li><p><span data-ttu-id="bb4bf-237">すべてのリストの場合</span><span class="sxs-lookup"><span data-stu-id="bb4bf-237">for full list</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="bb4bf-238">Skype for Business Server を使用する組織向けの有効化手順</span><span class="sxs-lookup"><span data-stu-id="bb4bf-238">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="bb4bf-239">上の [ここから始めてください] セクションで、前提条件を満たしているかをご説明します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-239">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="bb4bf-240">テナントを諸島モードに切り替える (9/1/2019 の後にプロビジョニングされたテナントの場合は、プレミアサポートに連絡して、この変更を行う)</span><span class="sxs-lookup"><span data-stu-id="bb4bf-240">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact premier support to make this change)</span></span>  
    [<span data-ttu-id="bb4bf-241">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-241">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="bb4bf-242">会社のビジネス/会社のポリシーに従ってテナントを構成する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-242">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="bb4bf-243">組織のMicrosoft Teams の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-243">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="bb4bf-244">Teams クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-244">Deploy the Teams client</span></span>  
    [<span data-ttu-id="bb4bf-245">Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-245">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="bb4bf-246">導入プログラムを推進する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-246">Drive your adoption program</span></span>  
    [<span data-ttu-id="bb4bf-247">Microsoft Teams を導入する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-247">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="bb4bf-248">Microsoft Teams の導入クイック スタートのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="bb4bf-248">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="bb4bf-249">他のワークロードの Office 365 への移行の計画を開始する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-249">Begin planning moving other workloads to Office 365</span></span>

7.  <span data-ttu-id="bb4bf-250">Skype for business ハイブリッドを確立し、Skype for Business および Lync サーバーの推奨されるアップグレードパスに従います。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-250">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="bb4bf-251">Skype for Business オンプレミスから Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="bb4bf-251">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="bb4bf-252">終了明細書</span><span class="sxs-lookup"><span data-stu-id="bb4bf-252">Closing statement</span></span>

<span data-ttu-id="bb4bf-253">Microsoft Teams は、組織が1つのプラットフォームですべての従業員、インフォメーションワーカー、および Firstline worker をまとめるためのイネーブラーとして使用することができます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-253">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="bb4bf-254">今すぐ[作業](https://products.office.com/microsoft-teams/group-chat-software)を始めることができます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-254">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="bb4bf-255">最新のお知らせと毎月の製品更新プログラムについては、[こちら](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-255">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="bb4bf-256">さらに、世界中の会社が現在の COVID-19 の状況を管理しているため、チームを活用して組織への影響を最大限に高めるために役立つ一連のコンテンツが作成されました。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-256">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="bb4bf-257">[COVID-19 でのお客様への確約](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="bb4bf-257">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="bb4bf-258">2週間以内: リモート作業について学習しました</span><span class="sxs-lookup"><span data-stu-id="bb4bf-258">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="bb4bf-259">オンライン会議とイベントの配信</span><span class="sxs-lookup"><span data-stu-id="bb4bf-259">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="bb4bf-260">Teams により中小規模企業でのリモート作業をサポートする</span><span class="sxs-lookup"><span data-stu-id="bb4bf-260">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="bb4bf-261">ライブイベントのデジタル変換: ボブが frontline からの1月の所見</span><span class="sxs-lookup"><span data-stu-id="bb4bf-261">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="bb4bf-262">Microsoft IT が社員のリモート作業を実現した 9 つの方法</span><span class="sxs-lookup"><span data-stu-id="bb4bf-262">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="bb4bf-263">リモートで作業する、セキュリティを維持する、CISOs のヒント</span><span class="sxs-lookup"><span data-stu-id="bb4bf-263">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="bb4bf-264">教師と学生がリモートラーニングに切り替えることができるように支援する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-264">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="bb4bf-265">Microsoft Teams を使用してリモートで作業しながら生産性を維持する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-265">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="bb4bf-266">サポートサービスリファレンス</span><span class="sxs-lookup"><span data-stu-id="bb4bf-266">Support Services reference</span></span>

<span data-ttu-id="bb4bf-267">チームは Exchange Online、SharePoint Online、OneDrive for Business、Microsoft 365 グループに依存して、完全に統合された Office 365 エクスペリエンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-267">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Office 365 experience.</span></span> <span data-ttu-id="bb4bf-268">上で説明したように、チームは、機能が制限されている場合に、これらのサービスを完全に展開することなく機能します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-268">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="bb4bf-269">チームとその前提条件の詳細については、「 [teams へようこそ](teams-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-269">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="bb4bf-270">上記の各サービスの詳細については、以下のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-270">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="bb4bf-271">Exchange Online は、予定表機能に使用され、Teams でピア to ピアメッセージを保存します。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-271">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="bb4bf-272">詳細については、「 [Exchange とチームの相互作用](exchange-teams-interact.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-272">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb4bf-273">オンプレミスの Exchange との Teams の相互運用機能については、「 [exchange と Exchange Online の間の oauth 認証の構成](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)」の説明に従って、新しい Exchange OAuth 認証プロトコルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-273">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="bb4bf-274">SharePoint はチャネルでのファイル共有に使用されますが、OneDrive for Business は1:1 またはグループチャットでのファイル共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-274">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="bb4bf-275">詳細については、「 [SharePoint Online と OneDrive For business が Microsoft Teams とどのように連携するか](sharepoint-onedrive-interact.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-275">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="bb4bf-276">[Microsoft 365 グループ](office-365-groups.md)は、チームとチャネルの作成/管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb4bf-276">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="bb4bf-277">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bb4bf-277">Related topics</span></span>

[<span data-ttu-id="bb4bf-278">Microsoft Teams IT アーキテクチャとテレフォニー ソリューション ポスター</span><span class="sxs-lookup"><span data-stu-id="bb4bf-278">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="bb4bf-279">Skype for Business Server と Office 365 の間のハイブリッド接続を計画する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-279">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="bb4bf-280">Teams を使用したリモートワーカーのサポート</span><span class="sxs-lookup"><span data-stu-id="bb4bf-280">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="bb4bf-281">Office 365 を使用してリモートで作業する</span><span class="sxs-lookup"><span data-stu-id="bb4bf-281">Work remotely with Office 365</span></span>](https://aka.ms/remote-work)