---
title: チーム対象の階層を設定する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 大規模なチームセットにコンテンツを公開するように、組織内でチーム階層を設定する方法について説明します。
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f5398b4d657a1c709c660f6e463794c5f7415a14
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62405999"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>チーム対象の階層を設定する

チームのターゲット階層を設定すると、組織は大規模なチームセットにコンテンツを公開できます。 階層を対象とするチームでは、階層内のすべてのチームが相互に関連付けられている方法、どのユーザーがタスクを発行できるか、どのチームユーザーが公開するアクセス許可を持つのかを定義します。 組織に対してチームのターゲット階層が設定されていない限り、発行機能はすべてのユーザーに対して無効になります。 チームのターゲット階層を設定するには、階層を定義するファイルを作成し、それをTeamsにアップロードして組織に適用する必要があります。 スキーマがアップロードされると、Teams内のアプリで使用できるようになります。

> [!IMPORTANT]
> 最初のリリースでは、タスク アプリのみが階層型チームをサポートします。  組織にチームのターゲット階層を適用すると、タスク アプリで [タスクの発行](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) が可能になります。 Microsoft Teamsの他の領域にチームの階層は表示されません。

Teamsのタスク アプリで階層を表す方法の例を次に示します。 タスク リストを作成した後、発行チームのメンバーは、タスク リストを送信 (発行) する受信者チームを選択できます。 チームを選択する場合、発行チームは階層、属性、またはその両方の組み合わせによってフィルター処理できます。<br>

![タスクの発行のスクリーンショット。](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>用語

階層を移動する際には、次の用語が重要になります。 Teamsは **ノード** と呼ばれます。

* **ルート ノード** は、階層内の最上位のノードです。 この例では、Retail Communications はルート ノードです。
* **親ノード** と **子ノード** は、2 つの接続されたノード間のリレーションシップを表す用語です。 この例では、地区 01 はエリア 1 の子ノードです。
* 複数のレベルの子は **、子孫** と呼ばれます。 地区 01、ストア 01、ストア 03、ストア 07、地区 02、および第 03 地区はすべて、エリア 1 の子孫です。
* 子を持たないノードは **リーフ ノード** と呼ばれます。 これらは階層の下部にあります。
* **受信者チーム** は、公開する特定のコンテンツセットを受け取るために選択されたチームです。 リーフ ノードである必要があります。

## <a name="plan-your-hierarchy"></a>階層を計画する

階層を定義するスキーマを作成する前に、いくつかの計画を立て、組織を形成する方法を決定する必要があります。  最初の優先順位の 1 つは、タスクを他のグループに発行する必要がある組織グループを決定することです。 階層内の各ノードは、作業グループまたはグループのグループを表します。

### <a name="permissions-to-publish"></a>発行するアクセス許可

公開するアクセス許可は、ユーザーが階層内の任意のチームのメンバーであるかどうかに加えて、そのチームまたは階層内の他のチームとの一連のチームの関係に依存します。

> [!NOTE]
> チームの所有者には、公開アクセス許可も付与されます。

* ユーザーが階層内に子孫を持つ少なくとも 1 つのチームのメンバーである場合、そのユーザーは、公開対象のすべてのチームのメンバーでなくても、それらの子孫に発行できます。
* ユーザーが階層内の少なくとも 1 つのチームのメンバーであり、階層内の子孫を持つチームのメンバーでない場合、そのユーザーは組織から発行されたコンテンツを表示および受信できます。
* ユーザーが階層内のどのチームのメンバーでもない場合、そのユーザーには発行関連の機能は表示されません。

### <a name="guidelines"></a>ガイドライン

* 組織ごとに適用できる階層ファイルは 1 つだけです。 ただし、組織のさまざまな部分を、1 つのファイル内のノードの個別の階層としてまとめて含めることができます。 たとえば、Contoso Pharmaceuticals には、ファーマシー ルート ノードと Retail ルート ノードがあります。 両方のルート ノードに複数の子孫行があり、それらの間に重複はありません。
* パブリケーションの受信者にできるのはリーフ ノードのみです。 階層内の他のノードは、パブリケーションの受信者を選択するのに役立ちます。
* チームを表すことができるのは、階層内で 1 回のみです。
* 階層には、最大 15,000 個のノードを含めることができます。 大規模な組織向けにこの制限を引き上げるため、お客様と協力する予定です。

### <a name="example-hierarchy"></a>階層の例

たとえば、次の階層では、Recall、Communications、HR は階層内のすべての下位ノード (チーム) にタスクを発行できますが、北東ゾーンではタスクをニューヨーク ストアとボストン ストアのチームにのみ発行できます。 この階層例を使用すると、リコール、通信、人事グループは、利益情報や CEO からのメッセージなど、会社全体に適用されるタスクを公開できます。 北東ゾーンでは、人員のスケジュール設定、気象情報などのタスクを公開できるのは、ニューヨーク ストアチームとボストン ストア チームのみです。

![チーム階層の例。](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>階層を作成する

> [!NOTE]
> この記事の残りの部分では、タスクを受信者チームに公開するコンテキストでチーム階層を設定する方法について説明します。 タスク アプリの概要については、「[Teamsで組織のタスク アプリを管理](./manage-tasks-app.md)する」を参照してください。タスクの発行が有効になっている場合に表示されます。

階層を定義するスキーマは、コンマ区切り値 (CSV) ファイルに基づいています。 ファイルは UTF-8 形式である必要があります。 CSV ファイル内の各行は、チームの階層内の 1 つのノードに対応します。 各行には、階層内のノードに名前を付ける情報、必要に応じてチームにリンクする情報、およびそれをサポートするアプリでチームをフィルター処理するために使用できる属性が含まれています。

**また、バケット** を定義することもできます。これは、発行チームが受信者チームに送信されたコンテンツを整理して、関連するコンテンツを表示、並べ替え、集中しやすくするために使用できるカテゴリです。

### <a name="add-required-columns"></a>必要な列を追加する

CSV ファイルには、最初の列から始まる次の 3 つの列が次の順序で含まれている必要があります。 タスクを受け取るには、ノードをチームにリンクする必要があります。

| 列名   | 必須 | 説明   |
----------------|----------|---------------|
| DisplayName    | Yes      | このフィールドは、ノードの名前です。 名前には最大 100 文字まで指定でき、A~Z、a-z、および 0 から 9 の文字のみを含めます。 ノード名は一意である必要があります。 |
| ParentName    | Yes       | これは親ノードの名前です。 ここで指定する値は、親ノードの **DisplayName** フィールドの値と正確に一致する必要があります。 複数の親ノードを追加する場合は、各親ノード名をセミコロン (;)で区切ります。 最大 25 個の親ノードを追加でき、各親ノード名は最大 2500 文字まで追加できます。 ノードは、親ノードがルート ノードである場合にのみ、複数の親ノードを持つことができます。   <br><br>**大事な** 階層の上位の親が階層内の下位の子ノードを参照するループを作成しないように注意してください。 これはサポートされていません。 |
| TeamId        | はい。チームがタスクを発行するか、親ノードからタスクを受け取る場合       | これには、ノードをリンクするチームの ID が含まれます。 各ノードは一意のチームを参照する必要があるため、各 TeamId 値は階層ファイルに 1 回しか表示されません。 ノードをリンクするチームの ID を取得するには、次の PowerShell コマンドを実行します `Get-Team | Export-Csv TeamList.csv`。 このコマンドは、組織内のチームを一覧表示し、各チームの名前と ID を含めます。 リンク先のチームの名前を見つけて、このフィールドに ID をコピーします。|

> [!NOTE]
> ノードがルート ノードまたはリーフ ノードではなく、発行とレポートに対応するアクセス許可を付与するためにチーム メンバーシップが必要ない場合は、TeamId を空白のままにできます。 この方法を使用すると、受信者チームを選択するときに、または対応するチームを持たずに完了レポートを表示する際に、より細かい粒度を追加できます。

### <a name="add-attribute-columns"></a>属性列を追加する

必要な 3 つの列を追加した後、省略可能な属性列を追加できます。 これらの属性を使用してノードをフィルター処理し、タスクを発行するノードをより簡単に選択できます。 属性の値が相互に排他的かどうかに応じて、属性を定義する方法は 2 つあります。

|属性を追加する方法|説明 |例  |
|---|---------|---------|
|属性の値が相互に排他的な場合は、指定した列名が属性の名前になります。|各行にはその属性に 1 つの値を含めることができます。各属性列には最大 50 個の一意の値を指定できます。 各値の長さに最大 100 文字を指定できます。 属性列に指定した属性値のセットは、チームのターゲット階層を使用して受信者チームを選択すると、その属性のフィルター値として表示されます。|ユーザーがレイアウトでストアをフィルター処理できるようにする必要があります。 この属性の値は、ストアに 1 つのレイアウトしか含めないため、相互に排他的です。 <br><br>レイアウトでストアをフィルター処理する属性を追加するには、Store layout という名前の列を追加します。 この例では、Store レイアウト属性の値は Compact、Standard、Large です。
|属性に複数の値を指定する必要があり、値が相互に排他的でない場合は、列名に **AttributeName:UniqueValue** 形式を使用します。 <br><br>**大事な** 必ず英語専用コロン (:)unicode は属性列区切り記号としてサポートされていません。 |コロンの前のテキスト文字列 (:)は属性の名前になります。 コロンの前に同じテキスト文字列を含むすべての列 (:)は、フィルター 処理メニューのセクションにグループ化されます。 コロンの後の各文字列は、そのセクションの値になります。<br><br>各行には、その属性に対して 0 (ゼロ) または 1 の値を指定できます。 値 0 は、属性がノードに適用されないことを意味し、値 1 は属性がそのノードに適用されることを意味します。|ユーザーが部署別にストアをフィルター処理できるようにする必要があります。 ストアには複数の部署を含めることができるため、この属性の値は相互に排他的ではありません。<br><br>この例では、Departments:Clothing、Departments:Electronics、Departments:フーズ、Departments:Home and Garden、Departments:Sporting goods を属性列として追加します。 部門は属性名になり、ユーザーは服、エレクトロニクス、食品、家庭と園、スポーツの各部門でフィルター処理できます。|

属性列を追加するときは、次の点に注意してください。

* 指定する列名、またはコロンの前に指定した列名 (:)は属性の名前になります。 この値は、階層を使用するTeams アプリに表示されます。
* 階層には最大 50 個の属性列を含めることができます。
* 列名には最大 100 文字まで指定でき、A~Z、a-z、および 0 から 9 の文字とスペースのみが含まれます。 列名は一意である必要があります。

### <a name="add-bucket-columns"></a>バケット列を追加する

バケット列を追加してバケットを作成できます。これは、タスクを整理できるグループです。 各バケットは、CSV ファイル内の独自の列を取得します。 作成するバケットは、発行チームが使用できるようになります。 その後、発行チームはこれらのバケットを使用して、受信者チームのタスクを分類できます。 チームにバケットがまだ存在しない場合は、タスクが発行されたときにオンデマンドでバケットが作成されます。

作業項目を一元的に分類することで、発行チームは、タスク リストを受け取る数十、数百、または数千の受信者チームのタスク リストを事前に整理できます。 その後、受信者チームは、タスクをバケット別に並べ替えてフィルター処理し、作業に最も関連する領域に焦点を当てることができます。

バケット列を追加するときは、次の点に注意してください。

* 列名がバケットの名前になります。 指定した各バケットは、階層を使用するTeams アプリの [バケット] 一覧に表示されます。
* バケット名に機密情報を含めないことをお勧めします。 現時点では、発行チームは作成後に発行を通じてバケットを削除することはできません。
* 列名の前にハッシュタグ (#)を付ける必要があります。 最大 100 文字の長さにすることができ、A~Z、a-z、および 0 から 9 の文字のみを含めることができます。 たとえば、商品の#Operationsと#Frozenなどです。
* 階層には、最大 25 個のバケット列を含める場合があります。 大規模な組織向けにこの制限を引き上げるため、お客様と協力する予定です。

### <a name="example"></a>例

前の図に示した階層をサポートするために作成されるスキーマ CSV ファイルの例を次に示します。 このスキーマには、次のものが含まれています。

* 、`ParentName`、、という名前`TargetName`の 3 つの必須列`TeamId`
* 、`Departments:Clothing`、、という名前`Store layout`の 3 つの属性列`Departments:Foods`
* 、`Frozen Foods`、、という名前`Fresh Foods`の 3 つのバケット列`Women's Wear`

この`Store layout`属性には、 を`Standard`含む`Compact`値があります`Large`。 属性列は `Departments` 、値 `0` (ゼロ) または `1`. レイアウトと`Departments`属性は`Store`、上の図には表示されません。 ノード エントリに属性を追加する方法を示すために、ここに追加されています。 3 つのバケット列についても同様です。

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

> [!NOTE] 
> この手順を実行するには、PowerShell ギャラリーからTeams PowerShell パブリック プレビュー モジュールをインストールして使用する必要があります。 モジュールをインストールする手順については、「PowerShell Teamsインストールする」を参照してください。

> [!NOTE]
> Government Community Cloud (GCC) のお客様は、パブリック クラウド環境ではなく、GCC環境にデータがルーティングされるように、[コマンドレット プレビュー バージョン 2.4.0 以降](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview)を使用する必要があります。

スキーマ CSV ファイルで階層を定義したら、それをTeamsにアップロードする準備が整いました。 これを行うには、次のコマンドを実行します。 この手順を実行するには、グローバル管理者またはTeamsサービス管理者である必要があります。

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>階層を更新する

上記と同じ PowerShell コマンドを使用して、古い階層を置き換えるために新しい階層をアップロードできます。 新しい階層をアップロードするたびに、前の階層が置き換えられます。

### <a name="check-the-status-of-your-hierarchy"></a>階層の状態を確認する

次のコマンドを実行して、階層のアップロードの状態を確認できます。

```powershell
Get-TeamTargetingHierarchyStatus
```

このコマンドは、次のフィールドを返します。

フィールド|説明
-----|------------
ID | アップロードの一意の ID。
ステータス | アップロード状態。 値には、 **開始**、 **検証**、 **成功**、 **失敗などがあります。**
ErrorDetails | アップロード エラーが発生した場合の詳細。 エラーの詳細については、「トラブルシューティング」セクションを参照してください。 エラーがない場合、このフィールドは空白です。
LastUpdatedAt | ファイルが最後に更新されたタイムスタンプと日付。
LastModifiedBy | ファイルを変更した最後のユーザーの ID。
FileName | CSV のファイル名。

## <a name="remove-your-hierarchy"></a>階層を削除する

組織内のすべてのユーザー **の [発行済みリスト** ] タブをすぐに無効にする場合は、階層を削除できます。 ユーザーは、[ **発行済みリスト** ] タブやタブの機能にアクセスできません。 これには、発行する新しいタスク リストの作成、下書きリストへのアクセス、発行、非公開、重複リストの表示、およびレポートの表示を行う機能が含まれます。 階層を削除しても、以前に発行されたタスクは公開されません。 これらのタスクは、受信者チームが完了するために引き続き使用できます。

階層を削除するには、次のコマンドを実行します。 この手順を実行するには、管理者である必要があります。

```powershell
Remove-TeamTargetingHierarchy
```

削除を確認すると、前のスキーマが存在する状態メッセージが引き続き表示されますが、もう一度削除しようとすると、オブジェクトが null であるというエラーが返されます。

## <a name="create-a-sample-hierarchy"></a>サンプル階層を作成する

### <a name="install-the-teams-powershell-module"></a>Teams PowerShell モジュールをインストールする

> [!IMPORTANT]
> この手順を実行するには、PowerShell ギャラリーからTeams PowerShell パブリック プレビュー [モジュールをインストール](https://www.powershellgallery.com/packages/MicrosoftTeams/)して使用する必要があります。 モジュールをインストールする手順については、「[PowerShell Teamsインストール](teams-powershell-install.md)する」を参照してください。

### <a name="sample-script"></a>サンプル スクリプト

次のスクリプトを使用して、チームを作成し、Microsoft Teams テナントに.csv ファイルをアップロードできます。 既存の階層がある場合は、このスクリプトによって置き換えられます。

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

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>チーム データを使用してコンマ区切り出力を作成する (DisplayName、ParentName、TeamId)

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

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>[ **ダウンロード** ] フォルダーの.csv ファイルに出力を保存する

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>階層をアップロードする

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="how-to-view-error-details"></a>エラーの詳細を表示する方法

次のコマンドを実行して、エラーの原因を把握し、エラーの詳細を返すことができます。

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>スキーマ CSV ファイルをアップロードすると、エラー メッセージが表示される

スキーマをアップロードできなかった理由を示すトラブルシューティング情報が含まれている必要があるため、エラー メッセージをメモしておきます。 エラー メッセージの情報に基づいてスキーマ CSV ファイルを確認して編集してから、もう一度やり直してください。

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>スキーマ CSV ファイルをアップロードすると、"Error: InvalidTeamId" というエラー メッセージが表示される

スキーマ CSV ファイルをアップロードしようとすると、次のエラー メッセージが表示されます。

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

スキーマ CSV ファイルでチームに対して正しい TeamId を使用していることを確認します。 TeamId は、チームをバックアップするMicrosoft 365 グループのグループ ID と同じである必要があります。 Microsoft Teams管理センターでチームのグループ ID を検索できます。

1. [Microsoft Teams管理センター](https://admin.teams.microsoft.com/)の左側のナビゲーションで、**Teams** >  **Manage チーム** に移動します。
2. テーブルに **[グループ ID** ] 列が表示されない場合は、テーブルの右上隅にある [ **列の編集]** を選択し、 **グループ ID** をオンにします。
3. 一覧でチームを検索し、グループ ID を見つけます。

スキーマ CSV ファイル内の TeamId が、Microsoft Teams管理センターに表示されているグループ ID と一致していることを確認します。

## <a name="related-topics"></a>関連項目

* [Teamsで組織のタスク アプリを管理する](manage-tasks-app.md)
* [Teams での PowerShell の概要](teams-powershell-overview.md)
