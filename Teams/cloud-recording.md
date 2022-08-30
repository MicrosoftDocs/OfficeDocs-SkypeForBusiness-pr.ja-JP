---
title: Teams のクラウド会議のレコーディング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- NOCSH
description: Teams にクラウド音声機能を展開して、音声、ビデオ、画面共有活動をキャプチャして、Teams 会議やグループ通話を記録するための実践的なガイダンスです。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a1f8aa97f43e70e2ec17e64cfa2a618b7a61af7
ms.sourcegitcommit: a64574da14969a33a77c7d979ffde452b5b3a531
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175711"
---
# <a name="teams-cloud-meeting-recording"></a>Teams のクラウド会議のレコーディング

Microsoft Teams では、ユーザーは Teams 会議やグループ通話を記録して、音声、ビデオ、および画面共有のアクティビティをキャプチャできます。 レコーディングから自動的に文字起こしするオプションもあるため、ユーザーは会議のレコーディングを字幕付きで再生して、重要な論点を振り返ることができます。 レコーディングはクラウドで実行され、Microsoft OneDrive または Microsoft SharePoint に保存されるため、ユーザーは組織全体に渡って安全にそのレコーディングを共有できます。

会議がレコーディングされると、自動的に次の処理が行われます:

- OneDrive または SharePoint にアップロードされます
- 会議に招待された人々に対して参加承認しました
- 会議のためのチャット内でリンクされています
- Teams 予定表の会議の [レコーディングとトランスクリプト] タブに表示されます
- Microsoft 365 のさまざまなファイル リストに追加されました: 共有アイテム、office.com、おすすめ、最近使用したファイルなどです。
- Microsoft 365 検索用にインデックスが作成されました

関連: [Teams 会議レコーディングのエンド ユーザー向けドキュメント](https://support.microsoft.com/en-us/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> 会議のレコーディングについて、Microsoft Stream (クラシック) から OneDrive および SharePoint へ移行することは、2021 年 8 月に自動的に発生します。 詳細については、「[OneDrive と SharePoint または Stream を使用して会議のレコーディングを行う](tmr-meeting-recording-change.md)」を参照してください。

> [!NOTE]
> Teams 会議でロールを使用する方法、およびユーザーのロールを変更する方法の詳細については、「[Teams 会議での役割](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)」を参照してください。 ライブ イベントのレコーディング オプションについては、「[Teams のライブ イベント記録ポリシー](teams-live-events/live-events-recording-policies.md)」を参照してください。

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams クラウド会議のレコーディングのための前提条件

Teams ユーザーの会議をレコーディングするには、テナントにおいて OneDrive と SharePoint を有効にする必要があります。 加えて、会議の開催者とレコーディングを開始するユーザーの双方は、次の前提条件を満たす必要があります:

- ユーザーは、非チャネル会議のレコーディングを保存するのに十分なストレージを OneDrive に持っています。

- Teams のチャネルは、チャネル会議のレコーディングを保存するのに十分なストレージを SharePoint に持っています。

- ユーザーは、会議やグループ通話をレコーディングするために、`CsTeamsMeetingPolicy -AllowCloudRecording` 設定を「はい」に設定しています。

- ユーザーは、1 対 1 の通話をレコーディングするために、`CsTeamsCallingPolicy -AllowCloudRecordingForCalls` 設定を「はい」に設定しています。

- ユーザーは、会議において匿名ユーザー、ゲスト ユーザー、またはフェデレーション ユーザーではありません。

- ユーザーの会議の文字起こしを有効にするには、割り当てされている Teams 会議ポリシーで `-AllowTranscription` 設定が「はい」に設定されている必要があります。

- チャネル会議のレコーディングを有効化して保存されるためには、チャネル メンバーがレコーディングを編集またはダウンロードできないように `CSTeamsMeetingPolicy -ChannelRecordingDownload` 設定を 「ブロック」 に設定する必要があります。

> [!IMPORTANT]
>
> ユーザーにレコーディングと、そのダウンロードのみを望む場合、ユーザーは OneDrive または SharePoint を有効化する必要はありません。 つまり、レコーディングは OneDrive または SharePoint に保存されず、削除されるまで 21 日間との制限付きで、一時的な Teams storage に保存されるということです。 現時点では、管理者が制御し、管理し、または削除できる様なものではありません。
>
> [一時的な会議レコーディング用ストレージのしくみ](#temp-storage)の詳細については、以下を参照してください。  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>組織内のユーザーに対して Teams クラウド会議のレコーディングを設定する

このセクションでは、「[ Teams 会議ポリシー](policy-assignment-overview.md)」を通して、Teams 会議をレコーディングするための計画と設定について説明します。

### <a name="turn-on-or-turn-off-cloud-recording"></a>クラウド レコーディングを開始または停止する

Microsoft Teams 管理センターまたは PowerShell を使用して、Teams の会議ポリシーを設定すると、ユーザーの会議を記録できるかどうかを制御できます。

Microsoft Teams 管理センターを使用する場合は、会議ポリシーの **[Cloud recording](クラウド レコーディング)** 設定をオンまたはオフにします。 詳細については、「[オーディオおよびビデオについての会議ポリシーの設定](meetings-policies-recording-and-transcription.md#allow-cloud-recording)」を参照してください。

PowerShell を使用する場合は、TeamsMeetingPolicy で AllowCloudRecording 設定を構成します。 詳細については、「[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy)」および「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

会議をレコーディングするには、会議の開催者とレコーディングを開始するユーザーの双方に、レコーディングのアクセス許可が必要です。 管理者がユーザーにカスタム ポリシーを割り当てていない限り、ユーザーはグローバル ポリシーを取得します。グローバル ポリシーでは、既定で AllowCloudRecording が有効になっています。

> [!NOTE]
> Teams の役割を使用して、会議を記録するためのアクセス許可を持つユーザーを構成する方法の詳細については、「[Teams 会議での役割](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)」 を参照してください。

ユーザーがグローバル ポリシーにフォールバックするには、次のコマンドレットを使用して、ユーザーの特定のポリシーの割り当てを削除します。

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

グローバル ポリシーの AllowCloudRecording の値を変更するには、次のコマンドレットを使用します。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true
```

|シナリオ|手順|
|--|--|
| 社内のすべてのユーザーが、自身の会議をレコーディングできるようにしたい。 | <ol><li>Global CsTeamsMeetingPolicy は、 AllowCloudRecording = True に設定されていることを確認する。<li>すべてのユーザーについて、Global CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = True に設定されていることを確認する。</ol> |
| ほとんどのユーザーに会議をレコーディングできるようにしたいが、レコーディングを許可されていない特定のユーザーについては、選択的に記録できないようにしたい。 | <ol><li>GlobalCsTeamsMeetingPolicy が AllowCloudRecording = True に設定されていることを確認する。<li>ほとんどのユーザーに、Global CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = True に設定されていることを確認する。<li>その他のすべてのユーザーは、CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = False として設定され、承認されている。</ol> |
| レコーディングを 100% 無効化する。 | <ol><li>Global CsTeamsMeetingPolicy が AllowCloudRecording = False に設定されていることを確認する。<li>すべてのユーザーについて、Global CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = False に設定され、承認されている。 |
| ユーザーの大半に対してはレコーディングを不可とし、特定のユーザーについてレコーディングすることを選択的に許可したい。 | <ol><li>Global CsTeamsMeetingPolicy が AllowCloudRecording = False に設定されていることを確認する。<li>ほとんどのユーザーに、Global CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = False として設定され、承認されている。<li>その他のすべてのユーザーには、 CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = True に設定され、承認されている。 <ol> |


<a name="bd-channel"></a>
### <a name="block-or-allow-download-of-channel-meeting-recordings"></a>チャネル会議のレコーディングのダウンロードを禁止または許可する

この設定は、チャネル会議をチャネルにある "Recordings" フォルダーに保存するか、それとも "Recordings\View only" フォルダーに保存するかどうか制御します。 この設定は、チャネル会議の記録を選択したユーザーのポリシーに適用されます。

この設定のための 2 つの値は次のとおり:

- [**許可する**] (既定) - チャネル会議のレコーディングを、チャネル内の "Recordings" フォルダーに保存します。 レコーディング ファイルについてのアクセス許可は、チャネルの SharePoint のアクセス許可とは関わりなく設定されます。 これは、チャネル用にアップロードされた他のファイルと同じです。

- [**禁止**] - チャネル会議のレコーディングを、チャネル内の "Recordings\View only" フォルダーに保存します。 チャネルの所有者は、このフォルダー内のレコーディングに対する完全な権限を持ちますが、チャネル メンバーは読み取りアクセスが可能で、ダウンロードはできません。

PowerShell を使用して、TeamsMeetingPolicy の ChannelRecordingDownload 設定を構成します。 詳細については、「[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy)」および「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

管理者がユーザーにカスタム ポリシーを割り当てていない限り、ユーザーはグローバル ポリシーを取得します。グローバル ポリシーでは、ChannelRecordingDownload が既定でAllow (許可) になっています。

ユーザーが元のグローバル ポリシーに戻るには、次のコマンドレットを使用してユーザーに対する特定ポリシーの割り当てを削除します:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

グローバル ポリシーの ChannelRecordingDownload の値を変更するには、次のコマンドレットを使用します:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Block
```

> [!NOTE]
> ChannelRecordingDownload 設定は、Teams PowerShell module version 2.4.1-preview 以降でのみ使用できます。 モジュールの最新プレビュー バージョンをダウンロードするには、次のコマンドを使用します:
>
>```powershell
>Install-Module -Name MicrosoftTeams -Force -AllowClobber -AllowPrerelease
>```

### <a name="turn-on-or-turn-off-recording-transcription"></a>記録の文字起こしを有効または無効にする
この設定は、会議の記録の再生中にキャプションと文字起こし機能を使用できるかどうかを制御します。 記録を開始したユーザーは、これらの機能で記録を操作できるようにするため、この設定を有効にする必要があります。
  
この設定をオンにすると、会議記録に保存されているトランスクリプトのコピーが作成されます。これにより、会議記録で **検索**、**CC**、および **トランスクリプト** を実行できるようになります。


> [!NOTE]
> 記録された会議の文字起こしは、現在、英語 (米国)、英語 (カナダ)、英語 (インド)、英語 (英国)、英語 (オーストラリア)、英語 (ニュージーランド)、アラビア語 (アラブ首長国連邦) 、アラビア語 (サウジアラビア)、中国語 (簡体字、中国)、中国語 (繁体字、香港特別行政区)、中国語 (繁体字、台湾)、チェコ語 (チェコ)、デンマーク (デンマーク)、オランダ語 (ベルギー)、オランダ語 (オランダ)、フランス語 (カナダ)、フランス語 (フランス)、フィンランド語 (フィンランド)、ドイツ語 (ドイツ)、ギリシャ語 (ギリシャ)、ヘブライ語 (イスラエル)、ヒンディー語 (インド)、ハンガリー語 (ハンガリー)、イタリア語 (イタリア)、日本語 (日本)、韓国語 (韓国)、ノルウェー語 (ノルウェー)、ポーランド語 (ポーランド)、ポルトガル語 (ブラジル)、ポルトガル語 (ポルトガル)、ルーマニア語 (ルーマニア)、ロシア語 (ロシア)、スロバキア語 (スロバキア)、スペイン語 (メキシコ)、スペイン語 (スペイン)、スウェーデン語 (スウェーデン)、タイ語 (タイ)、トルコ語 (トルコ)、ウクライナ語 (ウクライナ)、ベトナム語 (ベトナム) でのみサポートされています。 これらは、OneDrive および SharePoint クラウド ストレージに会議のレコーディングと共に保存されます。

Microsoft Teams 管理センターまたは PowerShell を使用して、Teams の会議ポリシーを設定すると、レコーディングを開始するユーザーが会議のレコーディングを文字起こしする機能を選択できるかどうかを制御できます。

Microsoft Teams 管理センターを使用する場合は、会議ポリシーの **[Allow transcription](議事録作成を許可する)** 設定をオンまたはオフにします。 詳細については、「[オーディオおよびビデオについての会議ポリシーの設定](meetings-policies-recording-and-transcription.md#allow-transcription)」を参照してください。

PowerShell を使用する場合は、TeamsMeetingPolicy で AllowTranscription 設定を構成します。 詳細については、「[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy)」および「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

管理者がユーザーにカスタム ポリシーを割り当てていない限り、ユーザーはグローバル ポリシーを取得します。グローバル ポリシーでは、既定で AllowTranscription が無効になっています。

ユーザーがグローバル ポリシーにフォールバックするには、次のコマンドレットを使用して、ユーザーの特定のポリシーの割り当てを削除します。

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

グローバル ポリシーの AllowCloudRecording の値を変更するには、次のコマンドレットを使用します。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```

</br>
</br>

|シナリオ|手順 |
|---|---|
|会議のレコーディングを始めるにあたって、社内のすべてのユーザーが文字起こしをできるようにしたい。 |<ol><li>Global CsTeamsMeetingPolicy が AllowTranscription = True に設定されていることを確認する。 <li>すべてのユーザーについて、Global CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowTranscription = True に設定されていることを確認する。 </ol>|
|ほとんどのユーザーに会議のレコーディングの文字起こしを可能とするが、一方で文字起こしを許可されていない特定のユーザーについては、不可とする。 |<ol><li>Global CsTeamsMeetingPolicy が AllowTranscription = True に設定されていることを確認する。 <li>大半のユーザーについて、Global CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowTranscription = True に設定されていることを確認する。 <li>その他のすべてのユーザーには、CsTeamsMeetingPolicy ポリシーの 1 つが AllowTranscription = False に設定され、承認されている。 </ol>|
|レコーディングの文字起こしを100% 無効にする。 |<ol><li>Global CsTeamsMeetingPolicy が AllowTranscription = False に設定されていることを確認する。 <li>すべてのユーザーについて、Global CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowTranscription = False に設定され、承認されている。 </ol>|
|ユーザーの大半について、文字起こしを無効にし、一方で文字起こしを許可されている特定のユーザーについては選択的に可能とする。 |<ol><li>Global CsTeamsMeetingPolicy が AllowCloudRecording = False に設定されていることを確認する。 <li>大半のユーザーについて、Global CsTeamsMeetingPolicy または CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = False として設定され、承認されている。 <li>その他のすべてのユーザーには、 CsTeamsMeetingPolicy ポリシーの 1 つが AllowCloudRecording = True に設定され、承認されている。 </ol>|

### <a name="terms-of-use-acceptance"></a>利用規約への同意
組織に会議録画ポリシーがあり、会議の録画前にユーザーの同意が必要な場合は、[Azure Active Directory の利用規約](/azure/active-directory/conditional-access/terms-of-use)機能を使用します。 この機能により、ユーザーは Microsoft Teams にアクセスする前に、組織のユーザー ポリシーの条件に同意する必要があります。 この機能は、記録ボタンをクリックすることに特化したものではなく、Teams や他の Microsoft 365 アプリを総合的に使用することに関連するものです。 Microsoft は、Teams や Microsoft 365 を使用する場合の全体的な利用規約に、会議記録に関する情報を追加することを提案します。

### <a name="set-a-custom-privacy-policy-url"></a>カスタム プライバシー ポリシーの URL を設定する

管理者は、Teams の記録と文字起こしのプライバシー ポリシーの URL を、組織のカスタム リンクで更新できます。 これは、[Azure AD 管理センター](https://aad.portal.azure.com)で次の手順を使用して実行できます。

1. Azure AD 管理センターにサインインします。
1. [**Azure Active Directory** > **のプロパティ**] にアクセスします。
1. プライバシー ポリシーへのリンクを使用して、**[プライバシーに関する声明の URL]** フィールドを更新します。

> [!NOTE]
> 組織のこのフィールドをすでに更新している場合は、変更を加える必要はありません。

プライバシー ポリシーの URL を追加すると、デフォルトの Teams 会議の記録と文字起こしのプライバシーに関する声明が、組織から提供された新しい URL に置き換えられます。

> [!NOTE]
> 組織がホストする Teams 会議に参加する匿名、ゲスト、およびフェデレーションのユーザーには、デフォルトの Teams 会議の記録と文字起こしのプライバシー ポリシーが引き続き適用されます。

## <a name="permissions-and-storage"></a>アクセス許可とストレージ

会議のレコーディングは、OneDrive および SharePoint クラウド ストレージに保存されます。 保管場所とアクセス許可は、会議の種類と会議におけるユーザーの役割に依存しています。 レコーディングに適用された既定のアクセス許可は以下にリストアップされます。ビデオ レコーディング ファイルに対する完全な編集権限を持つユーザーは、アクセス許可を変更し、後で必要に応じて他のユーザーと共有できます。

### <a name="non-channel-meetings"></a>非チャネル会議

- レコーディングは、その開始ボタンをクリックしたユーザーの OneDrive の「**Recordings**」という名前のフォルダーに格納されます。 

  例: <i>レコーディングしたユーザーの OneDrive</i>/**Recordings**

- 外部の参加者を除き、会議に招集された人々は、レコーディング ファイルに対して、ダウンロード権限が与えられておらず、かつ閲覧のみのアクセスが自動的に許可され、承認されます。

- 会議の所有者とレコーディングを開始した人は、他者への共有とアクセス許可の変更を含む、すべての編集アクセス許可が与えられます。

### <a name="channel-meetings"></a>チャネル会議

`Set-CsTeamsMeetingPolicy -ChannelRecordingDownload`が [許可] (既定) の場合:

- レコーディングは、Teams サイトのドキュメント ライブラリの **Recordings** という名前のフォルダーに格納されます。

  例: <i>Teams 名 - チャネル名</i>/**Documents**/**Recordings**

- [録画] をクリックしたメンバーには、レコーディングの編集権限があります。

- 他のすべてのメンバーのアクセス許可は、チャネル SharePoint のアクセス許可に基づいています。

`Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` が禁止の場合:

- レコーディングは、Teams サイトのドキュメント ライブラリにある **Recordings/View only** という名前のフォルダーに格納されます。 

  例: <i>Teams 名 - チャネル名</i>/**Documents/Recordings/View only**

- チャネルの所有者には、このフォルダー内のレコーディングに対する完全な編集とダウンロードの権限があります。

- チャネルのメンバーは、閲覧のみのアクセスが可能で、ダウンロードはできません。

特定の会議種別の詳細については、次の表を参照してください:

| 会議の種類  | レコードをクリックしたのは誰ですか?| 記録はどこにありますか? | 誰にアクセス権が与えられるか? R/W、R、または共有  |
|-------------|-----------------------|------------------------|------------------------|
|社内関係者との １ 対 １ の通話             |発信者                 |発信者の OneDrive アカウント                        |発信者は所有者であり、完全なアクセス権限を持っています。 <br /><br />(同じテナント内の) 受信者には、読み取り専用アクセス権が与えられます。アクセス許可を共有させることはできません。 <br /><br /> (別のテナントの場合) 受信者にはアクセス権がありません。 発信者は受信者にそれを共有する必要があります。|
|社内関係者との １ 対 １ の通話             |受信者                 |受信者の OneDrive アカウント                        |受信者は所有者であり、完全なアクセス権限を持っています。 <br /><br />発信者 (同じテナントの場合) は読み取り専用アクセス許可を与えられます。アクセス許可を共有させることはできません。 <br /><br />(別のテナントの場合) 発信者はアクセス権を持っていません。 発信者に共有する必要があります。|
|外部通話を使用した １ 対 １ の通話             |発信者                 |発信者の OneDrive アカウント                        |発信者は所有者であり、完全なアクセス権限を持っています。<br /> <br />受信者にはアクセス権がありません。 発信者は受信者にそれを共有する必要があります。|
|外部通話を使用した １ 対 １ の通話             |受信者                 |受信者の OneDrive アカウント                        |受信者は所有者であり、完全なアクセス権限を持っています。<br /><br />発信者にはアクセス権がありません。 受信者は発信者に共有する必要があります。|
|グループ通話                                 |通話のいずれかのメンバー |レコードの OneDrive アカウントをクリックしたグループ メンバー  |レコードをクリックしたメンバーは完全な権限を持っています。 <br /><br /> 同じテナントの他のメンバーには読み取り権限があります。 <br /><br /> 別テナントに所属するグループ メンバーには、何も権限がありません。|
|アドホック/スケジュールされた会議                    |開催者              |開催者の OneDrive アカウント                     |開催者は記録に対して完全な権限を持ちます。 <br /><br /> 会議の他のメンバー全員が読み取りアクセスは可能で、かつダウンロードはできません。|
|アドホック/スケジュールされた会議                    |その他の会議メンバー   |レコードをクリックした会議メンバー                                  |レコードをクリックしたメンバーには、記録への完全なアクセス権があります。 <br /><br />開催者は編集の権利を持ち、共有できます。<br /><br /> その他の全ての会議メンバーは読み取りアクセスが可能で、ダウンロードはできません。|
|外部の参加者とのアドホック/予定された会議|開催者              |開催者の OneDrive アカウント                     |開催者は記録に対して完全な権限を持ちます。<br /> <br /> 開催者と同じテナントに属するすべての会議メンバーは、読み取りアクセスが可能で、ダウンロードはできません。 <br /><br /> 他のすべての外部メンバーにはアクセス権がありません。開催者はそれを共有する必要があります。|
|外部の参加者とのアドホック/予定された会議|その他の会議メンバー   |レコードをクリックしたメンバー                                  |レコードをクリックしたメンバーには、記録への完全なアクセス権があります。 開催者は編集の権利を持ち、共有できます。 <br /><br /> 開催者と同じテナントに属するすべての会議メンバーは、読み取りアクセスが可能で、ダウンロードはできません。 <br /><br />他のすべての外部メンバーにはアクセス権がありません。開催者はそれを共有する必要があります。|
|チャネル会議                            |チャネル メンバー         |そのチャネルの Teams の SharePoint の場所                   |Set-CsTeamsMeetingPolicy -ChannelRecordingDownload が Allow (既定) に設定されている場合、[レコード] をクリックしたメンバーにはレコーディングに対する編集権限があります。 他のすべてのメンバーのアクセス許可は、チャネル SharePoint のアクセス許可に基づいています。<Br><Br>Set-CsTeamsMeetingPolicy -ChannelRecordingDownload が Block に設定されている場合、チャネル所有者はレコーディングに対するすべての編集権限があります。しかしチャネル メンバーは読み取りアクセスが可能で、ダウンロードはできません。|

<a name="temp-storage"></a>
### <a name="temporary-storage-when-unable-to-upload-to-onedrive-and-sharepoint"></a>OneDrive および SharePoint にアップロードできない時の一時的なストレージ

会議のレコーディングを OneDrive および SharePoint にアップロードできない場合は、削除されるまでの 21 日間、Teams から一時的にダウンロードできます。 現時点では、これは削除することを含めて管理者が制御または管理する対象ではありません。

会議のレコーディングは、この一時保管用ストレージ内で、次の理由により終了するかもしれません:

- 非チャネル会議において、ユーザーによるレコーディングに OneDrive がないか、または OneDrive がそのストレージ クオータに到達した場合
- チャネル会議において、SharePoint サイトが、そのストレージ クオータに到達した場合、またはサイトがまだ提供されていない場合
- 特定の OneDrive for Business ポリシーと SharePoint ポリシーが、既定の IP 範囲外からアップロードすること、などを制限しながら有効である場合

この一時的なストレージによるレコーディングの保持は、チャット メッセージそれ自身から影響を受けます。 そのため、レコーディングにおける任意のオリジナルのチャット メッセージを削除すると、当該ユーザーがそのレコーディングにアクセスし続けることを防ぐことができます。 これに影響を及ぼしうるシナリオには、次の 2 つがあります:

- **ユーザーは手動でチャット メッセージを削除する** - このシナリオでは、オリジナルのメッセージが削除された時、当該ユーザーはもはやレコーディングにアクセスできず、将来に渡ってダウンロードもできなくなります。 しかしながら、レコーディング自体はしばらくの間 (元の 21 日間を超えない期間) Microsoft の内部システム内で保持される場合があります。

- **チャット メッセージのレコーディングがチャット保持ポリシーに基づき削除される** - 一時的なストレージによるレコーディングは、チャット保持ポリシーと直接結び付けられています。 そのため、Teams の一時的ストレージにあるレコーディングは、その既定値において、削除されるまで 21 日間保存され、チャット メッセージが その期限前に自らのポリシーに基づき削除された場合は、レコーディングは同じく削除されます。 その後は、レコーディングを回復する方法は存在しません。

### <a name="planning-for-storage"></a>ストレージの計画

1 時間のレコーディングのサイズは 400 MB です。 レコーディング ファイルに要求される容量を理解していること、及び OneDrive と SharePoint に十分な記憶域が確保されていることを確かめて下さい。  サブスクリプションに含まれる基本のストレージを理解し、追加の記憶域の注文方法を知るために、[OneDrive に既定の記憶域を設定する](/onedrive/set-default-storage-space) そして [SharePoint サイトの記憶域の制限を管理する](/sharepoint/manage-site-collection-storage-limits) をご覧ください。

 <a name="auto-expiration"></a>
### <a name="auto-expiration-of-teams-meeting-recordings"></a>Teams 会議の記録の自動消去

管理者およびエンド ユーザーによく寄せられる質問を確認して、Teams 会議の記録の自動期限切れがどのように機能するか、今すぐできるアクション、および機能の開始後にできるアクションに関する分析情報を集めています。
  
管理者固有の変更の詳細については、[こちら](meeting-expiration.md#changes-to-meeting-expiration)を参照してください。

エンド ユーザーが会議の有効期限を管理する方法の詳細については、[こちら](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)を参照してください。
  
## <a name="manage-meeting-recordings"></a>会議のレコーディングを管理する

会議のレコーディングは、OneDrive および SharePoint にビデオ ファイルとして保存され、これらのプラットフォームで利用できる管理とガバナンスのオプションに従います。 詳細については、「[SharePoint ガバナンスの概要](/sharepoint/governance-overview)」をご覧ください。

非チャネル会議においては、レコーディングはその開始者の OneDrive に保存され、このためその所有についての取り扱いと、従業員が離職したあとのアイテム保持ポリシーについては、通常通りです [OneDrive と SharePoint プロセス](/onedrive/retention-and-deletion#the-onedrive-deletion-process)。

## <a name="closed-captions-for-recordings"></a>レコーディングのクローズド キャプション

Teams 会議の録音のクローズド キャプションは、ユーザーが記録時に書き起こしをオンにしている場合にのみ、再生中に利用できます。 管理者は、[ポリシーを介して文字起こしの記録をオン](#turn-on-or-turn-off-recording-transcription)にして、ユーザーが文字起こしを使用して会議を記録できるようにする必要があります。

キャプションは、様々な言語的対応力の視聴者を全て包含するコンテンツを制作することを支援してくれます。所有者として、会議のレコーディングにおいてキャプションを隠すこともできます、けれども会議の文字起こしは、削除しない限り Teams で引き続き利用可能となります。

今日においては、レコーディング ビデオ ファイルのクローズド キャプションは、Teams 会議の文字起こしにリンクされています。 このリンクは、ほとんどの場合、ファイルの有効期間にわたって残りますが、ビデオ ファイルが同じ OneDrive または SharePoint サイト内にコピーされた場合に、リンクが壊れる可能性があります。これにより、コピーされたビデオ ファイルでキャプションが使用できなくなります。

Teams の文字起こしとレコーディングの間のリンクに対する今後のいかなる変更も、ここ、およびメッセージ センターの通知で明らかにされます。 今後何か変更を加えた場合、60 日未満の記録ファイルには、会議のトランスクリプトがキャプションとして表示されます。

> [!NOTE]
> 会議の文字起こしは GCC ではまだ利用できません。

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>会議のレコーディングの電子情報開示とコンプライアンス

### <a name="ediscovery"></a>電子情報開示

会議のレコーディングは OneDrive と SharePoint に保存されます。これは、Microsoft 365 と Office 365 の Tier-D コンプライアンスに準拠しています。 会議や通話のレコーディングに専門的関心を持つコンプライアンス管理者における電子情報開示要求への対応をサポートするため、レコーディングの完了メッセージは Microsoft Teams のコンプライアンス コンテンツ検索機能の中で提供されています。 コンプライアンス管理者は、コンプライアンス コンテンツ検索プレビューのアイテムの件名で "レコーディング" をキーワード検索して、組織内の会議や通話のレコーディングを見つけることができます。

加えて、会議のレコーディング ビデオ ファイルは、SharePoint および OneDrive についての電子情報開示検索機能を介してファイルを見つけることができます。

電子情報開示の詳細については、[Microsoft 365 の電子情報開示ソリューション](/microsoft-365/compliance/ediscovery) の記事を参照してください

### <a name="retention-policies"></a>アイテム保持ポリシー

アイテム保持ポリシー 自動化ラベルを適用し、ProgID プロパティを使用して Teams 会議レコーディング ビデオ ファイルだけを抽出ターゲットにできます。 詳細については、「 [Teams 会議レコーディングにアイテム保持ポリシー ラベルを自動的に適用する方法](/microsoft-365/compliance/apply-retention-labels-automatically#microsoft-teams-meeting-recordings)」を参照してください。

### <a name="microsoft-purview-data-loss-prevention-dlp-policies"></a>Microsoft Purview データ損失防止 (DLP) ポリシー

DLP ポリシーの会議のレコーディング ファイルへの適用は、ProgID プロパティを利用することでも可能となります。 SharePoint と OneDrive のファイルのための DLP ルールにおいて、条件を次のように設定します:

- Document property = *ProgID*
- Value = *Media.Meeting*

DLP の詳細については、「[データ損失防止についての解説](/microsoft-365/compliance/dlp-learn-about-dlp)」を参照してください。

## <a name="meeting-recording-diagnostic-tools"></a>会議レコーディングの診断ツール
  ### <a name="user-cannot-record-meetings"></a>ユーザーが会議を記録できません

管理者の場合は、次の診断ツールを使用して、ユーザーが Teams で会議を記録するために適切に構成されていることを確認できます。

1. 以下の **[テストの実行]** を選択すると、診断が Microsoft 365 管理センターに表示されます。 

   > [!div class="nextstepaction"]
   > [テストの実行: 会議の記録](https://aka.ms/MeetingRecordingDiag)

2. [診断の実行] ウィンドウで、**[ユーザー名またはメール アドレス]** フィールドに会議を記録できないユーザーのメールアドレスを入力して、**[テストの実行]** を選択します。

3. このテストでは、テナントまたはポリシーの構成を処理するのに最適な次の手順が返され、ユーザーが Teams で会議を記録するために適切に構成されていることを確認します。
  
  ### <a name="meeting-record-is-missing"></a>会議の記録が見つかりません

管理者の場合は、次の診断ツールを使用して、会議の記録が正常に完了し、会議 ID と記録開始時刻に基づいて Stream または OneDrive にアップロードされたことを確認できます。

1. 以下の **[テストの実行]** を選択すると、診断が Microsoft 365 管理センターに表示されます。 

   > [!div class="nextstepaction"]
   > [テストの実行: 会議の記録が見つからない](https://aka.ms/MissingRecordingDiag)

2. [診断の実行] ウィンドウで、**[記録された会議の URL]** フィールド (通常は会議出席依頼に表示されます) に会議の URL を入力し、[**いつ会議が記録されましたか?**] フィールドに会議の日付を入力します。次に、**[テストの実行]** を選択します。

3. テストでは、会議の記録が正常に完了し、Stream または OneDrive にアップロードされたことを確認します。

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
