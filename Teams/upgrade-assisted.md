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
ms.openlocfilehash: a162a9151413137282d80e47f8f2b08c841e171a
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456890"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Skype for Business Online から Microsoft Teams への支援付きMicrosoft Teams

Microsoft は、Skype for Business 2021 年 7 月 31 日に Microsoft Online の提供を終了しました。  Microsoft は、組織がオンライン ユーザーの残りのユーザーを [オンラインのみ] Skype for Business移行するための支援Teams提供しています。  Microsoft の支援によるアップグレードでは、次の組織に関係なく、技術タスクの数を減らし、Skype for Business Online を使用せずに世界への移行を簡素化します。
 - Skype for Business *Online* からアップグレードして、純粋な組織Teamsする必要がある純粋なオンライン組織。
 - *Skype for Business Online とオンプレミスの Skype for Business Server*  環境の両方にユーザーを含むハイブリッド組織。Skype for Business *Online* ユーザーのみを Teams にアップグレードする必要があります。

アップグレードの前に、アップグレードガイダンス [を確認](https://aka.ms/SkypeToTeams) することをお勧めします。 アップグレード ガイダンスには、推奨されるアクティビティと、Skype for Business Online から Teams へのアップグレードを完了するための役に立つリソースが含まれています。 このガイダンスは、アップグレードのすべての側面を管理するか、支援されたプロセスを使用Teams、Teams へのアップグレードを計画しているすべての組織に適用されます。

## <a name="the-assisted-upgrade-experience"></a>支援されたアップグレード エクスペリエンス
Skype for Business Teams へのアップグレードを支援する予定のオンラインのお客様は、Microsoft 365 メッセージ センターでの投稿の変更、Teams 管理センターでのダッシュボード通知のアップグレード、エンド ユーザーへのアプリ内フラグなど、さまざまな形式の通知を受け取ります。 メッセージ センターと Teams 管理センターのアップグレード通知には、サポートされたアップグレードのスケジュールされた日付と、Teams の導入と使用を促進するためのリソースとトレーニングをアップグレードするためのリンクが含まれます。

アップグレードの支援のエクスペリエンスは、組織にオンプレミスの環境にユーザーが所属しているかどうかによって少しSkype for Business Serverされます。
- **純粋なオンライン組織:** Busineess Server  `TeamsUpgradeOverridePolicy` ユーザー向Skypeオンプレミスのアプリケーションがない組織の場合、支援されたアップグレード プロセスによって組織にポリシーが適用されます。 このポリシーを適用すると、Skype for Business Online のすべてのユーザーが TeamsOnly モードになります。
- **オンプレミスの Skype for Business** ユーザーを持つハイブリッド組織: これには、ハイブリッドが構成されているかどうかに関係なく、Skype for Business Server にホームしているユーザーを持つ組織が含まれます。 これらの組織には、次のいずれかのカテゴリに分類されるユーザーが含まれます。

  - Skype for Business Server にホームされたオンプレミス ユーザー (Teams を使用する場合と使用しない場合Teamsユーザーのみ)
  - Skype for Business Online にホームを持つ TeamsOnly ユーザー
  - Skype for Business Online にホームされている Teams 以外のユーザー

支援されたアップグレード プロセスは、ユーザーの最後のカテゴリにのみ影響を与えます。Skype for Business Online にホームされている非 Teams ユーザーのみ、Teams のみモードにアップグレードされます。 オンプレミスのSkype for Businessユーザーと既存の TeamsOnly ユーザーは、支援されたアップグレード プロセスの影響を受け取る必要はありません。

> [!NOTE]
> アップグレードが完了するまで、Skype for Business Online を引き続き使用できます。 Teams への支援付きアップグレードをスケジュールしている場合は、スケジュールされたアップグレード日の前に Skype for Business Online から独自のアップグレードを実行できます。 アプリケーションに手動でアップグレードする方法の詳細については、Teamsガイダンスを[参照してください](https://aka.ms/SkypeToTeams)。

アップグレードの期間は、ユーザーの量とデプロイの特性によって異なります。 ほとんどの場合、テナント内のユーザーは、アップグレードの開始から 24 時間以内にアップグレードされます。 この間、エンド ユーザーは引き続きオンライン機能Skype for Businessアクセスできます。 アップグレードが完了し、ユーザーが Skype for Business Online からサインアウトすると、メッセージング、会議、通話に Teams の使用が開始されます。

## <a name="the-post-upgrade-experience"></a>アップグレード後のエクスペリエンス

支援付きアップグレードが完了すると、アップグレードされたユーザーの共存モードが [共存モード] Teamsされます。 アップグレードの前に、Teams[モードに関する考慮事項を確認](teams-only-mode-considerations.md)することをお勧めします。 次の表は、「ユーザー エクスペリエンスのみ」の概要Teamsを示しています。

:::row:::
    :::column span="1":::
        **チャットと通話**
    :::column-end:::
    :::column span="3":::
        - すべての通話とチャットが開始され、受信Teams
        - ユーザーは、任意のユーザーと通信 (チャット/通話) Skype for Businessできます
        - 組織は、外部Teamsアクセス許可を管理することで、ユーザーが Skype コンシューマー サービスのユーザーと通信[できます。](manage-external-access.md)
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
        - 連絡先は、ユーザーが初めてログインTeams移行されます。
            > [!IMPORTANT]
            >連絡先は、アップグレードが完了した後 90 日以内に移行する必要があります。
        - 既存の Skype for Business Online 会議は、オンライン会議にTeamsされます
            > [!IMPORTANT]
            > 純粋な Skype for Business Online 構成をお持ちのお客様は、Meeting Migration Service (MMS) を使用して、既存の Skype for Business Online 会議を別の会議にTeams必要があります。 アップグレードの支援日より前に MMS を使用することをお勧めします。 MMS の詳細については、「Meeting [Migration Service (MMS) の使用」を参照してください](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
    :::column-end:::
:::row-end:::

ハイブリッド デプロイをSkype for Business Serverして Teams にアップグレードする場合は、アップグレードが完了した後、Skype for Business Server と Teams の間でユーザーを移動できます。

## <a name="related-content"></a>関連コンテンツ

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [Skype for Business Online のサポート終了](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams Only モードの考慮事項](teams-only-mode-considerations.md)
