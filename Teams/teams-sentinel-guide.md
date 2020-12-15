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
ms.openlocfilehash: 6aa8e733aeb3828bb1815001ba0299a9ee1aaf78
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852148"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel および Microsoft Teams

Teams は、Microsoft 365 クラウドでの通信とデータ共有の両方の中心的な役割を担います。 Teams サービスはクラウド内の多くの基になっているテクノロジを使用しているので、*ログの捜索* を行う場合だけではなく *会議をリアルタイムで監視* する場合も手動分析および自動分析を利用することができます。 Azure Sentinel は、管理者に次のようなソリューションを提案します。

> [!NOTE]
> Azure Sentinel の概要 [この記事](https://docs.microsoft.com/azure/sentinel/overview) は、まさにその通りです。

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Sentinel および Microsoft Teams のアクティビティ ログ

この記事では、Azure Sentinel でチーム アクティビティ ログを収集する方法について説明します。 管理者は、Sentinel のワークブックおよびランブックがセキュリティ監視を体系的に行うことで、セキュリティ管理を一枚のガラスの下に置くことができます （選択したサード パーティ製のデバイス、Microsoft Threat Protection、およびその他の Microsoft 365ワークロードを含む）。 このプロセスの最初の手順として、分析に必要なログを収集します。

> [!NOTE]
> 複数の Microsoft 365 サブスクリプションは、Azure Sentinel の同じインスタンスに表示できます。 これにより、[リアルタイム監視](https://docs.microsoft.com/azure/sentinel/livestream) および履歴ログ ファイルでの脅威の検索ができるようになります。 管理者は、1つのリソース グループ内もしくはリソース グループ間、または別のサブスクリプションで、[クロス リソース クエリ](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query) を使用して検索できます。

## <a name="step-1-collect-teams-logs"></a>ステップ 1: チームログを収集する

このセクションには、3つの部分があります。

1. **Microsoft 365** (M365) で監査ログを有効にします。
2. **Microsoft Azure** にアプリを登録して、認証とログ収集の承認を許可します。
3. **PowerShell** 経由で、M365 API を使用してログ収集を許可する API サブスクリプションを登録します。

### <a name="enable-audit-logs-in-m365"></a>M365 で監査ログを有効にする

Teams は M365 経由でアクティビティを記録するため、監査ログは既定では収集されません。 この機能を有効にするには、[次の手順](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0) を経由します。 Teams のデータは、*Audit.General* 下の M365 audit に収集されます。

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a>ログ収集用 Microsoft Azure にアプリを登録する

> [!TIP]
> 作業を開始する前に、後で使用するための **アプリケーション IDまたはクライアント ID** および **テナント ID** を記録する必要があります。 これらの情報は、次のアプリの登録手順を順番に行うため、必ずキャプチャしてください。 両方の ID が表示されます。
>- アプリが作成されたら、クイック起動のサイド バーにある [アプリの登録] をクリックし、新しいアプリの表示名を検出して、[アプリケーション (クライアント) ID をコピーします。
>- クイック起動のサイド バーにある [概要] をクリックして、ディレクトリ (テナント) ID をコピーします。

Azure Active Directory (Azure AD) アプリを認証し、API からログ データを収集することを承認します。

1. Azure ポータルで *Azure AD* ブレードに移動します。
2. クイック起動サイド バーにある *[アプリを登録]* をクリックします。
3. *[新規登録]* を選択します。
4. Teams ログ収集アプリの名前を入力し、*[登録]* をクリックします。
5. このパスに沿ってクリックします : *API のアクセス許可* > *アクセス許可を追加* > *Office 365 Management APIs* > *Application のアクセス許可*。
6. [アクティビティ フィード] を展開し、 *[ActivityFeed.Read]* を確認します。
7. ここでは、*[全体管理者の同意]* を選びます。 確認メッセージが表示されたら、[はい] をクリックします。
8. サイド バーの *[証明書と秘密]* > *[新規クライアント シークレット]* ボタンの順でクリックします。
9. [新規クライアント シークレット] ウィンドウで新規クライアント シークレットの説明を入力し、[有効期限] に [いいえ] を選択し、*[追加]* をクリックします。

> [!IMPORTANT]
> 新規クライアント シークレットを、新しく作成されたアプリの名前の下にあるパスワード マネージャーのエントリにコピーすることは、**[重要]** です。 Azure ブレード (*ブレード* はウィンドウの Azure 用語) を終了した後に、このシークレットを見に戻ることはできません。

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a>PowerShell で API を登録してチーム ログを収集する

セットアップの最後の手順では、ログ データを収集するために、API サブスクリプションを収集して登録します。 これを行うには、PowerShell REST を M365 管理アクティビティ API に呼び出します。

**アプリケーション (クライアント) ID**、新しい **クライアント シークレット**、**M365用の URL ドメイン**、および以下の PowerShell コマンドレットの **ディレクトリ (テナント) ID** 値を提供できるようにします。

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a>手順 2: チーム ログを取り込むための Sentinel プレイブックを展開する

Azure Sentinel プレイブック (ロジック アプリとも呼ばれます) を使用すると、収集した Teams データを Azure が取り込むことができます。 ロジック アプリは、Office 365 に対して、Azure Sentinel ワークスペースに書き込まれる監査データを検索します。

[この](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM テンプレートを使用して、Sentinel プレイブックを展開します。

留意すべき点がいくつかあります。

1. ARM テンプレートを通して、特定の値を使用している環境に適した値に置き換える必要があります。
2. ログを取り込んでから Azure Sentinel で結果を見るまでの時間を確保する必要があります。

   過去5分間のデータがない場合は、5 ～ 10 分待ってから、エラーメッセージが表示されます。 監査ログを確認し、Teams の情報は監査に含まれていることに注意してください。Teams のログよりも多くの情報を収集する一般的なイベントでは、使用中のシステムで 5 ～ 10 分以内に結果が表示されます。 テキスト環境を使用している場合は、ログを生成するために Teams を使用してください。

![ロジック アプリ クラスを示すグラフィック。](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> グラフィックのアクションの説明: 
  </summary>

  •定期的なパターンは、ワークフローが1時間ごとに実行されるようにするロジック アプリ トリガーです。
  <p>
•現在の時刻のアクションは、非常に基本的で、現在の時刻だけを取得します。
  <p>
変数を初期化すると、NextPage という名前の変数が作成され、1に設定されます。 これは、O365 API のページネーションを処理するために、後で使用されます。
  <p>
•変数の初期化2は、開始時刻という空の変数を作成します。
  <p>
•クエリおよびリスト結果の実行は、ロジック アプリから最後に入力された O365 ログをワークスペースに問い合わせる Azure モニター アクションです。
  <p>
•条件4は、クエリの実行とリスト結果クエリが何かデータを返したかどうかを確認するために使用されます。 これは、ロジック アプリが初めて使われるかどうかを確認するために行われます。 データが返されない場合、StartTime 変数は Now ～ 24 時間に設定されています。 データが返される場合、StartTime は最終発生時間に設定されます。 これは、O365 API に対して、クエリが最後のエントリから今までの時点、またはそれが初めて実行された場合は、直近の24時間の時点までのデータを取得できるように行われます。
  <p>
•変数の初期化3は、「AvaibleUri」 という名前の変数を作成します。 これは、StartTime と CurrentTime を使用し、それぞれ開始時刻と終了時刻として作成された URL の文字列です。
  <p>
•Until 条件は、ロジック アプリが API にポーリングを継続して、データ (ページネーション) があるかどうかを確認するためのループです。 NextPage 変数が1の場合、ループは続行します。 この変数は、その後、取得するページが残っていない場合に更新されます。
  <p>
Until ループの内部では、最初の HTTP ステップが AvaibleUri に接続します。 この URI は、使用できるコンテンツと各コンテンツ URI のリストを返します。 この URL での操作方法については、https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content を参照してください。
  <p>
•次に、データが返されることを確認するためのチェックが実行されます。 本文の長さが0かどうかを調べます。 この場合、ログ分析に書き込むデータがありません。 値が0より大きい場合、処理するデータがあります。
  <p>
•データが検出された場合は、次に処理される必要があります。 JSON 解析は、返されるデータのスキーマを定義します。 これにより、ロジック アプリは、後の手順で、解析されたデータをダイナミック コンテンツとして使用できます。
  <p>
•返される使用可能なデータのリストは配列であるため、For Each アクションを使用して、使用可能なコンテンツのリストをループするために使用されます。
  <p>
•次は、コンテンツを取得します。  HTTP を再び使用して、contentUri (JSON 解析で作成された動的プロパティ) を取得します。これは、取得するデータの URL です。
  <p>
• JSON 解析は、返されるデータの解析にも使用されます。 この URL には、https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content のような、いくつかのサンプルコンテンツが含まれています。
  <p>
•返されるデータは、配列です。 ここでは、for each ループも使用できます。 このループでは、ワークフローは現在のデータ アイテムを取得し、[データの送信] アクションを使用して、ログ分析にデータを書き込みます。
  <p>
•使用可能なコンテンツは複数ページにわたる可能性があるので、NextPageUri が NULL ではないかどうかを確認します。 NULL か空白の場合、NextPage は0に設定され、Until ループを終了します。 URL が含まれている場合は、その URL に AvaibleUri 変数が更新されます。 この方法では、Until ループの次の実行時には、開始 URL ではなく、次に利用可能な URL が使用されます。

  </details>

> [!TIP]
> 代わりに、*Azure 関数* を使用して、これらのログを取り込むことができます。その場合は、必要に応じて、展開方法についての詳細な説明は、[こちら](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) または [こちら](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp) にあります。

コネクタ (上記のいずれかのオプション) を実行すると、Azure Sentinel ワークスペースに O365API_CL と呼ばれるカスタム テーブルが表示されます。 Teams ログが作成されます。

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a>手順 3: Sentinel を使用して Microsoft Teams を監視する

ID は、Microsoft Teams に関して言えば、監視すべき重要な攻撃ベクトルです。 Azure Active Directory (Azure AD) は、Teams を含む、Microsoft 365 ディレクトリの土台であり、Azure AD 認証ログの脅威の収集および検索を行うことにより、ID の不審な動作をキャプチャするのに役立ちます。 内蔵コネクタを使用して Azure AD データを Azure Sentinel に引き込み、これらの [検出](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) および [検索](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) クエリを使用して、問題を探すことができます。

Microsoft Teams に固有の攻撃、データへの脅威については、たとえば、Azure Sentinel にも、それらを監視して追い詰める手段があります。

### <a name="create-a-parser-for-your-data"></a>データのパーサを作成する

収集されたデータの集合を理解するために最初に行う必要がある作業は、それを解析して意味づけすることです。 これは、データを簡単に使用できるようにする Kusto Query 言語 (KQL) 関数で実行されます。

> [!NOTE]
> KQL 関数は、「関数」と呼ばれるデータ型で保存された KQL クエリです。 KQL 関数には、Sentinel のクエリ ボックスに入力できるエイリアスがあるので、クエリをすばやく再実行できます。 KQL 関数の詳細とパーサ関数の作成方法の詳細については、[この技術コミュニティの記事](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381) を参照してください。
 
 以下のパーサは、*Teams* に関連する Office 365 Management API フィールドの一部を選択することを目的とした、カスタマイズ可能な例です。 また、パーサ [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) も提案されていますが、以下のパーサを変更して、さまざまなニーズや必要に合わせて変更できます。

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 このパーサを KQL 関数として、Teams データのエイリアスとして保存します。 これは、後に続くクエリに使用されます。 KQL 関数をパーサとして構成および使用する方法の詳細については、こちらの [技術コミュニティの記事](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381) を参照してください。

## <a name="helpful-hunting-kql-queries"></a>KQL クエリの役に立つ検索

これらのクエリを使用すると、Teams データとTeams 環境を理解できます。 疑わしいアクティビティを認識するには、最初の手順として環境がどのように見え、どのように振る舞うべきかを理解することをお勧めします。 そこから、スレッド ハンティングに進出することができます。

#### <a name="federated-external-users-query"></a>フェデレーション外部ユーザー クエリ

フェデレーション外部ユーザーを有する Teams サイト リストを取得します。 これらのユーザーは、組織によって *所有されていない* ドメイン名または UPN サフィックスが割り当てられます。 この例のクエリでは、組織が contoso.com. を所有しています。

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> Teams における外部アクセスおよびゲスト アクセスの種類の詳細については、[この記事](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations) または [Teams セキュリティ ガイド](https://docs.microsoft.com/microsoftteams/teams-security-guide) の *参加者の種類* セクションを参照してください。

#### <a name="who-recently-joined--whose-role-changed"></a>最近参加した、または役割を変更したユーザー

特定のユーザーに問い合わせて、過去7日間または1週間以内に、Teams チャネルに追加されたかどうかを確認することができます。

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

過去7日間にチームのユーザーの役割が変更されました。

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a>不明または新しい組織からの外部ユーザー

Teams では、環境やチャネルに外部ユーザーを追加できます。 多くの場合、組織では、キーとなるパートナーシップの数が限られています。また、これらのパートナーの中からユーザーを追加します。 このKQLは、チームに追加された外部ユーザーが、以前に表示または追加されていない組織から来ているかどうかを見ています。

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a>追加され、後に削除された外部ユーザー

ある程度の既存アクセス権を持つ攻撃者は、Teams 新しい外部アカウントを追加して、データにアクセスしたり、データを流出させたりする可能性があります。 また、アクセスしたことを隠すために、当該ユーザーをすぐに削除してしまう可能性もあります。 このクエリは、Teams に追加された外部アカウントを検索し、疑わしい動作を特定するために迅速に削除します。

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a>新しい bot またはアプリケーションが追加されました

Teams では、機能セットを拡張するためのアプリや bot をチームに含めることができます。 これには、カスタム アプリと bot が含まれます。 場合によっては、アプリまたは bot を使用して、ユーザー アカウントや、アクセス ファイル、その他のデータを必要とせずに、Teams の永続性を確立できます。 このクエリは、チームに新たに追加されたアプリや bot を検索します。

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>多数のチームの所有者であるユーザー アカウント

通常、ユーザーは特定のトピックについて少数のチームを作成して所有していますが、権限を高めようとする攻撃者は、多くの異なるチームの所有者権限を割り当てようとする可能性があります。 この KQL クエリは不審な動作を検索します。

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a>1人のユーザーによる多くのチームの削除

攻撃者は、複数のチームを削除することで、プロジェクトやデータを混乱させたり、危険にさらしたりする可能性があります。 通常、チームは個人の所有者によって削除されているため、多くのチームを中心に削除されている場合は、問題の徴候になる可能性があります。 この KQL は、複数のチームを削除するユーザーを検索します。

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a>スレッド ハンティングの機会を広げる

Azure Active Directory (Azure AD) などのリソースや他の Office 365 ワークロードからのクエリを Teams のクエリと組み合わせることで、ハンティングを拡大することができます。 一例として、Azure AD SigninLogs の疑わしいパターンの検出を組み合わせて、チーム オーナーを探している間にその情報を使用しています。

```kusto
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
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

また、Teams ベースのサインインのみのフィルターを追加することで、Teams 固有の SigninLogs の検出を行うことができます。

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

`where AppDisplayName starts with "Microsoft Teams"` をさらに使用する方法について、以下の KQL の例では、1つの IP アドレスからのログオンに成功し、異なる IP アドレスからは失敗していますが、Teams のサインインにのみ適用されます。

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
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

**Pete Bryan、Nicholas DiCola、および Matthew Lowe によるコンテンツの共同作業に感謝します。** Pete Bryan や共同作業を行っているユーザーは、チームの検出や検索のクエリを引き続き開発します。そのため、この [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) リポジトリで更新プログラムをチェックできます。  この記事で使用している [パーサー](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) および [ロジック アプリ](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) の更新プログラムを監視します。 [Azure Sentinel コミュニティ](https://github.com/Azure/Azure-Sentinel/wiki) に参加して投稿することもできます。 ご協力ありがとうございます。 良い検索を。

[Azure AD でアプリケーションを登録する](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[監査ログ検索を有効または無効にする](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[Azure Sentinel とは](https://docs.microsoft.com/azure/sentinel/overview)
