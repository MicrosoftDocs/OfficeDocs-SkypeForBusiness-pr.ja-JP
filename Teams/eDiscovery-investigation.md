---
title: コンテンツの電子情報開示調査を実施する
description: 電子情報開示を実行する必要がある場合 (法的手続きのために電子的に保存されたすべての情報を送信する必要がある場合など) について説明します。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- ediscovery
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8a9e7afdf55fbcb85dcbbf907ef974a62e4e8492
ms.sourcegitcommit: 86b9503eb0085e23176cb346767f880ea3a73e77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2022
ms.locfileid: "68808296"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams のコンテンツに対して電子情報開示の調査を行う

大企業は、多くの場合、すべての電子的に保存された情報(ESI)の提出を要求する高いペナルティ訴訟手続きにさらされます。 Microsoft Teams コンテンツは、電子情報開示の調査中に検索して使用できます。

## <a name="overview"></a>概要

すべての Microsoft Teams 1:1 またはグループ チャットは、それぞれのユーザーのメールボックスにジャーナル処理されます。 すべての標準チャネル メッセージは、チームを表すグループ メールボックスにジャーナル処理されます。 標準チャネルでアップロードされたファイルは、SharePoint Online とOneDrive for Businessの電子情報開示機能の対象となります。

[プライベート チャネル](private-channels.md)でのメッセージとファイルの電子情報開示は、標準チャネルとは異なる方法で動作します。 詳細については、「 [プライベート チャネルの電子情報開示](#ediscovery-of-private-and-shared-channels)」を参照してください。

すべての Teams コンテンツが eDiscoverable であるわけではありません。 次の表は、Microsoft 電子情報開示ツールを使用して検索できるコンテンツ タイプを示しています。

|**コンテンツの種類**|**メモ**|
|:---------------|:--------|
|録音||
|カードコンテンツ|詳細については、「 [カード コンテンツを検索する](#search-for-card-content) 」を参照してください。|
|チャット リンク||
|チャット メッセージ|これには、標準の Teams チャネルのコンテンツ、1:1 チャット、1:N グループ チャット、ゲスト ユーザー参加者とのチャットが含まれます。|
|コード スニペット||
|編集されたメッセージ|ユーザーが保留状態の場合は、以前のバージョンの編集済みメッセージも保持されます。|
|絵文字、GIF、ステッカー||
|インライン イメージ||
|ループ コンポーネント|ループ コンポーネント内のコンテンツは、ループ コンポーネントを送信するユーザーのOneDrive for Business アカウントに格納されている .fluid ファイルに保存されます。 つまり、ループ コンポーネント内のコンテンツを検索するときに、OneDrive をデータ ソースとして含める必要があります。|
|会議 IM の会話||
|会議メタデータ<sup>1</sup>||
|チャネルの名前||
|引用符|引用符で囲まれたコンテンツは検索可能です。 ただし、検索結果は、コンテンツが引用符で囲まれたことを示していません。|
|反応 (いいね、心、その他の反応など)|リアクションは、2022 年 6 月 1 日以降、すべての商用顧客に対してサポートされます。 この日付より前のリアクションは、電子情報開示では使用できません。 拡張された反応がサポートされるようになりました。 反応履歴を理解するには、コンテンツが法的に保留されている必要があります。|
|件名||
|テーブル||
|Teams ビデオ クリップ (TVC)|"Video-Clip" キーワードで TVC を検索し、プレビューを右クリックして各 TVC 添付ファイルの.mp4 ファイルを "名前を付けて保存" します (キーワードによる検索は 2022 年 10 月に利用可能になります)。 TVC データは、電子情報開示 [レビュー セット](/microsoft-365/compliance/add-data-to-review-set)で検出できます。

<a name="teams-metadata"></a><sup>1</sup> 会議 (および通話) メタデータには、次のものが含まれます。

- 会議の開始時刻と終了時刻、および期間
- 各参加者の会議参加イベントと退席イベント
- VOIP 参加/呼び出し
- 匿名結合
- フェデレーション ユーザー参加
- ゲスト ユーザー参加

会議中の参加者間のチャット会話の例を次に示します。

![Teams の参加者間の会話。](media/MeetingIMConversations.png)

電子情報開示ツールで表示されたのと同じチャット会話のコンプライアンス コピーの例を次に示します。

![電子情報開示検索結果の参加者間の会話。](media/MeetingImConversation2.png)

会議メタデータの例を次に示します。

![コンプライアンス コピーからの会議メタデータ。](media/conversationOption3.png)

電子情報開示調査の実施の詳細については、「電子情報開示 [の概要 (Standard)」](/microsoft-365/compliance/get-started-core-ediscovery)を参照してください。

Microsoft Teams データは、Excel 電子情報開示エクスポート出力に IM または会話として表示されます。 Outlook でファイルを `.pst` 開き、エクスポート後にそれらのメッセージを表示できます。

チームの .pst ファイルを表示すると、すべての会話が [会話履歴] の [チーム チャット] フォルダーに配置されます。 メッセージのタイトルには、チーム名とチャネル名が含まれています。 たとえば、次の図は、製造スペック チームの Project 7 標準チャネルにメッセージを送信した Bob からのメッセージを示しています。

![Outlook のユーザーのメールボックス内のチーム チャット フォルダーのスクリーンショット。](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

ユーザーのメールボックス内のプライベート チャットは、[会話の履歴] の [チーム チャット] フォルダーに格納されます。

## <a name="ediscovery-of-private-and-shared-channels"></a>プライベートチャネルと共有チャネルの電子情報開示

プライベート チャネルと共有チャネル内のメッセージのコンプライアンス コピーは、チャネルの種類に応じて異なるメールボックスに送信されます。 つまり、ユーザーがメンバーになっているチャネルの種類に基づいて、さまざまなメールボックスの場所を検索する必要があります。

- **プライベート チャネル**。 コンプライアンス コピーは、プライベート チャネル メンバーのすべてのメンバーのメールボックスに送信されます。 つまり、プライベート チャネル メッセージ内のコンテンツを検索するときは、ユーザー メールボックスを検索する必要があります。

- **共有チャネル**。 コンプライアンス コピーは、親チームに関連付けられているシステム メールボックスに送信されます。 Teams は共有チャネルの単一のシステム メールボックスの電子情報開示検索をサポートしていないため、共有チャネルでメッセージ コンテンツを検索する場合は、(チーム メールボックスの名前を選択して) 親チームのメールボックスを検索する必要があります。

各プライベート チャネルと共有チャネルには、親チーム サイトとは別の独自の SharePoint サイトがあります。 つまり、プライベート チャネルと共有チャネル内のファイルは、独自のサイトに格納され、親チームとは別に管理されます。 つまり、ファイルとチャネル メッセージの添付ファイル内のコンテンツを検索するときに、チャネルに関連付けられている特定のサイトを特定して検索する必要があります。

電子情報開示検索に含めるプライベート チャネルまたは共有チャネルを特定するには、次のセクションを使用します。

### <a name="identifying-the-members-of-a-private-channel"></a>プライベート チャネルのメンバーの識別

このセクションの手順を使用してプライベート チャネルのメンバーを特定し、電子情報開示ツールを使用して、メンバーのメールボックスでプライベート チャネル メッセージ内のコンテンツを検索できるようにします。

これらの手順を実行する前に、 [最新バージョンの Teams PowerShell モジュールが](teams-powershell-overview.md) インストールされていることを確認してください。

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

3. 次のコマンドを実行して、特定のプライベート チャネルのプライベート チャネル所有者とメンバーの一覧を取得します。

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. 電子 [情報開示 (Standard) の電子情報開示検索クエリ](/microsoft-365/compliance/search-for-content-in-core-ediscovery) の一部として、または電子情報開示 [(Premium) でカストディアン コンテンツを識別して収集する](/microsoft-365/compliance/add-custodians-to-case)場合は、所有者とプライベート チャネルのメンバーのメールボックスを含めます。

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>プライベート チャネルと共有チャネルの SharePoint サイトの識別

前に説明したように、プライベート チャネルと共有チャネルで共有されているファイル (およびチャネル メッセージに添付されたファイル) は、チャネルに関連付けられているサイト コレクションに格納されます。 このセクションの手順を使用して、特定のプライベート チャネルまたは共有チャネルに関連付けられているサイトの URL を特定します。 その後、電子情報開示ツールを使用して、サイト内のコンテンツを検索できます。

これらの手順を実行する前 [に、SharePoint Online 管理シェルをインストールし、SharePoint Online に接続します](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

1. 必要に応じて、次を実行して、親チームの共有チャネルに関連付けられているすべての SharePoint サイト コレクションの一覧を取得します。

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > プライベート チャネルと共有チャネルに関連付けられているサイトの URL の名前付け規則は です `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`。 たとえば、Contoso 組織の "エンジニア チーム" 親チームにある "パートナー コラボレーション" という名前の共有チャネルの URL は です `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`。

2. 次の PowerShell コマンドを実行して、組織内のプライベート チャネルと共有チャネルに関連付けられているすべての SharePoint サイトの URL を表示します。 スクリプトの出力には親チームのグループ ID も含まれています。これは、手順 3 でコマンドを実行する必要があります。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > 2021 年 6 月 28 日より前に作成されたプライベート チャネルの SharePoint サイトでは、カスタム テンプレート ID の値 `"TEAMCHANNEL#0"` を使用します。 この日付以降に作成されたプライベート チャネルを表示するには、前の 2 つのスクリプトを実行するときに 値 `"TEAMCHANNEL#1"` を使用します。 共有チャネルでは、 の `"TEAMCHANNEL#1"`値のみが使用されます。

3. 親チームごとに、次の PowerShell コマンドを実行して、プライベートおよび共有チャネル サイトを識別します。ここで `$groupID` 、親チームのグループ ID を指定します。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. 電子 [情報開示 (Standard) の電子情報開示検索クエリ](/microsoft-365/compliance/search-for-content-in-core-ediscovery) の一部として、または電子情報開示 [(Premium) でカストディアン コンテンツを特定して収集するときに](/microsoft-365/compliance/add-custodians-to-case)、プライベートまたは共有チャネルに関連付けられているサイトを含めます。

## <a name="search-for-content-for-guest-users"></a>ゲスト ユーザーのコンテンツを検索する

電子情報開示ツールを使用して、組織内のゲスト ユーザーに関連する Teams コンテンツを検索できます。 ゲスト ユーザーに関連付けられている Teams チャット コンテンツは、クラウドベースのストレージの場所に保持され、電子情報開示を使用して検索できます。 これには、ゲスト ユーザーが組織内の他のユーザーとの参加者である 1:1 と 1:N のチャット会話でコンテンツを検索することが含まれます。 また、ゲスト ユーザーが参加者であるプライベート チャネル メッセージを検索し、ゲスト ユーザーのみがゲスト ユーザーである *guest:guest* チャット会話のコンテンツを検索することもできます。

ゲスト ユーザーのコンテンツを検索するには:

1. Azure AD PowerShell に接続します。 手順については、「PowerShell を使用して [Microsoft 365 に接続する」の「Azure Active Directory PowerShell を使用して接続する](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)」セクションを参照してください。 前の記事の手順 1 と手順 2 を必ず完了してください。

2. Azure AD PowerShell に正常に接続したら、次のコマンドを実行して、組織内のすべてのゲスト ユーザーのユーザー プリンシパル名 (UPN) を表示します。 手順 4 で検索を作成するときは、ゲスト ユーザーの UPN を使用する必要があります。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > コンピューター画面にユーザー プリンシパル名の一覧を表示する代わりに、コマンドの出力をテキスト ファイルにリダイレクトできます。 これを行うには、前のコマンドにを `> filename.txt` 追加します。 ユーザー プリンシパル名を持つテキスト ファイルは、現在のフォルダーに保存されます。

3. 別のWindows PowerShell ウィンドウで、Security & Compliance Center PowerShell に接続します。 手順については、「 [Security & Compliance Center PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)」を参照してください。 多要素認証を使用して、または使用せずに接続できます。

4. 次のコマンドを実行して、指定したゲスト ユーザーが参加していたすべてのコンテンツ (チャット メッセージや電子メール メッセージなど) を検索するコンテンツ検索を作成します。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   たとえば、ゲスト ユーザーの Sara Davis に関連付けられているコンテンツを検索するには、次のコマンドを実行します。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    PowerShell を使用してコンテンツ検索を作成する方法の詳細については、「 [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)」を参照してください。

5. 次のコマンドを実行して、手順 4 で作成したコンテンツ検索を開始します。

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. に [https://compliance.microsoft.com](https://compliance.microsoft.com) 移動し、[ **すべての** > **コンテンツ検索** を表示] を選択します。

7. 検索の一覧で、手順 4 で作成した検索を選択してポップアップ ページを表示します。

8. ポップアップ ページでは、次のことを実行できます。

   - [ **結果の表示]** を選択して検索結果を表示し、コンテンツをプレビューします。

   - **[クエリ**] フィールドの横にある **[編集]** を選択して編集し、検索を再実行します。 たとえば、検索クエリを追加して結果を絞り込むことができます。

   - [ **結果のエクスポート]** を選択して、検索結果をエクスポートしてダウンロードします。

## <a name="search-for-card-content"></a>カード コンテンツを検索する

Teams チャネル、1:1 チャット、1xN チャットのアプリによって生成されたカード コンテンツはメールボックスに格納され、検索できます。 *カード* は、短いコンテンツの UI コンテナーです。 カードには、複数のプロパティと添付ファイルを含め、カードアクションをトリガーできるボタンを含めることができます。 詳細については、「[カード](/microsoftteams/platform/task-modules-and-cards/what-are-cards)」を参照してください。

他の Teams コンテンツと同様に、カード コンテンツが格納される場所は、カードが使用された場所に基づいています。 Teams チャネルで使用されるカードのコンテンツは、Teams グループ メールボックスに格納されます。 1:1 および 1xN チャットのカード コンテンツは、チャット参加者のメールボックスに格納されます。

カード コンテンツを検索するには、 または `itemclass:IPM.SkypeTeams.Message` 検索条件を`kind:microsoftteams`使用できます。 検索結果を確認する場合、Teams チャネルのボットによって生成されたカード コンテンツには、 **Sender/Author** 電子メール プロパティが として `<appname>@teams.microsoft.com`設定されます。ここで `appname` 、 はカード コンテンツを生成したアプリの名前です。 カード コンテンツがユーザーによって生成された場合、 **Sender/Author** の値によってユーザーが識別されます。

コンテンツ検索結果でカード コンテンツを表示すると、コンテンツがメッセージの添付ファイルとして表示されます。 添付ファイルの名前 `appname.html`は です。ここで `appname` 、カード コンテンツを生成したアプリの名前です。 次のスクリーンショットは、(Asana という名前のアプリの) カード コンテンツが Teams と検索結果にどのように表示されるかを示しています。

### <a name="card-content-in-teams"></a>Teams のカード コンテンツ

![Teams チャネル メッセージのカード コンテンツ。](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>検索結果のカード コンテンツ

![コンテンツ検索の結果と同じカード コンテンツ。](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> この時点でカード コンテンツの画像 (前のスクリーンショットのチェックマークなど) を検索結果に表示するには、検索結果を表示するために使用するのと同じブラウザー セッションの別のタブで Teams (at <https://teams.microsoft.com>) にサインインする必要があります。 それ以外の場合は、画像プレースホルダーが表示されます。

## <a name="ediscovery-in-federated-and-non-federated-environments"></a>フェデレーション環境と非フェデレーション環境での電子情報開示

管理者は、電子情報開示を使用して、次の制限に基づいて、フェデレーション ( *外部アクセス* と呼ばれる) 環境と非フェデレーション ( *ゲスト アクセス* と呼ばれる) 環境で Teams 会議のチャット メッセージ内のコンテンツを検索できます。

- **フェデレーション**: 組織のユーザーと外部組織のユーザー (組織内の外部アクセス権を持つ) との Teams 会議では、両方の組織の管理者は、会議からチャット メッセージ内のコンテンツを検索できます。

- **非フェデレーション**: 組織のユーザーとゲスト ユーザーとの Teams 会議では、Teams 会議をホストする組織内の管理者のみが、会議のチャット メッセージ内のコンテンツを検索できます。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 電子情報開示ソリューション](/microsoft-365/compliance/ediscovery)
- [電子情報開示の概要 (Standard)](/microsoft-365/compliance/get-started-core-ediscovery)
- [電子情報開示 (Premium) の Teams ワークフロー](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams PowerShell の概要](teams-powershell-overview.md)
