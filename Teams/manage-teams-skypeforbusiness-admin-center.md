---
title: 新しいTeams管理センターに移行するTeamsを管理する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 管理センターのTeamsから新しいTeams管理センターへの移行中に、Teamsのテナント全体とユーザー設定を管理する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 727aa58f3e7a91336355730ce5f0a552ea09fdc9
ms.sourcegitcommit: b2566e64e02cb51d18836630d3aa9b6f27b924da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491737"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>新しい Microsoft Teams 管理センターへの移行中に Teams を管理する

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>新しいMicrosoft Teams管理センターとは  

新しい管理センターでは、Teams と Skype for Business の両方を一元管理することができます。 追加の機能、エンド ツー エンドの分析情報、およびユーザー レベルでTeams設定を管理する機能を提供しています。

![Microsoft Teams 管理センターのスクリーンショット。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>新しい Microsoft Teams 管理センターに移行された設定

次の表で、移行が済んだ Teams エクスペリエンスのセクションと、現在の設定と新しい管理ポータルのポリシーとの関係を示します。

|Microsoft 365 管理センターの Teams のセクション  |設定名 (テナント レベル)  |Microsoft Teams 管理センターのポリシー   |レベル: テナントまたはユーザー   |
|---------|---------|---------|---------|
|全般     |個人用プロファイルで組織図を表示する        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  テナント       |
|全般     |Teamsがない受信者にSkype for Businessを使用する         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |テナント         |
|電子メールの統合     |ユーザーがチャネルにメールを送信することを許可する         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |テナント         |
|電子メールの統合     |差出人のリストを許可する         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |テナント         |
|カスタム クラウド ストレージ     |Box         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |テナント         |
|カスタム クラウド ストレージ     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |テナント         |
|カスタム クラウド ストレージ     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |テナント         |
|カスタム クラウド ストレージ     |Google ドライブ        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |テナント         |
|カスタム クラウド ストレージ     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |テナント         |
|ユーザー/ライセンスの種類別の設定     |すべてのユーザーに対して Microsoft Teams をオンまたはオフにする          |廃止<sup>1</sup>        |         |
|Teams とチャネル     |         |Azure Active Directory グループ管理にリダイレクト (現在のエクスペリエンスと同じ)。              |ユーザー         |
|Teams とチャネル     |         |AAD グループ管理にリダイレクト (現在のエクスペリエンスと同じ)。             |ユーザー          |
|アプリ|Enable new external apps by default (既定で新しい外部アプリを有効にする)|組織全体のアプリ設定|テナント|
|アプリ|外部アプリを許可する|組織全体のアプリ設定|テナント|
|アプリ|外部アプリのサイドロードを許可する<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|ユーザー|
|アプリ|既定のアプリ<sup>3</sup>|TeamsAppPermissionPolicy|ユーザー|
|アプリ|外部アプリ<sup>3</sup>|TeamsAppPermissionPolicy|ユーザー|
|通話と会議     |プライベート会議のスケジュール設定を許可する         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |ユーザー          |
|通話と会議     |アドホック チャネル Meetup を許可する         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |ユーザー          |
|通話と会議     |チャネル会議のスケジュール設定を許可する         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |ユーザー          |
|通話と会議     |会議でビデオを許可する         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |ユーザー          |
|通話と会議     |会議で画面共有を許可する         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |ユーザー          |
|通話と会議     |プライベート通話を許可する         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |ユーザー          |
|メッセージング     |ユーザーが会話に GIF を追加できるように Giphy を有効にする         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |ユーザー         |
|メッセージング     |コンテンツの規制         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |ユーザー         |
|メッセージング     |ユーザーが編集して会話に追加できるミームを有効にする         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |ユーザー         |
|メッセージング     |ユーザーが編集して会話に追加できるステッカーを有効にする         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |ユーザー         |
|メッセージング     |所有者がすべてのメッセージを削除できるようにする         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |ユーザー         |
|メッセージング     |ユーザーが自分のメッセージを編集できるようにする         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |ユーザー         |
|メッセージング     |ユーザーが自分のメッセージを削除できるようにする         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |ユーザー         |
|メッセージング     |ユーザーがプライベートにチャットできるようにする         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |ユーザー         |

<sup>1</sup> ゲストに対して廃止。 ゲストの有効化/無効化は、Microsoft Teams 管理センターで管理できるようになりました。 Teams for Business Enterprise、Edu Student、Edu Faculty の有効化/無効化は、まもなく廃止されます。 これは、Microsoft 365 管理センターでライセンスを割り当てることにより管理する必要があります。 「[Microsoft Teams へのユーザー アクセスを管理する](user-access.md)」を参照してください。
<br><br>
<sup>2</sup> サイドローディングは、次のように分割されます。

- [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy) でユーザー レベルで管理できるアプリのサイドロードをユーザーに許可します。
- 組織全体のアプリ設定でテナント レベルで管理できるカスタム アプリの操作を、テナント内のユーザーに許可します。

<sup>3</sup> 既定のアプリと外部アプリは、TeamsAppPermissionPolicy でユーザー レベルで有効または無効にできます。 また、アプリは、組織全体のアプリ設定でテナント レベルでブロックすることもできます。この場合、ユーザー設定やテナントレベルの設定は上書きされます。

> [!NOTE]
> Teamsとチャネルに関連する構成では、Microsoft 365 管理センターの [グループ] ダッシュボードを引き続き使用します。 アプリの設定は Microsoft 365 管理センターの Teams エリアに残っていますが、将来移行される予定です。

## <a name="manage-settings-during-the-migration"></a>移行時に設定を管理する

セクションの移行がテナントに対して完了するまでは、Microsoft 365 管理センターと Skype for Business 管理センターで設定を変更することができます。

次の表に、移行時に何で機能を管理できるかを示します。

|機能  |Microsoft Teams 管理センター                      |Skype for Business 管理センター (レガシ)  |Microsoft 365 管理センター  |
|---------|:---------:|:---------:|:---------:|
|Teams のメッセージング、会議、ライブ イベント ポリシー     |     X    |         |         |
|Teams のアップグレード ポリシー     |    X     |         |         |
|メッセージング、会議、音声のゲスト設定     |   X      |         |         |
|Teams のライフサイクル管理   |    X    |      |       |
|Teams の設定   |    X    |      |       |
|外部アクセス設定     |    X    |      |       |
|ユーザーの管理    |         |         |    X     |
|電話会議     |    X     |    X     |         |
|通話プラン     |    X    |    X     |         |
|電話システム    |    X    |     X    |         |
|電話番号の管理     |    X    |   X      |         |
|クラウド ボイス機能のライセンス     |         |         |    X     |
|自動応答     |    X    |          |         |
|通話キュー     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>移行後に設定を管理する

これらの設定の移行が完了したら、Microsoft 365 管理センターとSkype for Business管理センターで無効にし、新しいMicrosoft Teams管理センターで管理できるようになります。
