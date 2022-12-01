---
title: チーム対象の階層を設定する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 大規模なチームセットにコンテンツを公開するために、組織内のチーム階層を設定する方法について説明します。
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.openlocfilehash: 93b8b06238b0f6e15ab5fac5dcb0caeece819d9e
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198359"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>チーム対象の階層を設定する

チームターゲット階層を設定すると、組織は大規模なチームセットにコンテンツを公開できます。 チーム ターゲット階層では、階層内のすべてのチームが相互にどのように関連しているか、ユーザーがタスクを発行できるか、および発行するアクセス許可を持つチームが定義されています。 組織に対してチーム ターゲット階層が設定されていない限り、すべてのユーザーに対して発行機能が無効になります。 階層をターゲットとするチームを設定するには、階層を定義するファイルを作成し、それを Teams にアップロードして組織に適用する必要があります。 スキーマがアップロードされると、Teams 内のアプリで使用できます。

> [!IMPORTANT]
> 最初のリリースでは、タスク アプリのみが階層型チームをサポートします。  組織に階層をターゲットとするチームを適用すると、タスク アプリで [タスクの発行](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) が有効になります。 teams の他の領域には、チームの階層Microsoft表示されません。

Teams のタスク アプリで階層がどのように表されるかの例を次に示します。 タスク リストを作成した後、発行チームのメンバーは、タスク リストの送信先 (公開) 先の受信者チームを選択できます。 チームを選択する場合、発行チームは階層、属性、または両方の組み合わせでフィルター処理できます。<br>

![タスク発行のスクリーンショット](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>用語

階層を移動するときに、次の用語が重要になります。 Teams は **ノード** と呼ばれます。

* **ルート ノード** は、階層内の最上位ノードです。 この例では、Retail Communications はルート ノードです。
* **親ノード** と **子ノード** は、2 つの接続されたノード間の関係を表す用語です。 この例では、District 01 はエリア 1 の子ノードです。
* 複数のレベルの子は **子孫と呼** ばれます。 District 01、Store 01、Store 03、Store 07、District 02、District 03 はすべてエリア 1 の子孫です。
* 子を持たないノードはリーフ **ノード** と呼ばれます。 これらは階層の下部にあります。
* **受信者チーム** は、公開するコンテンツの特定のセットを受け取るために選択されたチームです。 リーフ ノードである必要があります。

## <a name="plan-your-hierarchy"></a>階層を計画する

階層を定義するスキーマを作成する前に、組織を形成する方法を計画して決定する必要があります。  最初の優先順位の 1 つは、他のグループにタスクを発行する必要がある組織グループを決定することです。 階層内の各ノードは、作業グループまたはグループのグループを表します。

### <a name="permissions-to-publish"></a>発行するアクセス許可

発行するアクセス許可は、ユーザーが階層内の任意のチームのメンバーに加えて、そのチームの関係、または階層内の他のチームとの一連のチームの関係によって異なります。

> [!NOTE]
> チームの所有者には、発行アクセス許可も付与されます。

* ユーザーが階層内に子孫を持つ少なくとも 1 つのチームのメンバーである場合、そのユーザーは、発行するすべてのチームのメンバーにならずに、それらの子孫に発行できます。
* ユーザーが階層内の少なくとも 1 つのチームのメンバーであっても、階層内に子孫を持つチームのメンバーではない場合、そのユーザーは、発行されたコンテンツを組織から表示および受信できます。
* ユーザーが階層内の任意のチームのメンバーでない場合、そのユーザーには発行関連の機能は表示されません。

### <a name="guidelines"></a>ガイドライン

* 1 つの組織に適用できる階層ファイルは 1 つだけです。 ただし、1 つのファイル内のノードの異なる階層として、組織のさまざまな部分を一緒に含めることができます。 たとえば、Contoso Pharmaceuticals には、薬局のルート ノードと小売ルート ノードがあります。 どちらのルート ノードにも複数の子孫行があり、それらの間に重複はありません。
* パブリケーションの受信者にできるのはリーフ ノードだけです。 階層内の他のノードは、パブリケーションの受信者を選択するのに役立ちます。
* 1 つのチームを表すことができるのは、階層内で 1 回だけです。
* 階層には、最大 15,000 個のノードを含めることができます。 お客様と協力して、大規模な組織に対してこの制限を引き上げる予定です。

### <a name="example-hierarchy"></a>階層の例

たとえば、次の階層では、Recall、Communications、HR は階層内のすべての下位ノード (チーム) にタスクを発行できますが、ノースイースト ゾーンではニューヨーク ストアチームとボストン ストア チームにのみタスクを発行できます。 階層例を使用すると、Recall、Communications、HR の各グループで、会社全体に適用されるタスク (特典情報や CEO からのメッセージなど) を公開できます。 ノースイースト ゾーンでは、担当者のスケジュール設定や気象情報などのタスクを、ニューヨーク ストアチームとボストン ストア チームにのみ公開できます。

![チーム階層の例。](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>階層を作成する

> [!NOTE]
> この記事の残りの部分では、受信者チームにタスクを発行するコンテキストでチーム階層を設定する方法について説明します。 有効にするとタスクの発行が表示されるタスク アプリの概要については、「 [Teams で組織](./manage-tasks-app.md) のタスク アプリを管理する」を参照してください。

階層を定義するスキーマは、コンマ区切り値 (CSV) ファイルに基づいています。 ファイルは UTF-8 形式である必要があります。 CSV ファイルの各行は、チームの階層内の 1 つのノードに対応します。 各行には、階層内のノードに名前を付け、必要に応じてそれをチームにリンクする情報が含まれており、それをサポートするアプリのチームをフィルター処理するために使用できる属性が含まれています。

**また、バケット** を定義することもできます。これは、発行チームが受信者チームに送信されたコンテンツを整理するために使用できるカテゴリで、関連するコンテンツの表示、並べ替え、およびフォーカスを容易にすることができます。

### <a name="add-required-columns"></a>必要な列を追加する

CSV ファイルには、最初の列から次の 3 つの列が次の順序で含まれている必要があります。 タスクを受信するには、ノードをチームにリンクする必要があります。

| 列名   | 必須 | 説明   |
----------------|----------|---------------|
| DisplayName    | Yes      | このフィールドはノードの名前です。 名前の長は最大 100 文字で、A から Z、a-z、0 から 9 の文字のみを含めることができます。 ノード名は一意である必要があります。 |
| ParentName    | Yes       | これは親ノードの名前です。 ここで指定する値は、親ノードの **DisplayName** フィールドの値と正確に一致する必要があります。 複数の親ノードを追加する場合は、各親ノード名をセミコロン (;)で区切ります。 最大 25 個の親ノードを追加でき、各親ノード名の長は最大 2500 文字です。 ノードは、親ノードがルート ノードである場合にのみ、複数の親ノードを持つことができます。   <br><br>**大事な** 階層内の上位の親が階層内の下位の子ノードを参照するループを作成しないように注意してください。 これはサポートされていません。 |
| TeamId        | はい。チームがタスクを発行するか、親ノードからタスクを受け取る場合       | これには、ノードをリンクするチームの ID が含まれます。 各ノードは一意のチームを参照する必要があるため、各 TeamId 値は階層ファイルに 1 回だけ表示できます。 ノードをリンクするチームの ID を取得するには、次の PowerShell コマンドを実行します。 `Get-Team | Export-Csv TeamList.csv` このコマンドは、組織内のチームを一覧表示し、各チームの名前と ID を含めます。 リンク先のチームの名前を見つけて、このフィールドに ID をコピーします。|

> [!NOTE]
> ノードがルート ノードまたはリーフ ノードではなく、発行とレポートに対応するアクセス許可を付与するためにチーム メンバーシップが必要ない場合は、TeamId を空白のままにすることができます。 このメソッドを使用すると、受信者チームを選択するとき、または対応するチームを持たずに完了レポートを表示するために、さらに細分性を追加できます。

### <a name="add-attribute-columns"></a>属性列を追加する

3 つの必須列を追加した後、オプションの属性列を追加できます。 これらの属性を使用すると、タスクを発行するノードをより簡単に選択できるように、ノードをフィルター処理できます。 属性の値が相互に排他的かどうかに応じて、属性を定義する方法は 2 つあります。

|属性を追加する方法|説明 |例  |
|---|---------|---------|
|属性の値が相互に排他的である場合、指定した列名が属性の名前になります。|各行には、その属性の値を 1 つ含めることができます。また、各属性列には最大 50 個の一意の値を指定できます。 各値の長は最大 100 文字です。 属性列で指定した属性値のセットは、チームターゲット階層を使用して受信者チームを選択すると、その属性のフィルター値として表示されます。|ユーザーがレイアウトでストアをフィルター処理できるようにする必要があります。 ストアには 1 つのレイアウトしか持てないため、この属性の値は相互に排他的です。 <br><br>レイアウトでストアをフィルター処理する属性を追加するには、[ストア レイアウト] という名前の列を追加します。 この例では、Store レイアウト属性の値は Compact、Standard、Large です。
|属性に複数の値を指定する必要があり、値が相互に排他的でない場合は、列名に **AttributeName:UniqueValue** 形式を使用します。 <br><br>**大事な** 必ず英語専用コロン (:)unicode は属性列区切り記号としてサポートされていないためです。 |コロンの前のテキスト文字列 (:)は 属性の名前になります。 コロンの前に同じテキスト文字列を含むすべての列 (:)は、フィルターメニューのセクションにグループ化されます。 コロンの後の各文字列は、そのセクションの値になります。<br><br>各行の値は、その属性に対して 0 (ゼロ) または 1 にすることができます。 値が 0 の場合、属性はノードに適用されません。値 1 は、そのノードに属性が適用されることを意味します。|ユーザーが部門別にストアをフィルター処理できるようにする必要があります。 ストアには複数の部署を含めることができるため、この属性の値は相互に排他的ではありません。<br><br>この例では、部門:衣料品、部門:エレクトロニクス、部門:食品、部門:家庭と庭、部門:スポーツ用品を属性列として追加します。 部門が属性名になり、ユーザーは衣料品部門、エレクトロニクス部門、食品部門、家庭用品部門、スポーツ用品部門でフィルター処理できます。|

属性列を追加するときは、次の点に注意してください。

* 指定した列名、またはコロンの前に指定した列名 (:)は 属性の名前になります。 この値は、階層を使用する Teams アプリに表示されます。
* 階層内には最大 50 個の属性列を含めることができます。
* 列名の長は最大 100 文字で、A から Z、a-z、0 から 9、およびスペースのみを含めることができます。 列名は一意である必要があります。

### <a name="add-bucket-columns"></a>バケット列を追加する

バケット列を追加してバケットを作成できます。これは、タスクを整理できるグループです。 各バケットは、CSV ファイル内の独自の列を取得します。 作成したバケットは、発行チームが使用できるようになります。 発行チームは、これらのバケットを使用して、受信者チームのタスクを分類できます。 チームにバケットがまだ存在しない場合、タスクが発行されたときにバケットがオンデマンドで作成されます。

発行チームは、作業項目を 1 回一元的に分類することで、タスク リストを受信するすべての 10、数百、または数千の受信者チームのタスク リストを事前に整理できます。 その後、受信者チームは、タスクをバケットで並べ替えてフィルター処理し、作業に最も関連する領域に焦点を当てることができます。

バケット列を追加する場合は、次の点に注意してください。

* 列名はバケットの名前になります。 指定した各バケットは、階層を使用する Teams アプリの [バケット] リストに表示されます。
* バケット名には機密情報を含めないようにすることをお勧めします。 現時点では、発行チームは、作成後に発行を通じてバケットを削除することはできません。
* 列名の前にハッシュタグ (#)を付ける必要があります。 最大 100 文字の長さにすることができ、A から Z、a-z、0 から 9 の文字のみを含めることができます。 たとえば、商品の#Operationsや#Frozenなどです。
* 階層には、最大 25 個のバケット列が含まれる場合があります。 大規模な組織のこの制限を引き上げるために、お客様と協力する予定です。

### <a name="example"></a>例

前の図に示した階層をサポートするために作成されるスキーマ CSV ファイルの例を次に示します。 このスキーマには、次のものが含まれます。

* 、、および という名前 `TargetName`の `ParentName`3 つの必須列 `TeamId`
* 、、および という名前 `Store layout`の `Departments:Clothing`3 つの属性列 `Departments:Foods`
* 、、および という名前 `Fresh Foods`の `Frozen Foods`3 つのバケット列 `Women's Wear`

属性には`Store layout`、、`Standard`、および を含む`Compact`値があります`Large`。 属性列は `Departments` 、値 `0` (ゼロ) または `1`に設定できます。 上の図では `Store` 、レイアウトと `Departments` 属性は表示されません。 ノード エントリに属性を追加する方法を示すために、ここに追加されています。 3 つのバケット列についても同じことが当てはまります。

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
> この手順を実行するには、Microsoft Teams PowerShell コマンドレットを使用する必要があります。 Microsoft Teams コマンドレットのバージョン 4.6.0 以降を使用する必要があります。 この要件は、Government Community Cloud (GCC) のお客様にも適用されます。

スキーマ CSV ファイルで階層を定義したら、それを Teams にアップロードする準備ができました。 これを行うには、次のコマンドを実行します。 この手順を実行するには、グローバル管理者または Teams サービス管理者である必要があります。

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>階層を更新する

上記と同じ PowerShell コマンドを使用して、新しい階層をアップロードして古い階層を置き換えることができます。 新しい階層をアップロードするたびに、前の階層が置き換えられます。

### <a name="check-the-status-of-your-hierarchy"></a>階層の状態を確認する

次のコマンドを実行して、階層のアップロードの状態を確認できます。

```powershell
Get-TeamTargetingHierarchyStatus
```

コマンドは、次のフィールドを返します。

フィールド|説明
-----|------------
ID | アップロードの一意の ID。
ステータス | アップロードの状態。 値には、 **開始**、 **検証**、 **成功**、 **失敗が含まれます**
ErrorDetails | アップロード エラーが発生した場合の詳細。 エラーの詳細については、「トラブルシューティング」セクションを参照してください。 エラーがない場合、このフィールドは空白です。
LastUpdatedAt | ファイルが最後に更新されたときのタイムスタンプと日付。
LastModifiedBy | ファイルを変更した最後のユーザーの ID。
FileName | CSV のファイル名。

## <a name="remove-your-hierarchy"></a>階層を削除する

組織内のすべてのユーザーの [ **発行済みリスト** ] タブをすぐに無効にする場合は、階層を削除できます。 ユーザーは、[ **発行済みリスト** ] タブまたはタブの機能にアクセスできません。 これには、発行、下書きリストへのアクセス、発行、発行解除、重複リストの作成、レポートの表示を行う新しいタスク リストを作成する機能が含まれます。 階層を削除しても、以前に発行されたタスクは発行解除されません。 これらのタスクは、受信者チームが完了するために引き続き使用できます。

階層を削除するには、次のコマンドを実行します。 この手順を実行するには、管理者である必要があります。

```powershell
Remove-TeamTargetingHierarchy
```

削除を確認すると、前のスキーマが存在する状態メッセージが表示されますが、もう一度削除しようとすると、オブジェクトが null であるというエラーが返されます。

## <a name="create-a-sample-hierarchy"></a>サンプル階層を作成する

### <a name="install-the-teams-powershell-module"></a>Teams PowerShell モジュールをインストールする

> [!IMPORTANT]
> この手順を実行するには、[PowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams/)から Teams PowerShell モジュールをインストールして使用する必要があります。 モジュールをインストールする手順については、「[Teams PowerShell モジュールMicrosoftインストール](teams-powershell-install.md)する」を参照してください。

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

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>チーム データを使用してコンマ区切りの出力を作成する (DisplayName、ParentName、TeamId)

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

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>**ダウンロード** フォルダーの.csv ファイルに出力を保存する

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

次のコマンドを実行して、エラーの原因を理解し、エラーの詳細を返すことができます。

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>スキーマ CSV ファイルをアップロードするときにエラー メッセージが表示される

スキーマをアップロードできなかった理由を示すトラブルシューティング情報が含まれている必要があるため、エラー メッセージを書き留めます。 エラー メッセージの情報に基づいてスキーマ CSV ファイルを確認して編集してから、もう一度やり直してください。

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>スキーマ CSV ファイルをアップロードすると、"Error: InvalidTeamId" というエラー メッセージが表示されます

スキーマ CSV ファイルをアップロードしようとすると、次のエラー メッセージが表示されます。

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

スキーマ CSV ファイルでチームに適切な TeamId が使用されていることを確認します。 TeamId は、チームをバックするMicrosoft 365 グループのグループ ID と同じである必要があります。 チームのグループ ID は、Microsoft Teams 管理センターで確認できます。

1. [Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)の左側のナビゲーションで、[**Teams****管理チーム** > ] に移動します。
2. テーブルに **[グループ ID** ] 列が表示されない場合は、テーブルの右上隅にある [ **列の編集]** を選択し、[ **グループ ID**] をオンにします。
3. 一覧からチームを見つけて、グループ ID を見つけます。

スキーマ CSV ファイルの TeamId が、Microsoft Teams 管理センターに表示されるグループ ID と一致していることを確認します。

## <a name="related-topics"></a>関連項目

* [Teams で組織のタスク アプリを管理する](manage-tasks-app.md)
* [Teams での PowerShell の概要](teams-powershell-overview.md)
