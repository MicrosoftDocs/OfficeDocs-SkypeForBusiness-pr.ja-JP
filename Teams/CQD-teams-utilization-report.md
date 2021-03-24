---
title: CQD データを使用して Power BI で Microsoft Teams の使用率を表示する
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Teams 使用率 Power BI レポートを使用して、Microsoft Teams 通話品質ダッシュボード (CQD) データにアクセスし、組織内での Microsoft Teams の使用状況を追跡します。
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095041"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>CQD データを使用して Power BI で Microsoft Teams の使用率を表示する

2020 年 3 月の新機能として [、CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)用のダウンロード可能な Power BI クエリ テンプレートに Teams 使用率レポートが追加されました。 

この新しい Teams 使用率レポートでは、Teams 通話品質ダッシュボード (CQD) データにアクセスして、ユーザーが Microsoft Teams を使用している方法 (およびどのくらい) を確認できます。 これらのレポートは、管理者とビジネス リーダーの両方が、このデータにすばやくアクセスできる一元管理された場所を目的としています。

Teams 使用率 Power BI レポートは、通話カウント **[](#call-count-summary-report)** の概要と音声通話分数の概要という 2 つの主要なレポート **[で構成されます](#audio-minutes-summary-report)**。 次[の](#daily-usage)[説明に示](#regional-audio-details)すドリルダウン[](#conference-details)レポートをユーザー[](#user-list)が利用すると、[毎日の使用状況]、[地域の音声の詳細]、[電話会議の詳細]、および [ユーザー リスト] レポートが再生されます。

> [!NOTE]
> 地域とネットワークのフィルター機能を提供するには、建物とサブネットのデータを入力する必要があります。

## <a name="call-count-summary-report"></a>通話数の概要レポート

メイン ページ (通話カウントの概要) では、セクション タイトルに示されている過去 30 日間と 90 日間の音声、ビデオ、画面共有セッションの数がすぐに表示されます。 最初に表示されるデータは組織全体を表し、ページの左側にあるスライサードロップダウン オプションを使用してフィルター処理できます。

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report1.png)

1. スライサーのドロップダウンの右側では、メディアの種類別の通話数は、過去 30 日間の内部ビューまたは外部ビューに分解されます。 上のスクリーンショットを見て、組織の外部からの通話が多く発生しているのを確認できます。これは、現在のグローバル環境を考慮すると理にかなっています。
  ![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report2.png)

1. メディアの種類数ボックスの右側には、過去 90 日間のメディアの種類別の月間通話数があります。 各列とメディアの種類をマウスでポイントすると、前月または現在の月の数が表示され、使用状況の傾向情報が表示されます。
  ![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report3.png)
 

1. 中央のグラフは 90 日間のグラフと同様に機能しますが、過去 30 日間の毎日の利用状況ビューが提供され、ユーザーは特定の日の詳細を右クリックしてドリルダウンできます。
  ![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report4.png)

ページの左下のセクションには、過去 1 年間のメディアの種類ごとに合計値を提供するテーブルがあります。 
    ![スクリーンショット: Teams 使用率レポート ](media/CQD-teams-utilization-report5.png) ![ のスクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report6.png)   

表の右側には、過去 30 日間のクライアントが最も多く使用されている (通話/ストリーム) が棒グラフに表示されます。
   ![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report7.png)

このページの最後のグラフ セットでは、各メディアの種類が個別に表示され、内訳には電話会議と P2P の使用状況が表示されます。 次のグラフは、P2P と比較して、電話会議の使用状況の数が非常に多い場合を示しています。
  ![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Audio Minutes Summary Report

オーディオ分数の使用状況レポートでは、分の合計使用量がいくつかの異なるビューで提供されます。 

スライサーの横に、テキスト ボックスを簡単に使用できる 30 日間の使用状況の概要が表示されます。 上位の数値は 30 日間の合計を示し、内部と外部の内訳が下に表示されます。

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report9.png)

上の右の棒グラフは、電話会議の音声使用状況を 1 年間表示します。 月の上にマウス ポインターを置くと、会議の音声の分数が表示されます。

P2P と電話会議の音声の違いを示す左下のグラフは、過去 1 年間のすべての音声を取得し、2 つの種類の間で分解します。

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report10.png)

[オーディオ分数] ページの最後のグラフには、グローバル マップ オーバーレイでの音声の分の使用状況が表示されます。 このグラフは、建物とサブネットのデータがテナントにアップロードされた場合にのみ機能します。 マップ上の円グラフのオーバーレイを詳細に表示し、その後で地域の音声を使用できます。

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>ドリルスルー機能

前に説明した通り、ユーザーは日次および地域の使用状況レポートを詳細に表示できます。

### <a name="daily-usage"></a>1 日の使用状況

[毎日の使用状況] レポートを使用すると、管理者は 1 日の間に最大使用時間を特定できます。 また、使用状況に加えて、その日の全体的なユーザー の感情やフィードバックも取り込む可能性があります。

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report12.png)

[毎日の使用状況] レポートには、選択した日のオーディオ、ビデオ、画面共有の数が表示され、内部接続と外部接続を区別する機能が追加されます。 会議およびピアツーピアのブレークダウンは、モーダル合計ボックスの右側に表示されます。 レポートの上部の右側には、その日の関連付けられた ID と参加者を含む電話会議の一覧が表示されます。 電話会議リストには、電話会議の詳細レポートのドリルダウンが追加で表示されます。 グラフィックを置き換える

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report13.png)

中央の領域の棒グラフを使用すると、ユーザーは 1 日の間にピーク時の消費期間を特定できます。 ユーザーは、グラフに表示される時間をドリルダウンして、その時間のユーザー リスト レポートを表示できます。

棒グラフの右側には、ユーザー フィードバックが視覚的な形式で表示されます。 ユーザーの感情は主観的な場合がある一方で、潜在的な問題を特定するために使用できる洞察を提供します。

下の表には、その日のメトリックの範囲が表示されます。 低品質のパーセンテージと障害率は、管理者に改善の可能性がある領域を提供する可能性があります。 次に示すように、各時間を個別に選択できます。

このデータは、ピーク時に問題がある地域を特定するために使用できます。


その日の列をクリックすると、その時間のメトリックが表示されます。
![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report14.png)
  
  1.  グラフの下の表には、その時間のメトリックが表示されます。 任意の列見出しで並べ替えを行います。ただし、問題のある領域を見つけることに関心があります。  
    ![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report15.png)
    
  2.  IND 地域では、この期間中の電話会議でのビデオパフォーマンスが低下しています。 その後、CQD QER Microsoft レポートを使用して、領域と時間枠が特定されると、問題のある場所を絞り込む可能性があります。

### <a name="conference-details"></a>電話会議の詳細

会議の詳細レポートでは、出席者リストからセッション中に使用されるメディアの種類まで、会議に関する追加の分析情報が提供されます。

[毎日の利用状況] ページの会議 ID グラフの参加者バーを右クリックして、会議の詳細をドリルダウンします。

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report24.png)

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report25.png)
  

会議の参加者だけでなく、すべての関連情報をパケット損失とジッターにまで表示して、下の表のトラブルシューティング作業の可能性を支援できます。

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>地域の音声の詳細

地域のオーディオの詳細のドリルダウンには、選択した地域の音声分の使用状況が具体的に表示されます。 CQD にアクセスできるユーザーは、選択した地域内の P2P と電話会議の音声の両方の使用状況の傾向を確認できます。

1.  [通話カウントの概要] ページで、テーブル内の特定の領域にドリルスルーします。
  ![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report16.png)

2.  追加情報が必要な領域を含む行を選択します。
  ![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report17.png)

3.  データの傾向は、内部ネットワークで使用されている分数が非常に多く、会議は P2P の使用をはるかに上回っています。
  ![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report18.png)

地域の音声傾向は、ユーザーが世界の外部影響の影響を受ける方法を示す場合に使用できます。 具体的には、現在、EMEA 地域と APAC 地域の外部使用量が増加し、リモートで作業を求める人々が増える可能性があります。


### <a name="user-list"></a>ユーザー リスト

ユーザー リストのドリルダウンでは、予想される方法として、レポートを表示しているユーザーが選択した特定の時間のユーザー固有の情報が提供されます。 ユーザー リスト レポートには、[毎日の使用状況] レポートの [時間別傾向] グラフのドリルダウンを使用してアクセスできます。 次に示すように、追加情報が必要な時間を右クリックし、[ドリルスルーとユーザー リスト] を選択します。

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report19.png)

ユーザー リスト レポートには、ページの上部中央にあるドーナツ グラフを介した内部または外部の接続が表示されます。 次の画像では、企業ネットワークの外部からの大量の参加が見受け取ることができます。

グラフの上の右には、その時間内に各ユーザーによって行われた通話の数が表示されます。

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report20.png)

下の表は、各ユーザーがその時間に参加したセッションの詳細情報を示しています。 [エラーの種類] 列は、呼び出しがドロップされる原因を特定する場合に便利です。 キャプチャとレンダリング デバイスの列は、通話が低品質と報告された理由を特定するのに役立ちます。


## <a name="related-topics"></a>関連項目

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Skype for Business の通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析および通話品質ダッシュボード](./monitor-call-quality-qos.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
