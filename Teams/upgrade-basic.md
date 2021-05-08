---
title: アップグレード のチェックリスト|SkypeBusiness to Teams Upgrade |基本的な手順
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: この高速な 10 ステップのアクション プランに従って、基本的な設定Skype for BusinessセットアップからMicrosoft Teamsに移行します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- seo-marvel-apr2020
- Teams-upgrade-guidance
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-in
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9453ad770b7ca21b5300b193cbafb932ea7645a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120528"
---
# <a name="upgrade-basic"></a>Basic のアップグレード

<a name="about-upgrade-basic"></a>

小規模な組織や、IM (チャット) および会議専用の Skype for Business Online を使用しているユーザー向けに設計された Upgrade Basic チェックリストは、Skype for Business から Teams への移行を成功に移す際のコア、推奨されるアクティビティ、関連リソースを含む高速アクション プランです。

この 10 の簡単な手順は、アップグレードを成功するために必要なすべてを提供します。 これらは約 30 ~ 45 日で完了するように設計されています。ただし、組織のアップグレード スケジュールに基づいてタスクの完了日を調整する必要があります。

> [!IMPORTANT]
> Skype for Businessオンラインは 2021 年 7 月 31 日に廃止されます。 その後、Skype for Business Online サービスにアクセスしたりサポートしたりしなくなりました。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。

アップグレード後Skype for Businessは何が起こりますか? ユーザーが Teams にアップグレードされた後 (**Teams のみ** モード) は次のようになります:

- クライアントSkype for Businessが無効になり、すべてのチャットと通話がTeams。 これにより、デスクトップ上のクライアントはアンインストールされないので注意してください。
- アップグレードSkype for Business前にスケジュールされていた会議は設計通り動作しますが、すべての新しい会議は、Teams。 このSkype for Businessは、このプラグインでは使用Outlook。 
- ユーザーが Skype for Business にサインインしようとして、クライアントからユーザーにアップグレードされたという通知をTeams。
- ユーザーは、モバイル デバイス上のSkype for Businessクライアントを手動でアンインストールする必要があります。

アップグレードに関 [するその他](./faq-journey.yml) の質問については、FAQ を参照してください。

使い慣れたTeams? [Teams](https://products.office.com/microsoft-teams/group-chat-software)が会話、会議、ファイル、Office アプリ、サード パーティの統合を結び付ける方法について説明します。Microsoft 365 と Office 365 でチームワークのための単一のハブを提供します。

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>手順 1. 主要な関係者に通知する

*(アップグレードの約 4 ~ 6 週間前)*

上級リーダーは、会社の成功に対して責任を持っています。テクノロジの変更について常に知り続ける必要があります。 すべてのユーザーがアップグレードの適格性の通知を受信または読んだ可能性はないので、アップグレードの計画を開始する前に、関係者 (CEO、IT プロ、マーケティング、ヘルプデスク リードなど) に通知する必要があります。

**リソース:**

- [電子メールの例: 関係者のコミュニケーション](upgrade-emails-surveys.md#step-1-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>手順 2. Teams に向けて組織を準備する

*(アップグレードの約 4 ~ 6 週間前)*

Teams IM (チャットSkype for Businessなど)、互換性のある機能を提供しますが、さらに多くの機能を利用できます。 チームワークの真のハブとして、Teamsワークグループがプロジェクト、ファイル、会話、アプリを 1 つの場所ですべて管理できます。 既定では、Teams はすべての組織でオンになります。 組織でアプリケーションを使用する方法を決定Teams環境を成功に向け構成します。 

> [!Note]
> 既存の顧客Skype for Business、現在のネットワーク インフラストラクチャが既に構成されている可能性Teams。 これを確認するには、以下にリンクされている「完全な技術計画」ガイダンスに従ってください (これは省略可能です)。

**リソース:**

- [Teams の概要](Teams-overview.md)
- [Microsoft Teams の使用を開始する](get-started-with-teams-quick-start.md)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>手順 3. 自分のユーザーをSkype for Businessする

*(アップグレードの約 4 週間前)*

アプリケーションに深く採用されているSkype for Businessユーザーは、アプリケーションへの移行にもう少し時間や支援が必要Teams。 追加のサポートを必要とするSkype for Businessユーザーを特定し、アップグレード後の番号に対して追跡できる使用基準を確立するために、現在の使用状況を確認する時間を取る。

**リソース:**

- [Microsoft 365センターでレポートを作成する](/microsoft-365/admin/activity-reports/activity-reports)

[ページのトップへ](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>手順 4. ユーザーが新しいバージョンから新しいバージョンにアップグレードSkype for Business通知Teams

*(アップグレードの約 2 ~ 3 週間前)*

ユーザーに十分な通知を提供することで、生産性に悪影響を与えることなく Teams に慣れる時間が与え、ユーザー エクスペリエンスが向上します。 通信を送信して、何が変化し、なぜ変化し、どのように準備できるのかを伝えます。

> [!Note]
> 必要に応じて、この時点Teams管理センターからユーザーのMicrosoft 365を有効にできます。

**リソース:**

- [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)
- [サンプルメール: ユーザーに関する通知Skype for Business](upgrade-emails-surveys.md#step-4-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>手順 5. ユーザー アップグレード通知をアクティブ化する

*(アップグレードの約 1 週間前)*

管理ポータルでユーザーのアップグレード通知を有効にすることでアップグレードの勢いを維持し、Skype for Business クライアントでユーザーが Skype for Business から Teams にアップグレードされるという視覚的なアラートを提供します。

**リソース:**

- [共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>手順 6. ユーザーが新しいバージョンから新しいバージョンにアップグレードSkype for Business通知Teams

*(アップグレードの約 5 日前)*

ユーザーは毎日の責任に取り組む必要があります。 保留中のアップグレードを通知すると、アップグレードの準備に必要な手順を忘れTeams。 これは、利用可能なトレーニングと、トレーニングの開始方法をユーザーに通知する最適なTeams。

**リソース:**

- [サンプル メール: ユーザーにメールの使用を開始Teams](upgrade-emails-surveys.md#step-6-email)

[ページのトップへ](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>手順 7. ユーザーをアップグレードしてTeams!

*(アップグレード日)*

今日は、組織が通信およびコラボレーション ソリューションとしてTeamsにアップグレードする日です。 管理センター Microsoft Teams、共存モードを [のみ] に設定して、アップグレード **スイッチTeamsします**。 (管理センターで、[組織全体]**ページに移動設定**  > **Teams アップグレード .)** ユーザーは、自分のクライアントSkype for Businessにアップグレードされたという通知を受け取Teams。

すべてのユーザーがアップグレードされた後、すべてのユーザーを歓迎する電子メールを送信Teams。

**リソース:**

- [共存およびアップグレードの設定](setting-your-coexistence-and-upgrade-settings.md)
- [サンプル メール: ユーザーをメールにTeams](upgrade-emails-surveys.md#step-7-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>手順 8. ベースラインTeams使用状況を監視する

*(アップグレード後約 1 ~ 2 週間)*

新しいテクノロジに合わせて調整する場合、時間がかかる場合があります。 使用状況を確認して、ユーザーが Teamsと同じレベル以上のレベルで使用Skype for Business。 期待されるレベルでユーザーを使用していないTeamsにチェックインします。

**リソース:**

- [使用状況データを確認する](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[ページのトップへ](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>手順 9. ユーザーの満足度を測定する

*(アップグレード後約 1 ~ 2 週間)*

従業員の満足度は、生産性、リテンション期間、最終的にはビジネス成果に影響を与える可能性があります。 アップグレードに関するユーザーのセンチメントと、アップグレードに対する満足度を評価するには、ユーザーにTeams。

**リソース:**

- [サンプルメール: ユーザーにチェックインし、](upgrade-emails-surveys.md#step-9-email)ユーザーアンケート [を追加する](upgrade-emails-surveys.md#step-9-surveys)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>手順 10. データを使用して ROI を最大化Teams

*(進行中)*

ユーザーが Teams での IM (チャット) と会議に快適に取り組む場合は、Teams コラボレーションとアプリ統合を使用して使用事例を拡張し、新しいソリューションを真に最適化し、投資収益を最大化します。

**リソース:**

- [電子メールのサンプル: ユーザーにさらに詳しいTeams勧め](upgrade-emails-surveys.md#step-10-email)

[ページのトップへ](#about-upgrade-basic)