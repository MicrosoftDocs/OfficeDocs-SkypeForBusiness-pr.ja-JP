---
title: Microsoft Teams のネットワークプランナーを使用する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 管理者は、Network Planner を使用して、Microsoft Teams のネットワーク要件を特定する方法についてを知ることができます。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: bfccd9b620bbe44c8fb8627504b7c25a03227b96
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581328"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Microsoft Teams のネットワークプランナーを使用する

Network Planner は、Teams 管理センターで利用できる新しいツールです。 これは、**プランナー**  >  **Network Planner** でアクセスできます。 ほんの少しの手順で、Network Planner では組織全体で Microsoft Teams ユーザーに接続するためのネットワーク要件を決定し、整理できます。 ネットワークの詳細と Teams の使用状況を提示すると、Network Planner は、組織の物理的な場所で Teams とクラウドの音声を展開するためのネットワーク要件を計算します。

![ネットワークプランナーのスクリーンショット](media/network-planner.png)

ネットワークプランナーでは次のことができます。

- サイトと Microsoft 推奨のペルソナ (オフィス ワーカー、リモート ワーカー、Teams ルーム システム) を使用して組織の表現を作成します。

    > [!NOTE]
    > 推奨されるペルソナは、Teams の最適な使用シナリオと一般的な使用パターンに基づいて開発されました。 ただし、推奨される3つのペルソナに加えて、最大3つのカスタム ペルソナを作成できます。

- Teams の使用状況の帯域幅要件に関するレポートを作成し計算します。

ネットワークプランナーを使用するには、グローバル管理者、Teams サービス管理者、またはチームコミュニケーション管理者である必要があります。

## <a name="create-a-custom-persona"></a>カスタム ペルソナを作成する

カスタム レポートを作成するには、次の手順に従います。

1. Microsoft Teams 管理センターのネットワークプランナーに移動します。

2. [**ペルソナ**] タブで、[**+ カスタム ペルソナ**] をクリックします。 

3. **新しいカスタム ペルソナ** ウィンドウで、新しいペルソナの名前と説明を入力します。

4. このペルソナが組織内で使用するアクセス権を選択します。

5. [**保存**] をクリックします。

## <a name="build-your-plan"></a>プランを作成する

ネットワーク プランを作成するには、次の手順を実行します。

1. Microsoft Teams 管理センターのネットワークプランナーに移動します。

2. [**ネットワーク プラン**] タブで、[**ネットワーク プランの追加**] をクリックします。

3. 新しいネットワーク プランの名前と説明を入力してください。 使用可能なプランのリストにネットワーク プランが表示されます。

4. プラン名をクリックして新しいプランを選択します。

5. 組織のネットワーク セットアップを作成するには、サイトを追加します。

    組織のネットワークによっては、ビル、オフィスの位置、またその他を表現するのにサイトを使用したい場合があるでしょう。 サイトは WAN によって接続され、インターネットや PSTN の接続が共有できるようになっている場合があります。 最良の結果を得るには、インターネットまたは PSTN にリモート接続するサイトを作成する前に、ローカル接続を使用してサイトを作成します。

    サイトを作成する

    1. サイトの名前と説明を追加します。

    2. [**ネットワーク設定**] の下に、そのサイトのネットワーク ユーザー数を追加します (必須)。

    3. ネットワークの詳細を追加します。WAN 対応、WAN 容量、インターネット エグレス (**ローカル** または **リモート**)、PSTN エグレス (なし、ローカル、またはリモート)。

      > [!NOTE]
      > レポートを生成するときに、特定の帯域幅の推奨値を表示するには、WAN およびインターネットの容量を追加する必要があります。

    4. [**保存**] をクリックします。

## <a name="create-a-report"></a>レポートを作成する

すべてのサイトを追加したら、次のようにレポートを作成できます。

1. [**レポート**] タブで、[**レポートを開始**] をクリックします。

2. 作成する各サイトについて、使用可能なペルソナにユーザー数を分配します。 Microsoft が推奨するペルソナを使用している場合、この数字は自動的に分配されます (オフィス ワーカーが 80% で、リモートワーカーが 20%)。

3. 分配が完了したら、**レポートの作成**をクリックします。

    生成されたレポートには、次のようなさまざまなビューの帯域幅要件が表示されるので、出力を正確に理解できます。
    - 個々の計算を含むテーブルには、許可されている各アクティビティの帯域幅要件が表示されます。
    - 追加のビューには、推奨事項による全体的な帯域幅ニーズが表示されます。

4. [**保存**] をクリックします。 レポートはレポート リストで、後で表示できます。

## <a name="example-scenario"></a>シナリオ例

ネットワークプランナーを使用してネットワーク計画を設定し、これらの手順を使用してレポートを生成する方法の例については、[ネットワークプランナーの使い方に関する PowerPoint デッキ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true)(英語のみ) をダウンロードしてください。
