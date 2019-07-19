---
title: ピアツーピア アクティビティ レポート
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: d3b2d569-4ee9-44b8-92bf-d518142f0713
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
ms.custom:
- Reporting
description: 'Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. '
ms.openlocfilehash: 6564c57cee0821aa0e9204692f160b154ee5513b
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792652"
---
# <a name="peer-to-peer-activity-report"></a>ピアツーピア アクティビティ レポート

[] 新しい Office 365 の [ **レポート**] ダッシュボードには、組織内の Office 365 製品全体にわたるアクティビティの概要が表示されます。 このダッシュボードでは、個々の製品レベルのレポートまで掘り下げ、各製品内のアクティビティについてより細かい洞察を得ることができます。 たとえば、 **Skype For business ピアツーピアアクティビティ**レポートを使用して、ユーザーがどの程度 IM、音声、ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。 

[レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)を確認します。
  
このレポートと他の Skype for Business レポートを使用すると、組織全体のアクティビティについて詳しく知ることができます。 これらの詳細は、組織でその他のビジネス上の決定を調査、計画、実行しているときに役立ちます。 
  
> [!NOTE]
> Microsoft 365 管理センターに管理者としてログオンすると、すべての Skype for Business レポートを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-peer-to-peer-activity-report"></a>Skype for Business ピアツーピア アクティビティ レポートを取得する方法

1. [管理センター >**レポート** > の**利用状況]** に移動します。
    
2. [**利用状況**] ページで、左側の [**レポートの選択] ボックスの一覧**の [ **Skype for business ピアツーピアアクティビティ**] をクリックします。 または、skype for business**アクティビティ**ウィジェットをクリックし、Skype for **business アクティビティ**リストで [ **skype for business ピアツーピアアクティビティ**] をクリックします。
    
     ![Skype ピアツーピアメニューが選択されました](../images/603ec74a-7f39-4e12-8f10-00979f7ee977.PNG)
  
    > [!IMPORTANT]
    > Office 365 のサブスクリプションによっては、ここで説明する製品やアクティビティ レポートの一部が表示されないことがあります。 
  
## <a name="interpret-the-skype-for-business-peer-to-peer-activity-report"></a>Skype for Business ピアツーピア アクティビティ レポートを解析する

[ **アクティビティ**]、[ **ユーザー**]、[ **分**] のグラフを見ることで、Skype for Business ピアツーピア アクティビティの状況を確認できます。
  
![吹き出し付きの Skype ピアツーピアレポート。](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>**Skype for Business ピアツーピア アクティビティ** レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポート内の特定の日をクリックすると、テーブル (「数値7」を参照) に30日間のデータが表示されます。これは、レポートが生成された日付 (2 を参照) になります。

> [!NOTE]
> 特定の日の詳細をクリックすると、レポートが生成された日付までの30日間のデータのみが表示されます。

***
![ナンバー 2](../images/sfbcallout2.png)<br/>各レポートには、このレポートが生成された日付が表示されます。 通常、レポートには、アクティビティの時刻からの 24 ~ 48 時間の遅延時間が反映されます。 
***
![ナンバー 3](../images/sfbcallout3.png)<br/>[ **アクティビティ**] グラフの対話型グラフ データを使用して、使用状況の傾向を把握し、参加者がいた電話会議の合計数と、組織で開催された電話会議の種類を確認します。 組織全体の**IM**、**音声**、**ビデオ**、**アプリケーション共有**、**ファイル転送**セッションの合計数と種類が表示されます。 
***
![ナンバー 4](../images/sfbcallout4.png)<br/>[ **ユーザー**] グラフの対話型チャート データを使用して、使用状況の傾向を把握し、組織で開催されたピアツーピア アクティビティに参加している重複しないユーザー数を確認します。 **IM**、**音声**、**ビデオ**、**アプリケーション共有**、**ファイル転送**の種類と共に、ピアツーピアセッションでのユーザーの合計数が表示されます。
***
![ナンバー 5](../images/sfbcallout5.png)<br/>[ **分**] グラフの対話型グラフ データを使用して、使用状況の傾向を把握し、音声とビデオによるピアツーピア アクティビティを行っているユーザーが使用した分単位の時間を確認します。このグラフは、ピアツーピア セッションで使用された **音声**と **ビデオ**の分単位の合計時間を示します。
***
![ナンバー 6](../images/sfbcallout6.png)<br/>各グラフには、「X」軸（水平）と「Y」軸（垂直）があります。 
*    [ **アクティビティ**] アクティビティ グラフの Y 軸は、組織でユーザーが実施した IM、音声、ビデオ、アプリケーション共有、ファイル転送のセッションの合計数です。
*    [**ユーザー** ] アクティビティグラフの Y 軸は、IM、音声、ビデオ、アプリケーション共有、ファイル転送のセッションを保持したユーザーの合計数です。 
*    [ **分**] アクティビティ グラフの Y 軸は、組織全体でユーザーが音声とビデオのピアツーピア セッションを使って消費した分単位の合計時間です。 

どちらのグラフも、X 軸はこの特定のレポートで選択した日付範囲です。
***
![番号7](../images/sfbcallout7.png)<br/>凡例の項目をクリックして、グラフに表示する系列をフィルター処理できます。 たとえば、[**アクティビティ**] グラフで、 **IM**、**音声**、**ビデオ**、**アプリケーション共有**、**ファイル転送**をクリックまたはタップすると、それぞれに関連する情報のみが表示されます。 この選択を変更しても、グリッド テーブルの情報は変更されません。 
***
![数値8](../images/sfbcallout8.png)<br/>この表は、ユーザーごとの、ピアツーピア アクティビティのブレークダウンを示しています。また、Skype for Business が割り当てられているすべてのユーザーと、ユーザーのピアツーピア アクティビティを示しています。表には、列を追加することができます。
*    [ **ユーザー名**] はユーザーの名前です。
*    [ **削除済み**] はユーザーのライセンスが削除されたことを示します。 <br/> <br/> **注:** 削除されたユーザーのアクティビティは、選んだ期間中にライセンスが付与されている限り、レポートに表示されたままになります。 [ **削除済み** ] 列は、アクティブではない状態になったユーザーが引き続きレポート内のデータに影響している可能性に注意するのに役立ちます。  <br/><br/>
*    [ **削除日**] は、ユーザーのライセンスが削除された日付です。 
*    [ **前回のアクティビティの日付 (UTC)**] は、ユーザーが前回アクティビティを行った日付 (UTC) です。
*    [ **IM**] は、ユーザーが使用したピアツーピア セッションの合計数を示します。
*    [ **音声**] は、音声を使用したピアツーピア セッションの合計数を示します。
*    [ **ビデオ**] は、ビデオを使用したピアツーピア セッションの合計数を示します。
*    [ **アプリケーション共有**] は、ピアツーピアのアプリケーション共有セッションの合計数を示します。
*    [ **ファイル転送**] は、ピアツーピアのファイル転送セッションの合計数を示します。
*    [ **音声 (分)**] は、組織全体で使用された音声の分単位の時間の合計数を示します。 
*    [ **ビデオ (分)**] は、組織全体で使用されたビデオの分単位の時間の合計数を示します。 

組織のポリシーにより、ユーザー情報を特定できるレポートを表示できない場合は、これらすべてのレポートのプライバシー設定を変更できます。 [管理センターのアクティビティレポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)で、[**ユーザーレベルの詳細を非表示にする方法**を教えてください。] セクションを確認します。 
***
![数値9](../images/sfbcallout9.png)<br/>また、[ **エクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。           <br/> ![Skype for Business レポートの [エクスポート] ボタン。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。
***
![数値10](../images/sfbcallout10.png)<br/>![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)<br/>任意の列の**列**アイコンをクリックまたはタップして、レポートに列を追加または削除します。         
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype for Business 電話会議開催者アクティビティ レポート](conference-organizer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サード パーティ、ダイヤルイン/アウト - Microsoft を使用した電話会議を開催しているかを確認できます。
    
- [Skype For business 電話会議参加者アクティビティレポート](conference-participant-activity-report.md)参加している IM、音声/ビデオ、アプリケーション共有、Web 会議、ダイヤルイン/ダイヤルアウト会議の数を確認できます。
    
- [Skype For business ユーザーがブロック](users-blocked-report.md)されたレポートPSTN 通話の発信をブロックされている組織内のユーザーを確認できます。
    
- [Skype For BUSINESS PSTN 使用状況レポート](pstn-usage-report.md)通話の着信/発信に費やした時間 (分) を確認することができます。
    
- [Skype For BUSINESS PSTN 分単位のプールレポート](pstn-minute-pools-report.md)には、組織内の現在の月に消費された分数が表示されます。

- [Skype For business セッションの詳細レポート](session-details-report.md)個々のユーザの通話エクスペリエンスについての詳細を見ることができます。
    
## <a name="related-topics"></a>関連トピック
[管理センターでのアクティビティレポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 