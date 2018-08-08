---
title: マイクロソフト チーム クラウドのインターネット電話サービスを展開します。
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 05/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: サイトの対応戦略、チームのロールアウトを計画し、加速し、ユーザーの選定、品質、および満足度の認識を最適化をダウンロードします。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a3e40009a76ef7c8f31d659d45de1e4acf0801ec
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "19695511"
---
# <a name="deploy-my-service"></a>サービスを展開します。

この資料では、クラウドの音声サービスを正しく展開するための要件の概要を示します。 次のことを確認するクラウドの音声サービスを展開するための規範的なガイダンスが正常にすべての要件を明確にして反復可能な結果を提供します。

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>音声のワークロードをマイクロソフト チームのサイトの有効化の戦略

このプレイブックを使用して、正常に計画し、サイトごとにマイクロソフトのチームの音声機能の展開を実行する組織を支援します。

このプレイブックのチーム ボイス展開を成功させる重要な要因に焦点を当てて、特定のサイトを確保するエンド ・ ツー ・ エンドのガイダンスの説明など必要なすべての活動、時間帯、およびリンクを各アクティビティに対応するガイダンスを推奨ユーザーです。

このプレイブックのアクティビティを完了すると、組織は次のタスクを実行できます。

-   効率的に計画して、チームのロールアウト スケジュールを設定します。

-   迅速化し、ユーザーの導入を最適化します。

-   サポートのニーズを削減し、ユーザーの満足度を向上します。

> [!NOTE]
> この記事と関連付けられている戦略はないサービスの有効化に必要なまたは特定のサイトにダイヤル トーンを提供するすべての技術的な構成手順を説明するものです。 代わりに、簡単にオンボードのユーザーに推奨されるタスク活動に重点を置いて、サポート要件を最小限に抑えながら採用の高速度、高速かつ滑らかな遷移をチーム音声のワークロードの使用を開始することがあります。 最適なチームの音声を環境を構成する方法についての技術的なガイダンスは、[チームの音声のワークロードを構成する](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)[チームに直接ルーティングの構成](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)を、契約時のチェックリストを参照してください[チームのコア機能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)を、[のネットワー キングチームの](onboarding-checklist-configure-networking.md)、および[Office 365 を有効化](onboarding-checklist-enable-office-365.md)します。

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>プレイブックの重点分野

プレイブックの焦点は、チームのボイスの展開のユーザーの認識に影響を与える要因に対処します。 アクティビティとタスクは、次の重点分野にグループ化されます。

-   サービス対応の検証
    - 電話会議
    - 通話プラン
    - 直接のルーティング

-   ユーザーの有効化

-   エンドポイント

-   使用率と品質

-   導入

[(戦略) の音声をサイトの有効化の戦略](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)は、Microsoft Excel ブックです。 ブック内の別のシートは、これらの 5 つの重点分野のそれぞれと各展開タスクと活動がこれらのシートのいずれかにグループ化します。

![プレイブックのスクリーン ショット](media/deploy-my-service-image1.png "プレイブックのスクリーン ショット")

> [!NOTE]
> チームの展開のスコープでは、各サイトのプレイブックの別のインスタンスを作成します。

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>プレイブックを使用する方法

規模と複雑さの場所に関係なく各サイトを有効にする必要があります、タスクおよび活動を計画すること十分な事前- し、最適な順序で実行-の前にいる間、および実際のサービス導入後です。 計画およびマイクロソフトのチームの音声を独自の旅を実行する際は、次の手順に従うことをお勧めします。

1.  マイクロソフト チームの音声を[サイトの有効化の戦略](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)(戦略) の音声をダウンロードしてください。

2.  各サイトのプレイブックの別のコピーを作成します。

3.  **{コード-サイト名} のプレイブック**をという名前のワークシートのタブ、[関連するサイトの名前とサイト コードの **{コード-サイト名}** を交換してください。

4.  下図のように**サイト名、サイト コード**、および**計画の実施日**をを入力します。 これは、推奨期限プレイブックですべてのアクティビティを調整するための重要なステップです。

    ![ニューヨークのサイト名、サイト コード NY01、18-20-3 月 3 日の予定日を使用した例](media/deploy-my-service-image2.png "ニューヨークのサイト名、サイト コード NY01、18-20-3 月 3 日の予定日を使用した例")

5.  各動作を確認して、必要な処理を行うスケジュールを説明するように状態を更新します。 状態が視覚的に、以下の説明として表されます。
    <ul>
    <li>![緑のチェック マーク](media/deploy-my-service-image3.png) **[はい]、または該当なし (緑):** 、アクティビティが完了すると、やこのサイトの該当する場合はそれ以上の操作は必要ありません。</li>
    <li>![黄色の感嘆符](media/deploy-my-service-image4.png)**活動はまだ完了されていない、(黄色):** 活動がまだ完了していないし、スケジュール上、はいまたは No に更新する必要があります。</li>
    <li>![赤の X](media/deploy-my-service-image5.png) **(赤):** 活動の問題が発生したためが完了できず、プロジェクトの進捗会議を行う必要があります。</li></ul>

6.  状態は、各セクションに重ね、セクションの見出しは、これらのステータス インジケーターのいずれかでフォーマットされました。 **毎週のステータス**に自動的に更新されます。

![毎週の状態のロールアップ、プレイブックでのスクリーン ショット](media/deploy-my-service-image6.png "毎週の状態のロールアップ、プレイブックでのスクリーン ショット")

> [!TIP]
> あるすべての場所で上記の手順を繰り返します。

> [!IMPORTANT]
> いくつかの手順をすべての場所やサイトに適用されることができない場合があります。 場合は、特定のアクティビティには、サイトに関連のない場合を選択してください**適用されない**この活動にします。 **削除しないで**プレイブック; のいずれかの行その場合は、状態ロールアップ数式は機能しません。<br/><br/>
番号を移植するなどの計画より多くの時間を要する可能性がある活動と調達活動に注意してください。 これらのアクティビティには、サイト展開の期限も悪影響します。 確認し、アクティビティのリストと関連付けられているタイムラインの更新を毎週、および利害関係者が各サイトと展開のスケジュールは、可能な差異の状態の認識であることを確認するのには、[運営委員会の会議](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide)でそれらを提示することを確認します。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>意思決定ポイント</td><td><ul><li>サイト対応の戦略は、配置に必要なかどうかを決定します。</li><li>マイクロソフト チームのサイトの有効化の戦略をカスタマイズするのすべてのサイトを展開することを担当するユーザーを決定します。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>次のステップ</td><td><ul><li>[サイト対応のプレイブックをダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)してください。</li><li>最初のサイトのサイトの有効化の戦略をカスタマイズします。</li><li>追加のサイトを必要に応じて繰り返します。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->