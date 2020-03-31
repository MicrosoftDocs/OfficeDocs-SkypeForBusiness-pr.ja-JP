---
title: Power BI を使用して Microsoft Teams の CQD データを分析する
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Power BI を使用して、Microsoft Teams の CQD データを分析します。
ms.openlocfilehash: 374f0da0342e5fbd50a7a27b9dde49acf605a23d
ms.sourcegitcommit: f96d66d08a9d6993edbb9554738dc8236d901933
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2020
ms.locfileid: "43053510"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Power BI を使用して Microsoft Teams の CQD データを分析する

2020年1月の新[機能: POWER BI クエリテンプレートをダウンロードして CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)します。 CQD データの分析と報告に使用できる、カスタマイズ可能な Power BI テンプレート。

Teams の CQD レポートの場合、Power BI を使ってデータのクエリやレポートを行う場合は、CQD Power BI テンプレートをダウンロードしてください。 Power BI でテンプレートを開くと、CQD 管理者の資格情報でサインインするように求められます。 これらのクエリテンプレートをカスタマイズして、Power BI ライセンスと CQD の管理者権限を持つ組織内のすべてのユーザーに配布することができます。

これらの .PBIX ファイルを使用するには、その前に、[ダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)に含まれている[Microsoft CQD の Power BI コネクタをインストール](CQD-Power-BI-connector.md)する必要があり*ます。* 


|  |  |
|---------|---------|
|CQD のヘルプデスクのレポート .pbix     |このレポートは、ビルディングと EUII のデータを統合することを目的としています。このレポートは、1人のユーザーとの間で、そのユーザーの通話品質の低下 (たとえば、ネットワークの問題が発生している建物内にいるなど) を見つけることができるように設計されています。         |
|CQD の場所の拡張レポート .pbix     | CQD SPD location レポートを再想像します。 9つのレポートが含まれており、通話品質の提供、WiFi、信頼性の構築、また、建物またはユーザーごとの追加のドリルダウン thrus での通話 (RMC) 情報の評価を行うことができます。        |
|CQD モバイルデバイスのレポート .pbix     | 通話品質、信頼性、通話料金などのモバイルデバイスユーザーに向けて、明確に調整された洞察を提供します。 モバイルネットワーク、WiFi ネットワーク、モバイルオペレーティングシステムレポート (Android、iOS) を表示します。        |
|CQD PSTN ダイレクトルーティングレポート .pbix     |直接ルーティングを経由する PSTN 通話に固有の洞察を提供します。 詳細については、「 [CQD PSTN ダイレクトルーティングレポートを使用](CQD-PSTN-report.md)する」を参照してください。         |
|CQD Summary レポート .pbix     |視覚エフェクトの向上、向上したプレゼンテーション、情報の密度の向上、日付のローリング。 これらのレポートを使用すると、値を簡単に識別することができます。 使いやすいインタラクティブな地図を使用して、場所別の通話品質を詳しく調べることができます。 9新しいレポート:</p>-全体的な品質<br>-信頼性全体<br>-RMC (通話の評価) 全体<br>-会議の品質<br>-P2P の品質<br>-会議の信頼性<br>-P2P の信頼性<br>-電話会議 RMC<br>-P2P RMC         |
|<strong>(New!)</strong>CQD Teams の使用状況レポート .pbix     | 組織内のユーザーが Teams をどのように使用しているかを示し、その量を示します。 詳細については、「 [CQD POWER BI レポートを使用して Microsoft Teams の利用状況を表示](CQD-teams-utilization-report.md)する」を参照してください。        |
|CQD ユーザーフィードバック (通話の評価) レポート .pbix     | 組織への通話をサポートするために簡単に使用できる方法で、通話データの料金が表示されます。 Verbatims との相互参照により、エンドユーザーの教育機会を特定します。        |

> [!TIP]
> Power BI レポートを CQD データ用に設定したら、それらをタブとしてチャネルに追加します。 チャネルでを**+** 選択した後、[ **Power BI** ] を選択してから、レポートを検索します。 これらのレポートにアクセスできるのは、Power BI ライセンスと CQD 管理者の資格情報を持っているユーザーのみです。


## <a name="related-topics"></a>関連項目

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Skype for Business の通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析および通話品質ダッシュボード](difference-between-call-analytics-and-call-quality-dashboard.md)
 