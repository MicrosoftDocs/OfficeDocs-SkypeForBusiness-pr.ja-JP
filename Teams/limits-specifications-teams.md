---
title: 制限とマイクロソフトのチームの仕様
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: karuanag
description: 制限、仕様、およびマイクロソフトのチームに適用されるその他の要件について説明します。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2288ea2c2359098bc66e317ff57ef16c7900e98
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347204"
---
<a name="limits-and-specifications-for-microsoft-teams"></a>制限とマイクロソフトのチームの仕様
=============================================

この資料では、いくつかの制限、仕様、およびマイクロソフトのチームに適用されるその他の要件について説明します。 

<a name="teams-and-channels"></a>チームとチャネル 
------------------

|機能    | 最大数の制限 |
|-----------|---------------|
|ユーザーが作成できるチームの数 | 250 オブジェクト制限 & sup1; の対象となります。         |
|チームのメンバーの数 | 2,500       |
|組織全体にわたるチームのメンバーの数 | 1,000       |
|グローバル管理者が作成できるチームの数        | 500,000   |
|チーム、Office 365 テナントの数を持つことができます。    | 500,000     |
|1 チームあたりのチャンネル数    | 200         |

& sup1;Azure Active Directory 内の任意のディレクトリ オブジェクトは、この制限の方向にカウントします。

<a name="meetings-and-calls"></a>会議と呼び出し 
------------------

|機能     | 最大数の制限 |
|------------|---------------|
|会議に出席する人の数  | 250    |
|プライベート チャットの参加者の数  | 20    |

<a name="storage"></a>ストレージ
-------

Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。

テナントを有効にし、SharePoint Online をお持ちでない場合は、マイクロソフトのチームのユーザーは常にチーム内のファイルを共有できません。 プライベート チャットのユーザーもファイルを共有できない (これは、SharePoint ライセンスに関連付けられている) ビジネスのための OneDrive は、その機能に必要なためです。

SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。 (詳細についてを参照してください[方法 SharePoint Online およびビジネスのための OneDrive がマイクロソフトのチームと対話](sharepoint-onedrive-interact.md)します。)

チームは、ファイル共有用の SharePoint Online のバックエンドで実行しているために、SharePoint の制限事項は、チーム内で [ファイル] セクションに適用されます。 SharePoint Online の適切な格納域の制限を次に示します。

|機能                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|ストレージ                 |1 組織につき 1 TB とライセンスの購入に 10 GB  |1 組織につき 1 TB とライセンスの購入に 10 GB  |1 組織につき 1 TB とライセンスの購入に 10 GB   |1 組織につき 1 TB とライセンスの購入に 10 GB |1 組織につき 1 TB とライセンスの購入に 10 GB  |1 組織につき 1 TB           |
|チームのファイル用のストレージ |サイト コレクションまたはグループごとに最大 25 TB |サイト コレクションまたはグループごとに最大 25 TB |サイト コレクションまたはグループごとに最大 25 TB |サイト コレクションまたはグループごとに最大 25 TB |サイト コレクションまたはグループごとに最大 25 TB |サイト コレクションまたはグループごとに最大 25 TB |
|ファイルのアップロード制限       |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

チームで各ファイルのタブは、上の格納域の制限は、チーム内の各チャンネルに適用するため、SharePoint Online のバックエンドで実行されます。

詳細については、 [SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)を参照してください。

<a name="messaging"></a>メッセージング
---------

マイクロソフト チームの [チャット] ボックスの一覧に含まれている会話に参加するユーザーには、チャットの会話を検索するのには管理者の Exchange オンライン (クラウド ・ ベース) のメールボックスが存在している必要があります。 チャットに参加して、クラウド ベースのメールボックスで、[チャット] ボックスの一覧の一部である会話が保存されるためです。 チャットの参加者には、Exchange Online のメールボックスが割り当てられていない、管理者を検索したり、チャットの会話の保留リストを配置することはできません。 たとえば、Exchange ハイブリッド展開の場合は、オンプレミスのメールボックスを持つユーザーありますマイクロソフト チームの [チャット] ボックスの一覧に含まれている会話に参加すること。 ただし、この例では、これらの会話からコンテンツを検索できないし、ユーザーがクラウド ベースのメールボックスを持っていないために、保留中の配置することはできません。 [(詳細については、どの Exchange と](exchange-teams-interact.md)参照対話マイクロソフト チーム)。

マイクロソフト チーム チャット機能は、Exchange メッセージング ・ マイクロソフトのチーム内でのチャット機能の制限を適用できるように、Microsoft Exchange のバックエンドで動作します。 ユーザーは、チーム内のチャネルに電子メールを送信する場合、チャネルの電子メール アドレスを使用します。 電子メール、チャネルの一部であると、会話を開始するためにだれでも応答できます。 チャネルに電子メールを送信するための適切な制限の一部を次に示します。 

|機能  |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|---------|---------|---------|---------|---------|
|メッセージ サイズの制限&dagger;  |25 KB   |25 KB   |25 KB   |25 KB   |
|ファイルの添付ファイルの制限&Dagger;  |20     |20     |20     |20    |
|インライン イメージを制限します。&Dagger; |50   |50   |50   |50   |

&dagger;メッセージがこの制限を超える場合プレビュー メッセージが生成され、提供されているリンクからのメールに元の表示/ダウンロードをユーザーに求めては。

&Dagger;添付ファイルや画像の数がこの制限を超える場合、メッセージは処理されませんし、エラーが通知の送信者に NDR 電子メールが送信されます。

詳細については、 [Exchange Online の制限](https://technet.microsoft.com/library/exchange-online-limits.aspx)を参照してください。

<a name="browsers"></a> ブラウザー 
--------

[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="operating-systems"></a>オペレーティング ・ システム
-----------------

オペレーティング システムの要件については、[マイクロソフトのチーム用のクライアントを取得する](get-clients.md)を参照してください。


