---
title: アップグレード チェックリスト|Skype Business to Teams アップグレード |基本的な手順
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: この 10 ステップの高速アクション プランに従って、基本Skype for BusinessセットアップからMicrosoft Teamsセットアップに移行します。
ms.localizationpriority: medium
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
ms.openlocfilehash: 9ad2dcc08bcbb1136c1b00fccf16b4e1e80a74f2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400811"
---
# <a name="upgrade-basic"></a>Basic をアップグレードする

<a name="about-upgrade-basic"></a>

小規模な組織向け、または im (チャット) 用のSkype for Business Online と会議のみを使用するユーザー向けに設計された Upgrade Basic チェックリストは、Skype for BusinessからTeamsへの正常な移行を実装するためのコア、推奨されるアクティビティ、関連リソースを含む迅速なアクション プランです。

これらの 10 個の簡単な手順により、アップグレードを正常に行うのに必要なものがすべて提供されます。 これらは約 30 日から 45 日以内に完了するように設計されていますが、組織のアップグレード スケジュールに基づいてタスクの完了日を調整する必要があります。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止されました。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。

アップグレード後のSkype for Businessはどうなりますか? ユーザーが Teams にアップグレードされた後 (**Teams のみ** モード) は次のようになります:

- Skype for Business クライアントは無効になっており、すべてのチャットと通話がTeamsに移動します。 デスクトップ上のクライアントはアンインストールされないことに注意してください。
- アップグレード前にスケジュールされたSkype for Business会議はすべて設計どおりに機能しますが、すべての新しい会議はTeamsでスケジュールされます。 Skype for Business プラグインはOutlookでは使用できなくなります。 
- ユーザーがSkype for Businessにサインインしようとすると、クライアントからTeamsにアップグレードされたことを通知されます。
- ユーザーは、モバイル デバイスでSkype for Business クライアントを手動でアンインストールする必要があります。

アップグレードに関するその他の質問については、 [FAQ](./faq-journey.yml) を参照してください。

Teamsについてよく知りませんか? Teamsが会話、会議、ファイル、Office アプリ、サードパーティの統合をまとめ、Microsoft 365とOffice 365のチームワークのための 1 つのハブを提供する[方法について説明](https://products.office.com/microsoft-teams/group-chat-software)します。

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>手順 1. 主要な利害関係者に通知する

*(アップグレードの約 4 ~ 6 週間前)*

上級リーダーは会社の成功に対して責任を負います。テクノロジの変更については、必ず把握しておいてください。 アップグレードの適格性に関する通知を全員が受け取ったり読んだりするわけではない可能性があるため、アップグレードの計画を開始する前に、利害関係者 (CEO、IT 担当者、マーケティング、ヘルプデスク リーダーなど) に通知する必要があります。

**リソース：**

- [電子メールのサンプル: 利害関係者とのコミュニケーション](upgrade-emails-surveys.md#step-1-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>手順 2. Teams に向けて組織を準備する

*(アップグレードの約 4 ~ 6 週間前)*

Teamsには、IM (チャット) や会議などの互換性のあるSkype for Business機能が用意されていますが、さらに多くの機能を実行することもできます。 チームワークの真のハブとして、Teamsはワークグループがプロジェクト、ファイル、会話、アプリをすべて 1 か所で管理できるようにします。 既定では、Teams はすべての組織でオンになります。 組織でTeamsを使用する方法を決定し、環境を成功に向けて構成します。 

> [!Note]
> 既存のSkype for Business顧客として、現在のネットワーク インフラストラクチャは既にTeams用に構成されている可能性があります。 これを確認するには、以下にリンクされている "完全な技術計画" ガイダンスに従います (これは省略可能です)。

**リソース：**

- [Teams の概要](Teams-overview.md)
- [Microsoft Teams の使用を開始する](get-started-with-teams-quick-start.md)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>手順 3. Skype for Business ユーザーを把握する

*(アップグレードの約 4 週間前)*

Skype for Businessで深く採用されているユーザーは、Teamsへの移行にもう少し時間や支援が必要な場合があります。 現在のSkype for Business使用状況を確認し、追加のサポートが必要な上位ユーザーを特定し、使用基準を確立するために時間を取ってアップグレード後の番号に対して追跡できます。

**リソース：**

- [管理センターでレポートをMicrosoft 365する](/microsoft-365/admin/activity-reports/activity-reports)

[ページのトップへ](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>手順 4. Skype for BusinessからTeamsにアップグレードすることをユーザーに通知する

*(アップグレードの約 2 ~ 3 週間前)*

ユーザーに十分な通知を提供すると、生産性に悪影響を及ぼすことなく、Teamsに慣れる時間が与えられます。その結果、ユーザー エクスペリエンスが向上します。 コミュニケーションを送信して、何が変わるのか、なぜ変わるのか、どのように準備できるかを伝えます。

> [!Note]
> 必要に応じて、この時点でMicrosoft 365 管理センター経由でユーザーのTeamsを有効にすることができます。

**リソース：**

- [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)
- [サンプル メール: Skype for Businessに関するユーザーへのお知らせ](upgrade-emails-surveys.md#step-4-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>手順 5. ユーザー アップグレード通知をアクティブ化する

*(アップグレードの約 1 週間前)*

管理者ポータルを使用してユーザーアップグレード通知を有効にすることで、アップグレードの勢いを維持し、ユーザーがSkype for BusinessからTeamsにアップグレードされていることをSkype for Business クライアントで視覚的に通知します。

**リソース：**

- [共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>手順 6. Skype for BusinessからTeamsにアップグレードすることをユーザーに通知する

*(アップグレードの約 5 日前)*

ユーザーは毎日の責任に追われます。 保留中のアップグレードを思い出すと、Teamsの準備に必要な手順を確実に実行できるようになります。 これは、利用可能なトレーニングと、Teamsの使用を開始する方法についてユーザーに思い出させるのに最適な時期です。

**リソース：**

- [サンプル メール: ユーザーにTeamsの使用を促す](upgrade-emails-surveys.md#step-6-email)

[ページのトップへ](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>手順 7. ユーザーをTeamsにアップグレードします。

*(アップグレード日)*

今日は、組織がコミュニケーションおよびコラボレーション ソリューションとしてTeamsに正式にアップグレードする日です。 Microsoft Teams管理センターで、共存モードを **[Teamsのみ**] に設定してアップグレード スイッチをアクティブにします。 (管理センターで、**Teams** >  **Teamsアップグレード設定** に移動します。ユーザーは、TeamsにアップグレードされたことをSkype for Business クライアントで通知を受け取ります。

すべてのユーザーがアップグレードされた後、Teamsにメールを送信することをお勧めします。

**リソース：**

- [共存およびアップグレードの設定](setting-your-coexistence-and-upgrade-settings.md)
- [サンプル メール: ユーザーをTeamsに招待する](upgrade-emails-surveys.md#step-7-email)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>手順 8. ベースラインに対するTeams使用状況を監視する

*(アップグレード後約 1~2 週間)*

新しいテクノロジへの調整には時間がかかる場合があります。 使用状況を確認して、ユーザーがSkype for Businessと同じレベル以上のレベルでTeamsを使用していることを確認します。 期待されるレベルでTeamsを使用していないユーザーにチェックインします。

**リソース：**

- [使用状況データを表示する](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[ページのトップへ](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>手順 9. ユーザーの満足度を測定する

*(アップグレード後約 1~2 週間)*

従業員の満足度は、生産性、保有期間、最終的にはビジネス成果に影響を与える可能性があります。 ユーザーに連絡して、アップグレードに関するユーザーのセンチメントと、Teamsに対する満足度を測定します。

**リソース：**

- [サンプル メール: ユーザーにチェックインし](upgrade-emails-surveys.md#step-9-email)、 [ユーザーアンケートを行う](upgrade-emails-surveys.md#step-9-surveys)

[ページのトップへ](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>手順 10. Teamsで ROI を最大化する

*(進行中)*

ユーザーがTeamsで IM (チャット) や会議に慣れた後は、Teamsコラボレーションとアプリの統合を使用してユース ケースを拡張し、新しいソリューションを真に最適化し、投資収益率を最大化することをお勧めします。

**リソース：**

- [サンプル メール: ユーザーがTeamsさらに詳しく調べるよう促す](upgrade-emails-surveys.md#step-10-email)

[ページのトップへ](#about-upgrade-basic)
