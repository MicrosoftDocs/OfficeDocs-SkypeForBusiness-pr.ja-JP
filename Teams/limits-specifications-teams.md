---
title: Microsoft Teams の制限事項と仕様
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 73193c1979e2db3632f84e762b9c716ab46a7e56
ms.sourcegitcommit: b5c747e2daad6dd3c1d91f4e61ae6f26db5c77f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064422"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams の制限事項と仕様

この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。

## <a name="teams-and-channels"></a>Teams とチャネル

|機能    | 上限 |
|-----------|---------------|
|ユーザーが作成できるチームの数 | オブジェクト制限 250、&sup1;         |
|ユーザーがメンバーの一員になることができるチームの数|1,000|
|チームのメンバーの数 | 5,000       |
|チーム 1 つあたりの所有者数 | 100   |
|テナントで許可されている組織全体のチームの数 | 5     |
|[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数 | 5,000       |
|グローバル管理者を作成できるチームの数        |  500,000   |
|Office 365 組織が持てるチームの数    | 500,000&sup2;     |
|チームごとのチャネル数    | 200 (削除されたチャネルを含む) &sup3;         |
|チームごとのプライベート チャネル数    |30|
|チャネル会話の投稿サイズ | 投稿ごとに約 28 KB<sup>4</sup> |

&sup1; Azure Active Directory の任意のディレクトリ オブジェクトは、この制限にカウントされます。 グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。

&sup2; この制限には、アーカイブ済みのチームが含まれます。

&sup3; 削除したチャネルは、30 日以内であれば復元できます。 この 30 日間、削除されたチャンネルはチームごとの制限である 200 チャンネルとしてカウントされ続けます。 30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャンネルはチームごとの制限である 200 チャンネルとしてカウントされなくなります。

<sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。

## <a name="messaging"></a>Messaging

### <a name="chat"></a>チャット

Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。 これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。 チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。 たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。 ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。 (詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)

Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。

|機能  | 上限  |
|---------|---------|
|プライベート チャットに参加できるユーザー数 <sup>1</sup>  | 100    |
|ビデオまたは音声通話でチャットに参加できるユーザーの数 | 20 |
|添付ファイルの数 <sup>2</sup>  |10     |
|チャットのサイズ | 投稿ごとに約 28 KB<sup>3</sup> |

<sup>1</sup> チャットに 20 人以上いる場合、次のチャット機能は無効になります。Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認。

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
> メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Office 365 ライセンスで同じです。

## <a name="channel-names"></a>チャネル名

チャネル名に次の文字や単語を含めることはできません。

|||
|---------|---------|
|文字     | ~ # % & * { } + / \ : < > ? &#124; ' " ..        |
|この範囲内の文字    | 0 ~ 1F<br>80 ~ 9F        |
|単語     | フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;|

チャネル名は、アンダースコア (_) またはピリオド (。) で始まったり終わったりすることもできません。

## <a name="meetings-and-calls"></a>会議と通話

|機能     | 上限 |
|------------|---------------|
|会議に参加できるユーザー数 (チャットして電話をかけることができる)  | 250 人    |
|ビデオまたは音声通話でチャットに参加できるユーザーの数 | 20 |
|PowerPoint ファイルの最大サイズ | 2GB|
|Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です | 20 日間 |

### <a name="meeting-expiration"></a>会議の有効期限

|会議の種類  |この時間が経過すると、会議は期限切れになります  |会議を開始または更新するたびに、有効期限はこの時間だけ延長されます  |
|---------|---------|---------|
|今すぐ会議     |開始時刻 + 8 時間         |該当なし         |
|終了時刻のない標準     |開始時刻 + 60 日         | 60 日        |
|終了時刻のある標準     |終了時刻 + 60 日         |60 日         |
|終了時刻のない定期     |開始時刻 + 60 日         |60 日         |
|終了時刻のある定期     |最後の発生の終了時刻 + 60 日         |60 日         |

## <a name="teams-live-events"></a>Teams のライブ イベント

|機能     | 上限 |
|------------|---------------|
|対象ユーザーの規模 | 出席者 10,000 名 |
|イベントの期間 | 4 時間 |
|Office 365 組織で実行されている同時ライブ イベント <sup>1</sup> | 15 |

<sup>1</sup> ライブ イベントはいくつでもスケジュールできますが、一度に実行できるのは 15 件のみです。 プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。 16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。

ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。

> [!IMPORTANT]
> **Microsoft 365 ライブ イベントの上限の引き上げ**
> 
> お客様が急速に変化するコミュニケーションのニーズに対応できるように、Microsoft 365 ライブ イベントは、2020 年 7 月 1 日まで、Teams でホストされるライブ イベントの既定の上限を一時的に引き上げます。 2020 年 4 月下旬から次の上限が適用されるようになります。
> - 参加者の制限: イベントは最大 20,000 人の参加者をサポートできます
> - 同時イベント: テナント全体で 50 のイベントを同時にホストできます
> - イベントの時間: イベントの長さが 1 回のブロードキャストにつき 16 時間に延長されました



## <a name="presence-in-outlook"></a>Outlook でのプレゼンス

Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。 Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。

## <a name="storage"></a>ストレージ

Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。

テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。 プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。

SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。 (詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)

Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。 ここでは、SharePoint Online の適用可能な記憶域の制限を示します。

|機能                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|ストレージ                 |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB   |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB           |
|Teams ファイル用のストレージ |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |
|ファイル アップロードの上限 (ファイルあたり)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

チャンネルは、チーム用に作成された SharePoint Online サイト コレクション内のフォルダーによってバックアップされるため、チャンネル内のファイル タブは、所属するチームのストレージ制限を共有します。

詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。

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
