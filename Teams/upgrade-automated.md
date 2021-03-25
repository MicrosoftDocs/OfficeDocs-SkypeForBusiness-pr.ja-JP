---
title: 自動アップグレード|Skype Business から Teams へのアップグレード
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Skype for Business から Teams への自動アップグレードの概要
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb3fef455e4031c61b6769e114d9cbd1d8bd3805
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120545"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Skype for Business Online から Microsoft Teams への自動アップグレード

Microsoft では、2021 年 7 月 31 日のサービス終了前に小規模企業が Skype for Business Online から移行を成功させるのに役立つ、Teams への自動アップグレードを提供しています。 自動アップグレードにより、顧客に必要な技術的なタスクの数が減り、組織の準備、ユーザーの認識、および Teams のトレーニングに集中できます。

Skype for Business から Microsoft Teams にアップグレードするには、技術的な準備とユーザーの準備を計画する必要があります。 使用を開始する準備ができたら、Microsoft は、Skype [](upgrade-basic.md) for Business から Teams への移行を正常に実装するための主要な推奨アクティビティと関連リソースを扱うアップグレード アクション プランを提供します。

## <a name="notifications-for-scheduled-customers"></a>スケジュール済み顧客への通知

Teams への自動アップグレードの対象となる Skype for Business Online のお客様は、スケジュールされているアップグレード日の 30 日前から一連のアップグレード通知を受け取ります。 これらの通知は、管理メッセージセンターでの変更計画の投稿として配信され、メールをグローバル管理者にアップグレードし、アプリ内フラグをエンド ユーザーにアップグレードします。

これらの通知は、自動アップグレードのスケジュールされた日付を通知し、Teams の導入と使用を促進するためにリソースとトレーニングをアップグレードするためのリンクを提供し、スケジュールされた日付までにアップグレードする準備ができていない場合に、自動アップグレードを 30 日延期するオプションをユーザーに提供します。

## <a name="the-automated-upgrade-experience"></a>自動アップグレードエクスペリエンス

自動アップグレードは、通知メール、メッセージ センター、Teams 管理ポータルで通知される、スケジュールされたアップグレード日に実行されます。 アップグレードには約 15 分かかりますが、エンド ユーザーは Skype for Business Online の機能に引き続きアクセスできます。 アップグレードが完了し、ユーザーが Skype for Business Online をログアウトすると、ユーザーはメッセージング、会議、通話にのみ Teams を使用できます。

## <a name="the-post-upgrade-experience"></a>アップグレード後のエクスペリエンス

自動アップグレードが完了すると、共存モードはTeams のみに設定され、Microsoft によって異なる共存モードにしか変更できません。 管理者は、アップグレード前 [に Teams のみモードに関する考慮事項](teams-only-mode-considerations.md) を確認する必要があります。 次の表は、Teams のユーザー エクスペリエンスの概要を示しています。


|  |  |
|---------|---------|
|**チャットと通話**     | <UL><LI>すべての通話とチャットが Teams で開始および受信される<LI>ユーザーは Skype for Business ユーザーと相互運用 (チャット/通話) できます<LI>ユーザーが Skype for Consumer を使用しているユーザーと通信できない<LI>ユーザーが Skype for Business にサインインしようとして Teams にリダイレクトされる      </UL>  |
|**会議**     |  <UL><LI>ユーザーが Teams ですべての新しい会議をスケジュールする (プラグインが置き換えられる)    </UL>   |
|**移行されたデータ**     |<UL><LI>フェデレーションを含む Skype for Business の既存の連絡先 (配布リストは含め)<LI>既存の Skype for Business 会議 (オンプレムとオンラインの両方) が Teams 会議に変換される</UL>         |

## <a name="postponing-your-automated-upgrade"></a>自動アップグレードを延期する

Skype for Business Online から Microsoft Teams への移行に成功するには、組織が Teams の拡張された機能とパフォーマンスを利用するための準備が完了するために、技術的な計画とユーザーの準備が必要です。 ただし、アップグレードを計画する場合、現時点では組織が Teams にアップグレードする準備ができていない場合があります。

Teams への自動アップグレードのスケジュールに関する通知を受け取り、後日に延期したい場合、グローバル管理者は Teams 管理ポータルにログインし、[延期]ボタンをクリックできます。 これにより、自動アップグレードの日付が 30 日後にプッシュされます。 延期後に Teams 管理ポータルを更新すると、新しい自動アップグレード日を含む通知が表示されます。

## <a name="requests-to-downgrade-to-skype-for-business"></a>Skype for Business へのダウングレード要求

Teams から SfBO への 1 回のダウングレードを許可し、テナントが Teams へのアップグレードの準備をさらに行うのを許可します。 ダウングレードされたテナントは、ダウングレード日から 60 日後に自動アップグレードに再び参加します。

## <a name="related-content"></a>関連コンテンツ

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [Skype for Business Online のサポート終了](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Teams Only モードの考慮事項](teams-only-mode-considerations.md)