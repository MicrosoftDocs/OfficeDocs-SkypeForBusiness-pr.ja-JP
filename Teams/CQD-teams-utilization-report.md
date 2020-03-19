---
title: CQD のデータを使用して、Power BI で Microsoft Teams の使用率を表示する
ms.author: lolaj
author: LolaJacobsen
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
description: Teams 使用率の Power BI レポートを使って、組織での Microsoft Teams の利用状況を追跡します。
ms.openlocfilehash: 7eb39d043fafae0464ac52aa1e328c24b22d73f3
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858762"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>CQD のデータを使用して、Power BI で Microsoft Teams の使用率を表示する

2020年3月に初めて、CQD のダウンロード可能な[POWER BI クエリテンプレート](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)に Teams の使用状況レポートが追加されました。 

この新しいチームの使用状況レポートでは、ユーザーが Microsoft Teams を使用している方法 (およびその程度) を確認できます。 これらのレポートは、管理者とビジネスリーダーの両方がこのデータにすばやくアクセスできる一元的な場所です。

Teams 使用率 Power BI レポートは、2つの主要なレポートで構成されています。**[通話カウントの概要](#call-count-summary-report)** と**[音声分の概要](#audio-minutes-summary-report)**。 以下の説明に記載されているように、ユーザーがドリルダウンレポートを利用すると、[デイリー Usage](#daily-usage)と[地域の音声詳細](#regional-audio-details)レポートが再生されます。

> [!NOTE]
> 地域とネットワークのフィルター処理機能を提供するには、建物およびサブネットデータを設定する必要があります。

## <a name="call-count-summary-report"></a>通話カウントの概要レポート

メインページ ([通話カウントの概要]) には、セクションタイトルに記載されているように、最後の 30 ~ 90 日間の音声、ビデオ、画面共有セッションの数がすぐに表示されます。 最初に表示されるデータは組織全体に対して設定され、ページの左側にある [スライサー] ドロップダウンオプションを使ってフィルター処理することができます。

![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report1.png)

1. スライサードロップダウンの右側では、メディアの種類別の呼び出しの数が、過去30日間にわたって内部/外部ビューに分割されます。 上のスクリーンショットでは、組織外の場所からより多くの通話が行われていることを示しています。これは、現在のグローバル環境を考慮していることを意味します。
  ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report2.png)

1. [メディアの種類のカウント] ボックスの右側には、過去90日間のメディアの種類別の月次通話カウントがあります。 各列とメディアの種類をマウスでポイントすると、前月または現在の月の数が表示され、使用傾向の情報が提供されます。
  ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report3.png)

1. 中央のグラフは、90日間のグラフとして機能しますが、過去30日間の日次利用状況ビューを提供し、ユーザーが右クリックして特定の日の詳細をドリルダウンできるようにします。
  ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report4.png)

ページの左下のセクションでは、過去1年の各メディアの種類の合計値を提供するテーブルが見つかります。 
    ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report5.png)
  
また、テーブルには、地域データの分類を表示できるドリルダウンもあります。
    ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report6.png)

テーブルの右側にある棒グラフには、過去30日間に最も頻繁に使用されているクライアント (通話/ストリーム) が表示されます。
   ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report7.png)


このページの最後のグラフセットでは、各メディアの種類が個別に表示され、会議と P2P の使用状況を示すブレークダウンが表示されます。 以下の図は、P2P と比較した場合の会議の利用回数が非常に多いことを示しています。
  ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>オーディオ分のサマリーレポート

[オーディオ時間の利用状況] レポートでは、合計分使用量がいくつかの異なるビューで提供されます。 

スライサーの隣には、テキストボックスを簡単に利用できるように、30日間の使用状況の概要が表示されています。 上部の番号には、その下に内部と外部の内訳が表示された、30日間の合計が表示されます。

![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report9.png)

右上の棒グラフでは、電話会議の音声使用状況が yearlong で表示されます。 月をポイントすると、会議の音声通話時間が表示されます。

P2P と会議の音声の違いを示すために、左下のグラフはすべてのオーディオを過去の年に向けて受け取り、2つの種類の間で分割します。

![スクリーンショット: 通話先の](media/CQD-teams-utilization-report10.png)通話先の [分間のサマリー] ページの最後のグラフには、グローバルマップオーバーレイでのオーディオ分の使用状況が表示されます。 このグラフは、構築およびサブネットデータがテナントにアップロードされた場合にのみ機能します。 地図上の円グラフのオーバーレイを表示して、その後で地域のオーディオ使用法を提供できます。

![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a>ドリルスルー機能

前に説明したように、ユーザーは日単位および地域の利用状況レポートについて詳しく調べることができます。

### <a name="daily-usage"></a>日常的な利用状況

日次利用状況レポートを使用すると、管理者は1日の間にピークの消費期間を特定できます。 利用状況に加えて、その日の全体的なユーザー感情とフィードバックをキャプチャすることもできます。

![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report12.png)

このデータは、消費時間のピーク時に問題が発生した地域を特定するために使用できます。

1.  [通話カウントの概要] ページで、特定の日にドリルスルーします。 その日の1時間の傾向を確認して、ピーク使用率を確認します。
  ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report13.png)

2.  その日の列をクリックして、その時間の指標を表示します。
  ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report14.png)
    
    1.  グラフの下の表には、その時間の測度が表示されます。 これは、任意の列見出しを基準にして並べ替えることができます。ただし、問題のある領域を見つけることに関心を持っています。  
        ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report15.png)
    
    2.  この期間中の会議では、IND 領域のビデオパフォーマンスが低下していることがわかります。 その後、CQD QER Microsoft レポートを使って、地域と時間のフレームが識別されたために、問題のある場所を絞り込むことができます。

### <a name="regional-audio-details"></a>地域の音声の詳細

[地域のオーディオ詳細] のドリルダウンでは、選択した地域の音声分の使用状況が具体的に表示されます。 CQD へのアクセス権を持つユーザーは、選択した地域内の P2P と会議のオーディオの使用状況の傾向を確認できます。

1.  [通話カウントの概要] ページで、表を通じて特定の地域にドリルダウンします。
  ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report16.png)

2.  領域の追加情報が必要な行を選択します。
  ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report17.png)

3.  データの傾向は、内部ネットワークで利用されている長い時間 (分単位) を示しています。これには、surpassing が P2P を使用しています。
  ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report18.png)

地域オーディオの傾向を使って、世界中の外部の影響によってユーザーがどのように影響を受けるかを示すことができます。 具体的には、この時点で、ユーザーがリモートで作業することを求められる場合に、EMEA と APAC 地域の外部使用が表示されることを想定しています。



## <a name="related-topics"></a>関連項目

[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質ダッシュボードでのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Skype for Business の通話分析をセットアップする](set-up-call-analytics.md)

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析および通話品質ダッシュボード](difference-between-call-analytics-and-call-quality-dashboard.md)
 