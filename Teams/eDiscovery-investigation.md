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
ms.openlocfilehash: 85124047c5bb894eb4eb4177fad0e0cfee53dfc3
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711771"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams のコンテンツに対して電子情報開示の調査を行う

多くの場合、大企業は、すべての電子的に保存された情報 (ESI) の提出を要求する高いペナルティ訴訟手続きにさらされます。 Microsoft Teamsコンテンツは、電子情報開示調査中に検索して使用できます。

## <a name="overview"></a>概要

すべてのMicrosoft Teams 1:1 またはグループ チャットは、それぞれのユーザーのメールボックスにジャーナルされます。 すべての標準チャネル メッセージは、チームを表すグループ メールボックスにジャーナルされます。 標準チャネルでアップロードされたファイルは、SharePoint Online および OneDrive for Business の電子情報開示機能の下で扱OneDrive for Business。

プライベート チャネルでのメッセージとファイルの電子情報開示 [は、](private-channels.md) 標準チャネルとは異なる方法で動作します。 詳細については、「プライベート チャネル [の電子情報開示」を参照してください](#ediscovery-of-private-and-shared-channels)。

すべてのコンテンツTeams eDiscoverable ではありません。 次の表は、Microsoft 電子情報開示ツールを使用して検索できるコンテンツ タイプを示しています。

| コンテンツの種類 | eDiscoverable | メモ |
|:--- | :--- |:--- |
|オーディオ録音 | いいえ | |
|カードの内容|はい|詳細については [、「カードコンテンツを検索する](#search-for-card-content) 」を参照してください。|
|チャット リンク | はい | |
|チャット メッセージ | はい |これには、Standard Teams チャネルのコンテンツ、1 対 1 のチャット、1:N グループ チャット、ゲスト ユーザー参加者とのチャットが含まれます。  |
|コード スニペット | いいえ | |
|編集されたメッセージ | はい | ユーザーが保留の場合、以前のバージョンの編集されたメッセージも保持されます。 |
|絵文字、GIF、ステッカー | はい | |
|フィード通知 | いいえ | |
|インライン 画像 | はい | |
|ループ コンポーネント| はい|ループ コンポーネント内のコンテンツは、ループ コンポーネントを送信するユーザーの OneDrive for Business アカウントに格納されている .fluid ファイルに保存されます。 つまり、ループ コンポーネント内のOneDriveを検索するときに、データ ソースとしてデータ ソースを含める必要があります。 |
|IM 会話を会議する | はい | |
|会議メタデータ<sup>1</sup> | はい |  |
|チャネルの名前 | はい | |
|プライベート チャネルと共有チャネルのチャット メッセージ | はい | |
|引用符 | はい | 引用符で囲まれたコンテンツは検索可能です。 ただし、検索結果は、コンテンツが引用されたというわけではありません。 |
|反応 (例: Likes、ハート、その他の反応) | いいえ | |
|件名 | はい | |
|テーブル | はい | |
||||

<sup>1 会議</sup> (および通話) メタデータには、次が含まれます。

- 会議の開始時刻と終了時刻、および期間
- 各参加者の会議への参加と退出のイベント
- VOIP の参加/呼び出し
- 匿名結合
- フェデレーション ユーザー参加
- ゲスト ユーザーの参加

会議中の参加者間のチャット会話の例を次に示します。

![Teams での参加者間の会話。](media/MeetingIMConversations.png)

[!div class="mx-imgBorder"]

電子情報開示ツールで表示された同じチャット会話のコンプライアンス コピーの例を次に示します。

![電子情報開示検索結果の参加者間の会話。](media/MeetingImConversation2.png)

会議のメタデータの例を次に示します。

  > [!div class="mx-imgBorder"]
  > ![コンプライアンス コピーの会議メタデータ。](media/conversationOption3.png)

電子情報開示調査の実施の詳細については、「Core [eDiscovery の概要」を参照してください](/microsoft-365/compliance/get-started-core-ediscovery)。

Microsoft Teams電子情報開示のエクスポート出力に、データが IM または会話Excel表示されます。 ファイルをエクスポートした後`.pst`、Outlookファイルを開き、それらのメッセージを表示できます。

チームの .pst ファイルを表示すると、すべての会話が [会話履歴] の [チーム チャット] フォルダーに置きます。 メッセージのタイトルには、チーム名とチャネル名が含まれている。 たとえば、次の図は、製造仕様チームの Project 7 標準チャネルにメッセージを送信した Bob からのメッセージを示しています。

![グループ内のユーザーのメールボックス内のチーム チャット フォルダー Outlook。](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

ユーザーのメールボックス内のプライベート チャットは、[会話履歴] の [チーム チャット] フォルダーに保存されます。

## <a name="ediscovery-of-private-and-shared-channels"></a>プライベート チャネルと共有チャネルの電子情報開示

プライベート チャネルと共有チャネル内のメッセージのコンプライアンス コピーは、チャネルの種類に応じて異なるメールボックスに送信されます。 つまり、ユーザーがメンバーであるチャネルの種類に基づいて、さまざまなメールボックスの場所を検索する必要があります。

- **プライベート チャネル**。 コンプライアンス コピーは、プライベート チャネル メンバーのすべてのメンバーのメールボックスに送信されます。 つまり、プライベート チャネル メッセージ内のコンテンツを検索するときに、ユーザー メールボックスを検索する必要があります。

- **共有チャネル**。 コンプライアンス コピーは、親チームに関連付けられているシステム メールボックスに送信されます。 Teams は共有チャネルの 1 つのシステム メールボックスの電子情報開示検索をサポートしないので、共有チャネルでメッセージ コンテンツを検索するときに、親チームのメールボックスを検索する (チーム メールボックスの名前を選択する) 必要があります。

各プライベート チャネルと共有チャネルには、SharePointチーム サイトとは別の独自のサイトがあります。 つまり、プライベート チャネルと共有チャネル内のファイルは、独自のサイトに保存され、親チームとは独立して管理されます。 つまり、ファイル内のコンテンツとチャネル メッセージの添付ファイルを検索する際に、チャネルに関連付けられている特定のサイトを特定して検索する必要があります。

電子情報開示検索に含めるプライベート チャネルまたは共有チャネルを識別するには、次のセクションを使用します。

### <a name="identifying-the-members-of-a-private-channel"></a>プライベート チャネルのメンバーの識別

このセクションの手順を使用して、プライベート チャネルのメンバーを識別し、電子情報開示ツールを使用して、メンバーのメールボックスでプライベート チャネル メッセージ内のコンテンツを検索できます。

これらの手順を実行する前に、[PowerShell](teams-powershell-overview.md) モジュールの最新バージョンTeams確認してください。

1. 次のコマンドを実行して、検索する共有チャネルを含むチームのグループ ID を取得します。

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > パラメーターを **指定せずに Get-Team** コマンドレットを実行し、組織内のすべてのTeams一覧を表示します。 一覧には、すべてのチームのグループ ID と DisplayName が含まれている。

2. 次のコマンドを実行して、親チームのプライベート チャネルの一覧を取得します。 手順 1 で取得したチームのグループ ID を使用します。

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. 次のコマンドを実行して、特定のプライベート チャネルのプライベート チャネル所有者とメンバーの一覧を取得します。

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. プライベート チャネルの所有者とメンバーのメールボックスを[、Core eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery) の電子情報開示検索クエリの一部として、または Advanced eDiscovery で管理人のコンテンツを識別して収集するときに含[める。](/microsoft-365/compliance/add-custodians-to-case)

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>プライベート チャネルSharePoint共有チャネルのサイトを識別する

前に説明したように、プライベート チャネルと共有チャネルで共有されているファイル (およびチャネル メッセージに添付されたファイル) は、チャネルに関連付けられているサイト コレクションに格納されます。 このセクションの手順を使用して、特定のプライベート チャネルまたは共有チャネルに関連付けられているサイトの URL を特定します。 その後、電子情報開示ツールを使用して、サイト内のコンテンツを検索できます。

これらの手順を実行する前に[、SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) をインストールし、SharePointします。

1. 必要に応じて、次のコマンドを実行して、親SharePoint共有チャネルに関連付けられているすべてのサイト コレクションの一覧を取得します。

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > プライベート チャネルと共有チャネルに関連付けられているサイトの URL の名前付け規則は です `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`。 たとえば、Contoso 組織の "エンジニア チーム" 親チームにある "パートナー コラボレーション" という名前の共有チャネルの URL は です `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`。

2. 次の PowerShell コマンドを実行して、組織内のプライベート チャネルSharePointに関連付けられているすべてのサイトの URL を表示します。 スクリプトの出力には、手順 3 でコマンドを実行する必要がある親チームのグループ ID も含まれています。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > SharePoint 2021 `"TEAMCHANNEL#0"` 年 6 月 28 日より前に作成されたプライベート チャネルのサイトでは、カスタム テンプレート ID の値が使用されます。 この日付より後に作成されたプライベート チャネルを表示するには、前の `"TEAMCHANNEL#1"` 2 つのスクリプトを実行するときに 値を使用します。 共有チャネルでは、 の値のみを使用します `"TEAMCHANNEL#1"`。

3. 親チームごとに、次の PowerShell `$groupID` コマンドを実行してプライベート チャネル サイトと共有チャネル サイトを識別します。親チームのグループ ID は です。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. プライベート チャネルまたは共有チャネルに関連付けられているサイトを[、Core eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery) の電子情報開示検索クエリの一部として、または Advanced eDiscovery で管理人のコンテンツを識別して収集[するときに含める](/microsoft-365/compliance/add-custodians-to-case)。

## <a name="search-for-content-for-guest-users"></a>ゲスト ユーザーのコンテンツを検索する

電子情報開示ツールを使用して、組織内のTeamsに関連するコンテンツを検索できます。 Teamsに関連付けられているチャット コンテンツは、クラウドベースの保存場所に保持され、電子情報開示を使用して検索できます。 これには、ゲスト ユーザーが組織内の他のユーザーと参加者である 1:1 と 1:N のチャット会話内のコンテンツの検索が含まれます。 ゲスト ユーザーが参加者であるプライベート チャネル メッセージを検索し、ゲスト *と* ゲスト チャットの会話でコンテンツを検索することもできます。この会話では、参加者はゲスト ユーザーのみです。

ゲスト ユーザーのコンテンツを検索するには:

1. Connect PowerShell をAzure ADする方法について説明します。 手順については、「PowerShell を使用したConnect」の「Azure Active Directory PowerShell を使用したConnect[」Microsoft 365参照してください](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。 前のトピックの手順 1 と手順 2 を必ず完了してください。

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

### <a name="card-content-in-teams"></a>[カードコンテンツ] Teams

![チャネル メッセージTeamsコンテンツ。](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>検索結果のカード コンテンツ
  
![コンテンツ検索の結果と同じカード コンテンツ。](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> この時点でカードコンテンツの画像を検索結果に表示するには (前のスクリーンショットのチェックマークなど)、(検索結果の表示に使用したのと同じブラウザー セッションの別のタブで) https://teams.microsoft.com) Teams にサインインする必要があります。 それ以外の場合は、画像プレースホルダーが表示されます。

## <a name="related-topics"></a>関連項目

- [Microsoft 365電子情報開示ソリューション](/microsoft-365/compliance/ediscovery)
- [Core eDiscovery の使用](/microsoft-365/compliance/get-started-core-ediscovery)
- [TeamsワークフローのAdvanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams PowerShell の概要](teams-powershell-overview.md)
