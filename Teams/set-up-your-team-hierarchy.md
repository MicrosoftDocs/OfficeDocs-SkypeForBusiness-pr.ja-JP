---
title: チーム対象の階層を設定する
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 大規模なチーム セットにコンテンツを発行するために、組織内のチーム階層を設定する方法について学習します。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63a9cf6cab1bfb50c17c8546a65ad50e41759edc
ms.sourcegitcommit: f0e5da6136656261567ffe0fa3f2fedd901209a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "51891284"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>チーム対象の階層を設定する

チームのターゲット階層を設定すると、組織は大規模なチーム セットにコンテンツを発行できます。 階層を対象とするチームは、階層内のすべてのチームが互いに関連する方法、タスクを発行できるユーザー、およびユーザーが公開するアクセス許可を持つチームを定義します。 組織に対してチームのターゲット階層が設定されていない限り、すべてのユーザーに対して公開機能が無効になります。 階層を対象とするチームを設定するには、階層を定義するファイルを作成し、それを Teams にアップロードして組織に適用する必要があります。 スキーマがアップロードされると、そのスキーマ内のTeamsを使用できます。

> [!IMPORTANT]
> 最初のリリースでは、タスク アプリだけが階層型チームをサポートします。  組織にチームのターゲット階層を適用すると、タスク [アプリで](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) タスクを発行できます。 チームの他の領域にチームの階層が表示Microsoft Teams。

次に示すのは、階層がタスク アプリ内のタスク アプリでどのように表Teams。 タスク リストが作成されると、発行チームのメンバーは、タスク リストの送信 (発行) 先の受信者チームを選択できます。 チームを選択すると、発行チームは階層、属性、または両方の組み合わせでフィルター処理できます。<br>

![タスク発行のスクリーンショット](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>用語

階層間を移動する場合、次の用語が重要になります。 Teamsノードと呼 **ばれます**。

* **ルート ノード** は、階層内の最上位のノードです。 この例では、Retail Communications はルート ノードです。
* **親ノードと****子ノードは**、接続されている 2 つのノード間の関係を表す用語です。 この例では、District 01 は領域 1 の子ノードです。
* 複数のレベルの子は、子孫 **と呼ばれます**。 District 01、Store 01、Store 03、Store 07、District 02、District 03 はすべて、Area 1 の子孫です。
* 子がないノードはリーフ ノードと **呼ばれる。** 階層の一番下に表示されます。
* **受信者チーム** は、公開するコンテンツの特定のセットを受信するために選択されたチームです。 リーフ ノードである必要があります。

## <a name="plan-your-hierarchy"></a>階層を計画する

階層を定義するスキーマを作成する前に、計画を立て、組織の形成方法を決定する必要があります。  最初の優先順位の 1 つは、タスクを他のグループに発行する必要がある組織グループを決定する方法です。 階層内の各ノードは、作業グループまたはグループのグループを表します。

### <a name="permissions-to-publish"></a>発行するアクセス許可

公開するアクセス許可は、ユーザーが階層内の任意のチームのメンバーかどうかに加えて、そのチームまたは一連のチームと階層内の他のチームとの関係によって異なります。

> [!NOTE]
> チームの所有者には、発行アクセス許可も付与されます。

* ユーザーが階層内に子孫を持つ少なくとも 1 つのチームのメンバーである場合、そのユーザーは、公開したいすべてのチームのメンバーにならずに、それらの子孫に公開できます。
* ユーザーが階層内の少なくとも 1 つのチームのメンバーであり、階層内の子孫を持つチームのメンバーではない場合、そのユーザーは組織から公開されたコンテンツを表示および受信できます。
* ユーザーが階層内のチームのメンバーではない場合、そのユーザーには発行関連の機能は表示されません。

### <a name="guidelines"></a>ガイドライン

* 組織ごとに適用できる階層ファイルは 1 つのみです。 ただし、組織の異なる部分を 1 つの CSV ファイル内のノードの個別の階層として組み込むことができます。 たとえば、Contoso Pharmaceuticals には、Retail ルート ノードと Retail ルート ノードがあります。 どちらのルート ノードにも複数の子孫の行が含まれますが、その間に重複はありません。
* リーフ ノードのみを文書の受信者に指定できます。 階層内の他のノードは、文書の受信者を選択する場合に役立ちます。
* チームは、1 つの階層内で 1 回だけ表されます。
* 階層には、最大 15,000 ノードを含めできます。 大規模な組織では、お客様と協力してこの制限を引き上げる予定です。

### <a name="example-hierarchy"></a>階層の例

たとえば、次の階層では、リコール、コミュニケーション、人事は、階層内のすべての下位ノード (チーム) にタスクを発行できますが、北東部ゾーンはニューヨークストアチームとボストン ストア チームにのみタスクを発行できます。 この階層の例では、リコール、コミュニケーション、人事グループが、福利厚生情報や CEO からのメッセージなど、会社全体に適用されるタスクを発行できます。 北東部では、人員のスケジュール設定、気象情報など、ニューヨークのストア チームとボストン ストア チームにのみタスクを発行できます。

![チーム階層の例](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>階層を作成する

> [!NOTE]
> この記事の残りの部分では、受信者チームにタスクを発行するコンテキストでチーム階層を設定する方法について説明します。 有効にした[場合にタスク](./manage-tasks-app.md)発行が表示されるタスク アプリの概要については、「Teams で組織のタスク アプリを管理する」を参照してください。

階層を定義するスキーマは、コンマ区切り値 (CSV) ファイルに基づいて作成されます。 CSV ファイル内の各行は、チームの階層内の 1 つのノードに対応します。 各行には、階層内のノードに名前を付け、必要に応じてチームにリンクする情報が含まれます。また、それをサポートするアプリでチームをフィルター処理するために使用できる属性も含まれています。

バケット を定義することもできます。これは、発行チームが受信者チームに送信されるコンテンツを整理して、関連するコンテンツの表示、並べ替え、集中を容易にするために使用できるカテゴリです。

### <a name="add-required-columns"></a>必要な列を追加する

CSV ファイルには、最初の列から始まる次の 3 つの列を次の順序で含める必要があります。 タスクを受信するには、ノードをチームにリンクする必要があります。

| 列名   | 必須 | 説明   |
----------------|----------|---------------|
| DisplayName    | はい      | このフィールドはノードの名前です。 名前は最大 100 文字で、A ~ Z、a ~ z、および 0 ~ 9 の文字のみを含めることができます。 ノード名は一意である必要があります。 |
| ParentName    | はい       | これは親ノードの名前です。 ここで指定する値は、親ノードの **DisplayName** フィールドの値と正確に一致する必要があります。 複数の親ノードを追加する場合は、各親ノード名をセミコロンで区切;)。 最大 25 の親ノードを追加できます。各親ノード名は最大 2,500 文字です。 ノードは、親ノードがルート ノードである場合にのみ、複数の親ノードを持つ可能性があります。   <br><br>**重要** 階層内の上位の親が階層の下位にある子ノードを参照するループを作成しないように注意してください。 これはサポートされていません。 |
| TeamId        | はい (チームがタスクを発行するか、親ノードからタスクを受け取った場合)       | これには、ノードをリンクするチームの ID が含まれている。 各ノードは一意のチームを参照する必要があります。したがって、各 TeamId 値は階層ファイルに 1 回しか表示されません。 ノードをリンクするチームの ID を取得するには、次の PowerShell コマンドを実行します `Get-Team | Export-Csv TeamList.csv` 。 このコマンドでは、組織内のチームが一覧表示され、各チームの名前と ID が含まれます。 リンク先のチームの名前を見つけ、このフィールドに ID をコピーします。|

> [!NOTE]
> ノードがルート ノードまたはリーフ ノードで、発行とレポートに対応するアクセス許可を付与するためにチーム メンバーシップを必要としない場合は、TeamId を空白のままにすることができます。 この方法を使用すると、受信者チームを選択する際に細分性を高め、対応するチームがなくても完了レポートを表示できます。

### <a name="add-attribute-columns"></a>属性列を追加する

必要な 3 つの列を追加した後、オプションの属性列を追加できます。 これらの属性を使用してノードをフィルター処理し、タスクを発行する属性を簡単に選択できます。 属性を定義するには、その属性の値が相互に排他的かどうかに応じて、2 つの方法があります。

|属性を追加する方法|説明 |例  |
|---|---------|---------|
|属性の値が相互に排他的である場合、指定した列名は属性の名前になります。|各行にはその属性に対して 1 つの値を含め、各属性列には最大 50 の一意の値を含めることができます。 各値の長は最大 100 文字です。 属性列で指定した属性値のセットは、チームのターゲット階層を使用して受信者チームを選択すると、その属性のフィルター値として表示されます。|ユーザーがレイアウトでストアをフィルター処理できる必要がある。 この属性の値は相互に排他的です。これは、ストアにレイアウトを 1 つしか設定しないのでです。 <br><br>レイアウトでストアをフィルター処理する属性を追加するには、[ストア レイアウト] という名前の列を追加します。 この例では、Store レイアウト属性の値は、Compact、Standard、Large です。
|属性に対して複数の値を指定する必要があるが、値が相互に排他的でない場合は、列名に **AttributeName:UniqueValue** 形式を使用します。 <br><br>**重要** 必ず英語専用コロン (:)Unicode は属性列の区切り記号としてサポートされていません。 |コロンの前のテキスト文字列 (:)は属性の名前になります。 コロンの前に同じテキスト文字列を含むすべての列 (:)は、フィルター 処理メニューのセクションにグループ化されます。 コロンの後の各文字列が、そのセクションの値になります。<br><br>各行には、その属性に対して 0 (ゼロ) または 1 の値を指定できます。 値 0 は、属性がノードに適用されません。値 1 は、その属性がそのノードに適用されるという意味です。|ユーザーが部門別にストアをフィルター処理できる必要がある。 ストアには複数の部署を含め、この属性の値は相互に排他的ではありません。<br><br>この例では、属性列として、Departments:Clothing、Departments:Electronics、Departments:Foods、Departments:Home and Garden、Departments:Sporting goods を追加します。 部門は属性名になり、ユーザーは、ウェア、電子、食品、家庭および庭、スポーツ用品の各部門でフィルター処理できます。|

属性列を追加する場合は、次の注意が必要です。

* 指定した列名、またはコロンの前に指定する列名 (:)は属性の名前になります。 この値は、階層を使用Teamsアプリに表示されます。
* 階層には最大 50 の属性列を含めできます。
* 列名の長は最大 100 文字で、文字 A ~ Z、a - z、0 ~ 9、およびスペースのみを含めることができます。 列名は一意である必要があります。

### <a name="add-bucket-columns"></a>バケット列を追加する

バケット列を追加してバケットを作成できます。バケットは、タスクを整理できるグループ化です。 各バケットは、CSV ファイル内の独自の列を取得します。 作成したバケットは、発行チームが利用できます。 発行チームは、これらのバケットを使用して、受信者チームのタスクを分類できます。 バケットがチームにまだ存在しない場合は、タスクの発行時にオンデマンドでバケットが作成されます。

発行チームは、作業項目を一度に 1 回分類することで、タスク リストを受け取る数十、数百、または数千の受信者チームのタスク リストを事前に整理できます。 受信者チームは、バケットでタスクを並べ替え、フィルター処理して、作業に最も関連性の高い領域に集中できます。

バケット列を追加する場合は、次の点に注意してください。

* 列名はバケットの名前になります。 指定した各バケットは、階層を使用するアプリのTeamsリストに表示されます。
* バケット名には機密情報を含めすることをお勧めします。 現時点では、発行チームは、作成後に発行を通じてバケットを削除することはできません。
* 列名の前にハッシュタグ (#) が付く必要があります。 最大 100 文字まで指定できます。A ~ Z、a ~ z、および 0 ~ 9 の文字のみを含めることができます。 たとえば、商品#Operationsと#Frozenします。
* 階層には、最大 25 のバケット列を含めできます。 大規模な組織では、この制限を引き上げ、お客様と協力する予定です。

### <a name="example"></a>例

前の図に示した階層をサポートするために作成されるスキーマ CSV ファイルの例を次に示します。 このスキーマには、次の情報が含まれます。

* 、、および という名前 `TargetName` の 3 `ParentName` つの必須列 `TeamId`
* 、、および という名前 `Store layout` の 3 `Departments:Clothing` つの属性列 `Departments:Foods`
* 、、および という名前 `Fresh Foods` の 3 `Frozen Foods` つのバケット列 `Women's Wear`

属性 `Store layout` には、、、 を `Compact` 含む `Standard` 値があります `Large` 。 属性 `Departments` 列は、(ゼロ) または `0` の値に設定できます `1` 。 レイアウト `Store` と `Departments` 属性は、上の図には表示されません。 ここでは、ノード エントリに属性を追加する方法を示すのに役立ちます。 3 つのバケット列でも同じです。

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,125399ce-a761-4983-a125-3abc249037fc,,,,,,
East Regional Office,HR;Communications;Recall,,,,,,,
West Regional Office,HR;Communications;Recall,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a>階層を適用する

スキーマ CSV ファイルで階層を定義した後は、その階層をスキーマ CSV ファイルにアップロードTeams。 これを行うには、次のコマンドを実行します。 この手順を実行するには、グローバル管理者Teamsまたはサービス管理者である必要があります。

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>階層を更新する

上記と同じ PowerShell コマンドを使用して、古い階層を置き換える新しい階層をアップロードできます。 新しい階層をアップロードするごとに、前の階層が置き換まれます。

### <a name="check-the-status-of-your-hierarchy"></a>階層の状態を確認する

次のコマンドを実行して、階層のアップロードの状態を確認できます。

```powershell
Get-TeamTargetingHierarchyStatus
```

コマンドは、次のフィールドを返します。

フィールド|説明
-----|------------
ID | アップロードの一意の ID。
状態 | アップロード状態。 値には **、Starting、Validating、Successful、Failed****が含まれます。**  
ErrorDetails | アップロード エラーが発生した場合の詳細。 エラーの詳細については、「トラブルシューティング」セクションを参照してください。 エラーがない場合、このフィールドは空白です。
LastUpdatedAt | ファイルが最後に更新されたタイムスタンプと日付。
LastModifiedBy | ファイルを変更した最後のユーザーの ID。
FileName | CSV のファイル名。

## <a name="remove-your-hierarchy"></a>階層を削除する

組織内のすべてのユーザーの [発行済み **リスト]** タブをすぐに無効にする場合は、階層を削除できます。 ユーザーは、[発行済みリスト] **タブ** またはタブの機能にアクセスできます。 これには、新しいタスク リストを作成して、発行、下書きリストへのアクセス、発行、発行解除、重複リストの表示、レポートの表示を行う機能が含まれます。 階層を削除しても、以前に発行されたタスクは発行されません。 これらのタスクは、受信者チームが完了するために引き続き使用できます。

階層を削除するには、次のコマンドを実行します。 この手順を実行するには、管理者である必要があります。

```powershell
Remove-TeamTargetingHierarchy
```

削除を確認すると、前のスキーマが存在する状態メッセージが引き続き表示されます。ただし、もう一度削除しようとすると、オブジェクトが null であるというエラーが返されます。

## <a name="create-a-sample-hierarchy"></a>サンプル階層を作成する

### <a name="install-the-teams-powershell-module"></a>PowerShell モジュールTeamsインストールする

> [!IMPORTANT]
> この手順を実行するには、PowerShell ギャラリー から powerShell パブリック Teams モジュールをインストールして[使用する必要があります](https://www.powershellgallery.com/packages/MicrosoftTeams/)。 モジュールをインストールする手順については、PowerShell のインストールに関[するページTeams参照してください](teams-powershell-install.md)。

### <a name="sample-script"></a>サンプル スクリプト

次のスクリプトを使用して、チームを作成し、.csvをテナントにMicrosoft Teamsできます。 既存の階層がある場合は、このスクリプトによって置き換まれます。

#### <a name="create-teams-for-a-simple-hierarchy"></a>単純な階層のチームを作成する

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>チーム データを使用してコンマ区切りの出力 (DisplayName、ParentName、TeamId) を作成する

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>[ダウンロード] フォルダー.csvファイルに **出力を保存** する

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>アップロードを選択する

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="how-to-view-error-details"></a>エラーの詳細を表示する方法

次のコマンドを実行して、エラーの原因を把握し、エラーの詳細を返します。

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>スキーマ CSV ファイルをアップロードするときにエラー メッセージが表示される

エラー メッセージには、スキーマをアップロードできなかった理由を示すトラブルシューティング情報が含まれる必要があります。 エラー メッセージの情報に基づいてスキーマ CSV ファイルを確認して編集し、もう一度やり直してください。

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>スキーマ CSV ファイルをアップロードすると、"エラー: InvalidTeamId" というエラー メッセージが表示される

スキーマ CSV ファイルをアップロードすると、次のエラー メッセージが表示されます。

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

スキーマ CSV ファイルでチームに正しい TeamId を使用していることを確認します。 TeamId は、チームをバックアップするグループのグループ ID Microsoft 365同じである必要があります。 管理センターでチームのグループ ID をMicrosoft Teamsできます。

1. 管理センターの左側のナビゲーション [Microsoft Teams、[](https://admin.teams.microsoft.com/)チームの管理] にTeams  >  **移動します**。
2. [**グループ ID]** 列がテーブルに表示されない場合は、テーブルの右上隅にある [列の編集] を選択し、[グループ **ID] をオンにします**。
3. 一覧でチームを見つけ、グループ ID を見つける。

スキーマ CSV ファイルの TeamId が、管理センターに表示されるグループ ID と一致Microsoft Teams確認します。

## <a name="related-topics"></a>関連トピック

* [組織内のタスク アプリを管理Teams](manage-tasks-app.md)
* [Teams での PowerShell の概要](teams-powershell-overview.md)
