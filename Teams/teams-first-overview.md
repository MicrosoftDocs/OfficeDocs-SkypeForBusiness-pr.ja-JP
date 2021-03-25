---
title: Microsoft Teams を最初に展開する
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
description: このガイダンスを使用して、Microsoft Teams を最初の Microsoft 365 または 365 ワークロードOffice展開します。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119356"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="c6655-103">Microsoft Teams を最初に展開する</span><span class="sxs-lookup"><span data-stu-id="c6655-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="c6655-104">Microsoft Teams は、特にリモートワークが世界中の従業員の現実である現在の例のない時間に、従業員が互いにつながって共同作業を行うのを支援します。</span><span class="sxs-lookup"><span data-stu-id="c6655-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="c6655-105">Teams 内でチャット、ビデオ会議、共同作業を行Officeは、企業の生産性を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c6655-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="c6655-106">小規模企業、非営利団体、または大規模な組織の場合は、Microsoft 365 または Office 365 スイートの最初の作業負荷として Teams を使い始めてから、他の Office アプリまたはサービスを展開できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="c6655-107">この記事では、"Teams First" アプローチで行う必要がある考慮事項について詳しい説明します。</span><span class="sxs-lookup"><span data-stu-id="c6655-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6655-108">Teams は組織初のクラウド展開ワークロードになりますが、Teams の展開は全体的なクラウド展開戦略の一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="c6655-109">既に他の Microsoft 365 または Office 365 サービスをロールアウト済みで、Teams が (最初のサービスではなく) 展開する次の作業負荷である場合は [、Teams](./deploy-overview.md)を展開する方法から開始します。</span><span class="sxs-lookup"><span data-stu-id="c6655-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="c6655-110">開始するには</span><span class="sxs-lookup"><span data-stu-id="c6655-110">Start here</span></span>

<span data-ttu-id="c6655-111">Teams First 展開を開始するには、少なくともいくつかの前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="c6655-112">次の一覧は、Teams を有効にする前に組織に必要な設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="c6655-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="c6655-113">Microsoft 365 または Office 365 組織がドメイン名で構成されている</span><span class="sxs-lookup"><span data-stu-id="c6655-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="c6655-114">Azure Active Directory 接続 (AAD 接続) または同様のクラウド ID 同期ソリューション – すべての必須属性がテナントと同期されている</span><span class="sxs-lookup"><span data-stu-id="c6655-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="c6655-115">AAD 同期と同期された属性を理解するには、「Azure AD Connect 同期: Azure Active Directory に同期された [属性」を参照してください。](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="c6655-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="c6655-116">Teams に割り当てられている適切なユーザー ライセンス</span><span class="sxs-lookup"><span data-stu-id="c6655-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="c6655-117">Teams のライセンスについて理解するには [、Microsoft Teams サービスの説明を参照してください](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="c6655-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="c6655-118">Teams 用に準備された組織のネットワーク</span><span class="sxs-lookup"><span data-stu-id="c6655-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="c6655-119">ネットワークの準備について理解するには、「組織のネットワーク [を Teams 用に準備する」を参照してください](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="c6655-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="c6655-120">Microsoft 365 または Office 365: Office [365 の URL](/office365/enterprise/urls-and-ip-address-ranges)と IP アドレス範囲で、Exchange、Sharepoint、OneDrive for Business へのネットワーク アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c6655-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="c6655-121">2019 年 9 月 1 日より後に作成されたテナントは、Teams のみモードでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="c6655-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="c6655-122">Skype for Business Server を展開し、2019 年 9 月 1 日より後にテナントがプロビジョニングされた場合は、Teams の共存機能を有効にするには、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c6655-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="c6655-123">Teams ライセンスをユーザーに割り当てる前に、"組織全体のアップグレード <span class="underline">ポリシー"</span> が "島モード" に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="c6655-124">移行の開始点</span><span class="sxs-lookup"><span data-stu-id="c6655-124">Migration Starting points</span></span>

<span data-ttu-id="c6655-125">Microsoft 365 または Office 365 への旅と Teams で利用できる機能は、開始点とオンプレミスの Skype for Business または Lync サーバーの存在に応じて異なる。</span><span class="sxs-lookup"><span data-stu-id="c6655-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="c6655-126">以下のセクションでは、上記の前提条件に加えて、基本的な機能と構成オプションについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="c6655-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="c6655-127">開始点のシナリオを次のトピックに分解しました。</span><span class="sxs-lookup"><span data-stu-id="c6655-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="c6655-128">**Tenant Teams 構成**: テナント モードとユーザー モードを使用して、受信者の動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="c6655-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="c6655-129">これらの設定は、テナント レベルまたは組織内のユーザー レベルで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c6655-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="c6655-130">詳細については [、「Skype for Business との共存」を参照してください](coexistence-chat-calls-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="c6655-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="c6655-131">**Teams でのチャット/外部** 通信: チャット サービスは、組織内および組織内外のピアツーピアまたはグループ チャットの会話を参照します。</span><span class="sxs-lookup"><span data-stu-id="c6655-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="c6655-132">外部通信は、Skype for Business ではフェデレーションとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c6655-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="c6655-133">**Teams での** 会議の作成と表示: ユーザーは Outlook Teams アドインを使用してオンライン会議をいつでも作成できます。PSTN ダイヤルインは、ユーザーのライセンスが取得された後、すべてのシナリオで利用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="c6655-134">Teams と Skype for Business では、予定表情報がユーザーの Exchange メールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c6655-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="c6655-135">Teams クライアントがユーザー Exchange Server操作するには、オンプレミスの Exchange サーバーが 2016 CU3 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="c6655-136">Exchange メールボックスにアクセスしない場合、Teams の予定表アイコンは表示されません。ユーザーは Teams クライアントで会議を表示、作成、または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6655-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="c6655-137">**Teams での通話機能 VoIP/PSTN: 通話** には、音声オーバー IP (VoIP) または公衆交換電話網 (PSTN) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="c6655-138">VoIP 接続は Teams クライアント間でネイティブで行い、PSTN 接続はユーザーが外部の電話番号をダイヤルするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="c6655-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="c6655-139">Teams では、2 種類の PSTN 接続がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c6655-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="c6655-140">Microsoft 通話プラン。Microsoft がユーザーの電話番号を含むテレフォニー インフラストラクチャ、または直接ルーティング構成を提供する場合、顧客は Teams ユーザーのセッション ボーダー コントローラー (SBC) を使用してテレフォニー接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6655-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="c6655-141">詳細については、「最適な [通話プラン](calling-plan-landing-page.md) 」と「電話システムダイレクト ルーティング」 [を参照してください](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="c6655-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="c6655-142">**Teams でのチームとチャネル** の共同作業: Teams では、チームは、作業、プロジェクト、共通の関心のためにまとめるユーザーのグループです。</span><span class="sxs-lookup"><span data-stu-id="c6655-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="c6655-143">チームはチャネルで作り上げされています。</span><span class="sxs-lookup"><span data-stu-id="c6655-143">Teams are made up of channels.</span></span> <span data-ttu-id="c6655-144">各チャネルは、"チーム イベント"、部門名、または単に楽しみのために、トピックを中心に構築されています。</span><span class="sxs-lookup"><span data-stu-id="c6655-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="c6655-145">チャネルは、会議を開催し、会話を行い、ファイルで一緒に作業する場所です。</span><span class="sxs-lookup"><span data-stu-id="c6655-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="c6655-146">共同作業中</span><span class="sxs-lookup"><span data-stu-id="c6655-146">During collaboration</span></span>

<span data-ttu-id="c6655-147">Teams での **OneDrive for Business (P2P** ファイル共有) : Teams およびチャネルの外部では、Teams ユーザーは OneDrive for Business または Citrix Files、DropBox、Box、Google Drive などの他の P2P 共有ファイル プログラムを使用して、ピアツーピアでファイルを共有できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="c6655-148">OneDrive for Business の場合、ユーザーには SharePoint Online ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="c6655-149">**アプリケーション プラットフォーム**: アプリは、組織が Teams をより多く利用するための、組み込みツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6655-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="c6655-150">このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="c6655-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="c6655-151">**セキュリティとコンプライアンスの機能:** Teams には、アイテム保持ポリシー、データ損失防止 (DLP)、電子情報開示、チャネル、チャットとファイルの法的保留、監査ログの検索など、コンプライアンス領域に役立つさまざまな情報があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="c6655-152">詳細については [、「Microsoft Teams のセキュリティとコンプライアンス」を参照してください](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c6655-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="c6655-153">Advance eDiscovery の機能を使用するには、E5 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6655-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="c6655-154">[ライセンス オプションを比較します](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="c6655-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="c6655-155">Exchange [と Microsoft Teams が対話して](exchange-teams-interact.md) 、シナリオで使用できるコンプライアンス機能を確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6655-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="c6655-156">Skype **<span class="underline"></span>** for Business または Lync Server がない組織</span><span class="sxs-lookup"><span data-stu-id="c6655-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="c6655-157">この開始点は、組織が現在 Skype for Business または Lync Server を利用していないと仮定し、Teams が Microsoft 365 または Office 365 の最初のアプリケーションになります。</span><span class="sxs-lookup"><span data-stu-id="c6655-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c6655-158">次の表では、主要サービス用の Teams の高レベルの構成とエンド ユーザーの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6655-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c6655-159">アイテム</span><span class="sxs-lookup"><span data-stu-id="c6655-159">Item</span></span></th>
<th><span data-ttu-id="c6655-160">備考</span><span class="sxs-lookup"><span data-stu-id="c6655-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c6655-161">テナント Teams の構成</span><span class="sxs-lookup"><span data-stu-id="c6655-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="c6655-162">Teams のみモード、すべてのチャット機能と通話機能は Teams のみになります。</span><span class="sxs-lookup"><span data-stu-id="c6655-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6655-163">Teams でのチャット/外部コミュニケーション</span><span class="sxs-lookup"><span data-stu-id="c6655-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="c6655-164">Teams から内部 (Microsoft 365 または Office 365 組織内) および外部チャット通信が可能。</span><span class="sxs-lookup"><span data-stu-id="c6655-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="c6655-165"><em>注: DNS エントリは、外部アクセス用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="c6655-166">Lync および Skype for Business 環境とのフェデレーションを許可するには、Skype for Business をオンプレミスまたは Microsoft 365 または Office 365 にインストールしていなくても、Skype for Business DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6655-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="c6655-167">
<a href="/office365/enterprise/external-domain-name-system-records">外部ドメイン ネーム システム レコード</a></em></span><span class="sxs-lookup"><span data-stu-id="c6655-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6655-168">Teams で会議を作成して表示する</span><span class="sxs-lookup"><span data-stu-id="c6655-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="c6655-169">Outlook アドインを使用して、内部会議と外部会議を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="c6655-170">PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="c6655-171">Teams の予定表へのアクセスには、Exchange ハイブリッドが確立された Exchange 2016 CU3+ オンプレミスが必要です。ハイブリッド構成ウィザードを使用してハイブリッド展開 <a href="/exchange/hybrid-deployment/deploy-hybrid">を作成します。</a> </span><span class="sxs-lookup"><span data-stu-id="c6655-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="c6655-172">Exchange ハイブリッド構成に加えて、Exchange OAuth 認証を確立します。Exchange と Exchange Online 組織の間で <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth 認証を構成します。"</span><span class="sxs-lookup"><span data-stu-id="c6655-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6655-173">通話機能</span><span class="sxs-lookup"><span data-stu-id="c6655-173">Calling Features</span></span><br />
<span data-ttu-id="c6655-174">Teams の VoIP /PSTN</span><span class="sxs-lookup"><span data-stu-id="c6655-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="c6655-175">テナントの内部および外部の VoIP を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="c6655-176">PSTN サービスは、Microsoft 電話システムを介して構成したり、Microsoft 通話プランまたは直接ルーティングを追加したりして構成できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6655-177">Teams でのチームとチャネルの共同作業</span><span class="sxs-lookup"><span data-stu-id="c6655-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="c6655-178">コンプライアンス機能を含む完全なエクスペリエンスを得る場合は、SharePoint Online ライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="c6655-179">既存のオンプレミスの SharePoint サイトを移行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c6655-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6655-180">OneDrive for Business (P2P ファイル共有)</span><span class="sxs-lookup"><span data-stu-id="c6655-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="c6655-181">OneDrive for Business では、ユーザーに SharePoint Online ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="c6655-182">このライセンスがない場合、ピアツーピアのファイル共有は行えなされます。</span><span class="sxs-lookup"><span data-stu-id="c6655-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6655-183">アプリケーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="c6655-183">Application platform</span></span></td>
<td><span data-ttu-id="c6655-184">ユーザーは、会社のポリシーに従って、ユーザーが使用できるアプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="c6655-185">詳細については、以下を参照してください: <a href="/microsoftteams/admin-settings">Teams のアプリの管理者設定</a></span><span class="sxs-lookup"><span data-stu-id="c6655-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6655-186">セキュリティとコンプライアンスの機能</span><span class="sxs-lookup"><span data-stu-id="c6655-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="c6655-187">アイテム保持ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="c6655-188">チャネル メッセージのコンプライアンスに関する電子情報開示と法的ホールドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c6655-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="c6655-189">データ損失防止ポリシー (DLP) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="c6655-190">Exchange Online で利用できる完全な機能セットExchange オンプレミスでは、これらのほとんどの機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c6655-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="c6655-191">完全な一覧については、「Exchange と Teams の <a href="/MicrosoftTeams/exchange-teams-interact">対話方法」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="c6655-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="c6655-192">Skype for Business または Lync Server を使用しない組織の有効化手順</span><span class="sxs-lookup"><span data-stu-id="c6655-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="c6655-193">上の 「ここから開始」セクションで詳しく説明されている前提条件を満たす</span><span class="sxs-lookup"><span data-stu-id="c6655-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="c6655-194">テナントを Teams のみモードに切り替える (既存のテナントの場合のみ):共存と [アップグレードの設定を設定します](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="c6655-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="c6655-195">会社のビジネス/会社のポリシーに従ってテナントを構成する: 組織の [Microsoft Teams 設定を管理します](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c6655-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="c6655-196">Teams クライアントをユーザーに展開する: [Teams のクライアントを取得する](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="c6655-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="c6655-197">導入プログラムを推進する</span><span class="sxs-lookup"><span data-stu-id="c6655-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="c6655-198">Microsoft Teams を導入する</span><span class="sxs-lookup"><span data-stu-id="c6655-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="c6655-199">Microsoft Teams の導入クイック スタートのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="c6655-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="c6655-200">他のワークロードを Microsoft 365 または 365 Officeする計画を開始する</span><span class="sxs-lookup"><span data-stu-id="c6655-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="c6655-201">Skype **<span class="underline"></span>** for Business または Lync サーバーを使用している組織</span><span class="sxs-lookup"><span data-stu-id="c6655-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="c6655-202">この開始点は、組織が Skype for Business 2019 または 2015+ または Lync 2013+ サーバーをオンプレミスで使用すると想定しています。</span><span class="sxs-lookup"><span data-stu-id="c6655-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="c6655-203">オンプレミス サーバーから Teams に移行する組織に関する広範なガイダンスが既に存在し、これらのシナリオに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="c6655-204">このガイダンスは、Teams が Microsoft 365 または Office 365 で使用する最初のアプリケーションであるシナリオに固有です。</span><span class="sxs-lookup"><span data-stu-id="c6655-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c6655-205">次の表では、主要サービス用の Teams の高レベルの構成とエンド ユーザーの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6655-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c6655-206">アイテム</span><span class="sxs-lookup"><span data-stu-id="c6655-206">Item</span></span></th>
<th><span data-ttu-id="c6655-207">備考</span><span class="sxs-lookup"><span data-stu-id="c6655-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c6655-208">テナント Teams の構成</span><span class="sxs-lookup"><span data-stu-id="c6655-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="c6655-209">諸島モード。</span><span class="sxs-lookup"><span data-stu-id="c6655-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6655-210">Teams でのチャット/外部コミュニケーション</span><span class="sxs-lookup"><span data-stu-id="c6655-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="c6655-211">自分のテナント内でのみ内部的に、外部通信 (フェデレーション) は Skype for Business または Lync サーバーの展開を介して行います。</span><span class="sxs-lookup"><span data-stu-id="c6655-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6655-212">Teams で会議を作成して表示する</span><span class="sxs-lookup"><span data-stu-id="c6655-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="c6655-213">Outlook アドインを使用して、内部会議と外部会議を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="c6655-214">PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="c6655-215">Teams の予定表へのアクセスには、Exchange ハイブリッドが確立された Exchange 2016 CU3+ オンプレミスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6655-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="c6655-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">ハイブリッド構成ウィザードを使用してハイブリッド展開を作成します。</a></span><span class="sxs-lookup"><span data-stu-id="c6655-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="c6655-217">管理者は、Teams 会議ポリシーの PreferredMeetingProviderForIslandsMode 属性<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> (set-csteamsmeetingpolicy)</a>を使用して Skype for Business Outlook アドインを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6655-218">通話機能</span><span class="sxs-lookup"><span data-stu-id="c6655-218">Calling Features</span></span><br />
<span data-ttu-id="c6655-219">Teams の VoIP /PSTN</span><span class="sxs-lookup"><span data-stu-id="c6655-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="c6655-220">テナント内部での VoIP を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="c6655-221">PSTN または通話プランのサービスは、ユーザーが Teams 専用のエクスペリエンスに移動されるまで利用できません。</span><span class="sxs-lookup"><span data-stu-id="c6655-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6655-222">Teams でのチームとチャネルの共同作業</span><span class="sxs-lookup"><span data-stu-id="c6655-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="c6655-223">コンプライアンス機能を含む完全なエクスペリエンスを得る場合は、SharePoint Online ライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="c6655-224">既存のオンプレミスの SharePoint サイトを移行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c6655-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6655-225">OneDrive for Business (P2P ファイル共有)</span><span class="sxs-lookup"><span data-stu-id="c6655-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="c6655-226">OneDrive for Business では、ユーザーに SharePoint Online ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6655-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="c6655-227">このライセンスがない場合は、ピアごとのファイル共有は行えなされます。</span><span class="sxs-lookup"><span data-stu-id="c6655-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c6655-228">アプリケーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="c6655-228">Application platform</span></span></td>
<td><span data-ttu-id="c6655-229">ユーザーは、会社のポリシーに従って、ユーザーが使用できるアプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="c6655-230">詳細については、以下を参照してください: <a href="/microsoftteams/admin-settings">Teams のアプリの管理者設定</a></span><span class="sxs-lookup"><span data-stu-id="c6655-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c6655-231">セキュリティとコンプライアンスの機能</span><span class="sxs-lookup"><span data-stu-id="c6655-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="c6655-232">アイテム保持ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="c6655-233">チャネル メッセージのコンプライアンスに関する電子情報開示と法的ホールドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c6655-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="c6655-234">データ損失防止ポリシー (DLP) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="c6655-235">Exchange Online で利用できる完全な機能セットExchange オンプレミスでは、これらのほとんどの機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c6655-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="c6655-236">完全な一覧については、「Exchange と <a href="/MicrosoftTeams/exchange-teams-interact">Teams の対話方法」を参照してください。</a></span><span class="sxs-lookup"><span data-stu-id="c6655-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="c6655-237">Skype for Business Server を使用する組織の有効化手順</span><span class="sxs-lookup"><span data-stu-id="c6655-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="c6655-238">上の 「ここから始める」セクションで詳しく説明されている前提条件をご説明します。</span><span class="sxs-lookup"><span data-stu-id="c6655-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="c6655-239">テナントを諸島モードに切り替える (2019 年 9 月 1 日より後にプロビジョニングされたテナントの場合は、この変更を行うサポートにお問い合わせください)</span><span class="sxs-lookup"><span data-stu-id="c6655-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="c6655-240">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="c6655-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="c6655-241">会社のビジネス/会社のポリシーに従ってテナントを構成する</span><span class="sxs-lookup"><span data-stu-id="c6655-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="c6655-242">組織のMicrosoft Teams の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="c6655-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="c6655-243">Teams クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="c6655-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="c6655-244">Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="c6655-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="c6655-245">導入プログラムを推進する</span><span class="sxs-lookup"><span data-stu-id="c6655-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="c6655-246">Microsoft Teams を導入する</span><span class="sxs-lookup"><span data-stu-id="c6655-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="c6655-247">Microsoft Teams の導入クイック スタートのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="c6655-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="c6655-248">他のワークロードを Microsoft 365 または 365 Officeする計画を開始する</span><span class="sxs-lookup"><span data-stu-id="c6655-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="c6655-249">Skype for Business ハイブリッドを確立し、Skype for Business および Lync サーバーの推奨されるアップグレード パスに従う</span><span class="sxs-lookup"><span data-stu-id="c6655-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="c6655-250">Skype for Business オンプレミスから Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="c6655-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="c6655-251">閉じるステートメント</span><span class="sxs-lookup"><span data-stu-id="c6655-251">Closing statement</span></span>

<span data-ttu-id="c6655-252">Microsoft Teams は、すべての従業員、情報ワーカー、フロントライン ワーカーを 1 つのプラットフォームでまとめる組織の有効利用者になります。</span><span class="sxs-lookup"><span data-stu-id="c6655-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="c6655-253">今すぐ [開始](https://products.office.com/microsoft-teams/group-chat-software) できます。</span><span class="sxs-lookup"><span data-stu-id="c6655-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="c6655-254">最新のお知らせや毎月の製品更新プログラムについては、こちらから連絡 [を取り合います](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。</span><span class="sxs-lookup"><span data-stu-id="c6655-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="c6655-255">また、世界中の企業が現在の COVID-19 の状況を管理する中で、Teams を組織内で最大限に活用するのに役立つ一連のコンテンツを作成しています。</span><span class="sxs-lookup"><span data-stu-id="c6655-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="c6655-256">[COVID-19 中](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)のお客様への取り組み</span><span class="sxs-lookup"><span data-stu-id="c6655-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="c6655-257">2 週間: リモートワークについて学んだこと</span><span class="sxs-lookup"><span data-stu-id="c6655-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="c6655-258">オンライン会議とイベントを実施する</span><span class="sxs-lookup"><span data-stu-id="c6655-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="c6655-259">Teams により中小規模企業でのリモート作業をサポートする</span><span class="sxs-lookup"><span data-stu-id="c6655-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="c6655-260">ライブ イベントのデジタル変換: フロントラインからのボブ ベジェノの観測</span><span class="sxs-lookup"><span data-stu-id="c6655-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="c6655-261">Microsoft IT が社員のリモート作業を実現した 9 つの方法</span><span class="sxs-lookup"><span data-stu-id="c6655-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="c6655-262">リモートで作業し、安全を確保する ——CIOS のヒント</span><span class="sxs-lookup"><span data-stu-id="c6655-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="c6655-263">教師と学生がリモート学習に切り替えるのを支援する</span><span class="sxs-lookup"><span data-stu-id="c6655-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="c6655-264">Microsoft Teams でリモートで作業しながら生産性を維持する</span><span class="sxs-lookup"><span data-stu-id="c6655-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="c6655-265">サポート サービスリファレンス</span><span class="sxs-lookup"><span data-stu-id="c6655-265">Support Services reference</span></span>

<span data-ttu-id="c6655-266">Teams は、完全に統合された Microsoft 365 または Office 365 エクスペリエンスをユーザーに提供するために、Exchange Online、SharePoint Online、OneDrive for Business、Microsoft 365 グループに依存します。</span><span class="sxs-lookup"><span data-stu-id="c6655-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="c6655-267">上記のように、Teams は、制限された機能でこれらのサービスを完全に展開することなく動作します。</span><span class="sxs-lookup"><span data-stu-id="c6655-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="c6655-268">Teams とその前提条件の詳細については [、「Teams](teams-overview.md)へようこそ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6655-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="c6655-269">上記の各サービスの詳細については、次のリンクに従ってください。</span><span class="sxs-lookup"><span data-stu-id="c6655-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="c6655-270">Exchange Online は、Teams の予定表機能やピアツーピア メッセージの保存に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6655-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="c6655-271">詳細については、「Exchange と [Teams の対話方法」を参照してください。](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="c6655-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6655-272">Teams と Exchange オンプレミスの相互運用では、「Exchange と Exchange Online 組織間の OAuth 認証を構成する」の説明に従って、新しい Exchange OAuth 認証プロトコルを [構成する必要があります](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="c6655-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="c6655-273">SharePoint はチャネルでのファイル共有に使用されます。/OneDrive for Business は 1 対 1 またはグループ チャットでのファイル共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6655-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="c6655-274">詳細については [、「SharePoint Online と OneDrive for Business](sharepoint-onedrive-interact.md)が Microsoft Teams と対話する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6655-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="c6655-275">[Microsoft 365 グループは](office-365-groups.md) 、チームおよびチャネルの作成/管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6655-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c6655-276">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6655-276">Related topics</span></span>

[<span data-ttu-id="c6655-277">Microsoft Teams IT アーキテクチャとテレフォニー ソリューション ポスター</span><span class="sxs-lookup"><span data-stu-id="c6655-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="c6655-278">Skype for Business Server と Office 365 の間のハイブリッド接続を計画する</span><span class="sxs-lookup"><span data-stu-id="c6655-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="c6655-279">Teams を使用してリモート ワーカーをサポートする</span><span class="sxs-lookup"><span data-stu-id="c6655-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="c6655-280">Microsoft 365 でリモートで作業する</span><span class="sxs-lookup"><span data-stu-id="c6655-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)