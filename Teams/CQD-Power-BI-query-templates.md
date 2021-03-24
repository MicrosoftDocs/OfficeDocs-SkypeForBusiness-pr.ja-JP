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
ms.openlocfilehash: 5ef98f75854cb4a255bf3f01aeb32de66c059b76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096523"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Power BI を使用して Microsoft Teams の CQD データを分析する

2020 年 1 月の新機能: [CQD 用の Power BI クエリ テンプレートをダウンロードします](https://www.microsoft.com/download/details.aspx?id=102291)。 カスタマイズ可能な Power BI テンプレートを使用して、CQD データを分析およびレポートできます。

Teams の通話品質ダッシュボード (CQD) レポートでは、Power BI を使用してデータのクエリとレポートを行う場合は、CQD Power BI テンプレートをダウンロードします。 Power BI でテンプレートを開いた場合は、CQD 管理者の資格情報でサインインするように求めるメッセージが表示されます。 これらのクエリ テンプレートをカスタマイズし、Power BI ライセンスと CQD 管理権限を持つ組織内のすべてのユーザーに配布できます。

これらの PBIT ファイルを使用する前に、ダウンロードに含まれる *MicrosoftCallQuality.pセキュリティ* ファイルを使用して、Microsoft [CQD](CQD-Power-BI-connector.md)用 Power BI Connector をインストールする必要 [があります](https://www.microsoft.com/download/details.aspx?id=102291)。 

Power BI レポートにアクセスするには [、適切な CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) アクセスロールを持っている必要があります。 

|  |  |
|---------|---------|
|<strong>(新機能)</strong> CQD Teams 自動応答 &通話キューの履歴レポート.pbit     |  このテンプレートには、次の 3 つのレポートが含まれます。</p><li>自動応答 – 自動応答に着信する通話の分析を表示します。</li><li>通話キュー – 通話キューに着信する通話の分析を示します。</li><li>エージェント タイムライン – 通話キューの呼び出しでアクティブなエージェントのタイムライン ビューを示します。</li><br>詳細については、「通話キューの [履歴自動応答 &を参照してください](aa-cq-cqd-historical-reports.md)。        |
|CQD ヘルプデスク レポート.pbit     |建物と EUII データを統合するこのレポートは、1 人のユーザーからドリル アップして、そのユーザーの通話品質の低下の原因である(たとえば、ネットワークの問題が発生している建物にいます) 原因を見つけ出せするように設計されています。         |
|CQD Location Enhanced Report.pbit     | CQD SPD 位置情報レポートを再想像します。 9 つのレポートを含み、通話品質、建物の WiFi、信頼性、通話の評価 (RMC) 情報を、建物別またはユーザー別に追加のドリルスルーで提供します。  レポート機能を最大限に活用するには、必ず建物データをアップロードしてください。        |
|CQD モバイル デバイス レポート.pbit     | 通話品質、信頼性、通話の評価など、モバイル デバイス ユーザー向けに特に調整された分析情報を提供します。 モバイル ネットワーク、WiFi ネットワーク、モバイル オペレーティング システムレポート (Android、iOS) を表示します。        |
|CQD PSTN ダイレクト ルーティング レポート.pbit     |直接ルーティングを経由する PSTN 通話に固有の分析情報を提供します。 詳細については [、「CQD PSTN](CQD-PSTN-report.md)ダイレクト ルーティング レポートの使用」を参照してください。         |
|CQD Summary Report.pbit     |視覚エフェクトの向上、プレゼンテーションの改善、情報の密度の向上、および日付の回転。 これらのレポートを使用すると、異常値を簡単に識別できます。 使いやすい対話型マップを使用して、場所別に通話品質を詳細に表示します。 9 つの新しいレポート:</p>- 品質全体<br>- 信頼性全体<br>- RMC (通話の評価) 全体<br>- 会議品質<br>- P2P 品質<br>- 電話会議の信頼性<br>- P2P の信頼性<br>- 電話会議 RMC<br>- P2P RMC         |
|<strong>(新機能)</strong> CQD Teams 使用率レポート.pbit     | 組織内のユーザーが Teams を使用している方法と量を示します。 レポート機能を最大限に活用するには、必ず建物データをアップロードしてください。 詳細については [、「CQD Power BI レポート](CQD-teams-utilization-report.md)を使用して Microsoft Teams の使用率を表示する」を参照してください。        |
|CQD ユーザー フィードバック (通話の評価) Report.pbit     | 組織の通話をサポートするために簡単に使用できる方法で、通話の評価データを表示します。 エンドユーザー教育の機会を特定するための詳細な相互参照。        |

> [!TIP]
> CQD データの Power BI レポートを設定したら、それらをタブとしてチャネルに追加します。 チャネルで選択 **+** した後 **、Power BI を選択し** 、レポートを見つける。 詳細については、「Teams の [Power BI タブを使用してレポートを埋め込む」を参照してください](/power-bi/service-embed-report-microsoft-teams)。 Power BI ライセンスと CQD 管理者の資格情報を持つユーザーだけがこれらのレポートにアクセスできます。


## <a name="related-topics"></a>関連項目

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Skype for Business の通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析および通話品質ダッシュボード](./monitor-call-quality-qos.md)
