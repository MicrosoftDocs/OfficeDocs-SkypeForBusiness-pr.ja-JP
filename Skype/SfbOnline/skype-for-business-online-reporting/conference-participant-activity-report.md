---
title: 電話会議参加者アクティビティ レポート
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: c3c89995-65dd-4715-9e38-bb244c742c6b
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
- O365E_ReportsS4BPartActivity
description: 'Learn how to get the Skype for Business Conference Participant Activity report, and how to interpret and customize it. '
ms.openlocfilehash: 75e19e665cef14c2b06202368948b0ab19e2836a987552634d72e84bf6e6527a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342692"
---
# <a name="conference-participant-activity-report"></a>電話会議参加者アクティビティ レポート

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[**レポート]** ダッシュボードには、組織内の製品の使用状況Microsoft 365またはOffice 365データが表示されます。 **Skype for Business** 会議参加者アクティビティ レポートを使用して、組織内のユーザーが参加している IM、音声/ビデオ、アプリケーション共有、Web 会議、ダイヤルイン/アウト会議の数を確認できます。

詳細については、「 [レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 」を参照してください。
  
このレポートと他のレポートSkype for Business、組織全体の会議アクティビティの詳細が表示されます。 これらの詳細は、組織でその他のビジネス上の決定を調査、計画、実行しているときに役立ちます。
  
> [!NOTE]
> Microsoft 365 管理センターに管理者としてログオンすると、すべての Skype for Business レポートを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-conference-participant-report"></a>Skype for Business 電話会議参加者レポートを取得する方法

1. [レポートの使用状況] の管理>**に**  >  **移動します**。
    
2. [使用状況 **] ページで**、左側 **Skype for Business** の [レポートの選択] ボックスの一覧で [会議の参加者アクティビティ]  >  を選択します。  または、[アクティビティ] **Skype for Businessウィジェットをクリック** し、Skype for Businessリストの [会議Skype for Business **アクティビティ] をクリック** します。
    
  
## <a name="interpret-the-skype-for-business-conference-participant-activity-report"></a>Skype for Business 電話会議参加者アクティビティ レポートを解析する

![Skype参加者アクティビティ レポートを作成する](../images/a5fb6a3f-d8bc-402e-850e-87a75fbc2546.PNG)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>**Skype for Business 電話会議参加者アクティビティ** レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポート内の特定の日をクリックすると、テーブル (数値 7 を参照) に、レポートが生成された日付 (数値 2 を参照) までの 30 日間のデータが表示されます。
> [!NOTE]
> 特定の日の詳細をクリックすると、レポートが生成された日付までの 30 日間のデータだけがテーブルに表示されます。
     
***
![数値 2](../images/sfbcallout2.png)<br/>各レポートには、このレポートが生成された日付が表示されます。 レポートには、通常、アクティビティの時刻から 24 ~ 48 時間の待機時間が反映されます。 
***
![ナンバー 3](../images/sfbcallout3.png)<br/>[ **アクティビティ**] グラフの対話型グラフ データを使用して、使用状況の傾向を把握し、参加者がいた電話会議の合計数と、組織で開催された電話会議のタイプを確認します。 このチャートには、組織全体にわたる **IM**、 **音声/ビデオ**、 **アプリケーション共有**、 **Web**、 **ダイヤルイン/アウト - サード パーティ** の電話会議の合計数とタイプが表示されます。
***
![ナンバー 4](../images/sfbcallout4.png)<br/>[ **ユーザー**] グラフの対話型チャート データを使用して、使用状況の傾向を把握し、組織で開催された電話会議の一意のユーザー数を確認します。 このグラフには、合計ユーザー数と、開催された電話会議の、 **IM**、 **音声/ビデオ**、 **アプリケーション共有**、 **Web**、 **ダイヤルイン/アウト - サード パーティ** のタイプが表示されます。
***
![ナンバー 5](../images/sfbcallout5.png)<br/>[分] グラフの対話型グラフ データを使用して、使用状況の傾向を把握し、音声/ビデオを使用して会議を開催するときにユーザーが使用する分数を確認し、ダイヤルインとダイヤルアウト - Microsoft を電話会議プロバイダーとして表示します。 このグラフには、参加者がいた電話会議中に使用された **音声/ビデオ** の合計通話分数が表示されます。
***
![ナンバー 6](../images/sfbcallout6.png)<br/>凡例の項目をクリックして、グラフに表示する系列をフィルター処理できます。たとえば、[ **アクティビティ**] グラフで [ **IM]**、[ **音声/ビデオ**]、[ **アプリケーション共有**]、[ **Web**]、または [ **ダイヤルイン/アウト - サード パーティ**] をクリックまたはタップすると、それぞれに関連した情報のみが表示されます。この選択を変更しても、グリッド テーブルの情報は変更されません。 
***
![番号 7](../images/sfbcallout7.png)<br/>各グラフには、「X」軸（水平）と「Y」軸（垂直）があります。  
*    [ **アクティビティ**] アクティビティ グラフの Y 軸は、組織内のユーザーが参加した IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/ダイヤルアウト サード パーティ電話会議の合計数です。 
*    [ **ユーザー**] アクティビティ グラフの Y 軸は、組織内のユーザーが参加した IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サード パーティ電話会議の合計ユーザー数です。
*    [ **分**] アクティビティ グラフの Y 軸は、組織内のユーザーが参加した電話会議で音声/ビデオが使用された合計通話分数です。

どちらのグラフも、X 軸はこの特定のレポートで選択した日付範囲です。
***
![数値 8](../images/sfbcallout8.png)<br/>この表は、ユーザーごとの、参加した電話会議アクティビティのブレークダウンを示しています。 また、Skype for Business が割り当てられているすべてのユーザーと、ユーザーが参加した電話会議を示しています。表には、追加の列を追加することができます。
*    [ **ユーザー名**] はユーザーの名前です。 
*    [ **削除済み**] はユーザーのライセンスが削除されたことを示します。 <br/> <br/> **注:**  削除されたユーザーのアクティビティは、選択した期間中、ある時点でライセンスを取得した限り、レポートに表示されます。 [ **削除済み** ] 列は、アクティブではない状態になったユーザーが引き続きレポート内のデータに影響している可能性に注意するのに役立ちます。   <br/><br/> 
*    [ **削除日**] は、ユーザーのライセンスが削除された日付です。 
*    [ **前回のアクティビティの日付 (UTC)**] は、ユーザーが前回アクティビティを行った日付 (UTC) です。
*    [ **IM**] は、参加した IM 会議の合計数を示します。 
*    [ **音声/ビデオ**] は、参加した音声/ビデオ会議の合計数を示します。
*    [ **アプリケーション共有**] は、参加したアプリケーション共有会議の合計数を示します。
*    [ **Web**] は、参加した Web 会議の合計数を示します。 
*    [ **ダイヤルイン/アウト - サード パーティ**] は、サード パーティの電話会議プロバイダーを使用して開催されたダイヤルイン/アウト電話会議の合計数を示します。 
*    [ **音声/ビデオ通話分数**] は、音声/ビデオを使用した電話会議に参加したときに使用した合計通話分数を示します。 

組織のポリシーにより、ユーザー情報を特定できるレポートを表示できない場合は、これらすべてのレポートのプライバシー設定を変更できます。 管理センターの **アクティビティ** レポートの「ユーザー レベルの詳細を非表示にする方法」 [セクションを参照してください](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。
***
![数値 9](../images/sfbcallout9.png)<br/>また、[ **エクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。           <br/> ![Skype for Business[レポートのエクスポート] ボタン。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。
***
![数値 10](../images/sfbcallout10.png)<br/>レポートに列を追加またはレポートから列を削除するには、[ **列**] をクリックまたはタップします。           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype for Business 電話会議開催者アクティビティ レポート](conference-organizer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サード パーティ、ダイヤルイン/アウト - Microsoft を使用した電話会議を開催しているかを確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype for Business ユーザーのブロック レポート](users-blocked-report.md) - PSTN 通話の発信がブロックされている組織内のユーザーを確認できます。
    
- [Skype for Business PSTN 使用状況レポート](pstn-usage-report.md)受信/送信呼び出しに費やされた分数と、これらの呼び出しのコストを確認できます。
    
- [Skype for Business PSTN の利用分数プール レポート](pstn-minute-pools-report.md) - 組織内で今月中に消費された分数を確認できます。

- [Skype for Business セッションの詳細レポート](session-details-report.md) - 個々のユーザーの通話体験に関する詳細を確認できます。
    
## <a name="related-topics"></a>関連トピック
[管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
