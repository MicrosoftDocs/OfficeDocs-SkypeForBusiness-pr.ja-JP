---
title: アップグレード チェックリスト|Skype Business から Teams へのアップグレード|基本的な手順
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: この加速された 10 段階のアクション プランに従って、基本的な Skype for Business セットアップから Microsoft Teams のセットアップに移行します。
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
# <a name="upgrade-basic"></a>Upgrade Basic

<a name="about-upgrade-basic"></a>

小規模な組織向け、または IM (チャット) および会議にのみ Skype for Business Online を使用しているユーザー向けには、アップグレード基本チェックリストは、Skype for Business から Teams への移行を成功に向け実装するためのコア、推奨アクティビティ、関連リソースを含む、高速化されたアクション プランです。

この 10 の簡単な手順は、アップグレードを成功するために必要なすべてを提供します。 これらのタスクは、約 30 ~ 45 日後に完了するように設計されています。ただし、組織のアップグレード スケジュールに基づいてタスクの完了日を調整する必要があります。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止されます。 その後、Skype for Business Online サービスへのアクセスやサポートは終了します。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。

アップグレード後の Skype for Business は何が起こりますか? ユーザーが Teams にアップグレードされた後 (**Teams のみ** モード) は次のようになります:

- Skype for Business クライアントが無効になり、すべてのチャットと通話が Teams に送信されます。 これにより、デスクトップ上のクライアントはアンインストールされないので注意してください。
- アップグレードの前にスケジュールされていた Skype for Business 会議は設計通り動作しますが、すべての新しい会議は Teams でスケジュールされます。 Skype for Business プラグインは Outlook で使用できなくなりました。 
- ユーザーが Skype for Business にサインインしようとする場合、クライアントから Teams にアップグレードされたという通知を受け取ります。
- ユーザーは、モバイル デバイスで Skype for Business クライアントを手動でアンインストールする必要があります。

アップグレードに関 [するその他](./faq-journey.yml) の質問については、よく寄せられる質問を参照してください。

Teams に慣れ親しくない場合 [](https://products.office.com/microsoft-teams/group-chat-software) Teams が会話、会議、ファイル、Office アプリ、サードパーティとの統合を一緒に行う方法について説明します。Microsoft 365 と Office 365 でチームワークのためのハブを 1 つ提供します。

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>手順 1. 主要な関係者に通知する

*(アップグレードの約 4 から 6 週間前)*

上級リーダーは会社の成功に対して責任を持つテクノロジの変更について常に知っている必要があります。 アップグレード資格の通知を受け取ったユーザーや読む人がいない可能性がある場合は、アップグレードの計画を開始する前に、関係者 (CEO、IT プロ、マーケティング、ヘルプデスク のリードなど) に通知する必要があります。

**リソース:**

- [メールの例: 関係者とのコミュニケーション](upgrade-emails-surveys.md#step-1-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>手順 2. Teams に向けて組織を準備する

*(アップグレードの約 4 から 6 週間前)*

Teams は、IM (チャット) や会議などの互換性のある Skype for Business 機能を提供しますが、さらに多くの機能を利用できます。 Teams はチームワークの真のハブとして、ワークグループがプロジェクト、ファイル、会話、アプリを 1 つの場所ですべて管理できます。 既定では、Teams はすべての組織でオンになります。 組織で Teams を使用する方法を決定し、成功のために環境を構成します。 

> [!Note]
> 既存の Skype for Business のお客様は、現在のネットワーク インフラストラクチャが Teams 用に既に構成されている可能性があります。 これを確認するには、以下にリンクされている「完全な技術計画」のガイダンスに従ってください (これはオプションです)。

**リソース:**

- [Teams の概要](Teams-overview.md)
- [Microsoft Teams の使用を開始する](get-started-with-teams-quick-start.md)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>手順 3. Skype for Business ユーザーを知る

*(アップグレードの約 4 週間前)*

Skype for Business に深く採用されているユーザーは、Teams への移行に少し時間や支援が必要になる場合があります。 追加のサポートが必要な上位ユーザーを特定し、アップグレード後の番号に対して追跡できる使用基準計画を確立するには、時間を取って現在の Skype for Business の使用状況を確認します。

**リソース:**

- [管理センターでの Microsoft 365 レポート](/microsoft-365/admin/activity-reports/activity-reports)

[ページのトップへ](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>手順 4. Skype for Business から Teams にアップグレードするユーザーに通知する

*(アップグレードの約 2 ~ 3 週間前)*

ユーザーに十分な通知を提供することで、生産性に悪影響を与えることなく Teams を使い慣れる時間が与え、ユーザー エクスペリエンスが向上します。 通信を送信して、何が変化し、なぜ変化し、どのように準備できるのかを伝えます。

> [!Note]
> 必要に応じて、現時点で Microsoft 365 管理センターを介してユーザーの Teams を有効にできます。

**リソース:**

- [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)
- [サンプル メール: Skype for Business に関するユーザーへのお知らせ](upgrade-emails-surveys.md#step-4-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>手順 5. ユーザー アップグレード通知をアクティブ化する

*(アップグレードの約 1 週間前)*

管理ポータルを介してユーザーアップグレード通知を有効にすることで、ユーザーが Skype for Business から Teams にアップグレードされるという視覚的な通知を Skype for Business クライアントで提供することで、アップグレードのモメンタムを維持します。

**リソース:**

- [共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>手順 6. Skype for Business から Teams にアップグレードするユーザーに通知する

*(アップグレードの約 5 日前)*

ユーザーは毎日の仕事に取り組む必要があります。 保留中のアップグレードをユーザーに通知すると、Teams の準備に必要な手順を忘れてはならないと思い出すのに役立ちます。 これは、利用可能なトレーニングと Teams の使用を開始する方法をユーザーに通知する最適な時間です。

**リソース:**

- [サンプル メール: Teams の使用を開始するユーザーに通知する](upgrade-emails-surveys.md#step-6-email)

[ページのトップへ](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>手順 7. ユーザーを Teams にアップグレードしましょう。

*(アップグレード日)*

今日は、組織がコミュニケーションとコラボレーションのソリューションとして Teams に正式にアップグレードする日です。 Microsoft Teams 管理センターで、共存モードを Teams のみに設定して、アップグレード スイッチを **アクティブにします**。 (管理センターで、組織全体の **設定に移動する**  > **Teams のアップグレード**.)ユーザーは、Skype for Business クライアントで、Teams にアップグレードされたという通知を受け取ります。

すべてのユーザーがアップグレードされた後は、歓迎するメールを Teams に送信することをお勧めします。

**リソース:**

- [共存およびアップグレードの設定](setting-your-coexistence-and-upgrade-settings.md)
- [サンプル メール: Teams へのユーザーのようこそ](upgrade-emails-surveys.md#step-7-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>手順 8. Teams の使用状況をベースラインに対して監視する

*(アップグレード後約 1 週間または 2 週間後)*

新しいテクノロジに合わせて調整する場合、時間がかかる場合があります。 使用状況を確認して、ユーザーが Skype for Business と同じレベル (またはより大きいレベル) で Teams を使用している必要があります。 期待されたレベルで Teams を使用していないユーザーにチェックインします。

**リソース:**

- [使用状況データを表示する](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[ページのトップへ](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>手順 9. ユーザーの満足度を測定する

*(アップグレード後約 1 週間または 2 週間後)*

従業員の満足度は、生産性、保持、最終的にはビジネス成果に影響を与えます。 アップグレードに関するユーザーの感情と Teams に対する満足度を評価するために、ユーザーに話し合います。

**リソース:**

- [サンプル メール: ユーザーに対するチェックインと](upgrade-emails-surveys.md#step-9-email)[ユーザーアンケート](upgrade-emails-surveys.md#step-9-surveys)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>手順 10. Teams で ROI を最大化する

*(進行中)*

ユーザーが Teams での IM (チャット) と会議に快適に取り組むには、Teams の共同作業とアプリの統合を使用して使用例を拡張し、新しいソリューションを真に最適化し、投資収益を最大化します。

**リソース:**

- [サンプル メール: ユーザーに Teams をさらに探索を促す](upgrade-emails-surveys.md#step-10-email)

[ページのトップへ](#about-upgrade-basic)