---
title: 読み取りの進行状況に関する推奨事項に関する Insights について
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 読み取り進行状況で Insights データを使用して、学生の読み取り能力を向上させる方法について説明します。
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30a98c9ccda13635a6c3fccaae41e8869b8cfce5
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2022
ms.locfileid: "67157885"
---
# <a name="understand-insights-for-reading-progress-recommendations"></a>読み取りの進行状況に関する推奨事項に関する Insights について

この記事は、読み取り進行状況の推奨事項に Insights データがどのように使用されるかを理解したい教育機関の IT 管理者向けです。

Insights を使用すると、教師は読み上げの進行状況を使用して学生の読み取りの流暢さを追跡できます。これは、学生が大声で読み上げを記録し、エラーを自動的に検出するツールです。

読み取りの進行状況には、次の種類の読み取りチャレンジの割り当てが用意されています。

- **コンテキスト語**: 過去の読み上げの進行状況の割り当てで学生が誤って発音した単語に基づいて推奨される単語を練習します。
- **相関単語**: 同じ種類の読み取りチャレンジを持つ学生に共通する間違いに基づいて推奨される単語を練習します。

Insights for Reading Progress の使用に関する教育者向けガイダンスについては、「Insights を使用した [読み取り進行状況チャレンジの割り当ての作成」を](https://support.microsoft.com/topic/c2f8f4c0-69d5-4302-b3a5-ee4dfb7a8ffe)参照してください。

## <a name="how-does-microsoft-recommend-correlated-words"></a>Microsoft では、関連付けられた単語はどのように推奨されますか?

関連付けられた単語は、Insights for Education が同様の読み取りパターンを共有する他の学生にとって困難であると特定した、パーソナライズされた推奨単語です。

相関単語は、 **コラボレーション フィルター処理** と呼ばれる機械学習手法に基づいています。

- Insights は、地理的な領域と言語を共有するクラス間で学生の読み取りデータを分析し、学生にとって困難な単語のクラスターを特定します。

- 一連の困難な単語を考えると、Insights では同様のクラスターも識別され、それらを使用して他の単語を学生に推奨し、対象を絞った練習を行います。

## <a name="does-microsoft-keep-students-data-private-and-secure"></a>Microsoft は学生のデータを非公開にしてセキュリティで保護していますか?

Microsoft は、責任ある倫理的なデータの使用に取り組んでいます。

この機能を構築するために実行されるいくつかの対策を次に示します。

- 学生データ分析は目を離した方法で構築されています。つまり、Microsoft は学生の読み取りデータにアクセスできず、分析結果にのみアクセスできます。

- テナント管理者は、[ [高度な推論] トグル](class-insights.md#turn-on-and-off-advanced-inferences-in-insights)をオフにすることで、データ分析プロセスからオプトアウトできます。

- 不適切な単語は、 **関連付けられた単語** の推奨事項リストから除外されます。 これは、データ サイエンス手法と既知の問題のある単語のブロックの組み合わせによって行われます。 ただし、このプロセスはエラー証明ではありません。 教育者は推奨事項を確認する必要があります。

## <a name="what-are-the-limitations-of-insights-word-recommendations"></a>Insights の単語の推奨事項の制限事項は何ですか?

- 現在、読み上げの進行状況に関する Word の推奨事項は [、これらの言語](https://support.microsoft.com/topic/getting-started-with-reading-progress-in-teams-7617c11c-d685-4cb7-8b75-3917b297c407#ID0EDD=Supported_Languages)でサポートされています。

- 相関単語は、読み取り進行状況の課題を提出した少なくとも 5 人の学生を含むクラスでのみ表示されます。

- 分析情報では、類似した同一の間違いパターンを持つ学生がいない場合に、新しい単語を推奨しない場合があります。
