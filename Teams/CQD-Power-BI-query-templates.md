---
title: Power BIを使用してMicrosoft Teamsの CQD データを分析する
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
ms.localizationpriority: medium
description: Power BIを使用して、Microsoft Teamsの CQD データを分析します。
ms.openlocfilehash: 4a96a53454f1f4d89feed3ea87342a7991d7975c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013771"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Power BIを使用してMicrosoft Teamsの CQD データを分析する

2020 年 1 月の新機能: [CQD 用の Power BI クエリ テンプレートのダウンロード](https://www.microsoft.com/download/details.aspx?id=102291)。 CQD データの分析やレポートに使えるカスタマイズ可能な Power BI テンプレートです。

Teamsの通話品質ダッシュボード (CQD) レポートでは、Power BIを使用してデータのクエリとレポートを行う場合は、CQD Power BI テンプレートをダウンロードします。 Power BIでテンプレートを開くと、CQD 管理者資格情報でサインインするように求められます。 これらのクエリ テンプレートをカスタマイズし、Power BI ライセンスと CQD 管理者アクセス許可を持つ組織内のすべてのユーザーに配布できます。

これらの PBIT ファイルを使用する前に、[ダウンロード](https://www.microsoft.com/download/details.aspx?id=102291)に含まれている *MicrosoftCallQuality.ppfx* ファイルを使用して、[Microsoft CQD 用のPower BI コネクタをインストール](CQD-Power-BI-connector.md)する必要があります。 

Power BI レポートにアクセスするための適切な [CQD アクセス ロール](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)があることを確認します。 

|&nbsp;|&nbsp;|
|---------|---------|
|<strong>(New!)</strong>CQD Teams自動応答&呼び出しキュー履歴レポート.pbit     |  このテンプレートには、次の 3 つのレポートが用意されています。</p><li>自動応答 – 自動応答に着信する呼び出しの分析を示します。</li><li>通話キュー – 通話キューに着信する通話の分析を示します。</li><li>エージェント タイムライン – 通話キューの呼び出しでアクティブになっているエージェントのタイムライン ビューを示します。</li><br>詳細については、「 [通話キュー履歴レポート&自動応答](aa-cq-cqd-historical-reports.md)」を参照してください。        |
|CQD Helpdesk Report.pbit     |このレポートは、建物と EUII データを統合して、1 人のユーザーからドリルダウンして、そのユーザーの呼び出し品質が低いアップストリームの根本原因を見つけられるように設計されています (たとえば、ユーザーがネットワークの問題が発生している建物にいる場合など)。         |
|CQD Location Enhanced Report.pbit     | CQD SPD の場所レポートを再想像します。 9 つのレポートが含まれており、通話品質、建物の WiFi、信頼性、および通話のレート (RMC) の情報を、ビルドまたはユーザー別に追加のドリルスルーで提供します。  レポート エクスペリエンスを最大限に高めるために、必ず建物データをアップロードしてください。        |
|CQD モバイル デバイス Report.pbit     | 通話品質、信頼性、通話の評価など、モバイル デバイス ユーザー向けに特別に調整された分析情報を提供します。 モバイル ネットワーク、WiFi ネットワーク、モバイル オペレーティング システムのレポート (Android、iOS) を表示します。        |
|CQD PSTN ダイレクト ルーティング レポート.pbit     |ダイレクト ルーティングを経由する PSTN 通話に固有の分析情報を提供します。 詳細については、「 [CQD PSTN ダイレクト ルーティング レポートの使用」](CQD-PSTN-report.md)を参照してください。         |
|CQD の概要レポート.pbit     |視覚化の向上、プレゼンテーションの改善、情報密度の向上、およびローリング日付。 これらのレポートを使用すると、外れ値を識別しやすくなります。 使いやすい対話型マップを使用して、場所ごとの通話品質を掘り下がります。 9 つの新しいレポート:</p>- 全体的な品質<br>- 信頼性全体<br>- RMC (通話のレート) 全体<br>- 会議の品質<br>- P2P 品質<br>- 会議の信頼性<br>- P2P の信頼性<br>- 電話会議 RMC<br>- P2P RMC         |
|<strong>(New!)</strong>CQD Teams使用率レポート.pbit     | 組織内のユーザーがTeamsを使用している方法と量を示します。 レポート エクスペリエンスを最大限に高めるために、必ず建物データをアップロードしてください。 詳細については、「[CQD Power BI レポートを使用してMicrosoft Teams使用率を表示する」を](CQD-teams-utilization-report.md)参照してください。        |
|CQD ユーザー フィードバック (通話のレート) Report.pbit     | 組織の呼び出しをサポートするために簡単に使用できる方法で、通話率データを表示します。 エンド ユーザー教育の機会を特定するための詳細を含む相互参照。        |

> [!TIP]
> CQD データのPower BI レポートを設定したら、チャネルにタブとして追加します。 チャネルで選択 **+** した後、**Power BI** を選択し、レポートを見つけます。 詳細については、Teamsの [[Power BI] タブでレポートを埋め込む方法に関するページを参照](/power-bi/service-embed-report-microsoft-teams)してください。 これらのレポートにアクセスできるのは、Power BI ライセンスと CQD 管理者資格情報を持つユーザーのみです。


## <a name="related-topics"></a>関連項目

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Skype for Business の通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析および通話品質ダッシュボード](./monitor-call-quality-qos.md)
