---
title: アップグレードの支援|Skype Business Online から Teams へのアップグレード
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Skype for Business Online から Teams への支援されたアップグレードの概要
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
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995198"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Skype for Business Online から Microsoft Teams へのアップグレード支援

Microsoft では、2021 年 7 月 31 日にサービスが終了するに合わせ、組織が Skype for Business Online から正常に移行できるよう、Teams へのアップグレード支援を提供しています。 アップグレード支援により、必要な技術的なタスクの数が減り、組織の準備、ユーザー認識、Teams トレーニングに集中できます。

アップグレードの前に、アップグレードガイダンス [を確認](https://aka.ms/SkypeToTeams) することをお勧めします。 アップグレード ガイダンスには、Skype for Business Online から Teams へのアップグレードを完了するための推奨アクティビティと役立つリソースが含まれています。 このガイダンスは、アップグレードのすべての側面を管理するか、支援されたプロセスを使用するかに関して、Teams へのアップグレードを計画している組織に適用されます。

> [!NOTE]
> Teams へのアップグレードを支援する予定の場合は、スケジュールされたアップグレード日の前に、Skype for Business Online から独自のアップグレードを実行できます。 Teams に手動でアップグレードする方法の詳細については、アップグレードのガイダンスを [参照してください](https://aka.ms/SkypeToTeams)。
>
> Skype for Business Server のオンプレミスデプロイでは、アップグレードの支援は利用できません。

## <a name="notifications-for-scheduled-customers"></a>スケジュールされた顧客に関する通知

Teams へのアップグレード支援を予定している Skype for Business Online のお客様は、一連のアップグレード通知を受け取ります。 これらの通知は、スケジュールされたアップグレード日の 90 日前に開始されます。 これらの通知は、Microsoft  365 メッセージ センターでの変更の計画の投稿、Teams 管理センターでのダッシュボード通知のアップグレード、エンド ユーザーへのアプリ内フラグとして配信されます。

アップグレード通知には、アップグレード支援の予定日が含まれます。また、Teams の導入と使用を促進するためにリソースとトレーニングのアップグレードにリンクします。

## <a name="the-assisted-upgrade-experience"></a>アップグレードの支援を受け取るエクスペリエンス

支援アップグレードは 2021 年 8 月に開始され、上記のスケジュール通知でテナント固有の日付が共有されます。

アップグレードの期間は、ユーザーのボリュームとデプロイの特性によって異なります。 ただし、ほとんどの場合、テナント内のユーザーは、アップグレードの開始から 24 時間以内にアップグレードされます。 この間、エンド ユーザーは引き続き Skype for Business Online 機能にアクセスできます。 アップグレードが完了し、ユーザーが Skype for Business Online からサインアウトすると、メッセージング、会議、通話に Teams の使用が開始されます。

## <a name="the-post-upgrade-experience"></a>アップグレード後のエクスペリエンス

支援されたアップグレードが完了すると、アップグレードされたユーザーの共存モードは Teams Only に設定され、Microsoft によって異なる共存モードにのみ変更できます。 アップグレード前に [Teams Only モードの考慮事項を確認](teams-only-mode-considerations.md) することをお勧めします。 次の表は、Teams Only ユーザー エクスペリエンスの概要を示しています。

:::row:::
    :::column span="1":::
        **チャットと通話**
    :::column-end:::
    :::column span="3":::
        - Teams ですべての通話とチャットが開始および受信される
        - ユーザーは、Skype for Business ユーザーと通信 (チャット/通話) できます
        - 組織は、外部アクセス許可を管理することで、Teams ユーザーが Skype コンシューマー サービスのユーザーと通信 [できます。](manage-external-access.md)
        - Skype for Business Online へのサインインを試みる Teams ユーザーは、Teams にリダイレクトされます。
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **会議**
    :::column-end:::
    :::column span="3":::
        - ユーザーが Teams ですべての新しい会議をスケジュールする (プラグインが置き換えられた)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **移行されたデータ**
    :::column-end:::
    :::column span="3":::
        - フェデレーションを含む Skype for Business Online の既存の連絡先 (ただし、配布リストはありません)
        - 既存の Skype for Business Online 会議が Teams 会議に変換される
    :::column-end:::
:::row-end:::

## <a name="related-content"></a>関連コンテンツ

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [Skype for Business Online のサポート終了](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams Only モードの考慮事項](teams-only-mode-considerations.md)
