---
title: Microsoft Teams の制限事項と仕様
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/10/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: karuanag
description: Microsoft Teams に適用される制限、仕様、およびその他の要件について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40c334a1a0159614b77de11f8eb3e5a0e3dcc1b5
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "35012928"
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

## <a name="messaging"></a>メッセージング 

Microsoft Teams のチャット リストの一部である会話に参加したユーザーが、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。 これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。 チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。 たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Microsoft Teams のチャットリストの一部である会話に参加できる場合があります。 ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。 (詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)

Microsoft Teams チャット機能は、Microsoft Exchange のバックエンドで動作するため、Microsoft Teams 内のチャット機能にExchange メッセージングの制限を適用することができます。 ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。 一度メールがチャネルの一部になると、誰でもそれに返信して会話を開始できます。 チャネルにメールを送信するための適用可能な制限の一部を次に示します。 

|機能  | 上限  |
|---------|---------|
|プライベート チャットに参加できるユーザー数  | 100    |
|メッセージサイズ&dagger;  |25 KB   |
|添付ファイルの数&Dagger;  |常用     |
|インライン画像の数&Dagger; |50   |

&dagger; メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールを表示/ダウンロードするように求められます。

&Dagger;添付ファイルまたは画像の数がこの制限を超えると、メッセージは処理されず、NDR メールが送信者に送信され、エラーが通知されます。

> [!NOTE]
> メッセージサイズ、添付ファイル、インライン画像の制限は、すべての Office 365 ライセンスで同じです。

詳細については、[「 Exchange Online の制限 」](https://technet.microsoft.com/library/exchange-online-limits.aspx)をご覧ください。

## <a name="browsers"></a>ブラウザー

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>オペレーティング システム

各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。
