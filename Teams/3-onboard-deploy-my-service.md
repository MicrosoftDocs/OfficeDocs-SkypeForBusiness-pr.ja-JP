---
title: Microsoft Teams クラウド ボイス サービスを展開する
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: サイトの有効化プレイブックをダウンロードして、Teams のロールアウトを計画し、ユーザーの導入を加速および最適化し、品質と満足度を認識します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112633"
---
# <a name="deploy-my-service"></a>サービスを展開する

この記事では、クラウド 音声サービスを適切に展開する場合の要件の概要を説明します。 クラウド 音声サービスの展開に関する事前のガイダンスに従って、すべての要件を正しく考慮し、繰り返し可能な結果を提供することができます。

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Microsoft Teams 音声ワークロード用のサイト有効化プレイブック

このプレイブックを使用して、組織が Microsoft Teams 音声機能のロールアウトをサイト単位で正常に計画および実行するのに役立ちます。

必要なすべてのアクティビティ、推奨されるタイムライン、各アクティビティに対応するガイダンスへのリンクなど、このプレイブックでは、ユーザーにとって重要な要素に重点を置き、特定のサイトで Teams の音声展開を成功に導く、エンドツーエンドのガイダンスについて説明します。

このプレイブックのアクティビティを完了すると、組織は次の作業を行います。

-   Teams のロールアウトを効果的に計画し、スケジュールします。

-   ユーザーの導入を加速し、最適化します。

-   サポートのニーズを減らし、ユーザーの満足度を高めます。

> [!NOTE]
> この記事と関連するプレイブックは、サービスの有効化や特定のサイトへのダイヤル トーンの提供に必要な技術的な構成手順について説明するためのものではありません。 代わりに、ユーザーを簡単にオンボードするために推奨されるアクティビティとタスクに重点を置き、サポート要件を最小限に抑えながら、迅速かつスムーズな移行を通じて Teams 音声ワークロードの消費を開始します。 Teams 音声用に環境を最適に構成する方法に関する技術的なガイダンスについては [、Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)音声ワークロードの構成 [、Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)での直接ルーティングの構成 [、Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)のコア機能 [、Teams](prepare-network.md)のネットワーク、 [および Microsoft 365 または Office 365](onboarding-checklist-enable-office-365.md)の有効化に関するオンボーディング チェックリストを参照してください。

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>プレイブックのフォーカス領域

プレイブックの焦点は、Teams の音声展開に対するユーザーの認識に影響する要因に対処します。 アクティビティとタスクは、次のフォーカス領域にグループ化されます。

-   サービスの準備の検証
    - 電話会議
    - 通話プラン
    - ダイレクト ルーティング

-   ユーザーの有効化

-   エンドポイント

-   使用状況と品質

-   導入

音声 [用サイト有効化プレイブック (Playbook) は](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 、Microsoft Excel ブックです。 これら 5 つのフォーカス領域は、それぞれブック内の個別のシートであり、各展開タスクとアクティビティは、これらのシートの 1 つにグループ化されます。

![サイト有効化プレイブックのスクリーンショット](media/deploy-my-service-image1.png "プレイブックのスクリーンショット")

> [!NOTE]
> Teams のロールアウトの範囲で、サイトごとにプレイブックの個別のインスタンスを作成します。

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>プレイブックの使い方

場所の規模や複雑さにかかわらず、各サイトを有効にする場合は、タスクとアクティビティを十分な早い段階で計画し、実際のサービス ロールアウトの前、中、後に最適な順序で実行する必要があります。 Microsoft Teams 音声への独自の手順を計画して実行する場合は、次の手順に従ってください。

1. Microsoft Teams [Voice 用の Voice 用サイト有効化プレイブック (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) をダウンロードします。

2. サイトごとにプレイブックのコピーを個別に作成します。

3. **{SiteName-Code}** の Playbook という名前のシートのタブで **、{SiteName-Code}** を関連するサイト名またはサイト コードに置き換えます。

4. 次に **示すサイト名、サイト** コード、および開始予定日を入力します。 これは重要な手順です。プレイブック内のすべてのアクティビティの推奨期限が調整されます。

   ![サイト名、サイト コード、および開始予定日の例](media/deploy-my-service-image2.png "ニューヨークのサイト名、サイト コード NY01、および 20-Mar-18 の開始予定日の例")

5. 各アクティビティを確認し、必要なアクションを実行し、タイムラインを移動すると状態を更新します。 状態は、以下で説明するようにグラフィックで表されます。
  
   - ![緑のチェック マーク [はい]、または該当しない (緑色) の図: アクティビティが完了したか、このサイトに適用できないので、それ以上のアクションは ](media/deploy-my-service-image3.png) 必要はありません。</li>
   - ![黄色の感嘆符の図。アクティビティがまだ完了していません (黄色): アクティビティはまだ完了していません。スケジュールに合って [はい] または [いいえ] に更新する必要があります。 ](media/deploy-my-service-image4.png) <strong></strong></li>
   - ![[いいえ] (赤) を示す赤い X の図: 問題が原因でアクティビティを完了できないので、プロジェクトの状況会議に持ち ](media/deploy-my-service-image5.png) <strong></strong>込む必要があります。</li></ul>

6. 状態は各セクション内でロールアップされ、セクション見出しは次のいずれかのステータス インジケーターで書式設定されます。 **週単位の** 状態も自動的に更新されます。

![プレイブックの週次ステータスロールアップのスクリーンショット](media/deploy-my-service-image6.png "プレイブックの週次ステータス ロールアップのスクリーンショット")

> [!TIP]
> すべての場所について、上記の手順を繰り返します。

> [!IMPORTANT]
> 一部の手順は、一部の場所とサイトに適用できない場合があります。 特定のアクティビティがサイトに関連しない場合は、[このアクティビティに該当しない] を **選択する必要** があります。 **プレイブック内** の行を削除しない。この操作を行った場合、状態のロールアップ数式は機能しません。<br/><br/>
番号の移植や調達活動など、計画よりも時間がかかる可能性があるアクティビティに注意してください。 これらのアクティビティは、サイト展開タイムラインに悪影響を与える可能性があります。 アクティビティ リストと関連するタイムラインを毎週確認して更新し、運営委員会の会議で[](./envision-steering-committee-complete-guide.md)発表して、関係者が各サイトの状態と展開スケジュールからの偏差の可能性を確実に認識します。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>展開にサイト有効化プレイブックが必要かを決定します。</li><li>展開するサイトごとに、Microsoft Teams のサイト有効化プレイブックをカスタマイズする責任者を決定します。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">サイトの有効化プレイブックをダウンロードします</a>。</li><li>最初のサイト用にサイトの有効化プレイブックをカスタマイズします。</li><li>必要に応じて、追加のサイトで同じ操作を繰り返します。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->