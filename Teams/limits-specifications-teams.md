---
title: Microsoft Teams の制限事項と仕様
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: この記事では、Microsoft Teams に適用される制限、仕様、およびその他の要件について説明します。
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee791259b938345876e9761344616fac7d1d9e45
ms.sourcegitcommit: 3056f95e9f654b78636949f43eacdde297e52c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2023
ms.locfileid: "69990412"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams の制限事項と仕様

この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。

## <a name="teams-and-channels"></a>Teams とチャネル

|機能    | 上限 |
|-----------|---------------|
|ユーザーが作成できるチームの数 | オブジェクト制限 250、&sup1;         |
|ユーザーがメンバーの一員になることができるチームの数|1,000&sup2;|
|チームのメンバーの数 | 25,000<sup>6</sup>     |
|チーム 1 つあたりの所有者数 | 100   |
|テナントで許可されている組織全体のチームの数 | 5&sup2;     |
|[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数 | 10,000       |
|グローバル管理者を作成できるチームの数        |  500,000   |
|Microsoft 365 または Office 365 組織が持てるチームの数    | 500,000&sup3;     |
|チームごとのチャネル数    | 200 (削除されたチャネルを含む)<sup>4</sup>        |
|チームごとのプライベート チャネル数    |30 (削除されたチャネルを含む)<sup>4</sup>        |
|プライベート チャネルのメンバー数    |250|
|チームにインポートできる配布リスト、セキュリティ グループ、または Microsoft 365 グループの最大サイズ    |3,500|
|チームに変換できる Microsoft 365 グループのメンバーの最大数    |10,000<sup>6</sup>     |
|チャネル会話の投稿サイズ | 投稿ごとに約 28 KB<sup>5</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).

<sup>2</sup> この制限には、アーカイブ済みのチームが含まれます。 

<sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant. Increase is only made for real-life production scenarios.

<sup>4</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.

<sup>5</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。

チーム外の <sup>6</sup> 人の共有チャネル メンバーは、この制限にカウントされます。 さらに、メンバー数が 10,000 人以上のチームでは、チーム/チャネルのメンションはブロックされます。

> [!NOTE]
> 共有チャネルの制限については、「[共有チャネルの制限](/MicrosoftTeams/shared-channels#limits-for-shared-channels)」 を参照してください。

## <a name="messaging"></a>Messaging

### <a name="chat"></a>チャット

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)


|機能  | 上限  |
|---------|---------|
|プライベート チャットに参加できるユーザー数 <sup>1</sup>  | 250<sup>2</sup> |
|チャットから開始されるビデオまたは音声通話に参加できるユーザー数 | 20 |
|添付ファイルの数 <sup>3</sup>  |10     |
|チャットのサイズ | 投稿ごとに約 28 KB<sup>4</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup> Only 200 members at a time can be added to a group chat. [See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。

<sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。

### <a name="emailing-a-channel"></a>電子メールでチャネルを送信する

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

|機能  | 上限  |
|---------|---------|
|メッセージ サイズ <sup>1<sup> | 24 KB |
|添付ファイルの数 <sup>2</sup>  |20     |
|各添付ファイルのサイズ | 10 MB 未満 |
|インライン画像の数 <sup>2</sup> |50   |

> [!NOTE]
> チャネルに送信できるメールの数には制限があります。 制限は、1 ユーザーあたりチャネルあたり 10 秒あたり 6 通のメール、ユーザーあたりテナントあたり 10 秒あたり 8 通のメールです。
<sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。

<sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。

詳細については、「[Exchange Online の制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。

> [!NOTE]
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.

## <a name="channel-names"></a>チャネル名

チャネル名に次の文字や単語を含めることはできません。

|種類|例|
|---------|---------|
|文字     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|この範囲内の文字    | 0 ~ 1F<br>80 ~ 9F        |
|単語     | フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;|

チャンネル名は、アンダースコア (_) またはピリオド (.) で開始したり、ピリオド (.) で終了したりすることもできません。

## <a name="meetings-and-calls"></a>会議と通話

|機能     | 上限 |
|------------|---------------|
|会議に参加できるユーザー数 (チャットして電話をかけることができる)  | 1000。GCC、GCCH、DoD は含まれますが、A1 (300) は含まれません。|
|チャットから開始されるビデオまたは音声通話に参加できるユーザー数 | 20 |
|PowerPoint ファイルの最大サイズ | 2 GB|
|Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です | 20 日間 |
| 会議記録の最大長 | 4 時間または 1.5 GB。 この制限に達すると、記録は終了し、自動的に再開されます。

詳細については、「 [会議、ウェビナー、ライブ イベント](/microsoftteams/quick-start-meetings-live-events)」を参照してください。  
  
> [!NOTE]
> ブレークアウト ルームは、出席者が300人未満の会議でのみ作成できます。 さらに、会議でブレークアウト ルームを作成すると、会議の出席者数が自動的に 300 人に制限されます。 300 人を超える参加者を予定している会議で、ブレークアウト ルームを初期設定しないように、エンドユーザーにアドバイスしてください。 大規模なチーム会議の詳細情報については、ガイダンス[大規模な Teams 会議のベスト プラクティス](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)をエンドユーザーと共有してください。

### <a name="meeting-expiration"></a>会議の有効期限

> [!NOTE]
> A meeting URL will never stop working. The expiry only relates to any PSTN dial-in numbers, CVI coordinates, and/or underlying meeting policies and settings.

|会議の種類  |この時間が経過すると、会議は期限切れになります  |会議を開始または更新するたびに、有効期限はこの時間だけ延長されます  |
|---------|---------|---------|
|今すぐ会議     |開始時刻 + 8 時間         |該当なし         |
|終了時刻のない標準     |開始時刻 + 60 日         | 60 日        |
|終了時刻のある標準     |終了時刻 + 60 日         |60 日         |
|終了時刻のない定期     |開始時刻 + 60 日         |60 日         |
|終了時刻のある定期     |最後の発生の終了時刻 + 60 日         |60 日         |

> [!NOTE]
> Microsoft Teams 会議には、30 時間の時間制限があります。

## <a name="live-events"></a>ライブ イベント
  
ライブ イベント は、組織が、最大 20,000 人までの大規模なオンライン参加者にストリーミングするイベントをスケジュールして生成できる構造化された会議です。 ライブ イベントでは、対象ユーザーの相互作用はマネージド Q&A エクスペリエンスです。

|機能     | 上限 |
|------------|---------------|
|対象ユーザーの規模 | 最大 20,000 人の出席者 <sup>1</sup> 人 |
|イベントの期間 | 4 時間 |
|Microsoft 365 または Office 365 組織で実行されている同時実行ライブ イベント <sup>2</sup> | 15 |

<sup>1</sup> 通常の 10,000 は、2023 年 6 月 30 日まで 20,000 に増加します。 Yammer や Microsoft Stream のライブ イベントを使用して、さらに多くの人数をスケジュールすることさえできます。 詳細については、「[Microsoft 365 全体でライブ イベントをする](/stream/live-event-m365)」を参照してください。 ただし、20,000 人を超える参加者のイベントには、[Live Events Assistance Program](/stream/live-events-assistance) が必要であることにご留意ください。  
  
<sup>2</sup> 必要な数のライブ イベントをスケジュールできますが、一度に実行できるのは 15 個のみです。 プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。 16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。

ライブ イベントの詳細については、「 [Teams ライブ イベント](teams-live-events/plan-for-teams-live-events.md#teams-live-events)」を参照してください。 詳細については、「[Teams ライブ イベントのスケジュールを設定する](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)」も参照してください。

> [!IMPORTANT]
> **Microsoft 365 ライブ イベントの上限の引き上げ**
>
> **お客様のニーズを引き続きサポートするために、2023 年 6 月 30 日までのライブ イベントの一時的な制限の引き上げを延長します。**
>
>- イベントでは、最大2万の出席者をサポートします
>- テナント全体で 50 のイベントを同時にホストできます
>- ブロードキャストあたり16時間のイベント期間
>
> Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

## <a name="presence-in-outlook"></a>Outlook でのプレゼンス

Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).

## <a name="storage"></a>ストレージ

Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.

> [!NOTE]
> 各[プライベート チャネル](./private-channels.md)には、独自の SharePoint サイトがあります。

If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.

By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)

Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.

|機能                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|ストレージ                 |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB   |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB           |
|Teams ファイル用のストレージ |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |
|ファイル アップロードの上限 (ファイルあたり)    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |

チャネルは、チーム用に作成された SharePoint Online サイト内のフォルダーによってバックアップされるため、チャネル内のファイル タブは、所属するチームのストレージ制限を共有します。

詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。

## <a name="class-teams"></a>クラス チーム

Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

クラス チームは、追加のアプリが含まれるテンプレートの種類で、チーム メンバーの数に応じた制限があります。

> [!NOTE]
> クラスチームを使用するには、[Office 365 Education ライセンス](https://www.microsoft.com/education/products/office)が必要です。

クラスチームの制限を次の表に示します。

|機能  |上限  |
|---------|---------|
|チームのメンバーの数    | この記事の「[チームとチャネル](#teams-and-channels)」のセクションを参照してください        |
|クラスチームで課題を使用するメンバーの数    | 300        |
|クラスチームで OneNote Class Notebook を使用するためのメンバー数     |300         |

A class team can support more than 300 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.

## <a name="tags"></a>タグ

|機能  |上限  |
|---------|---------|
|チームごとのタグ数    | 100        |
|チームごとに推奨される既定のタグ数    | 25        |
|1 つのタグに割り当てられるチームメンバーの数    |200         |
|チームごとにユーザーに割り当てられたタグ数    |25         |

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
