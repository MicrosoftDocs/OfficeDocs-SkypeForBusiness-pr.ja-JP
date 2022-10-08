---
title: すべての参加者に包括的な Teams 会議エクスペリエンスを作成する
ms.author: dstrome
author: dstrome
f1.keywords:
- Teams hybrid
- remote work
- Teams meetings
manager: serdars
audience: ITPro
description: Teams を使用して、ハイブリッドワークフォースの包括的な会議エクスペリエンスを作成する方法について説明します。
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
ms.collection:
- m365solution-teamshybrid
- m365solution-scenario
ms.custom: ''
keywords: ''
ms.openlocfilehash: 7c9083242ea08e36b31f97abfbf3ff895fca549f
ms.sourcegitcommit: 1be178dc3b34575e1914e629f004f897c02e0097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2022
ms.locfileid: "68138590"
---
# <a name="create-an-inclusive-teams-meeting-experience-for-all-participants"></a>すべての参加者に包括的な Teams 会議エクスペリエンスを作成する

Microsoft Teams の会議は、人々が集ってアイデアを交換し、困難な問題に取り組む場所です。 職場環境が大きく変化している時期に、人を集めて効果的な会議を実現することは困難な場合があります。 このソリューションでは、Microsoft Teams、Teams Rooms デバイス、会議室の設計、会議の原則、ビジネス プラクティスを組み合わせて、包括的な会議環境を作成する方法を示します。 インクルーシブ環境では、部屋にいるか、リモートにいるか、障舟を持っているかに関係なく、すべての受信者間のコミュニケーションとコラボレーションが可能になります。

Microsoft Teams は、Microsoft 全体のハイブリッド作業の中心です。 Teams、Microsoft 365、Azure、およびその他の Microsoft 製品を使用して組織全体にハイブリッドワークの考え方を組み込む方法については、 [Microsoft ハイブリッド ワーク センター](https://www.microsoft.com/hybridwork/)を参照してください。

この短いビデオでは、Teams Roomsとのハイブリッド会議に対する Microsoft のビジョンを共有しています。 最前列などの機能の多くは現在使用でき、このソリューションで説明されています。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEB5U]
>

インフラストラクチャでハイブリッド作業環境をサポートする準備を整える方法については、「 [Microsoft 365 でのハイブリッド作業用のインフラストラクチャのセットアップ」を参照してください](/microsoft-365/solutions/empower-people-to-work-remotely)。

Teams 会議エクスペリエンスの設計と設定を開始する前に、 [Teams ハイブリッド会議の原則](hybrid-meetings-principles.md)を確認してください。 これらの原則を使用して、プレゼンスや場所に関係なく、すべての参加者が等しく参加できる包括的な会議環境を作成するのに役立ちます。

## <a name="audiences"></a>観客

このソリューションの手順を実行する必要があるユーザーには、3 つの異なるグループがあります。 手順を実行する必要があるグループを確認するには、今後の記事で次の識別子を探します。


|識別子  |グループの責任  |
|---------|---------|
|:::image type="content" source="media/hybrid-audience-audiovisual-small.png" alt-text="オーディオ ビジュアルの対象ユーザー" border="false":::    | オーディオ ビジュアル グループ: <ul><li> 会議スペースでカメラ、スピーカー、マイク、ディスプレイを取得、設定、構成します。</li><li>展開後の会議参加者からのサポート要求に応答します。        |
|:::image type="content" source="media/hybrid-audience-facilities-small.png" alt-text="施設の対象ユーザー" border="false":::     | 施設グループ: <ul><li> 必要に応じて、オーディオ ビジュアル グループと連携して決定された仕様に合わせて会議スペースを構築または変更します。</li><li> テーブル、椅子、ホワイトボード、プロジェクション スクリーンなどの家具を取得して設定します。</li><li>さまざまなTeams Rooms コンポーネント間のケーブル接続を実行し、ネットワークポートとオーディオ ビジュアル ポートをインストールします。</li><li>すべてのTeams Rooms コンポーネントの電源ポイントをインストールします。</li></ul>       |
|:::image type="content" source="media/hybrid-audience-itpro-small.png" alt-text="IT Pro の対象ユーザー" border="false":::     | IT Pro グループ: <ul><li>会社または部門のリーダーと相談して、その機能要件と共に作成する会議スペースの種類を決定します。</li><li>オーディオ ビジュアル グループと連携して、会議スペースで使用されるTeams Rooms コンポーネントを選択して取得します。</li><li>Teams とTeams Rooms機能、原則、ベスト プラクティスを紹介します。</li><li>Teams とTeams Roomsの機能とポリシーを構成します。</li><li>Teams を管理および監視し、展開後の正常性をTeams Roomsします。</ul>        | 

次のセクションでは、このシナリオの主要な手順について説明します。

## <a name="step-1---get-familiar-with-teams-meeting-features"></a>手順 1 - Teams 会議機能について理解する

この手順は、Teams で利用できる機能を理解し、会議をより包括的かつ効果的なものにするのに役立ちます。

## <a name="step-2---evangelize-meeting-best-practices"></a>手順 2 - エバンジェリゼー 会議のベスト プラクティス

過去の会議は通常、会議室で開催され、リモート参加者は電話会議を介して定期的に呼び出されました。 会話は主に、リモート参加者がリッスンしている部屋の会話の間にありました。 会議がオンラインの場合、コンテンツはリモート参加者と共有される可能性がありますが、会議は依然として部屋の参加者によって大きく支配されていました。 リモート参加者と室内参加者の間に大きな不均衡がありました。

会議の等価性と包摂性とは、場所や能力に関係なく、すべての参加者が会議に貢献できることを意味します。 これを行うには、すべての参加者が開催者、発表者、リモート、または会議室のいずれであっても、"会議に参加" し、他の参加者と対話する方法に注意する必要があります。 この手順では、これらのグループごとにベスト プラクティスを提供し、より良い参加者になるために役立ちます。

## <a name="step-3---design-or-enhance-a-meeting-space"></a>手順 3 - 会議スペースを設計または強化する

新しい会議スペースを作成したり、既存の会議スペースを拡張したりすることもできます。 この手順は、約 6 ~ 10 人の会議室参加者と任意の数のリモート参加者を含む会議をサポートする会議スペースを設計するのに役立ちます。 どのような家具が最適か、参加者や使用するデバイスをサポートするために配置する場所などです。

## <a name="step-4---select-devices-for-your-space"></a>手順 4 - スペースのデバイスを選択する

使用可能なオプションがあるため、スペースに適したデバイスを選択すると、少し負荷が高い場合があります。 この手順では、スペースと参加者のニーズに合わせて適切なデバイスを選択するプロセスについて説明します。

## <a name="step-5---build-your-meeting-space"></a>手順 5 - 会議スペースを構築する

スペースを設計し、デバイスを選択したら、すべてをまとめてみましょう。 この手順は、デバイスと家具を配置する場所を決定し、自分と参加者に優れた会議エクスペリエンスを提供するのに役立ちます。

## <a name="step-6---set-up-your-devices"></a>手順 6 - デバイスを設定する

領域を構築したら、デバイスを設定する必要があります。 この手順は、デバイスを構成し、最初の会議の準備を整えるのに役立ちます。

## <a name="step-7---manage-and-monitor-your-space-and-its-devices"></a>手順 7 - 領域とそのデバイスを管理および監視する

すべてが設定されたら、会議スペースとそのデバイスの使用方法に関するポリシーを設定し、デバイスの正常性と会議のエクスペリエンスを把握できるように監視を設定する必要があります。 この手順は、会議ポリシーとデバイス ポリシーを構成し、Teams 監視ツールを使用して通話品質を監視する方法を示します。

> [!div class="nextstepaction"]
> [次の手順](hybrid-meetings-principles.md)
