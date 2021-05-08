---
title: アクティビティ レポート
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- O365E_ReportsS4BActivity
description: 'アクティビティ レポートを取得するSkype for Business、レポートに含まれるもの、およびデータを解釈する方法について学習します。 '
ms.openlocfilehash: 094d947088b1a1fea4a8585e09bdedfa6ffe2a2b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238313"
---
# <a name="activity-report"></a>アクティビティ レポート

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[**レポート]** ダッシュボードには、組織内の製品のMicrosoft 365またはOffice 365アクティビティの概要が表示されます。 これにより、個々の製品レベルのレポートにドリルダウンして、各製品内のアクティビティに関するより詳細な分析情報を提供できます。 たとえば **、Skype for Business** アクティビティ レポートを使用して、ユーザーがピアツーピアまたは組織会議セッションを使用している量や、ユーザーが会議セッションに参加している量を確認できます。 

詳細については、「 [レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 」を参照してください。
  
このレポートは、他のレポートとSkype for Business、組織全体のアクティビティに関する詳細を示します。 これらの詳細は、組織でその他のビジネス上の決定を調査、計画、実行しているときに役立ちます。
  
> [!NOTE]
> 管理センターで管理者Skype for Businessログオンすると、すべてのレポートをMicrosoft 365できます。 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>アクティビティ レポートにアクセスSkype for Business方法

1. [レポートの使用状況] の管理>**に**  >  **移動します**。
    
2. [使用状況 **] ページ** で、左側 **Skype for Business** レポートの選択] リストで [アクティビティの選択] を選択するか、アクティビティ ウィジェットSkype for Business  >  **クリック** します。 

  
## <a name="interpret-the-skype-for-business-activity-report"></a>アクティビティ レポートSkype for Business解釈する

[アクティビティ] グラフと [ユーザー] グラフをSkype for Business、ユーザーのアクティビティ **を****確認** できます。
  
![Skype for Businessオンライン アクティビティ レポート](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>
[Skype for Business **アクティビティ** の電子メール アクティビティ レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポート内の特定の日をクリックすると、テーブル (数値 7 を参照) には、(レポートが生成された日付ではなく) 現在の日付から最大 28 日間のデータが表示されます。

> [!NOTE]
> 特定の日の詳細をクリックすると、レポートが生成された日付までの 30 日間のデータだけがテーブルに表示されます。

***
![ナンバー 2](../images/sfbcallout2.png)<br/>
各レポートには、このレポートが生成された日付が表示されます。 レポートには、通常、アクティビティの時刻から 24 ~ 48 時間の待機時間が反映されます。 
***
![ナンバー 3](../images/sfbcallout3.png)<br/>
[アクティビティ] グラフの対話型グラフ データを使用して、使用状況の傾向を把握し、組織内で開催されている会議アクティビティの数を確認します。 組織全体の電話会議セッションのピアツーピア **セッション、開催** セッション、参加セッションの総数と種類が表示されます。 
***
![ナンバー 4](../images/sfbcallout4.png)<br/>
[ユーザー] グラフの対話型グラフ データを使用して、使用状況の傾向を把握し、組織内で開催されている会議アクティビティに参加している一意のユーザーの数を確認します。 ピアツーピア セッション、開催、および参加会議セッションの種類と共に、**ユーザーの** 総数が表示されます。
***
![ナンバー 5](../images/sfbcallout5.png)<br/>
凡例の項目をクリックして、グラフに表示する系列をフィルター処理できます。 たとえば、[アクティビティ]グラフで[ピア **ツー** ピア セッション]、[**開催**]、または [参加] をクリックまたはタップすると、それぞれに関連する情報だけが表示されます。 この選択を変更しても、グリッド テーブルの情報は変更されません。 
***
![ナンバー 6](../images/sfbcallout6.png)<br/>
各グラフには、「X」軸（水平）と「Y」軸（垂直）があります。
*    [ **アクティビティ]** グラフの Y 軸は、開催された会議セッションのピアツーピア、開催、および参加の総数です。
*    [ **ユーザー]** アクティビティ グラフの Y 軸は、ピアツーピア、開催、および会議に参加する各種類の一意のユーザーの数です。

どちらのグラフも、X 軸はこの特定のレポートで選択した日付範囲です。 
***
![番号 7](../images/sfbcallout7.png)<br/>
次の表は、ユーザーごとのすべての会議アクティビティの内訳を示しています。 これにより、ユーザーに割り当てられているSkype for Businessユーザーとその会議アクティビティが表示されます。 表には、列を追加することができます。
* **[ユーザー** 名] はユーザーの名前です。
* [ **削除済み**] はユーザーのライセンスが削除されたことを示します。<br/><br/>
  > [!NOTE]
  > 削除されたユーザーのアクティビティは、選択した期間中、ある時点でライセンスを取得した限り、レポートに表示されます。 [ **削除済み** ] 列は、アクティブではない状態になったユーザーが引き続きレポート内のデータに影響している可能性に注意するのに役立ちます。
     
* [ **削除日**] は、ユーザーのライセンスが削除された日付です。
* **最後のアクティビティの日付 (UTC)** は、ユーザーがピアツーピア セッションに参加した、または会議を開催した、または会議に参加した最新の時刻です。
* **ピアツーピアは、** ユーザーが使用したピアツーピア会議セッションの総数を示します。
* **[開催された電話** 会議] には、そのユーザーが開催した電話会議の総数が表示されます。
* **[参加した電話会議] には** 、このユーザーが参加した電話会議の総数が表示されます。
* **割り当** てられた製品はMicrosoft 365またはOffice 365に割り当てられている製品の一覧です。<br/>

組織のポリシーでユーザー情報を特定できるレポートを表示できない場合は、これらのすべてのレポートのプライバシー設定を変更できます。 管理センターの **[アクティビティ レポート] の [レポート** でユーザーの詳細を非表示 [にする] セクションを確認します](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。
***
![数値 8](../images/sfbcallout8.png)<br/>
レポートの列を **追加** または削除するには、任意の列の [列] アイコンをクリックまたはタップします。           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![数値 9](../images/sfbcallout9.png)<br/>
また、[ **エクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。           <br/> ![Skype for Business[レポートのエクスポート] ボタン。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2,000 人未満の場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行います。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Businessの使用状況レポート](device-usage-report.md)Skype for Business アプリがインストールされ、IM や会議に使用されている Windows ベースのオペレーティング システムやモバイル デバイスを含むデバイスを確認できます。
    
- [Skype for Business 電話会議開催者アクティビティ レポート](conference-organizer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サード パーティ、ダイヤルイン/アウト - Microsoft を使用した電話会議を開催しているかを確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポートの作成](peer-to-peer-activity-report.md)ユーザーが IM、音声/ビデオ、アプリケーション共有、ファイルの転送を使用している量を確認できます。
    
- [Skype for Businessブロックレポート](users-blocked-report.md)PSTN 通話がブロックされている組織内のユーザーを確認できます。
    
- [Skype for Business PSTN 使用状況レポート](pstn-usage-report.md)受信/送信呼び出しに費やされた分数と、これらの呼び出しのコストを確認できます。

- [Skype for Business PSTN 分](pstn-minute-pools-report.md)プール レポートでは、組織内の当月に消費された分数を確認できます。

- [Skype for Business詳細レポート](session-details-report.md)個々のユーザーの通話エクスペリエンスに関する詳細を確認できます。

    
## <a name="related-topics"></a>関連トピック
[管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
