---
title: CQD Power BIデータを分析する場合は、次のコマンドを使用Microsoft Teams
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
description: このPower BIを使用して、CQD データを分析Microsoft Teams。
ms.openlocfilehash: 67e6c8750d064c8472865a22f1367d297fd4fee5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616323"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>CQD Power BIデータを分析する場合は、次のコマンドを使用Microsoft Teams

2020 年 1 月の新機能: [CQD Power BIテンプレートをダウンロードします](https://www.microsoft.com/download/details.aspx?id=102291)。 カスタマイズ可能Power BIテンプレートを使用して、CQD データの分析とレポートを行います。

Teams の通話品質ダッシュボード (CQD) レポートでは、Power BI を使用してデータのクエリとレポートを行う場合は、CQD Power BI テンプレートをダウンロードします。 テンプレートを Power BI開き、CQD 管理者の資格情報でサインインするように求めるメッセージが表示されます。 これらのクエリ テンプレートをカスタマイズし、組織内のユーザーに配布して、Power BIおよび CQD 管理者のアクセス許可を持ちます。

これらの PBIT ファイルを使用する前に、ダウンロード に含まれる *MicrosoftCallQuality.p Power BI* ファイルを使用して [、Microsoft CQD](CQD-Power-BI-connector.md)用 Power BI コネクタをインストールする必要 [があります](https://www.microsoft.com/download/details.aspx?id=102291)。 

レポートにアクセスする適切な[CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)アクセス ロールPower BIします。 

|  |  |
|---------|---------|
|<strong>(New!)</strong>CQD Teams 自動応答 & Call Queue Historical Report.pbit     |  このテンプレートは、次の 3 つのレポートを提供します。</p><li>自動応答 – 自動応答に着信する通話の分析を表示します。</li><li>通話キュー – 通話キューに着信する通話の分析を示します。</li><li>エージェント タイムライン – 通話キュー呼び出しでアクティブなエージェントのタイムライン ビューを示します。</li><br>詳細については、「Call [Queue Historical Report (キュー履歴レポート自動応答 &を呼び出す) を参照してください](aa-cq-cqd-historical-reports.md)。        |
|CQD Helpdesk Report.pbit     |このレポートは、建物と EUII データを統合して、1 人のユーザーからドリルダウンして、そのユーザーの低品質の通話品質のアップストリームの根本原因を見つけ出せするように設計されています (たとえば、ユーザーはネットワークの問題が発生しているビルにいます)。         |
|CQD Location Enhanced Report.pbit     | CQD SPD の場所レポートを再想像します。 9 つのレポートが含まれています。通話品質、ビルの WiFi、信頼性、および通話料金 (RMC) の情報を、ビルまたはユーザーによる追加のドリルスルーで提供します。  レポートのエクスペリエンスを最大化するために、必ず建物のデータをアップロードしてください。        |
|CQD Mobile Device Report.pbit     | 通話品質、信頼性、通話の評価など、モバイル デバイス ユーザーに対して特にチューニングされた分析情報を提供します。 モバイル ネットワーク、WiFi ネットワーク、およびモバイル オペレーティング システム レポート (Android、iOS) を表示します。        |
|CQD PSTN ダイレクト ルーティング レポート.pbit     |直接ルーティングを経由する PSTN 通話に固有の分析情報を提供します。 詳細については、「CQD PSTN ダイレクト ルーティング [レポートの使用」を参照してください](CQD-PSTN-report.md)。         |
|CQD Summary Report.pbit     |視覚エフェクトの向上、プレゼンテーションの改善、情報密度の向上、およびローリング日付。 これらのレポートを使用すると、外れ値を簡単に識別できます。 使いやすい対話型マップを使用して、通話品質を場所別にドリルダウンします。 9 つの新しいレポート:</p>- 品質全体<br>- 信頼性全体<br>- RMC (通話料金) 全体<br>- 会議の品質<br>- P2P 品質<br>- 会議の信頼性<br>- P2P の信頼性<br>- Conference RMC<br>- P2P RMC         |
|<strong>(New!)</strong>CQD Teams使用率レポート.pbit     | 組織内のユーザーがアプリを使用している方法Teams量を示します。 レポートのエクスペリエンスを最大化するために、必ず建物のデータをアップロードしてください。 詳細については[、「CQD レポートを使用してPower BIを表示する」をMicrosoft Teamsしてください](CQD-teams-utilization-report.md)。        |
|CQD ユーザー フィードバック (通話の評価) Report.pbit     | 組織の通話をサポートするために簡単に使用できる方法で、通話データを評価する方法を示します。 エンド ユーザー教育の機会を識別するために、言葉による相互参照。        |

> [!TIP]
> CQD データ用にPower BIレポートを設定したら、それらをタブとしてチャネルに追加します。 チャネルで選択 **+** した後、[レポート]  Power BIレポートを見つける] を選択します。 詳細については、「レポートを埋め[込む」を参照Power BIタブを参照Teams。](/power-bi/service-embed-report-microsoft-teams) これらのレポートにアクセスできるのは、Power BIと CQD 管理者の資格情報を持つユーザーのみです。


## <a name="related-topics"></a>関連トピック

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Skype for Business の通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析および通話品質ダッシュボード](./monitor-call-quality-qos.md)
