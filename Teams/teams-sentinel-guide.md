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
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel および Microsoft Teams

> [!IMPORTANT]
> Azure Sentinel に統合コネクタが追加されました。 詳細については、「[Connect Office 365 Logs to Azure Sentinel (Office 365 のログを Azure Sentinel に接続する)](/azure/sentinel/connect-office-365)」を参照してください。 これは、これらのログを収集するための推奨ルートであり、以下で説明する収集方法よりも優先されます。

Teams は、Microsoft 365 クラウドでの通信とデータ共有において中心的な役割を担います。 チームはクラウド上の多くのテクノロジにタッチしますので、人によって自動で行われる分析からの益を受けることができます。 これは、*ログの検索* と *会議のリアルタイム監視* の両方に適用されます。 Azure Sentinel は、管理者に次のようなソリューションを提案します。

> [!NOTE]
> Azure Sentinel の概要 [この記事](/azure/sentinel/overview) は、まさにその通りです。

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Sentinel および Microsoft Teams のアクティビティ ログ

この記事では、Azure Sentinel でチーム アクティビティ ログを収集する方法について説明します。

Sentinel では、管理者は 1 つの場所でセキュリティ管理を行います。 これには次の管理が含まれます。

- サード パーティ製デバイス
- Microsoft Threat Protection
- Microsoft 365 ワークロード

Sentinel ブックと Runbook を使用すると、セキュリティ監視を *体系的* に行うことができます。 このプロセスの最初の手順として、分析に必要なログを収集します。

> [!NOTE]
> 複数の Microsoft 365 サブスクリプションは、Azure Sentinel の同じインスタンスに表示できます。 これにより、[リアルタイム監視](/azure/sentinel/livestream) および履歴ログ ファイルでの脅威の検索ができるようになります。 管理者は、1つのリソース グループ内もしくはリソース グループ間、または別のサブスクリプションで、[クロス リソース クエリ](/azure/azure-monitor/log-query/cross-workspace-query) を使用して検索できます。

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a>手順 1: Teams のログを収集する: Microsoft 365 で監査ログを有効にする

Teams は Microsoft 365 経由でアクティビティを記録するため、監査ログは既定では収集されません。 この機能を有効にするには、[次の手順](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) を実行します。 Teams のデータは、*Audit.General* 下にある Microsoft 365 監査で収集されます。

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a>手順 2: Office 365 のログを Azure Sentinel に接続する

Azure Sentinel には、Office 365 のログ用のコネクタが組み込まれており、Teams データを他の Office 365 データと共に Azure Sentinel に取り込むことができます。
 
Azure Sentinel で、Office 365 データ コネクタを有効にする。 詳細については、「[Azure Sentinel のドキュメント](/azure/sentinel/connect-office-365)」を参照してください。

## <a name="helpful-hunting-kql-queries"></a>KQL クエリの役に立つ検索

これらのクエリを使用すると、Teams データとTeams 環境を理解できます。 疑わしいアクティビティを認識するには、最初の手順として環境がどのように見え、どのように振る舞うべきかを理解することをお勧めします。 そこから、スレッド ハンティングに進出することができます。

### <a name="federated-external-users-query"></a>フェデレーション外部ユーザー クエリ

フェデレーション外部ユーザーを有する Teams サイト リストを取得します。 これらのユーザーは、組織によって所有されていないドメイン名および/または UPN サフィックスを持っています。

この例のクエリでは、組織が contoso.com. を所有しています。

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
> Teams における外部アクセスおよびゲスト アクセスの種類の詳細については、「[別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」 または Teams セキュリティ ガイドの「[参加者の種類](teams-security-guide.md#participant-types)」セクションを参照してください。

### <a name="who-recently-joined--whose-role-changed"></a>最近参加した、または役割を変更したユーザー

特定のユーザーに問い合わせて、過去 7 日間または 1 週間以内に、Teams チャネルに追加されたかどうかを確認することができます。

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

過去 7 日間にチームのユーザーの役割が変更されたかどうかをクエリします。

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a>不明または新しい組織からの外部ユーザー

Teams では、環境やチャネルに外部ユーザーを追加できます。 多くの場合、組織では、キーとなるパートナーシップの数が限られています。また、これらのパートナーの中からユーザーを追加します。 このKQLは、チームに追加された外部ユーザーが、以前に表示または追加されていない組織から来ているかどうかを見ています。

詳細については、「[Azure Sentinel コミュニティ git ハブ](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml)」のクエリを参照してください。

### <a name="external-users-who-were-added-and-then-removed"></a>追加され、後に削除された外部ユーザー

ある程度の既存アクセス権を持つ攻撃者は、Teams 新しい外部アカウントを追加して、データにアクセスしたり、データを流出させたりする可能性があります。 また、アクセスしたことを隠すために、当該ユーザーをすぐに削除してしまう可能性もあります。 このクエリは、Teams に追加された外部アカウントを検索し、疑わしい動作を特定するために迅速に削除します。

詳細については、「[Azure Sentinel コミュニティ git ハブ](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml)」のクエリを参照してください。

### <a name="new-bot-or-application-added"></a>新しい bot またはアプリケーションが追加されました

Teams にはチームにアプリまたはボットを含め、機能セット (カスタム アプリやボットを含む) を拡張できます。 場合によっては、アプリまたはボットを使用して、ユーザー アカウントを必要とせずに Teams 内で *永続化* でき、ファイルやその他のデータにアクセスできます。 このクエリは、チームに新たに追加されたアプリや bot を検索します。

詳細については、「[Azure Sentinel コミュニティ git ハブ](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml)」のクエリを参照してください。

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>多数のチームの所有者であるユーザー アカウント

権限の昇格を考える攻撃者は、多数の色々なチームに所有者特権を自身に割り当てる場合があります。 *通常*、ユーザーは特定のトピックに関するいくつかのチームを作成して所有します。 この KQL クエリは不審な動作を検索します。

詳細については、「[Azure Sentinel コミュニティ git ハブ](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml)」のクエリを参照してください。

### <a name="many-team-deletions-by-a-single-user"></a>1人のユーザーによる多くのチームの削除

攻撃者は、複数のチームを削除することで、プロジェクトやデータを混乱させたり、危険にさらしたりする可能性があります。 通常、チームは個人の所有者によって削除されているため、多くのチームを中心に削除されている場合は、問題の徴候になる可能性があります。 この KQL は、複数のチームを削除するユーザーを検索します。

詳細については、「[Azure Sentinel コミュニティ git ハブ](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml)」のクエリを参照してください。

### <a name="expanding-your-threat-hunting-opportunities"></a>サイバー攻撃の検索の機会を拡大する

Azure Active Directory (Azure AD) などのリソースや他の Office 365 ワークロードからのクエリを組み合わせて、 Teams のクエリで使用することができます。 たとえば、Azure AD SigninLogs で疑わしいパターンの検出を組み合わせて、チーム所有者を探している間にその出力を使用します。

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

また、Teams ベースのログオンのみのフィルターを追加することで、Teams 固有の SigninLogs の検出を行うことができます。

```Kusto
| where AppDisplayName has 'Teams'
```

*AppDisplayName にチームがある場所* の使用についてさらに説明するために、下に表示されている KQL の例では、1つの IP アドレスからのログオンに成功し、異なる IP アドレスからは失敗していますが、Teams のサインインに *のみ* 適用されます。

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

## <a name="important-information-and-updates"></a>重要な情報と更新プログラム

**Pete Bryan、Nicholas DiCola、および Matthew Lowe によるコンテンツの共同作業に感謝します。** Pete Bryan および彼と共同作業している人は、Teams の検出クエリと検索クエリを開発し続けています。

更新に関しては、[Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) リポジトリと連絡を取り合ってください。

この記事で使用している[パーサー](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)および[ロジック アプリ](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)の更新プログラムに注意してください。

[Azure Sentinel コミュニティ](https://github.com/Azure/Azure-Sentinel/wiki)に参加して投稿する必要があります。 この記事に関するフィードバックを心よりお待ちしておりいますので、以下のフィードバック オプションをご利用ください。 ご利用ありがとうございます。

[Azure AD でアプリケーションを登録する](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[監査ログ検索を有効または無効にする](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[Azure Sentinel とは](/azure/sentinel/overview)
