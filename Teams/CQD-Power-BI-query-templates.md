---
title: Power BI を使用して Microsoft Teams の CQD データを分析する
author: CarolynRowe
ms.author: crowe
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
description: Power BI を使用して、Microsoft Teams の CQD データを分析します。
ms.openlocfilehash: 66ae28125d743c647cd0d18376fb12a2cec7cdfd
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789842"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Power BI を使用して Microsoft Teams の CQD データを分析する

2020 年 1 月の新機能: [CQD 用の Power BI クエリ テンプレートのダウンロード](https://www.microsoft.com/download/details.aspx?id=102291)。 CQD データの分析やレポートに使えるカスタマイズ可能な Power BI テンプレートです。

Teams の通話品質ダッシュボード (CQD) レポートの場合、Power BI を使用してデータのクエリとレポートを行う場合は、CQD Power BI テンプレートをダウンロードします。 Power BI でテンプレートを開くと、CQD 管理者資格情報を使用してサインインするように求められます。 これらのクエリ テンプレートをカスタマイズし、Power BI ライセンスと CQD 管理者アクセス許可を持つ組織内のすべてのユーザーに配布できます。

これらの PBIT ファイルを使用するには、[ダウンロード](https://www.microsoft.com/download/details.aspx?id=102291)に含まれている *MicrosoftCallQuality.pctl* ファイルを使用して、[Power BI Connector for Microsoft CQD をインストール](CQD-Power-BI-connector.md)する必要があります。 

Power BI レポートにアクセスするための適切な [CQD アクセス ロール](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) があることを確認します。 

|Pbit |説明 |
|:----------|:---------|
|<strong>(New!)</strong> QER.pbit     |  Quality of Experience Report (QER) テンプレートを使用すると、顧客はエスカレートする前に Teams の会議と通話のエクスペリエンスに影響を与える問題を事前に特定できます。 また、管理者がエスカレートする問題に迅速に対応し、"会議中に何が起こったのか" という質問に答えるために役立つレポートも提供されています。  このテンプレートは、次のレポートを提供します。</p><li>検索 – 会議の URL、会議 ID、サブネット、または UPN で検索を有効にします。</li><li>会議の正常性の詳細 – 1 つの会議の詳細なメトリック。</li><li>ユーザー正常性の詳細 – 1 人のユーザーの詳細なメトリック。</li><li>Media Health – テナント全体の会議と通話の正常性に関する主要な正常性インジケーター (KHI) の概要。</li><li>メディアセットアップ – メディアセットアップエラーを分析します。</li><li>メディアの信頼性 – メディアの信頼性の問題を分析します。</li><li>オーディオ/ビデオ/共有の正常性 - オーディオ、ビデオ、または共有の正常性の中間レベルの KPI を確認します。</li><li>オーディオ/ビデオ/共有正常性の詳細 - オーディオ、ビデオ、または共有の正常性に関する詳細なメトリックを確認します。</li><li>VPN – 会議の正常性に対する VPN の影響を確認します。 (推定 VPN またはマップされた VPN)</li><li>上位 10 件のレポート – テナント内の問題領域を特定します。</li><li>日課 - KPI の日次レポートを確認します。</li><li>使用法 – 一般会議と通話の使用状況。</li><li>ユーザー フィードバック – ユーザーアンケートのフィードバック (Rate My Call とも呼ばれます) を確認します。</li><li>トランスポート – UDP をブロックしているネットワークを識別します。</li><li>デバイス – デバイスの影響を確認します。</li><li>クライアント - クライアントに重点を置いたメトリックを確認します。</li><li>データのビルド – CQD でビルド データ ファイルを確認します。</li><li>PSTN 正常性とユーザーの詳細 – PSTN ベースの通話の概要と個々のユーザー正常性を提供する 2 つのレポート。</li><li>ネットワーク メトリック – ジッター、パケット損失、待機時間に関する未加工のネットワーク メトリックの詳細を表示する 2 つのレポート。</li>  |
|CQD Teams 自動応答&通話キュー履歴レポート.pbit     |  このテンプレートには、次の 3 つのレポートが用意されています。</p><li>自動応答 – 自動応答に着信する呼び出しの分析を示します。</li><li>通話キュー – 通話キューに着信する通話の分析を示します。</li><li>エージェント タイムライン – 通話キューの呼び出しでアクティブになっているエージェントのタイムライン ビューを示します。</li><br>詳細については、「 [通話キュー履歴レポート&自動応答](aa-cq-cqd-historical-reports.md)」を参照してください。 |
|CQD Helpdesk Report.pbit     |このレポートは、建物と EUII データを統合して、1 人のユーザーからドリルダウンして、そのユーザーの呼び出し品質が低いアップストリームの根本原因を見つけられるように設計されています (たとえば、ユーザーがネットワークの問題が発生している建物にいる場合など)。 |
|CQD Location Enhanced Report.pbit     | CQD SPD の場所レポートを再想像します。 9 つのレポートが含まれており、通話品質、建物の WiFi、信頼性、および通話のレート (RMC) の情報を、ビルドまたはユーザー別に追加のドリルスルーで提供します。 レポート エクスペリエンスを最大限に高めるために、必ず建物データをアップロードしてください。 |
|CQD モバイル デバイス Report.pbit     | 通話品質、信頼性、通話の評価など、モバイル デバイス ユーザー向けに特別に調整された分析情報を提供します。 モバイル ネットワーク、WiFi ネットワーク、モバイル オペレーティング システムのレポート (Android、iOS) を表示します。 |
|CQD PSTN ダイレクト ルーティング レポート.pbit     |ダイレクト ルーティングを経由する PSTN 通話に固有の分析情報を提供します。 詳細については、「 [CQD PSTN ダイレクト ルーティング レポートの使用」](CQD-PSTN-report.md)を参照してください。 |
|CQD の概要レポート.pbit     |視覚化の向上、プレゼンテーションの改善、情報密度の向上、およびローリング日付。 これらのレポートを使用すると、外れ値を識別しやすくなります。 使いやすい対話型マップを使用して、場所ごとの通話品質を掘り下がります。 9 つの新しいレポート:</p>- 全体的な品質<br>- 信頼性全体<br>- RMC (通話のレート) 全体<br>- 会議の品質<br>- P2P 品質<br>- 会議の信頼性<br>- P2P の信頼性<br>- 電話会議 RMC<br>- P2P RMC         |
|CQD Teams 使用率レポート.pbit     | 組織内のユーザーが Teams を使用している方法と、その量を示します。 レポート エクスペリエンスを最大限に高めるために、必ず建物データをアップロードしてください。 詳細については、「 [CQD Power BI レポートを使用して Microsoft Teams の使用率を表示する」を参照してください](CQD-teams-utilization-report.md)。 |
|CQD ユーザー フィードバック (通話のレート) Report.pbit     | 組織の呼び出しをサポートするために簡単に使用できる方法で、通話率データを表示します。 エンド ユーザー教育の機会を特定するための詳細を含む相互参照。 |

> [!TIP]
> CQD データ用の Power BI レポートを設定したら、チャネルにタブとして追加します。 チャネルで選択 **+** した後、 **Power BI** を選択し、レポートを見つけます。 詳細については、 [Teams の [Power BI] タブを使用してレポートを埋め込む方法に関するページを参照してください](/power-bi/service-embed-report-microsoft-teams)。 Power BI ライセンスと CQD 管理者資格情報を持つユーザーのみがこれらのレポートにアクセスできることを覚えておいてください。

## <a name="related-topics"></a>関連項目

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Skype for Business の通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析および通話品質ダッシュボード](./monitor-call-quality-qos.md)
