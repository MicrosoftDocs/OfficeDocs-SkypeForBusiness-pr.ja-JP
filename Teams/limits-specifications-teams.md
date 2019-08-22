---
title: Microsoft Teams の制限事項と仕様
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: Microsoft Teams に適用される制限、仕様、およびその他の要件について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 854c6beeccdae6286bc609a226a49b15de1114e6
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "36493003"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams の制限事項と仕様

この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。

## <a name="teams-and-channels"></a>Teams とチャネル

|機能    | 上限 |
|-----------|---------------|
|ユーザーが作成できるチームの数 | オブジェクト制限 250、&sup1         |
|チームのメンバーの数 | 5,000       |
|テナントで許可されている組織全体のチームの数 | 5     |
|[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数 | 5,000       |
|グローバル管理者を作成できるチームの数        |  500,000   |
|Office 365 テナントが持てるチームの数    | 50万&sup2;     |
|チームごとのチャネル数    | 200 (削除されたチャンネルを含む) &sup3;         |

&sup1; Azure Active Directory の任意のディレクトリ オブジェクトは、この制限にカウントされます。 グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。

&sup2;この制限には、アーカイブされたチームが含まれます。

&sup3; 削除されたチャンネルは、30日以内に復元できます。 30日以内に、削除されたチャネルは、チームの上限に対して200チャネルに対してカウントされ続けます。 30日が経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャネルはチームの制限に従って200チャネルにカウントされなくなります。

## <a name="messaging"></a>メッセージング 

### <a name="chat"></a>チャット

チームのチャットリストの一部である会話に参加するユーザーには、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) のメールボックスが必要です。 これは、チャットリストに含まれている会話が、チャット参加者のクラウドベースのメールボックスに保存されているためです。 チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。 たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加することができます。 ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。 (詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)

Teams chat は Microsoft Exchange バックエンドで動作するため、Exchange メッセージングの制限が Teams 内のチャット機能に適用されます。

|機能  | 上限  |
|---------|---------|
|プライベートチャット<sup>1</sup>の参加者数  | 100    |
|添付ファイルの数<sup>2</sup>  |常用     |

<sup>1</sup>チャットで参加者が20人を超える場合は、次のチャット機能がオフになります: Outlook の自動返信とチームの状態メッセージ入力状態のインジケータービデオ通話と音声通話共用開封確認メッセージ。

<sup>2</sup>添付ファイルの数がこの制限を超えている場合は、エラーメッセージが表示されます。

### <a name="emailing-a-channel"></a>チャネルをメールで送信する

 ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。 メールがチャネルの一部になっている場合、全員に返信して会話を開始することができます。 チャネルにメールを送信するための適用可能な制限の一部を次に示します。

|機能  | 上限  |
|---------|---------|
|メッセージサイズ<sup>1<sup> | 24 KB |
|添付ファイルの数<sup>2</sup>  |超える     |
|各添付ファイルのサイズ | 10 MB 未満 |
|インライン画像の数<sup>2</sup> |50   |

<sup>1</sup>メッセージがこの制限を超えると、プレビューメッセージが生成され、提供されたリンクから元のメールをダウンロードして表示するように求められます。

<sup>2</sup>添付ファイルまたは画像の数がこの制限を超えると、エラーメッセージが表示されます。

詳細については、[「 Exchange Online の制限 」](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)をご覧ください。

> [!NOTE]
> すべての Office 365 ライセンスで、メッセージサイズ、添付ファイル、インライン画像の制限は同じです。

## <a name="channel-names"></a>チャネル名

チャネル名には、次の文字または単語を含めることはできません。

|||
|---------|---------|
|アルファベット     | ~ #% & * {} +/\:  < > ? &#124; ' "..        |
|これらの範囲に含まれる文字    | 0 ~ 1F<br>80から9F        |
|いう     | フォーム、CON、CONIN $、CONIN $、PRN、AUX、NUL、COM1 から COM9、LPT1 から LPT9、desktop.ini、&#95;vti&#95;|

チャネル名には、アンダースコア (_) またはピリオド (.) で始めることも、ピリオド (.) で終わらせることもできません。

## <a name="meetings-and-calls"></a>会議と通話

|機能     | 上限 |
|------------|---------------|
|会議に参加できるユーザー数  | 250    |

## <a name="teams-live-events"></a>Teams ライブイベント

|機能     | 上限 |
|------------|---------------|
|対象ユーザーのサイズ | 出席者 10,000 名 |
|イベントの期間 | 4 時間 |
|Office 365 テナントでの同時ライブイベント | マート |

ライブイベントと、Teams ライブイベントと Skype 会議ブロードキャストの比較の詳細については、「 [teams live イベント」および「Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」を参照してください。

## <a name="storage"></a>ストレージ

Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。

テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。 プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。

SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。 (詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)

Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。 ここでは、SharePoint Online の適用可能な記憶域の制限を示します。

|機能                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|ストレージ                 |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB   |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB |1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB  |1 組織につき 1 TB           |
|Teams ファイル用のストレージ |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |サイト コレクションまたはグループあたり最大 25 TB。 |
|ファイルアップロードの上限 (ファイル単位)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

チャネルは、チーム用に作成された SharePoint Online サイトコレクション内のフォルダーによってサポートされるため、チャネル内のファイルタブは、所属するチームの記憶域制限を共有します。

詳細については、「[SharePoint Online の制限事項](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。

## <a name="contacts"></a>連絡先

チームは以下の連絡先を使用します。

- 組織の Active Directory の連絡先
- ユーザーの Outlook の既定フォルダーに追加された連絡先

Teams ユーザーは、組織の active directory 内のユーザーと通信でき、組織の active directory のすべてのユーザーを連絡先として、また****  > は連絡先リスト**** > **** に追加することができます。**コンタクト**。

チームユーザーは、[ **** > **連絡先**に発信] に移動して、組織の Active Directory に含まれていないユーザーを連絡先として追加することもできます。

## <a name="browsers"></a>ブラウザー

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>オペレーティング システム

各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。
