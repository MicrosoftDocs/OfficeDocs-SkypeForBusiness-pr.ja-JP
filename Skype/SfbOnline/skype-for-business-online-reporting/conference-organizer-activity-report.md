---
title: 電話会議開催者アクティビティ レポート
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 03a255d4-0e1d-4b24-b73d-7a62fae36254
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- O365E_ReportsS4BOrgActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Conference Organized Activity report, and how to interpret and customize it. '
ms.openlocfilehash: 6cbba90fd874fb4b2d4b3799e0765c2de66e8be4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706072"
---
# <a name="conference-organizer-activity-report"></a>電話会議開催者アクティビティ レポート

[] 新しい Office 365 の [ **レポート**] ダッシュボードには、組織内の Office 365 製品全体にわたるアクティビティの概要が表示されます。 このダッシュボードでは、個々の製品レベルのレポートまで掘り下げ、各製品内のアクティビティについてより細かい洞察を得ることができます。 たとえば、[ **Skype for Business 電話会議開催者アクティビティ**] レポートを使用して、ユーザーが IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サードパーティ、およびダイヤルイン/アウト - Microsoft を使用する電話会議をどれだけ開催しているかを確認できます。 

詳細については、 [「レポートの概要」](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)をご覧ください。
  
このレポートは、他の Skype for Business レポートと共に、組織全体の会議の開催活動の詳細を提供します。 これらの詳細は、組織でその他のビジネス上の決定を調査、計画、実行しているときに役立ちます。 
  
> [!NOTE]
> Microsoft 365 管理センターに管理者としてログオンすると、すべての Skype for Business レポートを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-conference-organizer-report"></a>Skype for Business 電話会議開催者レポートを取得する方法

1. [管理センター >**レポート** > の**利用状況]** に移動します。
    
2. [**利用状況**] ページで、左側の [レポートの選択]**ボックスの一覧**の [ **Skype for business** >**電話会議開催者アクティビティ**] を選択します。 または、skype for business**アクティビティ**ウィジェットをクリックし、Skype for **business アクティビティ**リストで [ **skype for business 電話会議開催者アクティビティ**] をクリックします。
  
## <a name="interpret-the-skype-for-business-conferences-organizer-report"></a>Skype for Business 電話会議開催者レポートを解析する

[**アクティビティ**]、[**ユーザー**]、[**分**] のグラフを見ることで、開催された Skype for business 会議の状態を把握することができます。
  
![Skype for business 開催会議レポート](../images/0ab0e5e8-cf18-4f8f-a31a-94048e375a0f.PNG)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>**Skype for Business 電話会議開催者アクティビティ** レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポート内の特定の日をクリックすると、テーブル (「数値7」を参照) に30日間のデータが表示されます。これは、レポートが生成された日付 (2 を参照) になります。

> [!NOTE]
> 特定の日の詳細をクリックすると、レポートが生成された日付までの30日間のデータのみが表示されます。

***
![ナンバー 2](../images/sfbcallout2.png)<br/>各レポートには、このレポートが生成された日付が表示されます。 通常、レポートには、アクティビティの時刻からの 24 ~ 48 時間の遅延時間が反映されます。 
***
![ナンバー 3](../images/sfbcallout3.png)<br/>[ **アクティビティ**] グラフの対話型グラフとリアルタイム データを使用して、使用状況の傾向を把握し、開催された電話会議の合計数と、組織で開催された電話会議のタイプを確認します。このグラフには、組織全体で開催された [ **IM**]、[ **音声/ビデオ**]、[ **アプリケーション共有**]、[ **Web**]、[ **ダイヤルイン/アウト - サード パーティ**]、[ **ダイヤルイン/アウト Microsoft**] の電話会議の合計数とタイプが表示されます。 
***
![ナンバー 4](../images/sfbcallout4.png)<br/>[ **ユーザー**] グラフの対話型グラフとリアルタイム データを使用して、使用状況の傾向を把握し、組織で開催された電話会議の一意のユーザー数を確認します。このグラフには、開催された電話会議の [ **IM**]、[ **音声/ビデオ**]、[ **アプリケーション共有**]、[ **Web**]、[ **ダイヤルイン/アウト - サード パーティ**]、[ **ダイヤルイン/アウト Microsoft**] のタイプともに合計ユーザー数が表示されます。 
***
![ナンバー 5](../images/sfbcallout5.png)<br/>[ **分**] グラフの対話型グラフとリアルタイム データを使用して、使用状況の傾向を把握し、Microsoft を電話会議プロバイダーとして音声/ビデオ、ダイヤルインとダイヤルアウトを使用した電話会議を開催した場合の、ユーザーが使用した分単位の通話時間を確認します。このグラフは、開催された電話会議中に使用された [ **音声/ビデオ**]、[ **ダイヤルイン Microsoft (分)**]、[ **ダイヤルアウト Microsoft (分)**] の合計通話時間が分単位で表示されます。
***
![ナンバー 6](../images/sfbcallout6.png)<br/>
各グラフには、「X」軸（水平）と「Y」軸（垂直）があります。
*    [ **アクティビティ**] アクティビティ グラフの Y 軸は、組織内でユーザーが開催した電話会議の IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サードパーティ、ダイヤルイン/アウト Microsoft の合計数です。 
*    [ **ユーザー**] アクティビティ グラフの Y 軸は、組織内でユーザーが開催した電話会議の IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サードパーティ、ダイヤルイン/アウト Microsoft を行ったユーザーの合計数です。
*    [**分**] アクティビティグラフの Y 軸は、組織内でユーザーが開催した会議の、音声/ビデオ、ダイヤルイン microsoft 分、ダイヤルアウトの microsoft 議事録の合計数です。  

どちらのグラフも、X 軸はこの特定のレポートで選択した日付範囲です。 
***
![番号7](../images/sfbcallout7.png)<br/>凡例の項目をクリックして、グラフに表示する系列をフィルター処理できます。たとえば、[ **アクティビティ**] グラフで [ **IM]**、[ **音声/ビデオ**]、[ **アプリケーション共有**]、[ **Web**]、[ **ダイヤルイン/アウト - サード パーティ**]、[ **ダイヤルイン/アウト - Microsoft**] をクリックまたはタップすると、それぞれに関連した情報のみが表示されます。この選択を変更しても、グリッド テーブルの情報は変更されません。
***
![数値8](../images/sfbcallout8.png)<br/>この表は、ユーザーごとの、開催した電話会議アクティビティの内訳を示しています。また、Skype for Business が割り当てられているすべてのユーザーと、ユーザーが開催した電話会議を示しています。表に新しい列を追加することができます。 
* [ **ユーザー名**] はユーザーの名前です。 
* [ **削除済み**] はユーザーのライセンスが削除されたことを示します。<br/><br/>
  > [!NOTE]
  > 削除されたユーザーのアクティビティは、選んだ期間中にライセンスが付与されている限り、レポートに表示されたままになります。 [ **削除済み** ] 列は、アクティブではない状態になったユーザーが引き続きレポート内のデータに影響している可能性に注意するのに役立ちます。
     
* [ **削除日**] は、ユーザーのライセンスが削除された日付です。 
* [ **前回のアクティビティの日付 (UTC)**] は、ユーザーが前回アクティビティを行った日付 (UTC) です。 
* [ **IM**] は、開催された IM 会議の合計数を示します。 
* [ **音声/ビデオ**] は、開催された音声/ビデオ会議の合計数を示します。
* [ **アプリケーション共有**] は、開催されたアプリケーション共有会議の合計数を示します。 
* [ **Web**] は、開催された Web 会議の合計数を示します。 
* [**ダイヤルイン/アウト-サードパーティ**] は、サードパーティの電話会議プロバイダーを使用して開催されたダイヤルイン/アウト電話会議の合計数を示します。 
* **[ダイヤルイン/アウト Microsoft** ] は、開催されたダイヤルイン/アウト音声会議の合計数を示します。 
* [ **音声/ビデオ通話分数**] は、音声/ビデオを使用した電話会議を開催したときに使用した合計時間を分単位で示します。 
* [**ダイヤルイン microsoft 議事録**は、Microsoft を電話会議プロバイダーとして使用して開催された会議で使用されたダイヤルインの合計時間 (分) を示します。 
* [**ダイヤルアウト microsoft (分) (分)** を指定すると、Microsoft を電話会議プロバイダーとして使用して開催された会議で使用されたダイヤルアウトの合計時間が表示されます。 

組織のポリシーにより、ユーザー情報を特定できるレポートを表示できない場合は、これらすべてのレポートのプライバシー設定を変更できます。 [管理センターのアクティビティレポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)で、[**ユーザーレベルの詳細を非表示にする方法**を教えてください。] セクションを確認します。
***
![数値9](../images/sfbcallout9.png)<br/>また、[ **エクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。           <br/> ![Skype for Business レポートの [エクスポート] ボタン。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。
***
![数値10](../images/sfbcallout10.png)<br/>任意の列の**列**アイコンをクリックまたはタップして、レポートに列を追加または削除します。           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype For business 電話会議参加者アクティビティレポート](conference-participant-activity-report.md)参加している IM、音声/ビデオ、アプリケーション共有、Web 会議、ダイヤルイン/ダイヤルアウト会議の数を確認できます。
    
- [Skype For business ピアツーピアアクティビティレポート](peer-to-peer-activity-report.md)ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype For business ユーザーがブロック](users-blocked-report.md)されたレポートPSTN 通話の発信をブロックされている組織内のユーザーを確認できます。
    
- [Skype For BUSINESS PSTN 使用状況レポート](pstn-usage-report.md)通話の着信/発信に費やした時間 (分) を確認することができます。
    
- [Skype For BUSINESS PSTN 分単位のプールレポート](pstn-minute-pools-report.md)には、組織内の現在の月に消費された分数が表示されます。

- [Skype For business セッションの詳細レポート](session-details-report.md)個々のユーザの通話エクスペリエンスについての詳細を見ることができます。

## <a name="related-topics"></a>関連トピック
[管理センターでのアクティビティレポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
