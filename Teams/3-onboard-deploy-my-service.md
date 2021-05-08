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
description: Site Enablement Playbook をダウンロードして、Teams展開を計画し、ユーザーの導入、品質、満足度の認識を加速および最適化します。
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

この記事では、クラウド音声サービスを適切にデプロイする要件の概要を説明します。 クラウド 音声サービスのデプロイに関する事前のガイダンスに従って、すべての要件を確実に考慮し、反復可能な結果を確実に提供できます。

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>音声ワークロード用のサイトMicrosoft Teamsプレイブック

このプレイブックを使用して、組織がサイト単位で音声機能のMicrosoft Teamsを計画し、実行するのに役立ちます。

すべての必要なアクティビティ、推奨されるタイムライン、各アクティビティの対応するガイダンスへのリンクを含め、このプレイブックでは、特定のサイトに対して Teams 音声展開を成功に導くエンド to エンドガイダンスについて説明し、ユーザーにとって重要な要素に焦点を当てました。

このプレイブックのアクティビティを完了すると、組織は次の操作を実行できます。

-   ロールアウトを効果的に計画し、Teamsします。

-   ユーザーの導入を加速し、最適化します。

-   サポートのニーズを減らし、ユーザーの満足度を高めます。

> [!NOTE]
> この記事と関連するプレイブックは、サービスの有効化や特定のサイトへのダイヤル トーンの提供に必要な技術的な構成手順を説明するためのものではありません。 代わりに、ユーザーを簡単にオンボードするために推奨されるアクティビティとタスクに重点を置き、サポート要件を最小限に抑えながら、導入率の高い迅速でスムーズな移行を通じて Teams 音声ワークロードの使用を開始します。 Teams 音声用に環境を最適に構成する方法に関する技術的なガイダンスについては[、Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)音声ワークロードの構成、Teams での直接ルーティングの構成、Teams のコア機能、Teams[](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)のネットワーク、および Microsoft 365 または[](prepare-network.md)Office 365 の有効化に関する[](onboarding-checklist-enable-office-365.md)オンボード チェックリストを参照してください。 [](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>プレイブックのフォーカス領域

プレイブックの焦点は、音声展開に対するユーザーの認識に影響を与える要因Teamsです。 アクティビティとタスクは、次の重点領域にグループ化されます。

-   サービスの準備の検証
    - 電話会議
    - 通話プラン
    - ダイレクト ルーティング

-   ユーザーの有効化

-   エンドポイント

-   使用状況と品質

-   導入

音声[用サイト有効化プレイブック (プレイブック)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)は、Microsoft Excelです。 これら 5 つのフォーカス領域は、それぞれブック内の個別のシートであり、各展開タスクとアクティビティは、これらのシートの 1 つにグループ化されます。

![サイト有効化プレイブックのスクリーンショット](media/deploy-my-service-image1.png "プレイブックのスクリーンショット")

> [!NOTE]
> 各サイトのプレイブックのインスタンスを、ロールアウトのスコープ内に個別Teamsします。

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>プレイブックの使い方

場所のサイズや複雑さにかかわらず、各サイトを有効にするためには、タスクとアクティビティを十分な早い段階で計画し、実際のサービス ロールアウトの前、中、後に最適な順序で実行する必要があります。 音声を聞き取る独自の体験を計画して実行する場合は、次のMicrosoft Teams勧めします。

1. 音声用[の Site Enablement Playbook (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)をダウンロードして、Microsoft Teamsします。

2. サイトごとにプレイブックのコピーを個別に作成します。

3. **{SiteName-Code}** の Playbook という名前のシートのタブで **、{SiteName-Code}** を関連するサイト名またはサイト コードに置き換えます。

4. 次に **示す [サイト名]、[サイト コード**]、および [起動 **予定** 日] を入力します。 これは重要な手順です。プレイブック内のすべてのアクティビティの推奨期限が調整されます。

   ![サイト名、サイト コード、および予定されている起動日の例](media/deploy-my-service-image2.png "ニューヨークのサイト名、サイト コード NY01、および発売予定日が 3 月 20 日の例")

5. 各アクティビティを確認し、必要なアクションを実行し、タイムラインを操作する間に状態を更新します。 状態は、次の説明に従ってグラフィカルに表されます。
  
   - ![緑色のチェック マーク [はい] または [該当しない ](緑) の図: アクティビティが完了済みか、このサイトに適用できないので、それ以上の操作は ](media/deploy-my-service-image3.png) 必要はありません。</li>
   - ![黄色の感嘆符の図 アクティビティがまだ完了していない (黄色): アクティビティはまだ完了していないので、スケジュールに合って [はい] または [いいえ] に更新する ](media/deploy-my-service-image4.png) <strong></strong>必要があります。</li>
   - ![いいえ (赤) を示す赤い X の図: 問題が原因でアクティビティを完了できないので、プロジェクトの状態会議に持ち ](media/deploy-my-service-image5.png) <strong></strong>越す必要があります。</li></ul>

6. 状態は各セクション内でロールアップされ、セクション見出しは、これらのステータス インジケーターの 1 つで書式設定されます。 **週単位の** 状態も自動的に更新されます。

![プレイブックの週次状態ロールアップのスクリーンショット](media/deploy-my-service-image6.png "プレイブックの週次状態ロールアップのスクリーンショット")

> [!TIP]
> すべての場所について、上記の手順を繰り返します。

> [!IMPORTANT]
> 一部の手順は、すべての場所とサイトに適用できない場合があります。 特定のアクティビティがサイトに関連しない場合は、[このアクティビティに適用 **しない] を選択** する必要があります。 **プレイブック内** の行を削除しない。この場合、状態のロールアップ数式は機能しません。<br/><br/>
番号の移植や調達活動など、予定よりも時間がかかる可能性があるアクティビティに注意してください。 これらのアクティビティは、サイトの展開タイムラインに悪影響を及ぼす可能性があります。 アクティビティ リストと関連するタイムラインを毎週確認して更新し、運営委員会の会議で[](./envision-steering-committee-complete-guide.md)発表して、関係者が各サイトの状態と展開スケジュールからの逸脱の可能性を確実に認識します。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>デプロイに Site Enablement Playbook が必要な場合に決定します。</li><li>展開するサイトごとに、ユーザーのサイト有効化プレイブックMicrosoft Teamsをカスタマイズする責任を持つユーザーを決定します。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Site Enablement プレイブック をダウンロードします</a>。</li><li>最初のサイトのサイト有効化プレイブックをカスタマイズします。</li><li>必要に応じて、追加のサイトに対して同じ手順を繰り返します。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->