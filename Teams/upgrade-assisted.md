---
title: 支援付きアップグレード|Skype Business Online をアップグレードTeamsする
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Skype for Business Online から Teams への支援付きアップグレードの概要
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44ca04f9fce23876c7ee782ef5cc5078da7e67c4
ms.sourcegitcommit: 8d728ca42dc917a28b94e2de84ce4f5b2515d485
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61513468"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Skype for Business Online から Microsoft Teams への支援付きMicrosoft Teams

Microsoft では、サービスが 2021 年 7 月 31 日に終了するTeams Skype for Business Online から組織が正常に移行できるよう、Teams へのアップグレードを支援しています。 組織がハイブリッド (Skype for Business *Online* と Skype for Business *Online* の両方のユーザー) からアップグレードSkype for Business **かどうかSkype for Business Server**) 環境、支援付きアップグレードにより、実行する必要がある技術タスクの数が減り、組織の準備、ユーザーの認識、トレーニングへの集中Teamsできます。

アップグレードの前に、アップグレードガイダンス [を確認](https://aka.ms/SkypeToTeams) することをお勧めします。 アップグレード ガイダンスには、Skype for Business Online から Teams へのアップグレードを完了するための推奨アクティビティと役に立つリソースが含まれています。 このガイダンスは、アップグレードのすべての側面を管理するか、支援されたプロセスを使用Teams、Teams へのアップグレードを計画しているすべての組織に適用されます。

> [!NOTE]
> Teams への支援付きアップグレードをスケジュールしている場合は、Skype for Business Online からスケジュールされたアップグレード日の前に独自のアップグレードを実行できます。 アプリケーションに手動でアップグレードする方法の詳細については、Teams ガイダンスを[参照してください](https://aka.ms/SkypeToTeams)。
>
> サポートされているアップグレードは、オンプレミスのデプロイで使用Skype for Business Server。

## <a name="notifications-for-scheduled-customers"></a>スケジュールされた顧客に関する通知

Skype for Businessへのアップグレードの支援が予定されているオンラインのお客様Teams、一連のアップグレード通知を受け取ります。 これらの通知は、スケジュールされたアップグレード日の 30 日前に開始されます。 これらの通知は、Microsoft 365メッセージ センターでの変更の投稿の計画、Teams 管理センターでのダッシュボード通知のアップグレード、エンド ユーザーへのアプリ内フラグとして配信されます。

アップグレード通知には、支援されたアップグレードのスケジュールされた日付が含まれます。アップグレード リソースとトレーニングにリンクして、アップグレードリソースの導入と使用を促進Teams。

## <a name="the-assisted-upgrade-experience"></a>支援されたアップグレード エクスペリエンス

支援付きアップグレードは 2021 年 8 月に開始され、上記のスケジュール通知でテナント固有の日付が共有されます。

アップグレードの支援は、ハイブリッド環境を使用する Skype for Business Online と Skype for Business Online のどちらの環境を使用しているかによって少し異なります。

- **Skype for Businessオンラインのみ:** 支援されたアップグレード プロセスによって、組織 `TeamsUpgradeOverridePolicy` にポリシーが適用されます。 このポリシーを適用すると、すべての Skype for Business Online ユーザーが [のみ] Teamsされます。
- **Skype for Business ハイブリッド環境を使用する** オンラインでは、次のいずれかのカテゴリに分類されるユーザーが含まれます。

  - オンプレミスのユーザーがオンプレミスにSkype for Business Server
  - Skype for Businessのみモードのオンライン Teamsユーザー
  - Skype for Businessモードではない Online Teamsユーザー

  上記の各カテゴリにユーザーが複数存在する場合、サポートされるアップグレード プロセスでは、そのモードにまだユーザーが存在しない場合にのみ、Skype for Business Online ユーザーが Teams のみモードに切り替わります。 オンプレミスのSkype for Businessは、支援されたアップグレード プロセスの影響を受け取る必要はありません。

> [!NOTE]
> 2021 年 7 月 31 日より後の日付にアップグレードの支援が予定されている場合でも心配はいりません。 アップグレードが完了するまで、組織は Skype for Business Online を使用できます。

アップグレードの期間は、ユーザーの量とデプロイの特性によって異なります。 ほとんどの場合、テナント内のユーザーは、アップグレードの開始から 24 時間以内にアップグレードされます。 この間、エンド ユーザーは引き続きオンライン機能Skype for Businessアクセスできます。 アップグレードが完了し、ユーザーが Skype for Business Online からサインアウトすると、メッセージング、会議、通話に Teams の使用が開始されます。

## <a name="the-post-upgrade-experience"></a>アップグレード後のエクスペリエンス

支援付きアップグレードが完了すると、アップグレードされたユーザーの **共存** モードが [共存モード] Teamsされます。 アップグレードの前に、Teams[モードに関する考慮事項を確認](teams-only-mode-considerations.md)することをお勧めします。 次の表は、「ユーザー エクスペリエンスのみ」のTeams概要を示しています。

:::row:::
    :::column span="1":::
        **チャットと通話**
    :::column-end:::
    :::column span="3":::
        - すべての通話とチャットが開始され、受信Teams
        - ユーザーは、任意のユーザーと通信 (チャット/通話) Skype for Businessできます。
        - 組織は、外部Teamsアクセス許可を管理することで、Skypeコンシューマー サービスのユーザーと通信できます[。](manage-external-access.md)
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
        - 連絡先は、ユーザーが初めてログインTeamsに移行されます。
            > [!IMPORTANT]
            >連絡先は、アップグレードが完了した後 90 日以内に移行する必要があります。
        - 既存の Skype for Business Online 会議は、オンライン会議にTeamsされます
            > [!IMPORTANT]
            > 純粋な Skype for Business Online 構成をお持ちのお客様は、Meeting Migration Service (MMS) を使用して、既存の Skype for Business Online 会議を他の会議Teams必要があります。 アップグレードの支援日より前に MMS を使用することをお勧めします。 MMS の詳細については [、「Meeting Migration Service (MMS) の使用」を参照してください](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
    :::column-end:::
:::row-end:::

Skype for Business Server ハイブリッド デプロイを使用し、Teams にアップグレードする場合は、アップグレードが完了した後、Skype for Business Server と Teams の間でユーザーを移動できます。

## <a name="related-content"></a>関連コンテンツ

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [Skype for Business Online のサポート終了](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams Only モードの考慮事項](teams-only-mode-considerations.md)
