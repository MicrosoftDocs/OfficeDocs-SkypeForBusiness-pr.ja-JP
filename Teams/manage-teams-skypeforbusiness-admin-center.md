---
title: 新しい Microsoft Teams 管理センターへの移行中に Teams を管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: テナント全体を管理する方法を理解し、チームのチームから移行する際のユーザーの設定が新しいマイクロソフトのチーム管理センターに Office 365 の管理センターで発生します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 9f1adb47709d3e053bb2349d8a3e548bedc58d9d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199568"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>新しい Microsoft Teams 管理センターへの移行中に Teams を管理する
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>新しいマイクロソフトのチーム管理センターとは何ですか。  

新しい admin center のエクスペリエンスにチームやビジネス用の Skype の両方を管理するための統一された操作性が提供されます。 追加機能、エンド ・ ツー ・ エンドの洞察、およびユーザー レベルでのチームの設定を管理する機能を提供することはしています。

![マイクロソフトのチーム管理センターのスクリーン ショットです。](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>設定は新たにマイクロソフトのチーム管理センターに移行

移行され、新しい管理ポータルで現在の設定とポリシーの関係を示しているチームの経験のセクションを次の表に示します。

|Office 365 管理センターでのチームのセクション  |名 (テナント レベル) を設定します。  |マイクロソフトのチーム管理センターのポリシー   |レベル: テナントまたはユーザー   |
|---------|---------|---------|---------|
|General     |個人プロファイルで組織のチャットを表示します。        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  テナント       |
|General     |ビジネスの Skype を使用して、チームを持っていない受信者         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|電子メールの統合     |チャンネルに電子メールを送信するユーザーを許可します。         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|電子メールの統合     |送信者を許可する] ボックスの一覧         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |テナント         |
|カスタム クラウド ストレージ     |ボックス         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|カスタム クラウド ストレージ     |ドロップ ボックス        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|カスタム クラウド ストレージ     |Google ドライブ        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|カスタム クラウド ストレージ     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |テナント         |
|ユーザーとライセンスの種類を設定     |すべてのユーザーの Microsoft チームのオンとオフをオンにします。          |廃止<sup>1</sup>        |         |
|Teams とチャネル     |         |Azure Active Directory グループの管理 (現在のエクスペリエンスと同じ) にリダイレクトします。              |ユーザー         |
|Teams とチャネル     |         |AAD グループの管理 (現在のエクスペリエンスと同じ) にリダイレクトします。             |ユーザー          |
|アプリ|Enable new external apps by default (既定で新しい外部アプリを有効にする)|組織全体にわたるアプリケーションの設定|テナント|
|アプリ|外部のアプリケーションを許可します。|組織全体にわたるアプリケーションの設定|テナント|
|アプリ|外部アプリケーション<sup>2</sup>の sideloading を許可します。|[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|ユーザー|
|アプリ|既定のアプリケーション<sup>3</sup>|TeamsAppPermissionPolicy|ユーザー|
|アプリ|外部アプリケーション<sup>3</sup>|TeamsAppPermissionPolicy|ユーザー|
|通話や会議     |個人の会議のスケジュールを設定できるようにします。         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |ユーザー          |
|通話や会議     |アドホック チャネルの meetup を許可します。         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |ユーザー          |
|通話や会議     |チャネルの会議のスケジュールを設定できるようにします。         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |ユーザー          |
|通話や会議     |会議のビデオを許可します。         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |ユーザー          |
|通話や会議     |画面の会議で共有を許可します。         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |ユーザー          |
|通話や会議     |プライベート通話を許可します。         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |ユーザー          |
|メッセージング      |Gif を会話に追加できるように、Giphy を有効にします。         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |コンテンツの規制         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |Memes のユーザーは編集したり、会話に追加するを有効にします。         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |ユーザーが編集および会話に追加できるステッカーを有効にします。         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |所有者がすべてのメッセージを削除するのには         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |独自のメッセージの編集を許可します。         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |独自のメッセージを削除するユーザーを許可します。         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |
|メッセージング      |個別にチャットすることができます。         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |ユーザー         |

<sup>1</sup>は、ゲストから廃止されます。 ゲストを有効にする無効にすると管理できるように、マイクロソフトのチーム管理センターで。 企業、Edu の学生のチームを有効にする無効にして、Edu 教職員がすぐに使用できません。 これは、Office 365 の管理センターでのライセンスを割り当てることによって管理する必要があります。 [マイクロソフトのチームへのユーザー アクセスの管理](user-access.md)を参照してください。
<br><br>
<sup>2</sup> Sideloading に次のように分割されます。

- [TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)のユーザー レベルで管理することができる sideload アプリケーションにユーザーを許可します。
- テナント レベルで組織全体にわたるアプリケーションの設定を管理できますが、カスタム アプリケーションとの対話をテナントにできるようにします。
 
<sup>3</sup>既定のアプリケーションと外部アプリケーションが有効になって、TeamsAppPermissionPolicy のユーザー レベルで無効になります。 さらに、組織全体にわたるアプリケーションの設定ですべてのユーザーとテナント レベルの設定をオーバーライドするテナント レベルでアプリケーションをブロックできます。 

> [!NOTE]
> Office 365 の管理センターでチームとのチャネルに関連する構成のグループのダッシュ ボードを使用する続行するでしょう。 アプリケーションの設定は、Office 365 の管理センターの [チーム] 領域で残され、後で移行されます。 

## <a name="manage-settings-during-the-migration"></a>移行時に設定を管理します。

セクションの移行が、テナントの完了するまで、Office 365 管理センターでは、ビジネス管理センターの Skype の設定を変更するのには続行することができます。 

移行時に、機能を管理する場所を次の表に示します。

|機能  |マイクロソフトのチーム管理センター                      |Skype のビジネス管理センター (レガシ)  |Office 365 管理者センター  |
|---------|:---------:|:---------:|:---------:|
|チームが、メッセージング、会議、およびイベントのライブのポリシー     |     X    |         |         |
|チームのアップグレードのポリシー     |    X     |         |         |
|ゲストのメッセージ、会議、および音声の設定     |   X      |         |         |
|チームのライフ サイクル管理   |    X    |      |       |
|チームの設定   |    X    |      |       |
|外部アクセスの設定     |    X    |      |       |
|ユーザーの管理    |         |         |    X     |    
|電話会議     |    X     |    X     |         |
|通話プラン     |         |    X     |         |
|電話システム    |         |     X    |         |
|電話番号の管理     |         |   X      |         |
|クラウドの音声機能のライセンス     |         |         |    X     |
|自動応答     |         |    X     |         |
|通話キュー     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>移行後の設定を管理します。

これらの設定の移行が完了すると、Office 365 管理センターでは、ビジネス管理センターでは、Skype でに無効にし、新しいマイクロソフトのチーム管理センターで管理することができますし。


