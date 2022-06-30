---
title: コンテンツの電子情報開示調査を実施する
author: v-tophillips
ms.author: v-tophillips
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
description: 電子情報開示を実行する必要がある場合 (法的手続きのために電子的に保存されたすべての情報を送信する必要がある場合など) について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6f24c780944bfed6bb10fb8b1cd7634edc1ce850
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562426"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams のコンテンツに対して電子情報開示の調査を行う

大企業は、多くの場合、すべての電子的に保存された情報 (ESI) の提出を要求する高いペナルティ訴訟手続きにさらされます。 Microsoft Teams のコンテンツは、電子情報開示の調査中に検索および使用できます。

## <a name="overview"></a>概要

すべての Microsoft Teams 1:1 またはグループ チャットは、それぞれのユーザーのメールボックスに記録されます。 すべての標準チャネル メッセージは、チームを表すグループ メールボックスに記録されます。 標準チャネルでアップロードされたファイルについては、SharePoint Online とOneDrive for Businessの電子情報開示機能に関するページを参照してください。

[プライベート チャネル](private-channels.md)内のメッセージとファイルの電子情報開示は、標準チャネルとは異なります。 詳細については、「 [プライベート チャネルの電子情報開示](#ediscovery-of-private-and-shared-channels)」を参照してください。

すべての Teams コンテンツが eDiscoverable であるわけではありません。 次の表は、Microsoft 電子情報開示ツールを使用して検索できるコンテンツ タイプを示しています。

|コンテンツの種類|eDiscoverable|メモ|
|---|---|---|
|録音|いいえ||
|カードコンテンツ|はい|詳細については、「 [カード コンテンツの検索](#search-for-card-content) 」を参照してください。|
|チャット リンク|はい||
|チャット メッセージ|はい|これには、標準 Teams チャネルのコンテンツ、1 対 1 のチャット、1 対 1 のグループ チャット、ゲスト ユーザー参加者とのチャットが含まれます。|
|コード スニペット|いいえ||
|編集されたメッセージ|はい|ユーザーが保留中の場合は、以前のバージョンの編集済みメッセージも保持されます。|
|絵文字、GIF、ステッカー|はい||
|フィード通知|いいえ||
|インライン イメージ|はい||
|ループ コンポーネント|はい|ループ コンポーネント内のコンテンツは、ループ コンポーネントを送信するユーザーのOneDrive for Business アカウントに格納されている .fluid ファイルに保存されます。 つまり、ループ コンポーネント内のコンテンツを検索するときに、OneDrive をデータ ソースとして含める必要があります。|
|IM 会話の会議|はい||
|会議メタデータ<sup>1</sup>|はい||
|チャネルの名前|はい||
|プライベートおよび共有チャネル チャット メッセージ|はい||
|引用符|はい|引用符で囲まれたコンテンツは検索可能です。 ただし、検索結果は、コンテンツが引用符で囲まれたことを示すわけではありません。|
|リアクション (いいね、ハート、その他の反応など)|はい||
|件名|はい||
|テーブル|はい||

<sup>1</sup> 会議 (および通話) メタデータには、次のものが含まれます。

- 会議の開始時刻と終了時刻、および期間
- 各参加者の会議参加と退席イベント
- VOIP 参加/呼び出し
- 匿名結合
- フェデレーション ユーザーの参加
- ゲスト ユーザー参加

会議中の参加者間のチャット会話の例を次に示します。

![Teams の参加者間の会話。](media/MeetingIMConversations.png)

[!div class="mx-imgBorder"]

電子情報開示ツールで表示されたのと同じチャット会話のコンプライアンス コピーの例を次に示します。

![電子情報開示検索結果の参加者間の会話。](media/MeetingImConversation2.png)

会議のメタデータの例を次に示します。

  > [!div class="mx-imgBorder"]
  > ![コンプライアンス コピーからの会議メタデータ。](media/conversationOption3.png)

電子情報開示調査の実施の詳細については、「電子情報開示 [の概要 (Standard)](/microsoft-365/compliance/get-started-core-ediscovery)」を参照してください。

Microsoft Teams のデータは、Excel 電子情報開示エクスポート出力に IM または Conversations として表示されます。 Outlook でファイルを `.pst` 開くと、エクスポート後にそれらのメッセージを表示できます。

チームの .pst ファイルを表示すると、すべての会話が [会話履歴] の [チーム チャット] フォルダーに配置されます。 メッセージのタイトルには、チーム名とチャネル名が含まれています。 たとえば、次の図は、製造仕様チームの Project 7 標準チャネルにメッセージを送信した Bob からのメッセージを示しています。

![Outlook のユーザーのメールボックス内のチーム チャット フォルダーのスクリーンショット。](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

ユーザーのメールボックス内のプライベート チャットは、[会話履歴] の [チーム チャット] フォルダーに格納されます。

## <a name="ediscovery-of-private-and-shared-channels"></a>プライベート チャネルと共有チャネルの電子情報開示

プライベート チャネルと共有チャネル内のメッセージのコンプライアンス コピーは、チャネルの種類に応じて異なるメールボックスに送信されます。 つまり、ユーザーがメンバーであるチャネルの種類に基づいて、さまざまなメールボックスの場所を検索する必要があります。

- **プライベート チャネル**。 コンプライアンス コピーは、プライベート チャネル メンバーのすべてのメンバーのメールボックスに送信されます。 つまり、プライベート チャネル メッセージでコンテンツを検索するときに、ユーザー メールボックスを検索する必要があります。

- **共有チャネル**。 コンプライアンス コピーは、親チームに関連付けられているシステム メールボックスに送信されます。 Teams では、共有チャネルの 1 つのシステム メールボックスの電子情報開示検索がサポートされていないため、共有チャネルでメッセージ コンテンツを検索する場合は、親チームのメールボックスを検索する必要があります (チーム メールボックスの名前を選択)。

各プライベート チャネルと共有チャネルには、親チーム サイトとは別の独自の SharePoint サイトがあります。 つまり、プライベート チャネルと共有チャネル内のファイルは、独自のサイトに格納され、親チームとは独立して管理されます。 つまり、ファイル内のコンテンツとチャネル メッセージの添付ファイルを検索するときに、チャネルに関連付けられている特定のサイトを特定して検索する必要があります。

電子情報開示検索に含めるプライベート チャネルまたは共有チャネルを特定するには、次のセクションを使用します。

### <a name="identifying-the-members-of-a-private-channel"></a>プライベート チャネルのメンバーの識別

このセクションの手順を使用してプライベート チャネルのメンバーを識別し、電子情報開示ツールを使用してメンバーのメールボックスでプライベート チャネル メッセージ内のコンテンツを検索できるようにします。

これらの手順を実行する前に、 [Teams PowerShell モジュールの最新バージョンが](teams-powershell-overview.md) インストールされていることを確認してください。

1. 次のコマンドを実行して、検索する共有チャネルを含むチームのグループ ID を取得します。

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > パラメーターを指定せずに **Get-Team** コマンドレットを実行して、組織内のすべての Teams の一覧を表示します。 リストには、すべてのチームのグループ ID と DisplayName が含まれています。

2. 次のコマンドを実行して、親チームのプライベート チャネルの一覧を取得します。 手順 1 で取得したチームのグループ ID を使用します。

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. 次のコマンドを実行して、特定のプライベート チャネルのプライベート チャネルの所有者とメンバーの一覧を取得します。

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. [電子情報開示 (Standard) で電子情報開示検索クエリ](/microsoft-365/compliance/search-for-content-in-core-ediscovery)の一部として、または電子情報開示 (Premium) で[カストディアン コンテンツを識別して収集する](/microsoft-365/compliance/add-custodians-to-case)場合は、プライベート チャネルの所有者とメンバーのメールボックスを含めます。

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>プライベート チャネルと共有チャネルの SharePoint サイトを識別する

前述のように、プライベート チャネルと共有チャネルで共有されたファイル (およびチャネル メッセージに添付されたファイル) は、チャネルに関連付けられたサイト コレクションに格納されます。 このセクションの手順を使用して、特定のプライベート チャネルまたは共有チャネルに関連付けられているサイトの URL を特定します。 次に、電子情報開示ツールを使用してサイト内のコンテンツを検索できます。

これらの手順を実行する前 [に、SharePoint Online 管理シェルをインストールし、SharePoint Online に接続します](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

1. 必要に応じて、次を実行して、親チームの共有チャネルに関連付けられているすべての SharePoint サイト コレクションの一覧を取得します。

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > プライベート チャネルと共有チャネルに関連付けられているサイトの URL の名前付け規則は次のとおりです `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`。 たとえば、Contoso 組織の "エンジニア チーム" 親チームにある "パートナー コラボレーション" という名前の共有チャネルの URL は `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`.

2. 次の PowerShell コマンドを実行して、組織内のプライベート チャネルと共有チャネルに関連付けられているすべての SharePoint サイトの URL を表示します。 スクリプトの出力には、親チームのグループ ID も含まれています。これは、手順 3. のコマンドを実行する必要があります。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > 2021 年 6 月 28 日より前に作成されたプライベート チャネルの SharePoint サイトでは、カスタム テンプレート ID の値 `"TEAMCHANNEL#0"` が使用されます。 この日以降に作成されたプライベート チャネルを表示するには、前の 2 つのスクリプトを実行するときに値 `"TEAMCHANNEL#1"` を使用します。 共有チャネルでは、 `"TEAMCHANNEL#1"`.

3. 親チームごとに、次の PowerShell コマンドを実行して、プライベート チャネル サイトと共有チャネル サイト (親チームのグループ ID) `$groupID` を識別します。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. [電子情報開示 (Standard) の電子情報開示検索クエリ](/microsoft-365/compliance/search-for-content-in-core-ediscovery)の一部として、または電子情報開示 (Premium) で[カストディアン コンテンツを識別して収集する](/microsoft-365/compliance/add-custodians-to-case)場合は、プライベートチャネルまたは共有チャネルに関連付けられているサイトを含めます。

## <a name="search-for-content-for-guest-users"></a>ゲスト ユーザーのコンテンツを検索する

電子情報開示ツールを使用して、組織内のゲスト ユーザーに関連する Teams コンテンツを検索できます。 ゲスト ユーザーに関連付けられている Teams チャット コンテンツは、クラウドベースの保存場所に保持され、電子情報開示を使用して検索できます。 これには、ゲスト ユーザーが組織内の他のユーザーとの参加者である 1:1 と 1:N のチャット会話でコンテンツを検索することが含まれます。 また、ゲスト ユーザーが参加者であるプライベート チャネル メッセージを検索し、ゲストユーザーのみがゲスト ユーザーである *ゲスト チャット* 会話でコンテンツを検索することもできます。

ゲスト ユーザーのコンテンツを検索するには:

1. Azure AD PowerShell に接続します。 手順については、「PowerShell を使用して Microsoft 365 に接続する」の「Azure Active Directory [PowerShell で接続する](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)」セクションを参照してください。 前の記事の手順 1 と手順 2 を必ず完了してください。

2. Azure AD PowerShell に正常に接続したら、次のコマンドを実行して、組織内のすべてのゲスト ユーザーのユーザー プリンシパル名 (UPN) を表示します。 手順 4. で検索を作成するときは、ゲスト ユーザーの UPN を使用する必要があります。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > コンピューター画面にユーザー プリンシパル名の一覧を表示する代わりに、コマンドの出力をテキスト ファイルにリダイレクトできます。 これを行うには、前の `> filename.txt` コマンドに追加します。 ユーザー プリンシパル名を含むテキスト ファイルは、現在のフォルダーに保存されます。

3. 別のWindows PowerShell ウィンドウで、Security & Compliance Center PowerShell に接続します。 手順については、「 [セキュリティ & コンプライアンス センター PowerShell への接続](/powershell/exchange/connect-to-scc-powershell)」を参照してください。 多要素認証の有無にかかわらず接続できます。

4. 次のコマンドを実行して、指定したゲスト ユーザーが参加者であったすべてのコンテンツ (チャット メッセージや電子メール メッセージなど) を検索するコンテンツ検索を作成します。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   たとえば、ゲスト ユーザーのサラ デビスに関連付けられているコンテンツを検索するには、次のコマンドを実行します。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    PowerShell を使用してコンテンツ検索を作成する方法の詳細については、「 [New-ComplianceSearch」を](/powershell/module/exchange/new-compliancesearch)参照してください。

5. 次のコマンドを実行して、手順 4. で作成したコンテンツ検索を開始します。

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. [**すべての** > **コンテンツ検索** の [https://compliance.microsoft.com](https://compliance.microsoft.com)表示] に移動してクリックします。

7. 検索の一覧で、手順 4. で作成した検索を選択してポップアップ ページを表示します。

8. ポップアップ ページでは、次の操作を行うことができます。

   - [ **結果の表示]** をクリックして検索結果を表示し、コンテンツをプレビューします。

   - **[クエリ**] フィールドの横にある **[編集]** をクリックして編集し、検索を再実行します。 たとえば、検索クエリを追加して結果を絞り込むことができます。

   - **[結果のエクスポート]** をクリックして、検索結果をエクスポートしてダウンロードします。

## <a name="search-for-card-content"></a>カード コンテンツを検索する

Teams チャネル、1 対 1 チャット、および 1xN チャットでアプリによって生成されたカード コンテンツは、メールボックスに格納され、検索できます。 *カード* は、短いコンテンツの UI コンテナーです。 カードには複数のプロパティと添付ファイルを含めることができます。また、カードアクションをトリガーできるボタンを含めることができます。 詳細については、「[カード](/microsoftteams/platform/task-modules-and-cards/what-are-cards)」を参照してください。

他の Teams コンテンツと同様に、カード コンテンツが保存される場所は、カードが使用された場所に基づいています。 Teams チャネルで使用されるカードのコンテンツは、Teams グループ メールボックスに格納されます。 1:1 および 1xN チャットのカード コンテンツは、チャット参加者のメールボックスに格納されます。

カード コンテンツを検索するには、検索条件を`itemclass:IPM.SkypeTeams.Message`使用`kind:microsoftteams`します。 検索結果を確認する場合、Teams チャネル内のボットによって生成されたカード コンテンツには Sender **/Author** 電子メール プロパティがあります。この`appname`プロパティ`<appname>@teams.microsoft.com`は、カード コンテンツを生成したアプリの名前です。 カードコンテンツがユーザーによって生成された場合、 **Sender/Author** の値はユーザーを識別します。

コンテンツ検索結果でカード コンテンツを表示すると、コンテンツはメッセージの添付ファイルとして表示されます。 添付ファイルの名前 `appname.html`は、 `appname` カード コンテンツを生成したアプリの名前です。 次のスクリーンショットは、Teams と検索結果にカード コンテンツ (Asana という名前のアプリの場合) がどのように表示されるかを示しています。

### <a name="card-content-in-teams"></a>Teams のカード コンテンツ

![Teams チャネル メッセージのカード コンテンツ。](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>検索結果のカード コンテンツ

![コンテンツ検索の結果と同じカード コンテンツ。](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> この時点で検索結果にカード コンテンツの画像 (前のスクリーンショットのチェックマークなど) を表示するには、検索結果の表示に使用するのと同じブラウザー セッションの別のタブで Teams に <https://teams.microsoft.com>サインインする必要があります。 それ以外の場合は、画像プレースホルダーが表示されます。

## <a name="ediscovery-in-federated-and-non-federated-environments"></a>フェデレーション環境と非フェデレーション環境での電子情報開示

管理者は、電子情報開示を使用して、次の制限に基づいて、フェデレーション ( *外部アクセス* と呼ばれる) および非フェデレーション ( *ゲスト アクセス*) 環境の Teams 会議のチャット メッセージ内のコンテンツを検索できます。

- **フェデレーション**: 組織のユーザーと外部組織のユーザー (組織内の外部アクセス権を持つユーザー) との Teams 会議では、両方の組織の管理者が会議のチャット メッセージ内のコンテンツを検索できます。

- **非フェデレーション**: 組織のユーザーとゲスト ユーザーとの Teams 会議では、Teams 会議をホストする組織内の管理者のみが、会議のチャット メッセージ内のコンテンツを検索できます。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 電子情報開示ソリューション](/microsoft-365/compliance/ediscovery)
- [電子情報開示の概要 (Standard)](/microsoft-365/compliance/get-started-core-ediscovery)
- [電子情報開示の Teams ワークフロー (Premium)](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams PowerShell の概要](teams-powershell-overview.md)
