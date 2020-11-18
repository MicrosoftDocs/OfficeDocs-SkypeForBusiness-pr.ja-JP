---
title: Power BI を使用して Microsoft Teams の CQD データを分析する
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 4889428096209b9856d75caf11348ac036b4c7b0
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085571"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Power BI を使用して Microsoft Teams の CQD データを分析する

2020年1月の新 [機能: POWER BI クエリテンプレートをダウンロードして CQD](https://www.microsoft.com/download/details.aspx?id=102291)します。 CQD データの分析と報告に使用できる、カスタマイズ可能な Power BI テンプレート。

Teams の通話品質ダッシュボード (CQD) レポートの場合、Power BI を使ってデータのクエリやレポートを行う場合は、CQD Power BI テンプレートをダウンロードしてください。 Power BI でテンプレートを開くと、CQD 管理者の資格情報でサインインするように求められます。 これらのクエリテンプレートをカスタマイズして、Power BI ライセンスと CQD の管理者権限を持つ組織内のすべてのユーザーに配布することができます。

これらの PBIT ファイルを使用するには、その前に、[ダウンロード](https://www.microsoft.com/download/details.aspx?id=102291)に含まれている [Microsoft CQD の Power BI コネクタをインストール](CQD-Power-BI-connector.md)する必要があり *ます。* 

Power BI レポートにアクセスするための適切な [CQD アクセスロール](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) を持っていることを確認してください。 

|  |  |
|---------|---------|
|<strong>(New!)</strong> CQD Teams の自動応答 & 通話キューの履歴レポート。 pbit     |  このテンプレートには、次の3つのレポートが用意されています。</p><li>自動応答-自動応答への通話の分析が表示されます。</li><li>通話キュー–通話キューに入ってくる通話の分析が表示されます。</li><li>[エージェント] タイムライン–通話キュー通話でアクティブになっているエージェントのタイムラインビューが表示されます。</li><br>詳細については、「 [CQD POWER BI レポートを使用して自動応答 & 通話キューの履歴レポートを表示する](CQD-teams-aa-cq-historical-report.md)」を参照してください。        |
|CQD ヘルプデスクレポート pbit     |このレポートは、ビルディングと EUII のデータを統合することを目的としています。このレポートは、1人のユーザーとの間で、そのユーザーの通話品質の低下 (たとえば、ネットワークの問題が発生している建物内にいるなど) を見つけることができるように設計されています。         |
|CQD 位置拡張レポート pbit     | CQD SPD location レポートを再想像します。 9つのレポートが含まれており、通話品質の提供、WiFi、信頼性の構築、また、建物またはユーザーごとの追加のドリルダウン thrus での通話 (RMC) 情報の評価を行うことができます。  レポートの操作性を最大限に高めるために、建物のデータをアップロードしていることを確認してください。        |
|CQD モバイルデバイスレポート pbit     | 通話品質、信頼性、通話料金などのモバイルデバイスユーザーに向けて、明確に調整された洞察を提供します。 モバイルネットワーク、WiFi ネットワーク、モバイルオペレーティングシステムレポート (Android、iOS) を表示します。        |
|CQD PSTN ダイレクトルーティングレポート pbit     |直接ルーティングを経由する PSTN 通話に固有の洞察を提供します。 詳細については、「 [CQD PSTN ダイレクトルーティングレポートを使用](CQD-PSTN-report.md)する」を参照してください。         |
|CQD Summary レポート pbit     |視覚エフェクトの向上、向上したプレゼンテーション、情報の密度の向上、日付のローリング。 これらのレポートを使用すると、値を簡単に識別することができます。 使いやすいインタラクティブな地図を使用して、場所別の通話品質を詳しく調べることができます。 9新しいレポート:</p>-全体的な品質<br>-信頼性全体<br>-RMC (通話の評価) 全体<br>-会議の品質<br>-P2P の品質<br>-会議の信頼性<br>-P2P の信頼性<br>-電話会議 RMC<br>-P2P RMC         |
|<strong>(New!)</strong> CQD Teams の使用状況レポート pbit     | 組織内のユーザーが Teams をどのように使用しているかを示し、その量を示します。 レポートの操作性を最大限に高めるために、建物のデータをアップロードしていることを確認してください。 詳細については、「 [CQD POWER BI レポートを使用して Microsoft Teams の利用状況を表示](CQD-teams-utilization-report.md)する」を参照してください。        |
|CQD ユーザーフィードバック (通話の評価) レポート pbit     | 組織への通話をサポートするために簡単に使用できる方法で、通話データの料金が表示されます。 Verbatims との相互参照により、エンドユーザーの教育機会を特定します。        |

> [!TIP]
> Power BI レポートを CQD データ用に設定したら、それらをタブとしてチャネルに追加します。 チャネルでを選択した後 **+** 、[ **Power BI** ] を選択してから、レポートを検索します。 詳細については、「[ [POWER BI] タブで Teams の埋め込みレポート](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams)を閲覧する」を参照してください。 これらのレポートにアクセスできるのは、Power BI ライセンスと CQD 管理者の資格情報を持っているユーザーのみです。


## <a name="related-topics"></a>関連項目

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Skype for Business の通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析および通話品質ダッシュボード](difference-between-call-analytics-and-call-quality-dashboard.md)
 
