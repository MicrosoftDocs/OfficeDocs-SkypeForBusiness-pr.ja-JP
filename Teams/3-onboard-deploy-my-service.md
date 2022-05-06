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
description: Site Enablement Playbook をダウンロードして、Teamsのロールアウトを計画し、ユーザーの導入、品質の認識、満足度を加速して最適化します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5c027da20c6c305fd5924cd6483c5cbd63b8ddd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733546"
---
# <a name="deploy-my-service"></a>サービスを展開する

この記事では、クラウド 音声サービスを適切にデプロイするための要件の概要について説明します。 クラウド 音声サービスをデプロイするための規範的なガイダンスに従うことで、すべての要件を正しく考慮し、繰り返し可能な結果を提供できます。

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Microsoft Teams音声ワークロードのサイト有効化プレイブック

このプレイブックを使用して、組織がサイト単位でMicrosoft Teams音声機能のロールアウトを正常に計画して実行するのに役立ちます。

このプレイブックには、必要なすべてのアクティビティ、推奨されるタイムライン、および各アクティビティに対応するガイダンスへのリンクが含まれています。このプレイブックでは、特定のサイトの音声展開 Teamsを成功させるためのエンド ツー エンドのガイダンスを取り上げ、ユーザーにとって重要な要素に焦点を当てています。

このプレイブックのアクティビティを完了すると、組織は次のことができます。

-   Teamsロールアウトを効果的に計画し、スケジュールを設定します。

-   ユーザーの導入を加速し、最適化します。

-   サポート ニーズを減らし、ユーザー満足度を高めます。

> [!NOTE]
> この記事と関連するプレイブックは、サービスの有効化または特定のサイトへのダイヤル トーンの提供に必要なすべての技術的な構成手順を説明することを目的としていません。 代わりに、ユーザーを簡単にオンボードするために推奨されるアクティビティやタスクに焦点を当て、サポート要件を最小限に抑えながら、導入率の高い迅速かつスムーズな移行を通じて、Teams音声ワークロードの使用を開始させます。 Teams音声用に環境を最適に構成する方法に関する技術的なガイダンスについては、[Teams音声ワークロードの構成、Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)[でのダイレクト ルーティングの構成](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)、[Teamsコア機能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)、[Teamsのネットワーク](prepare-network.md)、[Microsoft 365または有効化に関するオンボード チェックリストを参照してください。Office 365](onboarding-checklist-enable-office-365.md)。

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>プレイブックのフォーカス領域

プレイブックの焦点は、Teams音声展開に対するユーザーの認識に影響を与える要因に対処することです。 アクティビティとタスクは、次の重点領域にグループ化されます。

-   サービスの準備の検証
    - 電話会議
    - 通話プラン
    - ダイレクト ルーティング

-   ユーザーの有効化

-   エンドポイント

-   使用状況と品質

-   導入

[Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) は、Microsoft Excel ブックです。 これら 5 つのフォーカス領域はそれぞれブック内の個別のシートであり、各展開タスクとアクティビティはこれらのシートのいずれかにグループ化されます。

![サイト有効化プレイブックのスクリーンショット。](media/deploy-my-service-image1.png "プレイブックのスクリーンショット")

> [!NOTE]
> Teamsロールアウトのスコープ内で、サイトごとにプレイブックの個別のインスタンスを作成します。

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>プレイブックを使用する方法

場所のサイズと複雑さに関係なく、各サイトを有効にするには、タスクとアクティビティを十分に早く計画し、実際のサービスロールアウトの前、中、後に最適な順序で実行する必要があります。 音声をMicrosoft Teamsする独自の道のりを計画して実行するときは、次の手順に従うことをお勧めします。

1. [Microsoft Teams Voice 用の Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) をダウンロードします。

2. サイトごとにプレイブックの別のコピーを作成します。

3. **[Playbook for {SiteName-Code}**] という名前のシートのタブで、**{SiteName-Code} を** 関連するサイト名またはサイト コードに置き換えます。

4. 次に示すように **、サイト名、サイト コード**、 **および計画開始日** を入力します。 これは重要な手順です。これは、プレイブック内のすべてのアクティビティに推奨される期限を調整するためです。

   ![サイト名、サイト コード、および計画的な開始日を含む例。](media/deploy-my-service-image2.png "ニューヨークのサイト名、サイト コード NY01、および計画開始日が 20- Mar-18 の例")

5. 各アクティビティを確認し、必要なアクションを実行し、タイムラインを歩いている間に状態を更新します。 次に示すように、状態はグラフィカルに表されます。
  
   - ![緑色のチェック マークの図。](media/deploy-my-service-image3.png) **はい、または該当しない (緑):** アクティビティが完了したか、このサイトには適用されず、それ以上のアクションは必要ありません。</li>
   - ![黄色の感嘆符の図。](media/deploy-my-service-image4.png) <strong>アクティビティはまだ完了していません (黄色):</strong> アクティビティはまだ完了しておらず、スケジュールに従って [はい] または [いいえ] に更新する必要があります。</li>
   - ![赤い X が示す図。](media/deploy-my-service-image5.png) <strong>いいえ (赤):</strong> 問題のためアクティビティを完了できず、プロジェクトの状態会議に持ち込む必要があります。</li></ul>

6. 状態は各セクション内でロールアップされ、セクション見出しは次のいずれかの状態インジケーターで書式設定されます。 **毎週の状態** も自動的に更新されます。

![プレイブックの毎週の状態のロールアップのスクリーンショット。](media/deploy-my-service-image6.png "プレイブックの毎週の状態のロールアップのスクリーンショット")

> [!TIP]
> すべての場所について、上記の手順を繰り返します。

> [!IMPORTANT]
> 一部の手順は、すべての場所とサイトに適用できるわけではありません。 特定のアクティビティがサイトに関連しない場合は、[このアクティビティ **には適用されません** ] を選択する必要があります。 プレイブック内の行を **削除しないでください**。この場合、状態のロールアップ数式は機能しません。<br/><br/>
番号の移植や調達アクティビティなど、計画したよりも時間がかかる可能性があるアクティビティに注意してください。 これらのアクティビティは、サイトの展開タイムラインに悪影響を与える可能性があります。 アクティビティリストと関連するタイムラインを毎週確認して更新し、関係者が各サイトの状態と展開スケジュールからの逸脱を把握できるように [、運営委員会の会議](./envision-steering-committee-complete-guide.md) で発表してください。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>展開にサイト有効化プレイブックが必要かどうかを決定します。</li><li>展開するすべてのサイトに対して、サイト有効化プレイブックのMicrosoft Teamsのカスタマイズを担当するユーザーを決定します。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次のステップ</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Site Enablement プレイブックをダウンロードします</a>。</li><li>最初のサイトのサイト有効化プレイブックをカスタマイズします。</li><li>必要に応じて、追加のサイトに対して繰り返します。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->