---
title: 支援付きアップグレード|SkypeBusiness Online からアップグレードTeamsする
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Skype for Business Online から Skype for Business への支援付きアップグレードの概要Teams
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
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Skype for Business Online から Microsoft Teams への支援付きMicrosoft Teams

Microsoft では、サービスが 2021 年 7 月 31 日に終了するSkype for Business Online から組織が移行を成功させるのに役立つ、Teams への支援付きアップグレードを提供しています。 アップグレードの支援により、実行する必要がある技術タスクの数が減り、組織の準備、ユーザーの認識、トレーニングへの集中Teamsできます。

アップグレードの前に、アップグレードガイダンス [を確認](https://aka.ms/SkypeToTeams) することをお勧めします。 アップグレード ガイダンスには、Skype for Business Online から Teams へのアップグレードを完了するための推奨アクティビティと役に立つリソースが含まれています。 このガイダンスは、アップグレードのすべての側面を管理するか、支援されたプロセスを使用Teams、Teams へのアップグレードを計画しているすべての組織に適用されます。

> [!NOTE]
> Teams への支援付きアップグレードをスケジュールしている場合は、スケジュールされたアップグレード日の前に Skype for Business Online から独自のアップグレードを実行できます。 アプリケーションに手動でアップグレードする方法の詳細については、Teams ガイダンスを[参照してください](https://aka.ms/SkypeToTeams)。
>
> サポートされているアップグレードは、オンプレミスのデプロイで使用Skype for Business Server。

## <a name="notifications-for-scheduled-customers"></a>スケジュールされた顧客に関する通知

Skype for Businessオンライン のお客様は、サービスへのアップグレードの支援をTeams、一連のアップグレード通知を受け取ります。 これらの通知は、スケジュールされたアップグレード日の 90 日前に開始されます。 これらの通知は、Microsoft 365メッセージ センターでの変更の投稿の計画、Teams 管理センターでのダッシュボード通知のアップグレード、エンド ユーザーへのアプリ内フラグとして配信されます。

アップグレード通知には、支援されたアップグレードのスケジュールされた日付が含まれます。アップグレードリソースとトレーニングにリンクして、アップグレードリソースの導入と使用を促進Teams。

## <a name="the-assisted-upgrade-experience"></a>支援付きアップグレード エクスペリエンス

支援付きアップグレードは 2021 年 8 月に開始され、上記のスケジュール通知でテナント固有の日付が共有されます。

アップグレードの期間は、ユーザーの量とデプロイの特性によって異なります。 ただし、ほとんどの場合、テナント内のユーザーは、アップグレードの開始から 24 時間以内にアップグレードされます。 この期間中、エンド ユーザーは引き続きオンライン機能Skype for Businessアクセスできます。 アップグレードが完了し、ユーザーが Skype for Business Online からサインアウトすると、メッセージング、会議、通話に Teams の使用が開始されます。

## <a name="the-post-upgrade-experience"></a>アップグレード後のエクスペリエンス

支援付きアップグレードが完了すると、アップグレードされたユーザーの共存モードは Teams のみに設定され、Microsoft によって異なる共存モードにのみ変更できます。 アップグレードの前に、Teams[モードに関する考慮事項を確認](teams-only-mode-considerations.md)することをお勧めします。 次の表は、「ユーザー エクスペリエンスのみ」の概要Teamsを示しています。

:::row:::
    :::column span="1":::
        **チャットと通話**
    :::column-end:::
    :::column span="3":::
        - すべての通話とチャットが開始され、受信Teams
        - ユーザーは、任意のユーザーと通信 (チャット/通話) Skype for Businessできます。
        - 組織は、外部Teamsアクセス許可を管理することで、Skype コンシューマー サービスのユーザーと通信できます[。](manage-external-access.md)
        - Teams Online にサインインしようとしたユーザーは、Skype for BusinessにリダイレクトTeams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **会議**
    :::column-end:::
    :::column span="3":::
        - ユーザーは、すべての新しい会議を Teamsスケジュールします (プラグインは置き換え)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **移行されたデータ**
    :::column-end:::
    :::column span="3":::
        - フェデレーションを含む Skype for Business Online の既存の連絡先 (ただし、配布リストは含め)
        - 既存の Skype for Business Online 会議は、オンライン会議にTeamsされます
    :::column-end:::
:::row-end:::

## <a name="related-content"></a>関連コンテンツ

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [Skype for Business Online のサポート終了](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams Only モードの考慮事項](teams-only-mode-considerations.md)
