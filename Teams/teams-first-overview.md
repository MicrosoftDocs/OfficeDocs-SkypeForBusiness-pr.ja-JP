---
title: 最初にMicrosoft Teamsする
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
description: このガイダンスを使用して、最初のMicrosoft TeamsワークロードとしてMicrosoft 365をOffice 365します。
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
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="ea867-103">最初にMicrosoft Teamsする</span><span class="sxs-lookup"><span data-stu-id="ea867-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="ea867-104">Microsoft Teams、特にリモートワークが世界中の従業員の現実である現在の前例のない時間に、従業員が互いにつながって共同作業を行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ea867-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="ea867-105">チャット、ビデオ会議、グループ内のドキュメントOffice共同作業を行Teamsは、企業の生産性を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ea867-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="ea867-106">小規模企業、非営利組織、または大規模な組織の場合でも、Microsoft 365 または Office 365 スイート内の最初のワークロードとして Teams を使い始めてから、他の Office アプリ またはサービスをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="ea867-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="ea867-107">この記事では、"Teams First" アプローチで行う必要がある考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea867-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea867-108">組織Teams初めてのクラウドデプロイ ワークロードになる可能性がある一方で、Teamsデプロイは、全体的なクラウド デプロイ戦略の一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="ea867-109">他の Microsoft 365 または Office 365 サービスを既にロールアウト済みで、Teams が (1 つ目ではなく) ロールアウトする次のワークロードである場合は、「Teams をロールアウトする方法」を[参照](./deploy-overview.md)してください。</span><span class="sxs-lookup"><span data-stu-id="ea867-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="ea867-110">開始するには</span><span class="sxs-lookup"><span data-stu-id="ea867-110">Start here</span></span>

<span data-ttu-id="ea867-111">Teams 最初のデプロイを開始するには、少なくともいくつかの前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="ea867-112">次の一覧は、有効にする前に組織に必要Teams示しています。</span><span class="sxs-lookup"><span data-stu-id="ea867-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="ea867-113">ドメイン名Microsoft 365構成Office 365組織または組織</span><span class="sxs-lookup"><span data-stu-id="ea867-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="ea867-114">Azure Active Directory接続 (AAD 接続) または同様のクラウド ID 同期ソリューション - 必要なすべての属性がテナントと同期されている</span><span class="sxs-lookup"><span data-stu-id="ea867-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="ea867-115">AAD 同期と同期される属性を理解するには、「Azure AD Connect 同期: 同期された属性[」をAzure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="ea867-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="ea867-116">アカウントに割り当てられている適切なユーザー ライセンスTeams</span><span class="sxs-lookup"><span data-stu-id="ea867-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="ea867-117">ライセンスの詳細Teamsについては、サービスのMicrosoft Teams[を参照してください](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="ea867-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="ea867-118">組織のネットワークを使用Teams</span><span class="sxs-lookup"><span data-stu-id="ea867-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="ea867-119">ネットワークの準備については、「組織のネットワークを準備する」を参照[Teams。](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="ea867-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="ea867-120">Exchange または Office 365: Exchange、Sharepoint、OneDrive for Business Microsoft 365 へのネットワーク アクセスを許可する: Office 365 [URL と IP](/office365/enterprise/urls-and-ip-address-ranges)アドレス範囲。</span><span class="sxs-lookup"><span data-stu-id="ea867-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="ea867-121">2019 年 9 月 1 日より後に作成されたテナントは、Teamsモードでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="ea867-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="ea867-122">デプロイがSkype for Business Server、2019 年 9 月 1 日より後にテナントがプロビジョニングされた場合は、Teams の共存機能を有効にするには、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="ea867-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="ea867-123">ユーザーにライセンスを割り当てる前に、"組織全体のアップグレード<span class="underline">ポリシー"</span>が "島モード" に設定Teams確認してください。</span><span class="sxs-lookup"><span data-stu-id="ea867-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="ea867-124">移行の開始点</span><span class="sxs-lookup"><span data-stu-id="ea867-124">Migration Starting points</span></span>

<span data-ttu-id="ea867-125">Microsoft 365 Teams Office 365 の開始点とオンプレミスの Skype for Business サーバーまたは Lync サーバーの存在に応じて、Teams で使用できる Skype for Business または Skype for Business と機能の使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="ea867-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="ea867-126">次のセクションでは、上記の前提条件に加えて、基本的な機能と構成オプションについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="ea867-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="ea867-127">開始点のシナリオを次のトピックに分けしました。</span><span class="sxs-lookup"><span data-stu-id="ea867-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="ea867-128">**テナントTeams構成**: テナントモードとユーザー モードを使用して、受信者の動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="ea867-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="ea867-129">これらの設定は、組織のテナント レベルまたはユーザー レベルで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ea867-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="ea867-130">詳細については、 との共存に関[する記事をSkype for Business。](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="ea867-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="ea867-131">**チャット/外部通信 Teams:** チャット サービスは、組織内または組織外のチャット会話をピアツーピアまたはグループ化します。</span><span class="sxs-lookup"><span data-stu-id="ea867-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="ea867-132">外部通信は、フェデレーションとも呼Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="ea867-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="ea867-133">**Teams** で会議を作成して表示する: ユーザーは常に Outlook Teams アドインを使用してオンライン会議を作成できます。PSTN ダイヤルインは、ユーザーのライセンスを取得すると、すべてのシナリオで利用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="ea867-134">Teams、Skype for Businessの予定表情報をユーザーのメールボックスに保存Exchangeします。</span><span class="sxs-lookup"><span data-stu-id="ea867-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="ea867-135">Teams Exchange Server クライアントがユーザーのメールボックスと対話するには、オンプレミスの Exchange サーバーが 2016 CU3 以上の 2016 CU3 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="ea867-136">メールボックスExchangeアクセスできない場合、Teams の予定表アイコンは表示されません。ユーザーは、Teams クライアントで会議を表示、作成、または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea867-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="ea867-137">**通話機能 VoIP/PSTN Teams:** 通話は、Voice over IP (VoIP) または Public Switched Telephone Network (PSTN) です。</span><span class="sxs-lookup"><span data-stu-id="ea867-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="ea867-138">VoIP 接続は、ユーザーが外部Teamsダイヤルするときに PSTN 接続が発生する一方で、クライアント間でネイティブに行います。</span><span class="sxs-lookup"><span data-stu-id="ea867-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="ea867-139">Teams 2 種類の PSTN 接続をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ea867-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="ea867-140">Microsoft 通話プラン(Microsoft がユーザーの電話番号を含むテレフォニー インフラストラクチャを提供する場合)、またはダイレクト ルーティング構成。この場合、顧客は Teams ユーザーのセッション ボーダー コントローラー (SBC) を使用してテレフォニー接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea867-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="ea867-141">詳細については、「どの通話プランが最適か[」](calling-plan-landing-page.md)を参照し、「ダイレクト[ルーティング電話システムを参照してください](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="ea867-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="ea867-142">**Teamsと** チャネルのコラボレーション : Teams: Teams では、チームは、仕事、プロジェクト、または共通の関心を持つユーザーのグループです。</span><span class="sxs-lookup"><span data-stu-id="ea867-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="ea867-143">Teamsは、チャネルで作成されます。</span><span class="sxs-lookup"><span data-stu-id="ea867-143">Teams are made up of channels.</span></span> <span data-ttu-id="ea867-144">各チャネルは、"チーム イベント" や部署名などのトピックを中心に構築され、楽しみたい場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="ea867-145">チャネルは、会議を開催し、会話を行い、ファイルをまとめて作業する場所です。</span><span class="sxs-lookup"><span data-stu-id="ea867-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="ea867-146">コラボレーション中</span><span class="sxs-lookup"><span data-stu-id="ea867-146">During collaboration</span></span>

<span data-ttu-id="ea867-147">**OneDrive for Business (P2P** ファイル共有) in Teams : Teams とチャネルの外部では、Teams ユーザーは、一般的な OneDrive を使用するか、Citrix Files、DropBox、Box、Google ドライブ などの他の P2P 共有ファイル プログラムを使用して、ファイルをピアツーピアで共有できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="ea867-148">一OneDriveの場合、ユーザーにはオンライン ライセンスSharePointが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="ea867-149">**アプリケーション プラットフォーム**: アプリは、組織が最新のツールを提供し、より多くの機能をTeams。</span><span class="sxs-lookup"><span data-stu-id="ea867-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="ea867-150">このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="ea867-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="ea867-151">**セキュリティと** コンプライアンスの機能: Teams には、保持ポリシー、データ損失防止 (DLP)、電子情報開示、チャネル、チャット、ファイルの法的ホールド、監査ログ検索など、コンプライアンス領域に役立つさまざまな情報があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="ea867-152">詳細については、「セキュリティとコンプライアンス[」を](security-compliance-overview.md)参照Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="ea867-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="ea867-153">Advance eDiscovery の機能には、E5 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ea867-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="ea867-154">[ライセンス オプションを比較します](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="ea867-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="ea867-155">シナリオ[でExchange機能をMicrosoft Teams方法](exchange-teams-interact.md)と対話方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea867-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="ea867-156">Skype for Business **<span class="underline"></span>** または Lync Server を使用しない組織</span><span class="sxs-lookup"><span data-stu-id="ea867-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="ea867-157">この開始点は、組織が現在 Skype for Business または Lync Server を利用していないと想定し、Teams が Microsoft 365 または Office 365 で初めてのアプリケーションになります。</span><span class="sxs-lookup"><span data-stu-id="ea867-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ea867-158">次の表では、コア サービスのサービスを使用する場合のTeamsの構成とエンド ユーザーの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea867-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ea867-159">アイテム</span><span class="sxs-lookup"><span data-stu-id="ea867-159">Item</span></span></th>
<th><span data-ttu-id="ea867-160">備考</span><span class="sxs-lookup"><span data-stu-id="ea867-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ea867-161">テナントTeams構成</span><span class="sxs-lookup"><span data-stu-id="ea867-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="ea867-162">Teamsモードのみ、すべてのチャット機能と通話機能はTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="ea867-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea867-163">チャット/外部通信 (Teams</span><span class="sxs-lookup"><span data-stu-id="ea867-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="ea867-164">内部 (組織Microsoft 365またはOffice 365) および外部チャットによる通信が可能Teams。</span><span class="sxs-lookup"><span data-stu-id="ea867-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="ea867-165"><em>注: DNS エントリは、外部アクセス用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="ea867-166">Skype for BusinessLync および Skype for Business 環境とのフェデレーションを許可するには、オンプレミスまたは Microsoft 365 または Office 365 に Skype for Business がない場合でも、DNS レコードがSkype for Businessされます。</span><span class="sxs-lookup"><span data-stu-id="ea867-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="ea867-167">
<a href="/office365/enterprise/external-domain-name-system-records">外部ドメイン ネーム システム レコード</a></em></span><span class="sxs-lookup"><span data-stu-id="ea867-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ea867-168">[会議] を作成して表示Teams</span><span class="sxs-lookup"><span data-stu-id="ea867-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="ea867-169">アドインを使用して、内部および外部Outlook作成できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="ea867-170">PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="ea867-171">Teamsアクセスするには、Exchange ハイブリッドが確立されたオンプレミスの Exchange 2016 CU3+ が必要です。ハイブリッド構成ウィザードを使用してハイブリッドデプロイを作成します<a href="/exchange/hybrid-deployment/deploy-hybrid">。</a> </span><span class="sxs-lookup"><span data-stu-id="ea867-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="ea867-172">ハイブリッド構成に加Exchange、OAuth 認証Exchangeを確立します。組織と組織の間で <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth 認証Exchange構成Exchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="ea867-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea867-173">通話機能</span><span class="sxs-lookup"><span data-stu-id="ea867-173">Calling Features</span></span><br />
<span data-ttu-id="ea867-174">VoIP/PSTN (Teams</span><span class="sxs-lookup"><span data-stu-id="ea867-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="ea867-175">テナントに対する内部および外部の VoIP を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="ea867-176">PSTN サービスは、Microsoft 通話プランMicrosoft 電話直接ルーティングを追加して構成できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ea867-177">TeamsでのチャネルとチャネルのコラボレーションTeams</span><span class="sxs-lookup"><span data-stu-id="ea867-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="ea867-178">コンプライアンス機能を含む完全なエクスペリエンスを得SharePoint Online ライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="ea867-179">既存のオンプレミス サイトとサイトSharePoint移行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ea867-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea867-180">OneDrive for Business (P2P ファイル共有)</span><span class="sxs-lookup"><span data-stu-id="ea867-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="ea867-181">OneDrive for Businessユーザーにオンライン ライセンスが割り当てられているSharePoint必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="ea867-182">このライセンスを使用しない場合、ピアツーピア ファイル共有は実行できない。</span><span class="sxs-lookup"><span data-stu-id="ea867-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ea867-183">アプリケーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="ea867-183">Application platform</span></span></td>
<td><span data-ttu-id="ea867-184">ユーザーは、会社のポリシーに従って、ユーザーが使用できるアプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="ea867-185">詳細については、「アプリの<a href="/microsoftteams/admin-settings">管理者設定」を参照Teams</a></span><span class="sxs-lookup"><span data-stu-id="ea867-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea867-186">セキュリティとコンプライアンスの機能</span><span class="sxs-lookup"><span data-stu-id="ea867-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="ea867-187">アイテム保持ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="ea867-188">チャネル メッセージに対するコンプライアンスに関する電子情報開示と法的ホールドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ea867-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="ea867-189">データ損失防止ポリシー (DLP) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="ea867-190">完全な機能セットは、Exchange Online。Exchangeオンプレミスでは、これらの機能のほとんどがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ea867-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="ea867-191">完全な一覧については<a href="/MicrosoftTeams/exchange-teams-interact">、「How Exchange and Teams interact 」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="ea867-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="ea867-192">ユーザーまたは Lync Server を使用しない組織Skype for Businessの有効化手順</span><span class="sxs-lookup"><span data-stu-id="ea867-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="ea867-193">前の「ここから開始する」セクションで詳しく説明されている前提条件を満たす</span><span class="sxs-lookup"><span data-stu-id="ea867-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="ea867-194">テナントを [Teamsのみ] モードに切り替えます (既存のテナントのみ): 共存とアップグレードの[設定を設定します](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ea867-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="ea867-195">会社のビジネス/会社のポリシーに従ってテナントを構成する: 組織の Microsoft Teams[設定を管理します](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ea867-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="ea867-196">ユーザーにTeamsクライアントをデプロイする:[ユーザーのクライアントを取得Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="ea867-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="ea867-197">導入プログラムを推進する</span><span class="sxs-lookup"><span data-stu-id="ea867-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="ea867-198">Microsoft Teams を導入する</span><span class="sxs-lookup"><span data-stu-id="ea867-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="ea867-199">Microsoft Teams の導入クイック スタートのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="ea867-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="ea867-200">他のワークロードの移行を計画して、Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="ea867-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="ea867-201">Skype for Business **<span class="underline">または</span>** Lync サーバーを使用している組織</span><span class="sxs-lookup"><span data-stu-id="ea867-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="ea867-202">この開始点は、組織がオンプレミスの Skype for Business 2019 または 2015+ または Lync 2013+ サーバーを使用すると想定しています。</span><span class="sxs-lookup"><span data-stu-id="ea867-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="ea867-203">オンプレミス サーバーからオンプレミス サーバーに移行する組織に関する広範なガイダンスTeams、これらのシナリオに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="ea867-204">このガイダンスは、ユーザーがTeamsで使用する最初のアプリケーションであるシナリオMicrosoft 365固有Office 365。</span><span class="sxs-lookup"><span data-stu-id="ea867-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ea867-205">次の表では、コア サービスのサービスを使用する場合のTeamsの構成とエンド ユーザーの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea867-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ea867-206">アイテム</span><span class="sxs-lookup"><span data-stu-id="ea867-206">Item</span></span></th>
<th><span data-ttu-id="ea867-207">備考</span><span class="sxs-lookup"><span data-stu-id="ea867-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ea867-208">テナントTeams構成</span><span class="sxs-lookup"><span data-stu-id="ea867-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="ea867-209">[Islands mode]を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea867-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea867-210">チャット/外部通信 (Teams</span><span class="sxs-lookup"><span data-stu-id="ea867-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="ea867-211">独自のテナント内でのみ内部的に、外部通信 (フェデレーション) は、Skype for Businessまたは Lync サーバーの展開を介して行います。</span><span class="sxs-lookup"><span data-stu-id="ea867-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ea867-212">[会議] を作成して表示Teams</span><span class="sxs-lookup"><span data-stu-id="ea867-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="ea867-213">アドインを使用して、内部および外部Outlook作成できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="ea867-214">PSTN ダイヤルインとダイヤルアウト機能は、電話会議ライセンスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="ea867-215">Teamsアクセスするには、Exchangeハイブリッドが確立されたオンプレミスの 2016 CU3+ Exchange必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="ea867-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">ハイブリッド構成ウィザードを使用してハイブリッド デプロイを作成します。</a></span><span class="sxs-lookup"><span data-stu-id="ea867-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="ea867-217">管理者は、Teams 会議ポリシーの PreferredMeetingProviderForIslandsMode 属性<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps">set-csteamsmeetingpolicy</a>を使用して、Skype for Business Outlook アドインを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea867-218">通話機能</span><span class="sxs-lookup"><span data-stu-id="ea867-218">Calling Features</span></span><br />
<span data-ttu-id="ea867-219">VoIP/PSTN (Teams</span><span class="sxs-lookup"><span data-stu-id="ea867-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="ea867-220">テナントに対して内部的に VoIP を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="ea867-221">PSTN サービスまたは通話プラン サービスは、ユーザーが [のみ] エクスペリエンスに移動Teams使用できません。</span><span class="sxs-lookup"><span data-stu-id="ea867-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ea867-222">TeamsでのチャネルとチャネルのコラボレーションTeams</span><span class="sxs-lookup"><span data-stu-id="ea867-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="ea867-223">コンプライアンス機能を含む完全なエクスペリエンスを得SharePoint Online ライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="ea867-224">既存のオンプレミス サイトとサイトSharePoint移行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ea867-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea867-225">OneDrive for Business (P2P ファイル共有)</span><span class="sxs-lookup"><span data-stu-id="ea867-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="ea867-226">OneDrive for Businessユーザーにオンライン ライセンスが割り当てられているSharePoint必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="ea867-227">このライセンスを使用しない場合、ピアごとのファイル共有は実行できない。</span><span class="sxs-lookup"><span data-stu-id="ea867-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ea867-228">アプリケーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="ea867-228">Application platform</span></span></td>
<td><span data-ttu-id="ea867-229">ユーザーは、会社のポリシーに従って、ユーザーが使用できるアプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="ea867-230">詳細については、「アプリの<a href="/microsoftteams/admin-settings">管理者設定」を参照Teams</a></span><span class="sxs-lookup"><span data-stu-id="ea867-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea867-231">セキュリティとコンプライアンスの機能</span><span class="sxs-lookup"><span data-stu-id="ea867-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="ea867-232">アイテム保持ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="ea867-233">チャネル メッセージに対するコンプライアンスに関する電子情報開示と法的ホールドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ea867-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="ea867-234">データ損失防止ポリシー (DLP) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="ea867-235">完全な機能セットは、Exchange Online。Exchangeオンプレミスでは、これらの機能のほとんどがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ea867-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="ea867-236">完全な一覧については、「<a href="/MicrosoftTeams/exchange-teams-interact">操作と対話のExchange方法Teams参照してください。</a></span><span class="sxs-lookup"><span data-stu-id="ea867-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="ea867-237">組織の有効化手順は、Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ea867-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="ea867-238">前の「ここから開始」セクションで詳しく説明されている前提条件を満たします。</span><span class="sxs-lookup"><span data-stu-id="ea867-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="ea867-239">テナントを諸島モードに切り替える (2019 年 9 月 1 日より後にプロビジョニングされたテナントの場合は、この変更を行うサポートにお問い合わせください)</span><span class="sxs-lookup"><span data-stu-id="ea867-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="ea867-240">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="ea867-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="ea867-241">会社のビジネス/会社のポリシーに従ってテナントを構成する</span><span class="sxs-lookup"><span data-stu-id="ea867-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="ea867-242">組織のMicrosoft Teams の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="ea867-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="ea867-243">クライアントをTeamsする</span><span class="sxs-lookup"><span data-stu-id="ea867-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="ea867-244">Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="ea867-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="ea867-245">導入プログラムを推進する</span><span class="sxs-lookup"><span data-stu-id="ea867-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="ea867-246">Microsoft Teams を導入する</span><span class="sxs-lookup"><span data-stu-id="ea867-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="ea867-247">Microsoft Teams の導入クイック スタートのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="ea867-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="ea867-248">他のワークロードの移行を計画して、Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="ea867-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="ea867-249">ハイブリッドSkype for Business確立し、Lync サーバーと Lync サーバーに推奨されるSkype for Businessパスに従います。</span><span class="sxs-lookup"><span data-stu-id="ea867-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="ea867-250">Skype for Business オンプレミスから Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="ea867-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="ea867-251">閉じるステートメント</span><span class="sxs-lookup"><span data-stu-id="ea867-251">Closing statement</span></span>

<span data-ttu-id="ea867-252">Microsoft Teams、すべての従業員、情報ワーカー、および Frontline ワーカーを 1 つのプラットフォームにまとめる、組織の有効化者になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea867-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="ea867-253">今すぐ [開始](https://products.office.com/microsoft-teams/group-chat-software) できます。</span><span class="sxs-lookup"><span data-stu-id="ea867-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="ea867-254">最新のお知らせや毎月の製品更新プログラムについては、こちら から連絡 [を取り合います](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。</span><span class="sxs-lookup"><span data-stu-id="ea867-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="ea867-255">また、世界中の企業が現在の COVID-19 の状況を管理する中で、Teams を組織で最大限に活用するのに役立つ一連のコンテンツを作成しました。</span><span class="sxs-lookup"><span data-stu-id="ea867-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="ea867-256">[COVID-19 のお客様](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)への取り組み</span><span class="sxs-lookup"><span data-stu-id="ea867-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="ea867-257">2 週間: リモート作業について学習した情報</span><span class="sxs-lookup"><span data-stu-id="ea867-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="ea867-258">オンライン会議とイベントの配信</span><span class="sxs-lookup"><span data-stu-id="ea867-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="ea867-259">Teams により中小規模企業でのリモート作業をサポートする</span><span class="sxs-lookup"><span data-stu-id="ea867-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="ea867-260">ライブ イベントのデジタル変換: フロントラインからの Bob Bejan の観察</span><span class="sxs-lookup"><span data-stu-id="ea867-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="ea867-261">Microsoft IT が社員のリモート作業を実現した 9 つの方法</span><span class="sxs-lookup"><span data-stu-id="ea867-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="ea867-262">リモートで作業し、セキュリティを確保する —CISOS のヒント</span><span class="sxs-lookup"><span data-stu-id="ea867-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="ea867-263">教師と学生がリモート学習に切り替えるのを支援する</span><span class="sxs-lookup"><span data-stu-id="ea867-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="ea867-264">ユーザーとリモートで作業しながら生産性をMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="ea867-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="ea867-265">サポート サービス リファレンス</span><span class="sxs-lookup"><span data-stu-id="ea867-265">Support Services reference</span></span>

<span data-ttu-id="ea867-266">Teamsは、Exchange Online、SharePoint Online、OneDrive for Business、Microsoft 365 グループに依存して、ユーザーに完全に統合された Microsoft 365 または Office 365 エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea867-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="ea867-267">上で説明したように、Teamsサービスを完全にデプロイせずに機能します。機能は限られています。</span><span class="sxs-lookup"><span data-stu-id="ea867-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="ea867-268">詳細については、Teams の前提条件に関するページを参照してください。「 へようこそ[」をTeams。](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ea867-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="ea867-269">上記の各サービスの詳細については、次のリンク先を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea867-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="ea867-270">Exchange Onlineは、予定表機能を使用し、ピアツーピア メッセージを Teams。</span><span class="sxs-lookup"><span data-stu-id="ea867-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="ea867-271">詳細については、「操作の方法[とExchange」をTeamsしてください。](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="ea867-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea867-272">Teams Exchange との相互運用を行う場合は、「Exchange 組織と Exchange Online 組織の間で OAuth 認証を構成する」の説明に従って、新しい Exchange OAuth 認証プロトコルを構成[する必要があります](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="ea867-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="ea867-273">SharePointチャネルでのファイル共有に使用し、/OneDrive for Business は 1:1 またはグループ チャットでのファイル共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea867-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="ea867-274">詳細については、「How [SharePoint Online and OneDrive for Business interact with Microsoft Teams 」を参照してください](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="ea867-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="ea867-275">[Microsoft 365グループは](office-365-groups.md)、チームとチャネルの作成/管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea867-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ea867-276">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ea867-276">Related topics</span></span>

[<span data-ttu-id="ea867-277">Microsoft Teams IT アーキテクチャとテレフォニー ソリューション ポスター</span><span class="sxs-lookup"><span data-stu-id="ea867-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="ea867-278">Skype for Business Server と Office 365 の間のハイブリッド接続を計画する</span><span class="sxs-lookup"><span data-stu-id="ea867-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="ea867-279">アプリケーションを使用してリモート ワーカーをTeams</span><span class="sxs-lookup"><span data-stu-id="ea867-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="ea867-280">ユーザーとリモートでMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="ea867-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)