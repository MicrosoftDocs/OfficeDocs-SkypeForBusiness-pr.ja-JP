---
title: Microsoft Teams の制限事項と仕様
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: この記事では、Microsoft Teams に適用される制限、仕様、およびその他の要件について説明します。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae0583225de5eabfd6cad77895859f9c7159276f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508084"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams の制限事項と仕様

この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。

## <a name="teams-and-channels"></a>Teams とチャネル

|機能    | 上限 |
|-----------|---------------|
|ユーザーが作成できるチームの数 | オブジェクト制限 250、&sup1;         |
|ユーザーがメンバーの一員になることができるチームの数|1,000&sup2;|
|チームのメンバーの数 | 10,000       |
|チーム 1 つあたりの所有者数 | 100   |
|テナントで許可されている組織全体のチームの数 | 5     |
|[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数 | 5,000       |
|グローバル管理者を作成できるチームの数        |  500,000   |
|Microsoft 365 または Office 365 組織が持てるチームの数    | 500,000&sup2;     |
|チームごとのチャネル数    | 200 (削除されたチャネルを含む) &sup3;         |
|チームごとのプライベート チャネル数    |30| (削除されたチャネルを含む) &sup3;
|プライベート チャネルのメンバー数    |250 人|
|チームに変換できる Office 365 グループのメンバーの最大数    |10,000|
|チャネル会話の投稿サイズ | 投稿ごとに約 28 KB<sup>4</sup> |

<sup>1</sup> Azure Active Directory のすべてのディレクトリ オブジェクトはこの制限にカウントされます。 グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。

<sup>2</sup> この制限には、アーカイブ済みのチームが含まれます。 最大数の上限を超える場合は、Microsoft サポートにお問い合わせください。

<sup>3</sup> 削除したチャネルは、30 日以内であれば復元できます。 この 30 日間、削除されたチャンネルはチームごとの制限である 200 チャンネルまたは30のプライベートチャンネルとしてカウントされ続けます。 30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャンネルはチームごとの制限内のチャンネルとしてカウントされなくなります。

<sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。

## <a name="messaging"></a>Messaging

### <a name="chat"></a>チャット

Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。 これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。 チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。 たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。 ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。 (詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)

Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。

|機能  | 上限  |
|---------|---------|
|プライベート チャットに参加できるユーザー数 <sup>1</sup>  | 250 人 |
|ビデオまたは音声通話でチャットに参加できるユーザーの数 | 20 |
|添付ファイルの数 <sup>2</sup>  |10     |
|チャットのサイズ | 投稿ごとに約 28 KB<sup>3</sup> |

<sup>1</sup> チャットに 20 人以上いる場合、次のチャット機能は無効になります。Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認。 プライベート グループのチャットに 20 を超えるメンバーが含まれている場合は、「配信オプションの設定」 (!) ボタンも削除されます。

<sup>2</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。

<sup>3</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。

### <a name="emailing-a-channel"></a>電子メールでチャネルを送信する

 ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。 メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。 チャネルにメールを送信するための適用可能な制限の一部を次に示します。

|機能  | 上限  |
|---------|---------|
|メッセージ サイズ <sup>1<sup> | 24 KB |
|添付ファイルの数 <sup>2</sup>  |20     |
|各添付ファイルのサイズ | 10 MB 未満 |
|インライン画像の数 <sup>2</sup> |50   |

<sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。

<sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。

詳細については、「[ Exchange Online の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。

> [!NOTE]
> メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。 Office の GCC/GCCH/DOD 組織用Teams では、チャネルにメールを送信することはできません。



## <a name="channel-names"></a>チャネル名

チャネル名に次の文字や単語を含めることはできません。

|種類|例|
|---------|---------|
|文字     | ~ # % & * { } + / \ : < > ? &#124; ' " , .        |
|この範囲内の文字    | 0 ~ 1F<br>80 ~ 9F        |
|単語     | フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;|

チャンネル名は、アンダースコア (_) またはピリオド (.) で開始したり、ピリオド (.) で終了したりすることもできません。

## <a name="meetings-and-calls"></a>会議と通話

> [!IMPORTANT]
> **Microsoft 365 ライブ イベントの上限の引き上げ**
>
> **お客様をサポートするために、2021 年 1 月 1 日まで、Teams、Stream、Yammer でホストされるライブイベントの一時的な制限の引き上げを延長します。**
>
>- イベントごとに最大 2 万人の参加者
>- Teams テナントごとに最大 50 の同時イベント
>- ブロードキャストあたり最大 16 時間
>
> さらに、Microsoft 365 支援プログラムを通じて、最大 10 万人が参加するライブイベントを計画できます。 チームは各要求を評価し、お客様と協力して利用可能なオプションを決定します。 [詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。 **2021 年 1 月 1 日以降、これらの制限の引き上げが必要なお客様は、[Advanced Communications](teams-add-on-licensing/advanced-communications.md) アドオンを購入する必要があります。**


|機能     | 上限 |
|------------|---------------|
|会議に参加できるユーザー数 (チャットして電話をかけることができる)  | 300 |
|ビデオまたは音声通話でチャットに参加できるユーザーの数 | 20 |
|PowerPoint ファイルの最大サイズ | 2GB|
|Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です | 20 日間 |

>[!Note]
> Microsoft Stream の使用から [会議の記録用の OneDrive for Business および SharePoint ](tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。 リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、新しい会議の記録に OneDrive と SharePoint を使用するように要請する予定です。

### <a name="meeting-expiration"></a>会議の有効期限

|会議の種類  |この時間が経過すると、会議は期限切れになります  |会議を開始または更新するたびに、有効期限はこの時間だけ延長されます  |
|---------|---------|---------|
|今すぐ会議     |開始時刻 + 8 時間         |該当なし         |
|終了時刻のない標準     |開始時刻 + 60 日         | 60 日        |
|終了時刻のある標準     |終了時刻 + 60 日         |60 日         |
|終了時刻のない定期     |開始時刻 + 60 日         |60 日         |
|終了時刻のある定期     |最後の発生の終了時刻 + 60 日         |60 日         |

> [!NOTE]
> Microsoft Teams 会議には、24 時間の時間制限があります。

## <a name="teams-live-events"></a>Teams のライブ イベント

|機能     | 上限 |
|------------|---------------|
|対象ユーザーの規模 | 出席者 10,000 名 |
|イベントの期間 | 4 時間 |
|Microsoft 365 または Office 365 組織で実行されている同時ライブ イベント <sup>1</sup> | 15 |

<sup>1</sup> ライブ イベントはいくつでもスケジュールできますが、一度に実行できるのは 15 件のみです。 プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。 16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。

ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。

> [!IMPORTANT]
> **Microsoft 365 ライブ イベントの上限の引き上げ**
>
> お客様が急速に変化するコミュニケーションのニーズに対応できるように、Teams、Stream、Yammer でホストされるライブイベントの既定の上限を 2021 年 1 月 1 日まで一時的に引き上げます。
>
> - 参加者の制限: イベントは最大 20,000 人の参加者をサポートできます
> - 同時イベント: テナント全体で 50 のイベントを同時にホストできます
> - イベントの時間: イベントの長さが 1 回のブロードキャストにつき 16 時間に延長されました
>
> さらに、最大 10 万人の参加者がいるライブイベントを、MIcrosoft のライブイベント支援プログラムを通じて計画できます。 [詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。 **2021 年 1 月 1 日以降、これらの制限の引き上げが必要なお客様は、[Advanced Communications](teams-add-on-licensing/advanced-communications.md) アドオンを購入する必要があります。**

## <a name="presence-in-outlook"></a>Outlook でのプレゼンス

Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。 Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。

## <a name="storage"></a>ストレージ

Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。

> [!NOTE]
> 各 [プライベート チャネル](https://docs.microsoft.com/microsoftteams/private-channels) には、独自の SharePoint サイト コレクションがあります。

テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。 プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。

SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。 (詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)

Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。 ここでは、SharePoint Online の適用可能な記憶域の制限を示します。

|機能                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|ストレージ                 |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB   |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB           |
|Teams ファイル用のストレージ |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |
|ファイル アップロードの上限 (ファイルあたり)    |100 GB    |100 GB    |100 GB    |100 GB    |100 GB    |100 GB    |

チャンネルは、チーム用に作成された SharePoint Online サイト コレクション内のフォルダーによってバックアップされるため、チャンネル内のファイル タブは、所属するチームのストレージ制限を共有します。

詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。

## <a name="class-teams"></a>クラス チーム

Microsoft Teams for Education には、教育機関向けの特別なシナリオ (授業教材など) 向けのテンプレートが用意されています。//Microsoft Teams for Education には、教室での授業など、独自の教育シナリオ用に設計されたテンプレートが用意されています。 クラスチームなど、チームの種類の詳細については、「[Microsoft Teams で共同作業を行うチームの種類を選択する](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)」を参照してください。

クラスチームは、追加のアプリが含まれるテンプレートの種類で、チームメンバーの数に応じた制限があります。

> [!NOTE]
> クラスチームを使用するには、[Office 365 Education ライセンス](https://www.microsoft.com/education/products/office)が必要です。

クラスチームの制限を次の表に示します。

|機能  |上限  |
|---------|---------|
|チームのメンバーの数    | この記事の「[チームとチャネル](#teams-and-channels)」のセクションを参照してください        |
|クラスチームで課題を使用するメンバーの数    | 200        |
|クラスチームで OneNote Class Notebook を使用するためのメンバー数     |200         |

クラスチームは、200を超えるメンバーをサポートできます。 ただし、チーム内でアサインメントアプリまたはクラスノートブックアプリのいずれかを使用する場合は、メンバー数を上記の上限未満に保つ必要があります。


## <a name="tags"></a>タグ

|機能  |上限  |
|---------|---------|
|チームごとのタグ数    | 100        |
|チームごとに推奨される既定のタグ数    | 25        |
|タグに割り当てられたチームメンバーの数    |100         |
|ユーザーに割り当てられたるタグ数    |25         |

## <a name="contacts"></a>連絡先

Teams は次の連絡先を使用します。

- 組織の Active Directory の連絡先
- ユーザーの Outlook 既定フォルダーに追加された連絡先

Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[**チャット**]  >  [**連絡先**] または [**通話**]  >  [**連絡先**] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。

Teams ユーザーは、[**通話**]  >  [**連絡先**] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。

## <a name="browsers"></a>ブラウザー

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>オペレーティング システム

各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。
