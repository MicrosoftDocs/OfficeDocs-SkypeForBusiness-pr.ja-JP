---
title: CQD データを使用して Power BI の Microsoft Teams 使用率を表示する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Teams 使用率 Power BI レポートを使用して、Microsoft Teams 通話品質ダッシュボード (CQD) データにアクセスして、組織内の Microsoft Teams の使用状況を追跡します。
ms.openlocfilehash: bd579fa3f57c6e3b50a363eb77523f577c750efb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270692"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>CQD データを使用して Power BI の Microsoft Teams 使用率を表示する

Teams 使用率レポートは、 [CQD 用のダウンロード可能な Power BI クエリ テンプレートの](https://www.microsoft.com/download/details.aspx?id=102291)一部として使用できます。 

このレポートでは、Teams 通話品質ダッシュボード (CQD) データにアクセスして、ユーザーが Microsoft Teams を使用している方法 (および量) を確認できます。 これらのレポートは、管理者とビジネス リーダーの両方がこのデータにすばやくアクセスできる一元的な場所であることを目的としています。 [通話品質テレメトリの性質上、このデータを具体的な数値に依存しないことを](CQD-frequently-asked-questions.md#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)お勧めします。

Teams 使用率 Power BI レポートは、 **[通話数の概要](#call-count-summary-report)** と **[音声分](#audio-minutes-summary-report)** の概要という 2 つの主要なレポートで構成されます。 ユーザーがドリルダウン レポートを利用すると、 [毎日の使用状況](#daily-usage)、 [地域オーディオの詳細](#regional-audio-details)、会議の [詳細](#conference-details) 、 [ユーザー リスト](#user-list) のレポートが表示されます(以下の説明を参照)。

> [!NOTE]
> リージョンとネットワークのフィルター機能を提供するには、建物データとサブネット データを設定する必要があります。

## <a name="call-count-summary-report"></a>通話数の概要レポート

メイン ページ (通話数の概要) では、セクション タイトルに記載されているように、過去 30 日間と 90 日間のオーディオ、ビデオ、画面共有セッションの数がすぐに表示されます。 最初に表示されるデータは組織全体のものであり、ページの左側にあるスライサー ドロップダウン オプションを使用してフィルター処理できます。

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report1.png)

1. スライサー ドロップダウンの右側にあるメディアの種類別の呼び出しの数は、過去 30 日間の内部ビューまたは外部ビューに分割されます。 上のスクリーンショットを見ると、組織の外部の場所からの呼び出しが増え、現在のグローバル環境を考慮すると理にかなっていることがわかります。
  ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report2.png)

1. メディアの種類のカウント ボックスの右側には、過去 90 日間のメディアの種類別の月次通話数があります。 各列とメディアの種類をポイントして、前の月または現在の月の数を表示し、使用状況の傾向情報を提供できます。
  ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report3.png)
 

1. 中央のグラフは 90 日間のグラフと同様に機能しますが、過去 30 日間の毎日の使用状況ビューが提供され、ユーザーは特定の日の詳細を右クリックしてドリルダウンできます。
  ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report4.png)

ページの左下セクションには、過去 1 年間のメディアの種類ごとの合計値を示すテーブルがあります。 
    ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report5.png)
    ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report6.png)   

表の右側には、過去 30 日間に最も多く使用されたクライアント (呼び出し/ストリーム) が横棒グラフに表示されます。
   ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report7.png)

このページのグラフの最後のセットは、各メディアの種類を個別に示し、内訳は会議と P2P の使用状況を示しています。 次の図は、P2P と比較して会議の使用量が大幅に多いことを示しています。
  ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>オーディオ分の概要レポート

オーディオ分の使用状況レポートでは、合計分の使用量がいくつかの異なるビューで提供されます。 

テキスト ボックスを使いやすいように、スライサーの横に 30 日間の使用状況の概要が表示されています。 上位の数値は 30 日間の合計を示し、内部と外部の内訳はその下に表示されます。

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report9.png)

右上の棒グラフは、電話会議のオーディオ使用状況を 1 年間表示します。 月の上にマウス ポインターを合わせると、会議の音声の分数が表示されます。

P2P と電話会議のオーディオの違いを表示するために、左下のグラフは過去 1 年間のすべてのオーディオを受け取り、2 つの種類の間で分割します。

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report10.png)

[オーディオ分] ページの最後のグラフには、グローバル マップ オーバーレイでのオーディオ分の使用状況が表示されます。 このグラフは、建物データとサブネット データがテナントにアップロードされている場合にのみ機能します。 マップ上の円グラフオーバーレイをドリルインし、その後、地域のオーディオを使用できます。

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>ドリルスルー機能

既に説明したように、ユーザーは日次および地域の使用状況レポートにドリル インできます。

### <a name="daily-usage"></a>毎日の使用状況

毎日の使用状況レポートを使用すると、管理者は 1 日のうちにピーク消費期間を特定できます。 使用状況に加えて、その日の全体的なユーザーセンチメントとフィードバックをキャプチャすることもできます。

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report12.png)

日次使用状況レポートには、選択した日のオーディオ、ビデオ、画面共有の数が表示され、内部接続と外部接続を区別する機能が追加されます。 電話会議とピアツーピアの内訳は、モダリティの合計ボックスのすぐ右側にあります。 レポートの右上には、その日の関連付けられた ID と参加者を含む会議の一覧が表示されます。 会議の一覧には、会議の詳細レポートへの追加のドリルダウンも用意されています。 グラフィックを置き換える

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report13.png)

中央領域の棒グラフを使用すると、ユーザーは 1 日の間のピーク消費期間を特定できます。 ユーザーは、その時間のユーザー リスト レポートを表示するグラフで表される時間をドリルダウンできます。

棒グラフの右側には、ユーザー フィードバックが視覚的な形式で表示されます。 ユーザーセンチメントは主観を持つことができますが、潜在的な問題を特定するために使用できる分析情報を提供します。

下の表では、その日のメトリックの範囲を示します。 失敗率と共に割合が低い場合、管理者は改善の可能性がある領域を提供できます。 各時間は、次に示すように個別に選択することもできます。

このデータは、ピーク時に問題が発生しているリージョンを特定するために使用できます。


その日の列をクリックすると、その時間のメトリックが表示されます。
![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report14.png)
  
  1.  グラフの下の表には、その時間のメトリックが表示されます。 これは、任意の列ヘッダーで並べ替えることができます。ただし、問題のある領域を見つけることに関心があります。  
    ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report15.png)
    
  2.  この期間中に、IND リージョンで会議のビデオ パフォーマンスが低下していることがわかります。 その後、CQD QER Microsoft レポートを使用して、リージョンと時間枠が特定された問題のある場所を絞り込むことができます。

### <a name="conference-details"></a>会議の詳細

会議の詳細レポートは、出席者リストから、セッション中に使用されるメディアの種類に関する追加の分析情報を提供します。

[毎日の使用状況] ページの会議 ID グラフの参加者バーを右クリックして、会議の詳細をドリルダウンします。

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report24.png)

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report25.png)
  

会議の参加者と、パケット損失とジッターに関連するすべての情報を確認し、下の表の潜在的なトラブルシューティング作業を支援することができます。

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>リージョンオーディオの詳細

[地域オーディオの詳細] ドリルダウンには、選択したリージョンのオーディオ分の使用状況が具体的に表示されます。 CQD にアクセスできるユーザーは、選択したリージョン内の P2P と電話会議の両方のオーディオの使用状況の傾向を確認できます。

1.  [通話数の概要] ページで、テーブルを介して特定のリージョンにドリルスルーします。
  ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report16.png)

2.  リージョンの追加情報が必要な行を選択します。
  ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report17.png)

3.  データの傾向は、内部ネットワークで非常に多くの分が使用されており、会議は P2P の使用をはるかに上回っています。
  ![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report18.png)

地域オーディオの傾向は、ユーザーが世界の外部の影響によってどのように影響を受けるかを示すために使用できます。 具体的には、今のところ、EMEA と APAC リージョンの外部使用が増加し、リモートで作業するよう求められる人が増えると予想されます。


### <a name="user-list"></a>ユーザー リスト

ユーザー 一覧のドリルダウンでは、レポートを表示しているユーザーが選択した特定の時間のユーザー固有の情報が予想どおりに提供されます。 ユーザー リスト レポートには、毎日の使用状況レポートの時間ごとの傾向グラフのドリルダウンからアクセスできます。 時間の追加情報が必要な時間を右クリックし、次に示すように [ドリルスルー] と [ユーザー リスト] を選択します。

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report19.png)

ユーザー リスト レポートには、ページの上部中央にあるドーナツ グラフを介した内部/外部接続が表示されます。 次の図では、企業ネットワークの外部から大量の参加があることがわかります。

グラフの右上には、その時間内に各ユーザーが行った呼び出しの数が表示されます。

![スクリーンショット: Teams 使用率レポート。](media/CQD-teams-utilization-report20.png)

下の表は、各ユーザーがその時間に参加したセッションの詳細な情報を示しています。 [失敗の種類] 列は、呼び出しが削除された原因を特定するのに役立ちます。 [キャプチャ] 列と [Render Device] 列は、通話の品質が低いと報告された理由を特定するのに役立ちます。


## <a name="related-topics"></a>関連項目

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Skype for Business の通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析および通話品質ダッシュボード](./monitor-call-quality-qos.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
