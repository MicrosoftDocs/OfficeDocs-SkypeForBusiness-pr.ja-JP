---
title: ネットワーク プランナーを使用してMicrosoft Teams
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
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f05be30158cf934459f26965d7cef2dafbc708f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240480"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>ネットワーク プランナーを使用してMicrosoft Teams

Network Planner は、Teams 管理センターで利用できる新しいツールです。 これは、Planning Network Plannerにアクセス  >  **して確認できます**。 ほんの少しの手順で、Network Planner では組織全体で Microsoft Teams ユーザーに接続するためのネットワーク要件を決定し、整理できます。 ネットワークの詳細と Teams の使用状況を提示すると、Network Planner は、組織の物理的な場所で Teams とクラウドの音声を展開するためのネットワーク要件を計算します。

![Network Planner のスクリーンショット](media/network-planner.png)

Network Planner では、次の機能を使用できます。

- サイトと Microsoft 推奨のペルソナ (オフィス ワーカー、リモート ワーカー、Teams ルーム システム) を使用して組織の表現を作成します。

    > [!NOTE]
    > 推奨されるペルソナは、Teams の最適な使用シナリオと一般的な使用パターンに基づいて開発されました。 ただし、推奨される3つのペルソナに加えて、最大3つのカスタム ペルソナを作成できます。

- Teams の使用状況の帯域幅要件に関するレポートを作成し計算します。

Network Planner を使用するには、グローバル管理者、管理者、またはコミュニケーションTeams管理者Teams必要があります。

## <a name="create-a-custom-persona"></a>カスタム ペルソナを作成する

カスタム レポートを作成するには、次の手順に従います。

1. 管理センターで Network Planner にMicrosoft Teamsします。

2. [**ペルソナ**] タブで、[**+ カスタム ペルソナ**] をクリックします。 

3. **新しいカスタム ペルソナ** ウィンドウで、新しいペルソナの名前と説明を入力します。

4. このペルソナが組織内で使用するアクセス権を選択します。

5. [**保存**] をクリックします。

## <a name="build-your-plan"></a>プランを作成する

ネットワーク プランを作成するには、次の手順を実行します。

1. 管理センターで Network Planner にMicrosoft Teamsします。

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

3. 分配が完了したら、**レポートの作成** をクリックします。

    生成されたレポートには、次のようなさまざまなビューの帯域幅要件が表示されるので、出力を正確に理解できます。
    - 個々の計算を含むテーブルには、許可されている各アクティビティの帯域幅要件が表示されます。
    - 追加のビューには、推奨事項による全体的な帯域幅ニーズが表示されます。

4. [**保存**] をクリックします。 レポートはレポート リストで、後で表示できます。

## <a name="example-scenario"></a>シナリオ例

Network Planner を使用してネットワーク プランを設定し、これらの手順を使用してレポートを生成する方法の例については[、Network Planner](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) How-To PowerPoint デッキをダウンロードします (英語のみ)。
