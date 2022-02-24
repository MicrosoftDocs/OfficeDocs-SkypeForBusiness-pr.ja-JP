---
title: コンテンツの電子情報開示調査を実施する
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 法的手続きのためにすべての電子的に保存された情報を送信する必要がある場合など、電子情報開示を実行する必要がある場合の操作について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b78ec3ad6741d2c7f83d7732400d5f1154747d5e
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929162"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams のコンテンツに対して電子情報開示の調査を行う

多くの場合、大企業は、すべての電子的に保存された情報 (ESI) の提出を要求する高いペナルティ訴訟手続きにさらされます。 Microsoft Teamsコンテンツは、電子情報開示調査中に検索して使用できます。

## <a name="overview"></a>概要

すべてのMicrosoft Teams 1:1 またはグループ チャットは、それぞれのユーザーのメールボックスにジャーナルされます。 すべての標準チャネル メッセージは、チームを表すグループ メールボックスにジャーナルされます。 標準チャネルでアップロードされたファイルは、SharePoint Online および OneDrive for Business の電子情報開示機能の下で扱OneDrive for Business。

プライベート チャネルでのメッセージとファイルの電子情報開示 [は、](private-channels.md) 標準チャネルとは異なる方法で動作します。 詳細については、「プライベート チャネル [の電子情報開示」を参照してください](#ediscovery-of-private-channels)。

すべてのコンテンツTeams eDiscoverable ではありません。 次の表は、Microsoft 電子情報開示ツールを使用して検索できるコンテンツ タイプを示しています。

| コンテンツの種類 | eDiscoverable | メモ |
|:--- | :--- |:--- |
|オーディオ録音 | いいえ | |
|カードの内容|Yes|詳細については [、「カードコンテンツを検索する](#search-for-card-content) 」を参照してください。|
|チャット リンク | Yes | |
|チャット メッセージ | Yes |これには、Teams チャネルのコンテンツ、1 対 1 のチャット、1:N グループ チャット、ゲスト ユーザー参加者とのチャットが含まれます。  |
|コード スニペット | いいえ | |
|編集されたメッセージ | Yes | ユーザーが保留の場合、以前のバージョンの編集されたメッセージも保持されます。 |
|絵文字、GIF、ステッカー | Yes | |
|フィード通知 | いいえ | |
|インライン 画像 | Yes | |
|ループ コンポーネント| いいえ|ループ コンポーネントを含むチャット メッセージは検索可能です。 ただし、ループ コンポーネントの内容は検索用にインデックスが作成されないので、検索結果には返されません。 ループ コンポーネントを含むメッセージが検索結果に含まれている場合は、ループ コンポーネントの内容を表示できます。  |
|IM 会話を会議する | Yes | |
|会議メタデータ<sup>1</sup> | Yes |  |
|チャネルの名前 | Yes | |
|プライベート チャネル メッセージ | Yes | |
|引用符 | Yes | 引用符で囲まれたコンテンツは検索可能です。 ただし、検索結果は、コンテンツが引用されたというわけではありません。 |
|反応 (例: Likes、ハート、その他の反応) | いいえ | |
|件名 | Yes | |
|テーブル | Yes | |
||||

<sup>1 会議</sup> (および通話) メタデータには、次が含まれます。

- 会議の開始時刻と終了時刻、および期間
- 各参加者の会議への参加と退出のイベント
- VOIP の参加/呼び出し
- 匿名結合
- フェデレーション ユーザー参加
- ゲスト ユーザーの参加

  この画像は、会議のメタデータの例を示しています。

  > [!div class="mx-imgBorder"]
  > ![コンプライアンス コピーの会議メタデータ。](media/conversationOption3.png)

会議中の参加者間の IM 会話の例を次に示します。

![Teams での参加者間の会話。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![電子情報開示検索結果の参加者間の会話。](media/MeetingImConversation2.png)

電子情報開示調査の実施の詳細については、「Core [eDiscovery の概要」を参照してください](/microsoft-365/compliance/get-started-core-ediscovery)。

Microsoft Teams電子情報開示のエクスポート出力に、IM または会話Excelとして表示されます。 エクスポートしたメッセージを`.pst`Outlookファイルを開き、それらのメッセージを表示できます。

チームの .pst ファイルを表示すると、すべての会話が [会話履歴] の [チーム チャット] フォルダーに置きます。 メッセージのタイトルには、チーム名とチャネル名が含まれている。 たとえば、次の図は、製造仕様チームの Project 7 標準チャネルにメッセージを送信した Bob からのメッセージを示しています。

![グループ内のユーザーのメールボックス内のチーム チャット フォルダー Outlook。](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

ユーザーのメールボックス内のプライベート チャットは、[会話履歴] の [チーム チャット] フォルダーに保存されます。

## <a name="ediscovery-of-private-channels"></a>プライベート チャネルの電子情報開示

プライベート チャネルで送信されたメッセージのコンプライアンス コピーは、グループ メールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。 コンプライアンス コピーのタイトルは、送信されたプライベート チャネルを示す形式です。

各プライベート チャネルには、親チーム サイトとは別の独自の SharePoint サイトが用意されています。プライベート チャネル内のファイルは、親チームとは独立して管理されます。

Teamsチーム内の 1 つのチャネルの電子情報開示検索をサポートしないので、チーム全体を検索する必要があります。 プライベート チャネル内のコンテンツの電子情報開示検索を実行するには、チーム全体、プライベート チャネルに関連付けられているサイト コレクション (ファイルを含める)、プライベート チャネル メンバーのメールボックス (メッセージを含める) を検索します。

次の手順を使用して、電子情報開示検索に含めるプライベート チャネル内のファイルとメッセージを識別します。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>電子情報開示検索にプライベート チャネル ファイルを含める

これらの手順を実行する前に、[SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) をインストールし、SharePoint Online に接続します。

1. 次のコマンドを実行して、チーム内のプライベート SharePointに関連付けられているすべてのサイト コレクションの一覧を取得します。

    ```PowerShell
    Get-SPOSite
    ```

2. 次の PowerShell スクリプトを実行して、チーム内のプライベート SharePointに関連付けられているすべてのサイト コレクション URL と親チーム グループ ID の一覧を取得します。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. チームまたはグループ ID ごとに、次の PowerShell `$groupID` スクリプトを実行して、関連するすべてのプライベート チャネル サイトを識別します。ここでは、チームのグループ ID です。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```
> [!NOTE]
> SharePoint 2021 `teamchannel#1` 年 6 月 28 日より後に作成されたプライベート チャネルのサイトでは、カスタム テンプレート ID の値が使用されます。 したがって、この日付より後に作成されたプライベート チャネルの場合は、前の `teamchannel#1` 2 つのスクリプトを実行するときに 値を使用します。

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>電子情報開示検索にプライベート チャネル メッセージを含める

これらの手順を実行する前に、[PowerShell](teams-powershell-overview.md) モジュールの最新バージョンTeams確認してください。

1. 次のコマンドを実行して、検索するプライベート チャネルを含むチームのグループ ID を取得します。

   ```powershell
   Get-Team -MailNickName <mail alias of the associated Office 365 Group>
   ```

   > [!TIP]
   > パラメーターを **指定せずに Get-Team** コマンドレットを実行し、組織内のすべてのTeams一覧を表示します。 一覧には、すべてのチームのグループ ID と MailNickName が含まれている。

2. 次のコマンドを実行して、チーム内のプライベート チャネルの一覧を取得します。 手順 1 で取得したチームのグループ ID を使用します。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupId> -MembershipType Private
    ```

3. 次のコマンドを実行して、プライベート チャネルの所有者とメンバーの一覧を取得します。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupId> -DisplayName "Engineering" 
    ```

4. 電子情報開示検索クエリの一部として、チーム内の各プライベート チャネルのすべての所有者とメンバーの [メールボックスを含める](/microsoft-365/compliance/search-for-content-in-core-ediscovery)。

## <a name="search-for-content-for-guest-users"></a>ゲスト ユーザーのコンテンツを検索する

電子情報開示ツールを使用して、組織内のゲスト Teams関連するコンテンツを検索できます。 Teamsに関連付けられているチャット コンテンツは、クラウドベースの保存場所に保持され、電子情報開示を使用して検索できます。 これには、ゲスト ユーザーが組織内の他のユーザーと参加者である 1:1 と 1:N のチャット会話内のコンテンツの検索が含まれます。 ゲスト ユーザーが参加者であるプライベート チャネル メッセージを検索し、ゲスト *と* ゲスト チャットの会話でコンテンツを検索することもできます。この会話では、参加者はゲスト ユーザーのみです。

ゲスト ユーザーのコンテンツを検索するには:

1. Connect PowerShell をAzure ADします。 手順については、「PowerShell を使用したConnect」の「Azure Active Directory PowerShell のConnect[」Microsoft 365参照してください](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。 前のトピックの手順 1 と手順 2 を必ず完了してください。

2. PowerShell に正常にAzure ADしたら、次のコマンドを実行して、組織内のすべてのゲスト ユーザーのユーザー プリンシパル名 (UPN) を表示します。 手順 4 で検索を作成するときに、ゲスト ユーザーの UPN を使用する必要があります。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > コンピューターの画面にユーザー プリンシパル名の一覧を表示する代わりに、コマンドの出力をテキスト ファイルにリダイレクトできます。 これを行うには、前のコマンドに `> filename.txt` を追加します。 ユーザー プリンシパル名を持つテキスト ファイルは、現在のフォルダーに保存されます。

3. 別のウィンドウWindows PowerShell、Security & Compliance Center PowerShell に接続します。 手順については、「Security [Connect Compliance Center PowerShell &」を参照してください](/powershell/exchange/connect-to-scc-powershell)。 多要素認証を使用する場合と接続せずに接続できます。

4. 次のコマンドを実行して、指定されたゲスト ユーザーが参加者だったすべてのコンテンツ (チャット メッセージや電子メール メッセージなど) を検索するコンテンツ検索を作成します。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   たとえば、ゲスト ユーザー Sara Davis に関連付けられているコンテンツを検索するには、次のコマンドを実行します。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    PowerShell を使用してコンテンツ検索を作成する方法の詳細については、「 [New-ComplianceSearch」を参照してください](/powershell/module/exchange/new-compliancesearch)。

5. 次のコマンドを実行して、手順 4 で作成したコンテンツ検索を開始します。

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com)、[Show **allContent** >  **search]をクリックします**。

7. 検索の一覧で、手順 4 で作成した検索を選択して、フライアウト ページを表示します。

8. フライアウト ページでは、次の操作を行います。

   - [ **結果の表示]** をクリックして検索結果を表示し、コンテンツをプレビューします。

   - [クエリ] **フィールドの横** にある [編集 **] をクリック** して編集し、検索を再実行します。 たとえば、検索クエリを追加して結果を絞り込むなどです。

   - [結果 **のエクスポート]** をクリックして、検索結果をエクスポートしてダウンロードします。

## <a name="search-for-card-content"></a>カードコンテンツを検索する

Teams チャネル、1 対 1 のチャット、および 1xN チャットのアプリによって生成されたカード コンテンツは、メールボックスに格納され、検索できます。 カード *は* 、短いコンテンツの UI コンテナーです。 カードには複数のプロパティと添付ファイルを含め、カードアクションをトリガーできるボタンを含めることができます。 詳細については、「カード」を [参照してください。](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

他のTeamsコンテンツと同様に、カードコンテンツが格納される場所は、カードが使用された場所に基づいて行います。 チャネルで使用されるカードのTeamsは、グループ メールボックスTeams保存されます。 1 対 1 および 1xN のチャットのカード コンテンツは、チャット参加者のメールボックスに保存されます。

カードコンテンツを検索するには、 または 検索条件 `kind:microsoftteams` を `itemclass:IPM.SkypeTeams.Message` 使用します。 検索結果を確認すると、Teams チャネル内のボットによって生成されたカード コンテンツは、Sender **/Author** メール プロパティとして として設定されます`<appname>@teams.microsoft.com``appname`。ここでは、カード コンテンツを生成したアプリの名前です。 カードコンテンツがユーザーによって生成された場合、 **Sender/Author** の値はユーザーを識別します。

コンテンツ検索結果でカードコンテンツを表示すると、そのコンテンツがメッセージの添付ファイルとして表示されます。 添付ファイルの名前は `appname.html`です。ここで `appname` は、カードコンテンツを生成したアプリの名前です。 次のスクリーンショットは、(Asana という名前のアプリの) カード コンテンツが検索の結果Teamsに表示される方法を示しています。

**カードのコンテンツ Teams**

![チャネル メッセージのTeamsコンテンツ。](media/CardContentTeams.png)

**検索結果のカード コンテンツ**
  
![コンテンツ検索の結果と同じカード コンテンツ。](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 現時点では、カードコンテンツの画像を検索結果に表示するには (https://teams.microsoft.com)前のスクリーンショットのチェックマークなど)、検索結果の表示に使用するのと同じブラウザー セッションの別のタブで Teams にサインインする必要があります。 それ以外の場合は、画像プレースホルダーが表示されます。

## <a name="related-topics"></a>関連項目

- [Microsoft 365電子情報開示ソリューション](/microsoft-365/compliance/ediscovery)
- [Core eDiscovery の使用](/microsoft-365/compliance/get-started-core-ediscovery)
- [TeamsワークフローのAdvanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams PowerShell の概要](teams-powershell-overview.md)
