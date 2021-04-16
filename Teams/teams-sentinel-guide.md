---
title: Azure Sentinel および Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: IT 管理者が Sentinel を使用して、Teams で発生する可能性のある脅威を監視し、捜索するためのセキュリティに関するアドバイスと学習です。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3b2c37f7f3731b34abb5337bf954250e0c3564d
ms.sourcegitcommit: 046b020cee8af00a1d0e5f5866f847d42e8ad9a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51712769"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="82097-103">Azure Sentinel および Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82097-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82097-104">Azure Sentinel に統合コネクタが追加されました。</span><span class="sxs-lookup"><span data-stu-id="82097-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="82097-105">詳細については、「[Connect Office 365 Logs to Azure Sentinel (Office 365 のログを Azure Sentinel に接続する)](/azure/sentinel/connect-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82097-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="82097-106">これは、これらのログを収集するための推奨ルートであり、以下で説明する収集方法よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="82097-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="82097-107">Teams は、Microsoft 365 クラウドでの通信とデータ共有において中心的な役割を担います。</span><span class="sxs-lookup"><span data-stu-id="82097-107">Teams serves a central role in communication and data-sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="82097-108">チームはクラウド上の多くのテクノロジにタッチしますので、人によって自動で行われる分析からの益を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="82097-108">Since Teams touches on so many technologies in the Cloud, it can benefit from human and automated analysis.</span></span> <span data-ttu-id="82097-109">これは、*ログの検索* と *会議のリアルタイム監視* の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="82097-109">This applies to both *hunting in logs*, and *real-time monitoring of meetings*.</span></span> <span data-ttu-id="82097-110">Azure Sentinel は、管理者に次のようなソリューションを提案します。</span><span class="sxs-lookup"><span data-stu-id="82097-110">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="82097-111">Azure Sentinel の概要</span><span class="sxs-lookup"><span data-stu-id="82097-111">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="82097-112">[この記事](/azure/sentinel/overview) は、まさにその通りです。</span><span class="sxs-lookup"><span data-stu-id="82097-112">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="82097-113">Sentinel および Microsoft Teams のアクティビティ ログ</span><span class="sxs-lookup"><span data-stu-id="82097-113">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="82097-114">この記事では、Azure Sentinel でチーム アクティビティ ログを収集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="82097-114">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span>

<span data-ttu-id="82097-115">Sentinel では、管理者は 1 つの場所でセキュリティ管理を行います。</span><span class="sxs-lookup"><span data-stu-id="82097-115">Sentinel lets administrators do security management in one location.</span></span> <span data-ttu-id="82097-116">これには次の管理が含まれます。</span><span class="sxs-lookup"><span data-stu-id="82097-116">This includes managing:</span></span>

- <span data-ttu-id="82097-117">サード パーティ製デバイス</span><span class="sxs-lookup"><span data-stu-id="82097-117">Third-party devices</span></span>
- <span data-ttu-id="82097-118">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="82097-118">Microsoft Threat Protection</span></span>
- <span data-ttu-id="82097-119">Microsoft 365 ワークロード</span><span class="sxs-lookup"><span data-stu-id="82097-119">Microsoft 365 Workloads</span></span>

<span data-ttu-id="82097-120">Sentinel ブックと Runbook を使用すると、セキュリティ監視を *体系的* に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="82097-120">Sentinel workbooks and runbooks can make security monitoring *systematic*.</span></span> <span data-ttu-id="82097-121">このプロセスの最初の手順として、分析に必要なログを収集します。</span><span class="sxs-lookup"><span data-stu-id="82097-121">A good first step in this process is collecting the logs needed analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="82097-122">複数の Microsoft 365 サブスクリプションは、Azure Sentinel の同じインスタンスに表示できます。</span><span class="sxs-lookup"><span data-stu-id="82097-122">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="82097-123">これにより、[リアルタイム監視](/azure/sentinel/livestream) および履歴ログ ファイルでの脅威の検索ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="82097-123">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log files.</span></span> <span data-ttu-id="82097-124">管理者は、1つのリソース グループ内もしくはリソース グループ間、または別のサブスクリプションで、[クロス リソース クエリ](/azure/azure-monitor/log-query/cross-workspace-query) を使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="82097-124">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="82097-125">手順 1: Teams のログを収集する: Microsoft 365 で監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="82097-125">Step 1: Collect Teams logs: Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="82097-126">Teams は Microsoft 365 経由でアクティビティを記録するため、監査ログは既定では収集されません。</span><span class="sxs-lookup"><span data-stu-id="82097-126">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="82097-127">この機能を有効にするには、[次の手順](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) を実行します。</span><span class="sxs-lookup"><span data-stu-id="82097-127">Turn on this feature with [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> <span data-ttu-id="82097-128">Teams のデータは、*Audit.General* 下にある Microsoft 365 監査で収集されます。</span><span class="sxs-lookup"><span data-stu-id="82097-128">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a><span data-ttu-id="82097-129">手順 2: Office 365 のログを Azure Sentinel に接続する</span><span class="sxs-lookup"><span data-stu-id="82097-129">Step 2: Connect Office 365 logs to Azure Sentinel</span></span>

<span data-ttu-id="82097-130">Azure Sentinel には、Office 365 のログ用のコネクタが組み込まれており、Teams データを他の Office 365 データと共に Azure Sentinel に取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="82097-130">Azure Sentinel provides a built-in connector for Office 365 logs, which enables you to ingest Teams data into Azure Sentinel together with other Office 365 data.</span></span>
 
<span data-ttu-id="82097-131">Azure Sentinel で、Office 365 データ コネクタを有効にする。</span><span class="sxs-lookup"><span data-stu-id="82097-131">In Azure Sentinel, enable the Office 365 data connector.</span></span> <span data-ttu-id="82097-132">詳細については、「[Azure Sentinel のドキュメント](/azure/sentinel/connect-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82097-132">For more information, see the [Azure Sentinel documentation](/azure/sentinel/connect-office-365).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="82097-133">KQL クエリの役に立つ検索</span><span class="sxs-lookup"><span data-stu-id="82097-133">Helpful hunting KQL queries</span></span>

<span data-ttu-id="82097-134">これらのクエリを使用すると、Teams データとTeams 環境を理解できます。</span><span class="sxs-lookup"><span data-stu-id="82097-134">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="82097-135">疑わしいアクティビティを認識するには、最初の手順として環境がどのように見え、どのように振る舞うべきかを理解することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82097-135">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="82097-136">そこから、スレッド ハンティングに進出することができます。</span><span class="sxs-lookup"><span data-stu-id="82097-136">From there, you can branch out into threat hunting.</span></span>

### <a name="federated-external-users-query"></a><span data-ttu-id="82097-137">フェデレーション外部ユーザー クエリ</span><span class="sxs-lookup"><span data-stu-id="82097-137">Federated external users query</span></span>

<span data-ttu-id="82097-138">フェデレーション外部ユーザーを有する Teams サイト リストを取得します。</span><span class="sxs-lookup"><span data-stu-id="82097-138">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="82097-139">これらのユーザーは、組織によって所有されていないドメイン名および/または UPN サフィックスを持っています。</span><span class="sxs-lookup"><span data-stu-id="82097-139">These users have a domain name and/or a UPN suffix that isn't owned by your organization.</span></span>

<span data-ttu-id="82097-140">この例のクエリでは、組織が contoso.com. を所有しています。</span><span class="sxs-lookup"><span data-stu-id="82097-140">In this example query, the organization owns contoso.com.</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
```

> [!TIP]
> <span data-ttu-id="82097-141">Teams における外部アクセスおよびゲスト アクセスの種類の詳細については、「[別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」 または Teams セキュリティ ガイドの「[参加者の種類](teams-security-guide.md#participant-types)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82097-141">To learn more about External and Guest access types in Teams see [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md), or the [Participant Types](teams-security-guide.md#participant-types) section in the Teams Security Guide.</span></span>

### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="82097-142">最近参加した、または役割を変更したユーザー</span><span class="sxs-lookup"><span data-stu-id="82097-142">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="82097-143">特定のユーザーに問い合わせて、過去 7 日間または 1 週間以内に、Teams チャネルに追加されたかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="82097-143">Query a specific user to check if they were added to a Teams channel in the last seven days, or within a week:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

<span data-ttu-id="82097-144">過去 7 日間にチームのユーザーの役割が変更されたかどうかをクエリします。</span><span class="sxs-lookup"><span data-stu-id="82097-144">Query whether a user's role changed for a Team in the last seven days:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="82097-145">不明または新しい組織からの外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="82097-145">External users from unknown or new organizations</span></span>

<span data-ttu-id="82097-146">Teams では、環境やチャネルに外部ユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="82097-146">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="82097-147">多くの場合、組織では、キーとなるパートナーシップの数が限られています。また、これらのパートナーの中からユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="82097-147">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="82097-148">このKQLは、チームに追加された外部ユーザーが、以前に表示または追加されていない組織から来ているかどうかを見ています。</span><span class="sxs-lookup"><span data-stu-id="82097-148">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

<span data-ttu-id="82097-149">詳細については、「[Azure Sentinel コミュニティ git ハブ](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml)」のクエリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82097-149">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span></span>

### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="82097-150">追加され、後に削除された外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="82097-150">External users who were added and then removed</span></span>

<span data-ttu-id="82097-151">ある程度の既存アクセス権を持つ攻撃者は、Teams 新しい外部アカウントを追加して、データにアクセスしたり、データを流出させたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82097-151">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="82097-152">また、アクセスしたことを隠すために、当該ユーザーをすぐに削除してしまう可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="82097-152">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="82097-153">このクエリは、Teams に追加された外部アカウントを検索し、疑わしい動作を特定するために迅速に削除します。</span><span class="sxs-lookup"><span data-stu-id="82097-153">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

<span data-ttu-id="82097-154">詳細については、「[Azure Sentinel コミュニティ git ハブ](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml)」のクエリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82097-154">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span></span>

### <a name="new-bot-or-application-added"></a><span data-ttu-id="82097-155">新しい bot またはアプリケーションが追加されました</span><span class="sxs-lookup"><span data-stu-id="82097-155">New bot or application added</span></span>

<span data-ttu-id="82097-156">Teams にはチームにアプリまたはボットを含め、機能セット (カスタム アプリやボットを含む) を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="82097-156">Teams can include apps or bots in a Team to extend the feature set (including custom apps and bots).</span></span> <span data-ttu-id="82097-157">場合によっては、アプリまたはボットを使用して、ユーザー アカウントを必要とせずに Teams 内で *永続化* でき、ファイルやその他のデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="82097-157">In some cases, an app or bot can be used for *persistence* in Teams without needing a user account, and can access files and other data.</span></span> <span data-ttu-id="82097-158">このクエリは、チームに新たに追加されたアプリや bot を検索します。</span><span class="sxs-lookup"><span data-stu-id="82097-158">This query hunts for apps or bots that are new to Teams.</span></span>

<span data-ttu-id="82097-159">詳細については、「[Azure Sentinel コミュニティ git ハブ](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml)」のクエリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82097-159">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span></span>

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="82097-160">多数のチームの所有者であるユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="82097-160">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="82097-161">権限の昇格を考える攻撃者は、多数の色々なチームに所有者特権を自身に割り当てる場合があります。</span><span class="sxs-lookup"><span data-stu-id="82097-161">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams.</span></span> <span data-ttu-id="82097-162">*通常*、ユーザーは特定のトピックに関するいくつかのチームを作成して所有します。</span><span class="sxs-lookup"><span data-stu-id="82097-162">*Usually*, users create and own a few teams around specific topics.</span></span> <span data-ttu-id="82097-163">この KQL クエリは不審な動作を検索します。</span><span class="sxs-lookup"><span data-stu-id="82097-163">This KQL query looks for suspicious behavior.</span></span>

<span data-ttu-id="82097-164">詳細については、「[Azure Sentinel コミュニティ git ハブ](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml)」のクエリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82097-164">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span></span>

### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="82097-165">1人のユーザーによる多くのチームの削除</span><span class="sxs-lookup"><span data-stu-id="82097-165">Many Team deletions by a single user</span></span>

<span data-ttu-id="82097-166">攻撃者は、複数のチームを削除することで、プロジェクトやデータを混乱させたり、危険にさらしたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82097-166">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="82097-167">通常、チームは個人の所有者によって削除されているため、多くのチームを中心に削除されている場合は、問題の徴候になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82097-167">Since teams are usually deleted by individual Owners, central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="82097-168">この KQL は、複数のチームを削除するユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="82097-168">This KQL looks for single users who delete multiple teams.</span></span>

<span data-ttu-id="82097-169">詳細については、「[Azure Sentinel コミュニティ git ハブ](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml)」のクエリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82097-169">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span></span>

### <a name="expanding-your-threat-hunting-opportunities"></a><span data-ttu-id="82097-170">サイバー攻撃の検索の機会を拡大する</span><span class="sxs-lookup"><span data-stu-id="82097-170">Expanding your threat hunting opportunities</span></span>

<span data-ttu-id="82097-171">Azure Active Directory (Azure AD) などのリソースや他の Office 365 ワークロードからのクエリを組み合わせて、 Teams のクエリで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="82097-171">Combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads can be used with Teams queries.</span></span> <span data-ttu-id="82097-172">たとえば、Azure AD SigninLogs で疑わしいパターンの検出を組み合わせて、チーム所有者を探している間にその出力を使用します。</span><span class="sxs-lookup"><span data-stu-id="82097-172">For example, combine the detection of suspicious patterns in Azure AD SigninLogs, and use that output while hunting for Team Owners.</span></span>

```Kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
OfficeActivity
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '2'
| where Members in (failed_signins)
```

<span data-ttu-id="82097-173">また、Teams ベースのログオンのみのフィルターを追加することで、Teams 固有の SigninLogs の検出を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="82097-173">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based logons by using:</span></span>

```Kusto
| where AppDisplayName has 'Teams'
```

<span data-ttu-id="82097-174">*AppDisplayName にチームがある場所* の使用についてさらに説明するために、下に表示されている KQL の例では、1つの IP アドレスからのログオンに成功し、異なる IP アドレスからは失敗していますが、Teams のサインインに *のみ* 適用されます。</span><span class="sxs-lookup"><span data-stu-id="82097-174">To help explain using *where AppDisplayName has Teams* further, the KQL you see below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped to *only* Teams sign-ins:</span></span>

```Kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName has "Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="82097-175">重要な情報と更新プログラム</span><span class="sxs-lookup"><span data-stu-id="82097-175">Important information and updates</span></span>

<span data-ttu-id="82097-176">**Pete Bryan、Nicholas DiCola、および Matthew Lowe によるコンテンツの共同作業に感謝します。**</span><span class="sxs-lookup"><span data-stu-id="82097-176">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="82097-177">Pete Bryan および彼と共同作業している人は、Teams の検出クエリと検索クエリを開発し続けています。</span><span class="sxs-lookup"><span data-stu-id="82097-177">Pete Bryan, and people he collaborates with, continue to develop detection and hunting queries for Teams.</span></span>

<span data-ttu-id="82097-178">更新に関しては、[Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) リポジトリと連絡を取り合ってください。</span><span class="sxs-lookup"><span data-stu-id="82097-178">Stay in touch with this [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>

<span data-ttu-id="82097-179">この記事で使用している[パーサー](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)および[ロジック アプリ](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)の更新プログラムに注意してください。</span><span class="sxs-lookup"><span data-stu-id="82097-179">Watch for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span>

<span data-ttu-id="82097-180">[Azure Sentinel コミュニティ](https://github.com/Azure/Azure-Sentinel/wiki)に参加して投稿する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82097-180">You should also join (and contribute to) the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="82097-181">この記事に関するフィードバックを心よりお待ちしておりいますので、以下のフィードバック オプションをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="82097-181">We are actively looking for feedback on this article, so please use the feedback option below.</span></span> <span data-ttu-id="82097-182">ご利用ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="82097-182">Thank you & Happy hunting.</span></span>

[<span data-ttu-id="82097-183">Azure AD でアプリケーションを登録する</span><span class="sxs-lookup"><span data-stu-id="82097-183">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="82097-184">監査ログ検索を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="82097-184">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[<span data-ttu-id="82097-185">Azure Sentinel とは</span><span class="sxs-lookup"><span data-stu-id="82097-185">What is Azure Sentinel?</span></span>](/azure/sentinel/overview)
