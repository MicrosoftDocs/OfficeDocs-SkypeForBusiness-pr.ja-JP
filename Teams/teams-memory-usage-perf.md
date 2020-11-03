---
title: Microsoft Teams のメモリ使用方法
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Microsoft Teams によるシステム メモリの使用方法、およびデスクトップ アプリケーションと Web アプリケーションでメモリ使用量が同じ理由について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59940eafcdb6f86961b3cd6805cb9c5bb40f9fb2
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033401"
---
# <a name="how-microsoft-teams-uses-memory"></a>Microsoft Teams のメモリ使用方法

一部の Microsoft Teams ユーザーから、Teams によるメモリ使用方法について質問を受けています。 この記事では、Teams がメモリを使用する方法を説明します。また、Teams デスクトップ アプリケーション (アプリ) と Teams Web アプリによって、同じコンピューター上の別のアプリとワークロードに最適な実行のための十分なメモリが渡されることが阻害されない理由を説明します。 Teams は先進の Web テクノロジを使用するように設計されています。 これを実現するために、Teams のデスクトップ クライアントは Electron で開発されました。Electron はレンダリングに Chromium を使用します。 これは、Microsoft Edge や Chrome など、現在人気のある多くのブラウザーで採用されているレンダリング エンジンと同じです。

## <a name="how-teams-works"></a>Teams のしくみ

Electron で設計されている Teams を使用すると、迅速な展開が可能になります。また、異なるオペレーティング システム (Windows、Mac、Linux) 間の各種 Teams バージョン間で同一性を維持できます。 この同一性は、Electron と Chromium によってすべてのバージョンで同じコード ベースが維持されるので可能になります。 このアーキテクチャのもう 1 つの利点は、Teams Web アプリとデスクトップのバージョンにおけるメモリ使用プロファイルが類似することです。 Web アプリとデスクトップのどちらのバージョンでも、ブラウザーで使用する場合と同じようにメモリを使用します。 Electron について詳しくは、[こちらの Web サイト](https://electronjs.org/)を参照してください。

詳しくは、「[Chromium のメモリ使用](https://www.chromium.org/developers/memory-usage-backgrounder)」および「[Chrome メモリにおける主要概念](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)」をご覧ください。

次の画像では、Windows 用の Teams デスクトップ アプリと Teams Web アプリ (この例では Google Chrome で実行されています) のメモリ使用量を並べて示しています。

![Teams デスクトップ アプリと Web アプリのメモリ使用量](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Teams でのメモリ使用量

Teams がシステム メモリを使用する際に *予期される* 動作と、システム メモリの問題が実際に生じたときの症状について理解するのは重要です。

### <a name="expected-memory-usage-by-teams"></a>Teams による予期されるメモリ使用量

Teams デスクトップ アプリと Teams Web アプリのどちらを実行しているとしても、使用可能なシステム メモリ量がChromium によって検出され、その中の十分な量のメモリを使用してレンダリング エクスペリエンスが最適化されます。 他のアプリやサービスによってシステム メモリを必要とする場合、Chromium はそれらのプロセスにメモリを渡します。 Chromium は、現在実行中の他のものに影響を与えることなく Teams のパフォーマンスを最適化するために、Teams のメモリ使用量を継続的に調整します。

このようにして、Chromium ワークロードは、使用可能なシステム メモリ量に応じて変化するメモリ量を利用します。

次のグラフは、4 つの独立したシステムにおける Teams でのメモリ使用量を示しています。システムごとに使用できるメモリ量が異なります。 各システムは同様のワークロードを処理しています (同じアプリを開いて実行しています)。

![異なるシステム間の Teams メモリ使用量](media/teams-memory-usage.png)

コンピューターに搭載されているメモリが多い場合、Teams はそのメモリを使用します。 メモリが十分にないシステムでは、Teams が使用するメモリは少なくなります。

### <a name="symptoms-of-system-memory-issues"></a>システム メモリの問題の症状

使用しているコンピューターで、次の 1 つ以上の問題が発生する場合は、システム メモリに重大な問題がある可能性があります。

- 複数の大規模なアプリケーションを同時に実行しているときに、メモリ使用量が高くなります。
- システムのパフォーマンスが低下する、またはアプリケーションがハングします。
- すべてのアプリのシステム メモリ使用量全体が継続的に 90% 以上になります。 このメモリ使用量の場合、Teams は他のアプリおよびワークロードにメモリを戻す必要があります。 メモリ使用量が継続的に 90% になるということは、Teams がシステムにメモリを戻しておらず、問題が生じていることを示します。

次の画像は、システム メモリ使用率が異常に高い場合のタスク マネージャーのビューの例を示しています。

![タスク マネージャーにおける Teams メモリ使用量ビュー](media/teams-memory-high-mem-process-list.png)

![タスク マネージャーにおける Teams メモリ使用量グラフ](media/teams-memory-high-mem-process-list2.png)
