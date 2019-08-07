---
title: アップグレードのチェックリスト |Skype Business から Teams へのアップグレード |基本的な手順
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Skype for Business から Teams へのアップグレードに関する10段階のアクションプランの高速化
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 397155766bc966c9591f863a3f97fca59dcb1128
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "35934551"
---
<a name="about-upgrade-basic"></a>

# <a name="upgrade-basic"></a>アップグレードの基本

小規模の組織または Skype for Business Online で IM (チャット) と会議のみを使用するように設計されています。また、アップグレードの基本チェックリストは、コア、推奨アクティビティ、関連リソースを含む、Skype for Business から Teams に正常に移行されました。

この10個の簡単な手順で、アップグレードを成功させるために必要なすべての操作を行うことができます。 30 ~ 45 日後に完了するように設計されていますが、組織のアップグレードスケジュールに基づいて、タスクの完了日を調整する必要があります。

> [!IMPORTANT]
> Skype for Business Online は、2021年7月31日に廃止されます。 その後、Skype for Business Online サービスは、アクセスまたはサポートされなくなります。 給付金を最大限に活用し、組織がアップグレードを実装するための適切な時間を確保するために、Microsoft Teams の現在の旅を開始することをお勧めします。

アップグレード後の Skype for Business はどうなりますか? ユーザーが Teams (**Teams のみ**モード) にアップグレードされた後、次の操作を行います。

- Skype for Business クライアントが無効になり、すべてのチャットと通話が Teams に移動します。 これにより、デスクトップ上のクライアントがアンインストールされることはありません。
- アップグレード前にスケジュールされていた Skype for Business 会議は、設計どおりに動作しますが、すべての新しい会議は Teams でスケジュールされています。
- ユーザーが Skype for Business にサインインしようとすると、そのユーザーはクライアントからチームにアップグレードされたという通知を受け取ります。
- ユーザーは、モバイルデバイスで Skype for Business クライアントを手動でアンインストールする必要があります。

アップグレードに関するその他の質問については、 [FAQ](https://aka.ms/SkypeToTeams-FAQ)をご覧ください。

Teams について理解していない場合 チームでの会話、会議、ファイル、Office アプリ、サードパーティの統合の[概要について説明](https://products.office.com/microsoft-teams/group-chat-software)します。 office 365 でチームワークの単一のハブを提供します。

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>手順1 主要な関係者に通知する

*(アップグレードの前に約 4 ~ 6 週間)*

シニアリーダーは、企業の成功の責任を持ちます。技術の変更については、必ず知っておいてください。 アップグレードの計画を始める前に、参加者 (CEO、IT プロフェッショナル、マーケティング、ヘルプデスクの潜在顧客など) に通知する必要があるため、お客様の関係者に通知する必要があります。

**参照**

- [サンプルメール: 関係者とのコミュニケーション](upgrade-emails-surveys.md#step-1-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>手順2 Teams に向けて組織を準備する

*(アップグレードの前に約 4 ~ 6 週間)*

チームは、IM (チャット) や会議などの Skype for Business の互換性のある機能を提供していますが、その他にも多くのことを行うことができます。 Teams では、チームワークグループの実際のハブとして、プロジェクト、ファイル、スレッド、アプリを1つの場所で管理できます。 組織でチームをどのように使用するかを決定し、成功のために環境を構成します。

> [!Note]
> 既存の Skype for Business のお客様としては、現在のネットワークインフラストラクチャが Teams 用に既に構成されている可能性があります。 これを確認するには、以下にリンクされている「完全な技術計画」のガイダンスに従う必要があります (これは省略可能です)。

**参照**

- [Teams の概要](Teams-overview.md)
- [チームとチャネルについて](teams-channels-overview.md)
- [完全な技術計画](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [Microsoft Teams Rooms を管理する](https://aka.ms/MTRDocs)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>手順3 Skype for Business ユーザーについて知る

*(アップグレードの4週間前)*

Skype for Business に深く採用されているユーザーは、チームへの移行を行うために、さらに時間がかかることがあります。 現在の Skype for Business の使用状況を確認して、追加のサポートが必要な上位ユーザーを特定し、更新後の番号に対して追跡できる使用方法のベースラインを設定します。

**参照**

- [Office 365 のアクティビティレポートの利用状況データを表示する](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

[ページのトップへ](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>手順4。 Skype for Business から Teams にアップグレードすることをユーザーに通知する

*(アップグレードの 1 ~ 3 週間前)*

ユーザーに十分な通知を提供することで、チームの生産性に悪影響を与えずに、チームの理解を深めることができます。その結果、よりポジティブなユーザーエクスペリエンスが得られます。 通信を送信して、何が変更されているか、変更される理由、準備を行う方法を伝えます。

> [!Note]
> この時点で、必要に応じて、Office 365 管理ポータルを使用して、ユーザーに対して Teams を有効にすることができます。

**参照**

- [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)
- [サンプルメール: Skype for Business についてのユーザーへのお知らせ](upgrade-emails-surveys.md#step-4-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>手順5 ユーザーアップグレード通知を有効にする

*(アップグレードの1週間前)*

管理ポータルを使用してユーザーのアップグレード通知を有効にし、skype for business クライアントでユーザーが Skype for Business から Teams にアップグレードすることによって、アップグレードの勢いを維持します。

**参照**

- [共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>手順6 Skype for Business から Teams にアップグレードすることをユーザーに通知する

*(アップグレードの5日後)*

ユーザーは、毎日の責任の対象となります。 保留中のアップグレードについて通知すると、チームの準備に必要な手順を確実に行うことができます。 これは、利用可能なトレーニングや Teams の使用を開始する方法についてユーザーに通知するのに最適なタイミングです。

**参照**

- [サンプルメール: Teams の使用を開始するようにユーザーに通知する](upgrade-emails-surveys.md#step-6-email)

[ページのトップへ](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>手順7 ユーザーを Teams にアップグレードする

*(アップグレード日)*

本日は、お客様の組織がコミュニケーションとコラボレーションソリューションとしてチームに正式にアップグレードした日です。 Microsoft Teams 管理センターで、[共存] モードを [**チームのみ**] に設定してアップグレードスイッチをアクティブ化します。 (管理センターで、[**組織全体の設定** > ]**チームのアップグレード**に移動します)。ユーザーは、Skype for Business クライアントで、チームにアップグレードされたという通知を受け取ります。

全員のアップグレードが完了したら、チームに歓迎するメールを送信することをお勧めします。

**参照**

- [共存およびアップグレードの設定](setting-your-coexistence-and-upgrade-settings.md)
- [サンプルメール: Teams へようこそ](upgrade-emails-surveys.md#step-7-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>手順8 チームの使用状況をベースラインに対して監視する

*(アップグレード後の1週間または2週間後)*

新しいテクノロジに調整するには、時間がかかることがあります。 使用状況を確認して、ユーザーが Skype for Business と同じレベルまたはそれ以上のレベルで Teams を使用していることを確認します。 チームを使用していないユーザーと期待されるレベルでチェックインします。

**参照**

- [利用状況データを表示する](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[ページのトップへ](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>手順9 ユーザー満足度の評価

*(アップグレード後の1週間または2週間後)*

従業員の満足度は生産性、保持度、および最終的なビジネスの結果に影響を与える可能性があります。 ユーザーに連絡して、アップグレードについてのユーザー感情とチームとの満足度を評価する。

**参照**

- [サンプルメール: ユーザーと](upgrade-emails-surveys.md#step-9-email)[ユーザーアンケート](upgrade-emails-surveys.md#step-9-surveys)をチェックインする

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>手順10 Teams で ROI を最大限に活用する

*現状*

ユーザーがチームの IM (チャット) と会議に慣れたら、チームのグループ作業とアプリの統合を使用して、新しいソリューションの最適化と投資による収益の最大化を行うことで、ユースケースを延長することをお勧めします。

**参照**

- [サンプルメール: チームをより詳しく調査するようにユーザーに促します。](upgrade-emails-surveys.md#step-10-email)

[ページのトップへ](#about-upgrade-basic)
