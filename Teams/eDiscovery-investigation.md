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
description: 法的手続きのために電子的に保存された情報を送信する必要がある場合など、電子情報開示を実行する必要がある場合の操作について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980461"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams のコンテンツに対して電子情報開示の調査を行う

大企業は、電子的に保存された情報 (ESI) の提出を要求する高いペナルティ法的手続きにさらされる場合が多いです。 Microsoft Teams のコンテンツは、電子情報開示の調査中に検索して使用できます。

## <a name="overview"></a>概要

すべての Microsoft Teams 1 対 1 またはグループ チャットは、各ユーザーのメールボックスにジャーナル処理されます。 すべての標準チャネル メッセージは、チームを表すグループ メールボックスにジャーナリングされます。 標準チャネルでアップロードされたファイルは、SharePoint Online と OneDrive for Business の電子情報開示機能の下で扱います。

プライベート チャネル内のメッセージとファイルの電子情報開示は [、](private-channels.md) 標準チャネルとは異なる方法で動作します。 詳細については、「プライベート チャネル [の電子情報開示」を参照してください](#ediscovery-of-private-channels)。

すべての Teams コンテンツが eDiscoverable という訳ではありません。 次の表に、Microsoft 電子情報開示ツールを使用して検索できるコンテンツ タイプを示します。

| コンテンツの種類 | eDiscoverable | 備考 |
|:--- | :--- |:--- |
|オーディオ録音 | いいえ | |
|カードの内容|はい|詳細 [については、「カードのコンテンツを検索する](#search-for-card-content) 」を参照してください。|
|チャット リンク | はい | |
|チャット メッセージ | はい |これには、Teams チャネルのコンテンツ、1 対 1 のチャット、1:N グループ チャット、ゲスト ユーザーの参加者とのチャットが含まれます。  |
|コード スニペット | いいえ | |
|編集したメッセージ | はい | ユーザーが保留にされている場合、以前のバージョンの編集されたメッセージも保持されます。 |
|絵文字、GIF、ステッカー | はい | |
|インライン画像 | はい | |
|会議の IM 会話 | はい | |
|会議のメタデータ<sup>1</sup> | はい |  |
|チャネルの名前 | いいえ | |
|プライベート チャネル メッセージ | はい | |
|見積もり | はい | 引用符で囲まれたコンテンツは検索可能です。 ただし、検索結果は、コンテンツが引用されたというわけではありません。 |
|リアクション ("良い"、"ハート"、"その他のリアクション" など) | いいえ | |
|件名 | はい | |
|テーブル | はい | |
|||

<sup>1 つの</sup> 会議 (および通話) メタデータには、次が含まれます。

- 会議の開始時刻と終了時刻、および期間
- 各参加者の会議への参加と退出のイベント
- VOIP の参加/通話
- 匿名参加
- フェデレーション ユーザーの参加
- ゲスト ユーザーの参加

  この画像は、会議のメタデータの例を示しています。

  > [!div class="mx-imgBorder"]
  > ![画像は、CVR レコードの会議メタデータの画像です。](media/conversationOption3.png)

会議中の参加者間の IM 会話の例を次に示します。

![Teams の参加者間の会話。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![電子情報開示検索結果の参加者間の会話。](media/MeetingImConversation2.png)

電子情報開示調査の実施の詳細については、「コア電子情報開示の使用を開始する [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)。

Microsoft Teams のデータは、Excel の電子情報開示エクスポート出力に IM またはスレッドとして表示されます。 Outlook でファイルを `.pst` 開き、エクスポート後にそれらのメッセージを表示できます。

チームの .pst ファイルを表示すると、すべての会話は [会話履歴] の [チーム チャット] フォルダーに保持されます。 メッセージのタイトルには、チーム名とチャネル名が含まれている。 たとえば、次の画像は、製造仕様チームの Project 7 標準チャネルにメッセージを送信した Bob からのメッセージを示しています。

![Outlook のユーザーのメールボックス内のチーム チャット フォルダーのスクリーンショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

ユーザーのメールボックス内のプライベート チャットは、[会話履歴] の下の [チーム チャット] フォルダーに保存されます。

## <a name="ediscovery-of-private-channels"></a>プライベート チャネルの電子情報開示

プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。 レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。

各プライベート チャネルには、親チーム サイトとは別の独自の SharePoint サイトが用意されています。プライベート チャネル内のファイルは、親チームとは独立して管理されます。

Teams は、チーム内の 1 つのチャネルの電子情報開示検索をサポートしないので、チーム全体を検索する必要があります。 プライベート チャネル内のコンテンツの電子情報開示検索を実行するには、チーム、プライベート チャネルに関連付けられているサイト コレクション (ファイルを含める)、プライベート チャネル メンバーのメールボックス (メッセージを含める) を検索します。

次の手順を使用して、電子情報開示検索に含めるプライベート チャネル内のファイルとメッセージを識別します。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>電子情報開示検索にプライベート チャネル ファイルを含める

これらの手順を実行する前に、SharePoint Online 管理シェルをインストールし [、SharePoint Online に接続します](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

1. チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクションの一覧を取得するには、次を実行します。

    ```PowerShell
    Get-SPOSite
    ```

2. 次の PowerShell スクリプトを実行して、チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクション URL と親チーム グループ ID の一覧を取得します。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. チームまたはグループ ID ごとに、次の PowerShell スクリプトを実行して、関連するすべてのプライベート チャネル サイトを特定します。$groupID はチームのグループ ID です。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>電子情報開示検索にプライベート チャネル メッセージを含める

これらの手順を実行する前に、最新バージョンの [Teams PowerShell モジュールがインストールされていることを確認](teams-powershell-overview.md) します。

1. 次のコマンドを実行して、チーム内のプライベート チャネルの一覧を取得します。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 次のコマンドを実行して、プライベート チャネル メンバーの一覧を取得します。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. 電子情報開示検索クエリの一部として、チームの各プライベート チャネルのすべてのメンバーの [メールボックスを含める](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)。

## <a name="search-for-content-for-guest-users"></a>ゲスト ユーザーのコンテンツを検索する

電子情報開示ツールを使用して、組織内のゲスト ユーザーに関連する Teams コンテンツを検索できます。 ゲスト ユーザーに関連付けられている Teams チャット コンテンツは、クラウドベースの保存場所に保持され、電子情報開示を使用して検索できます。 これには、ゲスト ユーザーが組織内の他のユーザーとの参加者である 1 対 1 と 1:N のチャット会話のコンテンツの検索が含まれます。 ゲスト ユーザーが参加者であるプライベート チャネル メッセージを検索し、ゲスト *と* ゲスト チャットの会話のコンテンツを検索することもできます。ゲスト ユーザーはゲスト ユーザーのみです。

ゲスト ユーザーのコンテンツを検索するには:

1. Azure AD PowerShell に接続します。 手順については、「PowerShell で Microsoft 365 に接続する」の「Azure Active Directory PowerShell で接続する [」セクションを参照してください](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。 前のトピックの手順 1 と手順 2 を必ず完了してください。

2. Azure AD PowerShell に正常に接続したら、次のコマンドを実行して、組織内のすべてのゲスト ユーザーのユーザー プリンシパル名 (UPN) を表示します。 手順 4 で検索を作成する場合は、ゲスト ユーザーの UPN を使用する必要があります。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > コンピューター画面にユーザー プリンシパル名のリストを表示する代わりに、コマンドの出力をテキスト ファイルにリダイレクトできます。 この操作を行うには、前の `> filename.txt` コマンドに追加します。 ユーザー プリンシパル名を含むテキスト ファイルは、現在のフォルダーに保存されます。

3. 別のウィンドウWindows PowerShell、セキュリティ/コンプライアンス センターの PowerShell &接続します。 手順については、「セキュリティ/コンプライアンス [センター PowerShell への&を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。 多要素認証を使用するか、または使用せずに接続できます。

4. 指定したゲスト ユーザーが参加者だったすべてのコンテンツ (チャット メッセージやメール メッセージなど) を検索するコンテンツ検索を作成するには、次のコマンドを実行します。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   たとえば、ゲスト ユーザー Sara Davis に関連付けられているコンテンツを検索するには、次のコマンドを実行します。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    PowerShell を使用してコンテンツ検索を作成する方法の詳細については [、「New-ComplianceSearch」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)。

5. 次のコマンドを実行して、手順 4 で作成したコンテンツ検索を開始します。

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. [すべてのコンテンツ [https://compliance.microsoft.com](https://compliance.microsoft.com) 検索を表示] に  >  **移動し、[すべてのコンテンツ検索を表示] をクリックします**。

7. 検索の一覧で、手順 4 で作成した検索を選択して、フライアウト ページを表示します。

8. フライアウト ページでは、次の操作を行います。

   - [ **結果の表示]** をクリックして検索結果を表示し、コンテンツをプレビューします。

   - [クエリ] **フィールドの横** にある [編集] を **クリック** して編集し、検索を再実行します。 たとえば、検索クエリを追加して結果を絞り込むなどです。

   - [ **結果のエクスポート] を** クリックして、検索結果をエクスポートしてダウンロードします。

## <a name="search-for-card-content"></a>カードコンテンツを検索する

Teams チャネルのアプリ、1 対 1 のチャット、1xN チャットによって生成されたカード コンテンツはメールボックスに保存され、検索できます。 カード *は* 、短いコンテンツの UI コンテナーです。 カードには複数のプロパティと添付ファイルを含め、カードの操作をトリガーできるボタンを含めることができます。 詳細については、「カード」を [参照してください。](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)

他の Teams コンテンツと同様に、カードコンテンツが保存される場所は、カードが使用された場所に基づいて行います。 Teams チャネルで使用されるカードのコンテンツは、Teams グループ メールボックスに保存されます。 1 対 1 および 1xN のチャットのカード コンテンツは、チャット参加者のメールボックスに保存されます。

カードのコンテンツを検索するには、または検索条件 `kind:microsoftteams` を `itemclass:IPM.SkypeTeams.Message` 使用できます。 検索結果を確認すると、Teams チャネルのボットによって生成されたカード コンテンツには、送信者 **/** 作成者のメール プロパティがあります。カード コンテンツを生成したアプリの名前です `<appname>@teams.microsoft.com` `appname` 。 カードコンテンツがユーザーによって生成された場合、 **送信者/作成者の** 値によってユーザーが識別されます。

コンテンツ検索結果でカードコンテンツを表示すると、そのコンテンツはメッセージの添付ファイルとして表示されます。 添付ファイルの名前 `appname.html` は、 `appname` カードコンテンツを生成したアプリの名前です。 次のスクリーンショットは、カードコンテンツ (Asana という名前のアプリの場合) が Teams および検索の結果に表示される方法を示しています。

**Teams のカード コンテンツ**

![Teams チャネル メッセージのカード コンテンツ](media/CardContentTeams.png)

**検索結果のカード コンテンツ**
  
![コンテンツ検索の結果と同じカード コンテンツ](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 現時点でカードコンテンツの画像を検索結果に表示するには (前のスクリーンショットのチェックマークなど)、Teams にサインインする必要があります (検索結果の表示に使用したのと同じブラウザー セッションの別のタブで)。 https://teams.microsoft.com) それ以外の場合は、画像のプレースホルダーが表示されます。

## <a name="advanced-ediscovery"></a>Advanced eDiscovery

一部の Microsoft Teams コンテンツは、Advanced eDiscovery ワークフローを使用して検索 [および保持できます](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。 電子情報開示にはさまざまな検索、保留、エクスポート機能が含まれていますが、Advanced eDiscovery では、コンプライアンス管理者がデータ ソースを特定し、その内容を分析するためのより多くのツールを提供します。

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Teams コンテンツの高度な電子情報開示カストディアン ワークフロー

カストディアンは、さまざまなチームのメンバーである可能性があります。 これらのカストディアンに関連する Teams コンテンツをキャプチャできます。 カストディアン ワークフローの手順については、「Advanced eDiscovery ケースにカストディアンを追加する [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。

カストディアンを追加したら、[次へ] ボタンを **クリック** し、[追加] ボタン **をクリック** します。 ウィンドウが表示され、追加の場所を選択するように求めるメッセージが表示されます。このウィンドウには、カストディアンのすべてのメンバーシップとそのデータに対応する SharePoint サイトの場所が表示されます。 これらのすべてのデータ ソースとチームから、電子情報開示に使用するコンテンツを選択し、そのユーザーと、特定したすべてのデータ ソースを保留にできます。

Exchange コンテンツ、OneDrive コンテンツ、または両方を含めるかどうかを選択できます。 Exchange コンテンツには、ユーザーのメールボックス内のすべてのアプリケーション コンテンツ (メール、メールボックスに保存されている Teams コンテンツなど) が含まれます。 OneDrive のコンテンツには、ユーザーのコンテンツだけでなく、1 対 1 のチャット、1:N チャット、チャットで共有されているファイルなど、OneDrive に保存されている Teams のすべてのコンテンツも含まれます。

また、カストディアンがメンバーであるチームを関連付け、カストディアンがアクセスできるチャネル チャット メッセージとファイルを含めることもできます。 さらに、他のすべてのチームをカストディアンと関連付けできます。

> [!NOTE]
> プライベート チャネル内のメッセージとファイルの電子情報開示は [、](private-channels.md) 標準チャネルとは異なる方法で動作します。 詳細については、「プライベート チャネル [の電子情報開示」を参照してください](#ediscovery-of-private-channels)。

### <a name="placing-a-data-source-on-hold"></a>データ ソースを保留する

カストディアンとして指定する特定のユーザーがない場合は、データ ソース全体を保留にできます。 保留の詳細については、「Advanced eDiscovery で保留を管理する [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。

Teams コンテンツの保留リストを作成する場合は、保留に含めるすべての場所を選択できます。 ユーザーがコンテンツを削除または変更している場合でも、保留すると、そのコンテンツのすべての以前のバージョンのコピーが保持されます。

オプションのクエリを使用して、キーワード、日付範囲、作成者、その他の多くの条件に基づいて保留の条件を設定することもできます。 キーワードを指定しない場合、そのデータ ソースのすべての内容が保留の対象と見なされます。

### <a name="advanced-ediscovery-searches"></a>高度な電子情報開示検索

Teams のコンテンツも検索できます。 検索の詳細については [、「Advanced eDiscovery でケースのデータを収集する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。 1 つのメッセージが検索クエリと一致する場合でも、検索は会話全体を返します。

検索クエリを作成するときに、既に選択しているすべてのソースが検索されるカストディアンを選択できます。 また、ユーザーにマップされていない Teams サイトなど、管理者以外のソースを検索できます。 Teams コンテンツ内の検索を絞り込むには、オプションのクエリも使用できます。

検索を作成して選択すると、ウィンドウが表示され、選択した検索に対して実行できる追加の詳細とアクションが表示されます。 [統計情報]ボタンをクリックすると、場所の種類、コンテンツの元のソースに応じて内訳が表示され、コンテンツがグループ メールボックス、個々のユーザー メールボックス、または SharePoint サイトにあるかどうかなど、検索に関する統計情報を表示できます。 したがって、どのソースが検索結果に貢献しているのかの内訳を確認できます。 また、クエリ ビュー **も** 利用できます。クエリ ビューでは、結果にどのキーワードが関連付けられているのか確認できます。

検索を完了した後、[結果をレビュー セットに追加] ボタンをクリックし、レビュー セットに追加できます。 レビュー セットの詳細については、この記事の後半にある [「Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) ワークフローと [レビュー](#review-sets-workflow) セット ワークフローでレビュー セットを管理する」を参照してください。

#### <a name="normal-review-sets-and-conversation-review-sets"></a>標準レビュー セットとスレッド レビュー セット

レビュー セットに検索を追加する場合は、通常のレビュー セットまたは会話レビュー セットから選択できます。

通常のレビュー セットはエクスポートに似ています。Teams コンテンツの `.msg` 個々のファイルが提供され、基本的なビューでコンテンツが表示されます。 通常、他のソフトウェア ツールを使用して後でファイルを再処理する場合は、通常のレビュー セットを使用します。

会話レビュー セットは、会話のより直感的でスレッド化されたビューを提供します。関連するメッセージが適切な順序でまとめて表示されます。

> [!div class="mx-imgBorder"]
> ![会話レビュー セットのスクリーンショット](media/conversationOptions2.png)

やり直しなどの機能は、両方の種類のレビュー セットで使用できます。 レビュー セットの詳細については、「Advanced eDiscovery での会話 [のレビュー」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)。

#### <a name="collection-options"></a>コレクション オプション

レビュー セットに追加する場合、ウィンドウの [コレクション オプション]セクションのチェック ボックスとして、[会話の取得オプション] や [Teams の会話] など、いくつかの **オプションを****使用できます**。 これらのオプションを有効にした場合、レビュー セットの一部である個々の Teams メッセージも、コンテキストのためにそれらを囲む追加のメッセージと一緒に表示されます。 たとえば、クエリが特定であり、結果として 1 つのメッセージだけが返される場合、これらのオプションを有効にすると、クエリに一致したメッセージの後に続く複数のメッセージも返されます。

多くの論理条件は、追加のメッセージがクエリに一致するメッセージにコンテキストを提供するかどうかを判断するために使用されます。 たとえば、Teams コンテンツの場合、これらのオプションを有効にすると、メッセージのスレッド化方法のために、親メッセージとすべての子メッセージが取得されます。

メッセージのタイム スタンプもチェックされます。 メッセージがクエリと一致する場合、メッセージの前に 4 時間の範囲にあるか、4 時間以内に続く隣接するメッセージは会話の一部であると見なされ、結果にも含まれます。

検索クエリに一致するコンテキスト メッセージを確実に返す必要がある場合は、これらのオプションを使用する必要があります。 すべてのコンテンツを収集するか、検索の日付範囲を広くして、クエリの結果として返されるメッセージを追加できます。

### <a name="review-sets-workflow"></a>レビュー セットワークフロー

既存のレビュー セットを表示したり、[レビュー セット] タブをクリックして新しい **レビュー セットを作成** することができます。レビュー セットの詳細については、「Advanced eDiscovery でレビュー セットを管理 [する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。

ドキュメントに加えて、メール、Teams メッセージ、Yammer、その他のコンテンツをレビュー セットに追加できます。 レビュー セット内では、コンテンツの検索やカスタム クエリの作成など、他のコンテキストで実行できる操作の多くを実行できます。 これらの操作は、レビュー セットに追加されたアイテムにのみ適用されます。

[ **レビュー セットの管理** ] ボタンには、分析、サマリー レポート、追加されたロード セットの数などの追加オプションが表示されます。

データの視覚エフェクトやグラフにアクセスするには、右上にある [個々の **結果** の \> 検索] プロファイル ビューをクリックします。 これらのグラフのくさび形をクリックすると、クエリを実行するコンテンツの種類を対話的に選択できます。 たとえば、Teams のコンテンツにのみクエリを実行できます。 手動で作成したクエリを保存するのと同じ方法で、これらのクエリを保存することもできます。

#### <a name="summary-view-text-view-and-annotate-view"></a>概要ビュー、テキスト ビュー、注釈ビュー

レビュー セットで Teams の会話をクリックすると、[概要]ビューが表示され、Teams の会話全体が個別にやり取りできるメッセージの一覧として表示されます。 メッセージの右側にある下向き矢印をクリックすると、メッセージの詳細を表示したり、個々のファイルをダウンロードしたりできるコンテキスト メニューが表示 `.msg` されます。 メッセージの詳細をクリックすると、メタデータの概要またはメッセージの完全なメタデータが表示されます。

PDF をダウンロードするには、概要ビューの右上にあるダウンロード ボタンをクリックします。

[テキスト **ビュー] タブを** クリックして、Teams の会話の抽出されたテキストのプレーン テキスト ビューを表示します。 このテキスト形式のコンテンツはエクスポートに適しています。他のソフトウェア ツールを使用して簡単に作業できます。

コメント機能にアクセス **するには、[注釈ビュー** ] タブをクリックします。 このタブには、Teams の会話に似た形式でコンテンツが表示されますが、編集するためのその他のオプションがあります。 鉛筆ツールを使用して、メモを作成したり、メッセージに描画したり、やり直しのために細かいスクラッチを行う場合に使用できます。 また、 **領域を黒** くして "赤字" とマークする四角形を描画するために使用できる領域の再編集ツールもあります。

次に、ユーザー間のスレッド化された会話に対して、ファイルが機能し直した例を示します。

> [!div class="mx-imgBorder"]
> ![破損したファイルのスクリーンショット](media/RedactedFileExample.png)

[注釈ビュー] **タブの** 下部には、[タグ **付** けドキュメント] ボタンが表示され、タグ付けパネルが表示されます。 このパネル内で、Teams の会話内のすべてのメッセージにタグを適用できます。 会話に "興味を持つアイテム" が含まれているかどうか、エクスポートに含める必要があるかどうか、さらに確認する必要があるかどうかなど、応答型または非応答型、特権付き、または特権ではない会話としてラベルを付けできます。 その他のカスタマイズ可能なタグを管理して適用することもできます。

#### <a name="action-menu"></a>アクション メニュー

[レビュー セット] ウィンドウ内で、[アクション エクスポート] をクリックしてコンテンツ **をエクスポート** \> **できます**。 エクスポート時には、多くのオプションを使用できます。

すべての Teams メッセージのすべてのメタデータを含むファイルをエクスポートするには、[ファイルの読み込み] チェック ボックス **をオンにします** 。 コンテンツに適用したタグをファイルに含めるには、[タグ] チェック ボックスを **オン** にします。

[ネイティブ ファイル **] オプションを** 使用して、ネイティブ形式でファイルをエクスポートします。 1 つの会話を 1 つのファイルとしてエクスポートするか、個別のファイル内のすべてのチャット メッセージとしてエクスポートすることができます。

[ **テキスト ファイル]** オプションでは、テキスト形式のコンテンツを保存できます。 レビュー セットで Teams の会話のプレーン テキスト ビューを取得する方法の詳細については、上記の概要ビュー、テキスト ビュー、注釈 [ビューを参照](#summary-view-text-view-and-annotate-view) してください。

上記の概要ビュー、テキスト ビュー、注釈ビューのセクションで[](#summary-view-text-view-and-annotate-view)説明したように、コンテンツにやり直しを適用した場合は、[変換された PDFで編集したネイティブを置き換える] オプションを選択して、ネイティブ ファイルを PDF の変換されたコピーに置き換えます。

Microsoft が提供する Azure BLOB ストレージ コンテナーにエクスポートするか、独自の Azure BLOB ストレージ コンテナーを提供することができます。

エクスポート プロセスを開始する準備ができたら、[エクスポート] ボタン **をクリック** します。 エクスポート [が完了したら、Azure](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) BLOB ストレージ コンテナーにアクセスし、エクスポートしたコンテンツをダウンロードする方法の詳細については、エクスポート ジョブのダウンロードに関するページを参照してください。

> [!NOTE]
> エクスポートには、長い時間がかかる場合があります。 エクスポート プロセスの状態を追跡するには、[レビューセット] タブを終了し、[エクスポート] タブ **をクリック** します。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 の電子情報開示](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Teams PowerShell の概要](teams-powershell-overview.md)
