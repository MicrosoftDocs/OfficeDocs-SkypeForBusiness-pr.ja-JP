---
title: アップグレードのサポート|Teams アップグレードに Business Online をSkypeする
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Skype for Business Online から Teams へのアップグレードの概要
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
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Skype for Business Online から Microsoft Teams へのアップグレードの支援

Microsoft は、2021 年 7 月 31 日に Skype for Business Online を廃止しました。  Microsoft は、組織が残りのオンライン ユーザーを Teams のみSkype for Business移行できるように、アップグレード プロセスを支援しています。  Microsoft が支援するアップグレードにより、技術的なタスクの数が減り、組織が次の場合、Skype for Business Online なしで世界への移行が簡略化されます。
 - Skype for Business Online から純粋なTeamsのみになるようにアップグレードする必要がある純粋な *オンライン* 組織、または
 - *Skype for Business Online* **と** オンプレミスの *Skype for Business Server* 環境の両方にユーザーを含むハイブリッド組織。Skype for Business *Online* ユーザーのみを Teams のみにアップグレードする必要があります。

アップグレードする前に [、アップグレードガイダンス](https://aka.ms/SkypeToTeams) を確認することをお勧めします。 アップグレード ガイダンスには、Skype for Business Online から Teams へのアップグレードを完了するための推奨アクティビティと役立つリソースが含まれています。 このガイダンスは、アップグレードのすべての側面を管理するか、支援されたプロセスを使用するかに関係なく、Teamsへのアップグレードを計画しているすべての組織に適用されます。

## <a name="the-assisted-upgrade-experience"></a>アップグレード支援エクスペリエンス
Teamsへのアップグレードを支援するようにスケジュールされているSkype for Business Online のお客様には、Microsoft 365 メッセージ センターでの *変更の投稿の計画*、Teams管理センターでのダッシュボード通知のアップグレード、エンド ユーザーへのアプリ内フラグなど、さまざまな形式の通知が表示されます。 メッセージ センターとTeams管理センターのアップグレード通知には、アップグレードのスケジュールされた日付と、Teamsの導入と使用を促進するためのアップグレード リソースとトレーニングへのリンクが含まれます。

アップグレードを支援するエクスペリエンスは、組織にオンプレミスのSkype for Business Server環境にユーザーが所属しているかどうかによって若干異なります。
- **純粋なオンライン組織:** Busineess Server ユーザーのオンプレミス Skype *がない* 組織の場合、支援されたアップグレード プロセスによってポリシーが`TeamsUpgradeOverridePolicy`組織に適用されます。 このポリシーが適用されると、Skype for Business Online のすべてのユーザーが TeamsOnly モードになります。
- **オンプレミス Skype for Business ユーザーを含むハイブリッド組織:** これには、ハイブリッドが構成されているかどうかに関係なく、Skype for Business Serverに所属するすべてのユーザーを持つ組織が含まれます。 これらの組織には、次のいずれかのカテゴリに分類されるユーザーが存在する場合があります。

  - Skype for Business Serverに所属するオンプレミス ユーザー (Teamsを使用する場合と使用しない場合がありますが、ユーザーのみTeamsされません)
  - Skype for Business Online に所属している TeamsOnly ユーザー
  - Skype for Business Online に所属している TeamsOnly 以外のユーザー

アップグレード支援プロセスは、ユーザーの最後のカテゴリにのみ影響します。非Teams オンラインに所属しているユーザーのみが Skype for Business Teamsのみモードにアップグレードされます。 オンプレミス Skype for Business ユーザーと既存の TeamsOnly ユーザーは、アップグレード の支援プロセスの影響を受けません。

> [!NOTE]
> アップグレードが完了するまで、組織は引き続き Skype for Business Online を使用できます。 Teamsへのアップグレードを支援する予定の場合は、スケジュールされたアップグレード日の前に、Skype for Business Online から独自のアップグレードを実行できます。 Teamsに手動でアップグレードする方法の詳細については、[アップグレードガイダンス](https://aka.ms/SkypeToTeams)を参照してください。

アップグレードの期間は、ユーザーの量とデプロイの特性によって異なります。 ほとんどの場合、テナント内のユーザーは、アップグレードの開始から 24 時間以内にアップグレードされます。 この間、エンド ユーザーは引き続き Skype for Business Online 機能にアクセスできます。 アップグレードが完了し、ユーザーが Skype for Business Online からサインアウトすると、メッセージング、会議、通話にTeamsの使用が開始されます。

## <a name="the-post-upgrade-experience"></a>アップグレード後のエクスペリエンス

支援されたアップグレードが完了すると、アップグレードされたユーザーの **共存モード** が [Teamsのみ] に設定されます。 アップグレード前に[Teamsモードのみの考慮事項を](teams-only-mode-considerations.md)確認することをお勧めします。 次の表に、Teamsのみユーザー エクスペリエンスの概要を示します。

:::row:::
    :::column span="1":::
        **チャットと通話**
    :::column-end:::
    :::column span="3":::
        - すべての通話とチャットは、Teamsで開始および受信されます。
        - ユーザーは、任意のSkype for Business ユーザーと通信 (チャット/通話) できます
        - 組織は、[外部アクセス許可](manage-external-access.md)を管理することで、Teams ユーザーがSkypeコンシューマー サービスのユーザーと通信できるようにします
        - Skype for Business Online にサインインしようとしたユーザーがTeamsにリダイレクトTeams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **会議**
    :::column-end:::
    :::column span="3":::
        - ユーザーは、Teamsのすべての新しい会議をスケジュールします (プラグインが置き換えられました)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **移行されたデータ**
    :::column-end:::
    :::column span="3":::
        - フェデレーションを含む Skype for Business Online からの既存の連絡先 (配布リストは含まない)
        - ユーザーが初めてTeamsにログインすると、連絡先が移行されます。
            > [!IMPORTANT]
            >アップグレードが完了してから 90 日以内に連絡先を移行する必要があります。
        - 既存のSkype for Business オンライン会議は、Teams会議に変換されます
            > [!IMPORTANT]
            > 純粋なSkype for Business Online 構成をお持ちのお客様は、Meeting Migration Service (MMS) を使用して、既存のSkype for Business Online 会議をTeams会議に移行する必要があります。 アップグレードを支援する日付より前に MMS を使用することをお勧めします。 MMS の詳細については、「 [会議移行サービス (MMS) の使用](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。
    :::column-end:::
:::row-end:::

Skype for Business Serverハイブリッド展開があり、Teamsにアップグレードする場合は、アップグレード完了後にユーザーをSkype for Business ServerとTeamsの間で移動できます。

## <a name="related-content"></a>関連コンテンツ

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [Skype for Business Online のサポート終了](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams Only モードの考慮事項](teams-only-mode-considerations.md)
