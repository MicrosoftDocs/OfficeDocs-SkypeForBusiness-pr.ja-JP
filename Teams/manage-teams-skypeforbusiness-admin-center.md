---
title: 新しい Microsoft Teams 管理センターへの移行中に Teams を管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Microsoft 365 管理センターの Teams エクスペリエンスから新しい Microsoft Teams 管理センターに移行しているときに、チームのテナント全体とユーザー設定を管理する方法について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 0d473ffa67b21c4ec3a160a8687a1688ea1d1cf5
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "37564786"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>新しい Microsoft Teams 管理センターへの移行中に Teams を管理する
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>新しい Microsoft Teams 管理センターについて教えてください。  

新しい管理センターのエクスペリエンスでは、チームと Skype for Business の両方を管理するための統一されたエクスペリエンスを提供します。 Microsoft は、追加機能、エンドツーエンドの洞察、チーム設定をユーザーレベルで管理する機能を提供しています。

![Microsoft Teams 管理センターのスクリーンショット。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>新しい Microsoft Teams 管理センターに移行された設定

次の表は、移行された Teams の環境のセクションと、現在の設定と新しい管理ポータルのポリシーの関係を示しています。

|Microsoft 365 管理センターの Teams のセクション  |設定名 (テナントレベル)  |Microsoft Teams 管理センターのポリシー   |Level: テナントまたはユーザー   |
|---------|---------|---------|---------|
|General     |個人プロファイルで組織図を表示する        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  テナント       |
|General     |Teams を持っていない受信者に Skype for Business を使用する         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|電子メールの統合     |チャネルに電子メールを送信することをユーザーに許可する         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|電子メールの統合     |送信者リストを許可         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |テナント         |
|カスタム クラウド ストレージ     |ボックス         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|カスタム クラウド ストレージ     |フォルダ        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|カスタム クラウド ストレージ     |Google ドライブ        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|カスタム クラウド ストレージ     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|ユーザー/ライセンスの種類別の設定     |すべてのユーザーに対して Microsoft Teams のオンとオフを切り替える          |廃止<sup>1</sup>        |         |
|Teams とチャネル     |         |Azure Active Directory グループ管理にリダイレクトします (現在のエクスペリエンスと同じ)。              |ユーザー         |
|Teams とチャネル     |         |AAD グループ管理にリダイレクトします (現在のエクスペリエンスと同じ)。             |ユーザー          |
|アプリ|Enable new external apps by default (既定で新しい外部アプリを有効にする)|組織全体でのアプリの設定|テナント|
|アプリ|外部アプリを許可する|組織全体でのアプリの設定|テナント|
|アプリ|外部アプリのサイドローディングを許可する<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|ユーザー|
|アプリ|既定のアプリ<sup>3</sup>|TeamsAppPermissionPolicy|ユーザー|
|アプリ|外部アプリ<sup>3</sup>|TeamsAppPermissionPolicy|ユーザー|
|通話と会議     |プライベート会議のスケジュールを設定する         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |ユーザー          |
|通話と会議     |アドホックチャネルの meetup を許可する         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |ユーザー          |
|通話と会議     |チャンネル会議のスケジュールを許可する         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |ユーザー          |
|通話と会議     |会議でのビデオの使用を許可する         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |ユーザー          |
|通話と会議     |会議での画面共有を許可する         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |ユーザー          |
|通話と会議     |プライベート通話を許可する         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |ユーザー          |
|メッセージング      |ユーザーが会話に gif を追加できるように Giphy を有効にする         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |コンテンツの評価         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |ユーザーが編集して会話に追加できるミームを有効にする         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |ユーザーが編集して会話に追加できるステッカーを有効にする         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |所有者がすべてのメッセージを削除できるようにする         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |ユーザーが自分のメッセージを編集できるようにする         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |ユーザーが自分のメッセージを削除できるようにする         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |ユーザーがプライベートでチャットすることを許可します         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |

<sup>1</sup>ゲストの場合は廃止されました。 ゲストを有効または無効にすることで、Microsoft Teams 管理センターで管理できるようになりました。 Teams、Edu Student、Edu 教職員の Teams の有効化/無効化は、まもなく廃止されます。 これは、Microsoft 365 管理センターでライセンスを割り当てることで管理する必要があります。 「 [Microsoft Teams へのユーザーアクセスを管理する」を](user-access.md)参照してください。
<br><br>
<sup>2</sup>サイドローディングは、次のように分割されます。

- [TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)のユーザーレベルで管理できるアプリをユーザーがサイドローディングできるようにします。
- テナントのユーザーが、組織全体のアプリ設定でテナントレベルで管理できるカスタムアプリを操作できるようにします。
 
<sup>3 つ</sup>の既定のアプリと外部アプリは、TeamsAppPermissionPolicy のユーザーレベルで有効または無効にすることができます。 さらに、ユーザーとテナントレベルの設定を上書きする組織全体のアプリ設定で、テナントレベルでアプリをブロックすることができます。 

> [!NOTE]
> 引き続き、Microsoft 365 管理センターの Groups ダッシュボードを使用して、チームとチャネルに関する構成を行います。 アプリの設定は、Microsoft 365 管理センターの [Teams] 領域に保持され、後で移行されます。 

## <a name="manage-settings-during-the-migration"></a>移行時に設定を管理する

引き続き、テナントのセクションの移行が完了するまで、Microsoft 365 管理センターと Skype for Business 管理センターで設定を変更することができます。 

次の表は、移行中に機能を管理できる場所を示しています。

|機能  |Microsoft Teams 管理センター                      |Skype for Business 管理センター (レガシー)  |Microsoft 365 管理センター  |
|---------|:---------:|:---------:|:---------:|
|Teams のメッセージング、会議、ライブイベントのポリシー     |     X    |         |         |
|Teams のアップグレードポリシー     |    X     |         |         |
|メッセージング、会議、音声のゲスト設定     |   X      |         |         |
|Teams のライフサイクル管理   |    X    |      |       |
|Teams の設定   |    X    |      |       |
|外部アクセスの設定     |    X    |      |       |
|ユーザー管理    |         |         |    X     |    
|電話会議     |    X     |    X     |         |
|通話プラン     |         |    X     |         |
|電話システム    |         |     X    |         |
|電話番号の管理     |         |   X      |         |
|クラウド音声機能のライセンス     |         |         |    X     |
|自動応答     |         |    X     |         |
|通話キュー     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>移行後に設定を管理する

これらの設定の移行が完了したら、Office 365 管理センターと Skype for Business 管理センターでそれらの設定を無効にし、新しい Microsoft Teams 管理センターで管理することができます。


## <a name="edu-migration-june-july-2019"></a>EDU の移行: 2019 年6月

2019年6月と7月以降、残りの EDU テナントは、以前の管理者エクスペリエンス (Microsoft 365 管理センター) から Teams 管理センターに移行されます。 (Microsoft 365 管理センターで) メッセージセンターを確認して、移行するタイミングを確認します。 移行後に表示されるものを次に示します。

|Microsoft 365 管理センターの Teams のセクション  |設定名 (テナントレベル)  |Microsoft Teams 管理センターのポリシー   |Level: テナントまたはユーザー   |
|---------|---------|---------|---------|  
| メッセージング   |所有者が送信したメッセージを削除できる |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |
| メッセージング  | 送信したメッセージを削除できるユーザー |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |
| メッセージング   | 送信したメッセージをユーザーが編集できるようにする |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)  |ユーザー|
| メッセージング  | ユーザのチャットを許可する |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |
| メッセージング  | スレッドで Giphy を使用する | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |
| メッセージング  | Giphy コンテンツの評価 | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |
| メッセージング  | 会話でミームを使う  |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |
| メッセージング  | 会話でステッカーを使用する |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |

さらに、Microsoft Teams 管理センターでのみ使用できる設定を以下に示します。

|設定名 | Microsoft Teams 管理センターのポリシー | Level: テナントまたはユーザー
|-------------|-------------------------------------|---------|
|URL プレビューを許可する | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |
|グループチャットからユーザーを削除することをユーザーに許可する |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |
|メッセージの表示にイマーシブリーダーを許可する |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| ユーザー |
|ユーザーにメッセージの翻訳を許可する |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| ユーザー |
|開封済みメッセージ | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |
|ユーザーは優先度通知を送信できます | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | ユーザー |
|音声メッセージの作成 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| ユーザー |
|モバイルデバイスでは、最近のチャットの上にお気に入りのチャンネルを表示 |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| ユーザー |
