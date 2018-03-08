---
title: "アクティビティ レポート"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: "ビジネス アクティビティ レポートの Skype を取得する方法、何が含まれている、データを解釈する方法を学習します。 "
ms.openlocfilehash: 21b34d8c99d03030eb5699feea54d4eb7629537c
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="activity-report"></a>アクティビティ レポート

新しい Office 365 の**レポート**のダッシュ ボードによって、組織で Office 365 製品間でのアクティビティの概要がわかります。各製品内で活動に関するより詳細な情報を提供する個別の製品レベル レポート ドリルダウンすることができます。たとえば、 **Skype for Business のアクティビティ**のレポートを使用して、ユーザーはピア ツー ピアを使用してどの程度か、会議のセッション、または会議のセッションに参加しているがどの程度別に整理します。 

詳細については、[レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)を確認します。
  
このレポートと、その他の Skype for Business のレポート、詳細を確認できますアクティビティで、組織全体でします。これらの詳細については、調査、計画、および組織の他のビジネス上の決定を行うときに非常に便利します。
  
> [!NOTE]
> すべての Skype for Business のレポートは、Office 365 管理センターで、管理者としてログオンするときに表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Skype for Business の活動レポートにアクセスする方法

1. **Office 365 管理センター**に移動 > **レポート** > **使用**します。
    
2. **使用法**] ページで、[**レポートのリストを選び**左側の [ **Skype for Business のアクティビティ**をクリックするか、 **Skype for Business のアクティビティ**ウィジェット] をクリックします。
    
     ![ダッシュ ボードのウィジェットをビジネス用 Skype します。](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > によっては、Office 365 サブスクリプションがあるすべての製品とここに示すレポートを表示することがありますされません。 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>Skype for Business の活動レポートの内容を理解します。

ユーザーの Skype for Business のアクティビティにビューを取得するには、**ユーザー**の**アクティビティ**とグラフを確認します。
  
![Skype for Business Online の活動レポート](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/>
過去 7 日、90 日間、または 180 日、30 日間に傾向の**Skype for Business のアクティビティ**のレポートを表示できます。

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![数値 2](../images/sfbcallout2.png)<br/>各レポートには、このレポートが生成されたときの日付があります。レポートは、通常のアクティビティの時刻から 24 ~ 48 時間遅延を反映します。 
***
![数値 3](../images/sfbcallout3.png)<br/>傾向を把握し、組織内で保持されている会議のアクティビティの数を表示する**アクティビティ**のグラフのインタラクティブなグラフのデータを使用します。総数および表示**構成されている**と**Participated**では、**ピア ツー ピア セッション**の種類会議セッションで、組織全体でします。 
***
![番号 4](../images/sfbcallout4.png)<br/>傾向を把握し、組織内で保持されている会議の活動に参加している固有のユーザーの数を表示する**ユーザー**のグラフのインタラクティブなグラフのデータを使用します。表示されますが**ピア ツー ピア セッション**、**構成されている**、および**Participated**の種類とユーザーの合計数で会議のセッション。
***
![5](../images/sfbcallout5.png)<br/>[凡例のアイテムをクリックして、グラフに表示するデータ系列をフィルター処理することができます。たとえば、**アクティビティ**グラフ] をクリックしてまたは 1 つずつに関連する情報のみを表示するには、**ピア ツー ピア セッション**、**構成されている**、または**Participated**をタップします。このオプションを変更すると、グリッド表内の情報は変更されません。 
***
![6](../images/sfbcallout6.png)<br/>
各グラフを X (水平) と Y (垂直) 軸があります。
*    **アクティビティ**図、Y 軸はピア ツー ピア、整理、および保持されている会議のセッションに参加して数の合計です。
*    **ユーザー**アクティビティ チャートで、Y 軸、出席ピア ツー ピアの種類ごとに固有のユーザーの数の編成、会議に参加します。

X 軸の両方のグラフは、この特定のレポートの選択した日付範囲です。 
***
![7](../images/sfbcallout7.png)<br/>テーブルでは、ユーザーごとのすべての会議活動に関する詳細を表示します。ユーザーが Skype for Business と、会議アクティビティに割り当てられているすべてのユーザーが表示されます。テーブルに列を追加できます。
*    **ユーザー名**は、ユーザーの名前です。
*    **[削除済み**ユーザーのライセンスが削除されたことを示します。 <br/> <br/> **メモ:**削除済みのユーザーのアクティビティをいてが選択されている期間中に少し時間にライセンスが付与されていればもレポートで表示されます。**削除された**列を使用すると、ユーザー不要になったありますアクティブになり、レポートのデータを投稿しましたが、ことができます。<br/><br/>
*    **[削除済みの日付**は、ユーザーのライセンスを削除するための日付です。
*    **最後のアクティビティの日付 (UTC)**は、ユーザーは、ピア ツー ピア セッションに参加またはまたは会議のメッセージを整理、会議に参加して最新時間です。
*    **ピア ツー ピア**は、ユーザーが使用されている会議のピア ツー ピア セッションの合計数を示しています。
*    **会議を整理する**には、そのユーザー別に整理された会議の合計数が表示されます。
*    **Participated で会議**には、会議に参加して現在のユーザー数の合計が表示されます。
*    このユーザーに割り当てられている Office 365 製品は、**製品が割り当てられています**。<br/>

組織のポリシーからレポートを表示するユーザーの情報が特定できるように、これらのすべてのレポートのプライバシー設定を変更します。[Office 365 管理センターでのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)で**、レポート内のユーザーの詳細を非表示にする**セクションをご覧ください。
***
![数字の 8](../images/sfbcallout8.png)<br/>
クリックするかを追加またはレポートから列を削除する列のいずれかの場合は、[**列**] をタップします。           <br/> ![Skype for Business Online のレポートの管理] ボタン。](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![番号 9](../images/sfbcallout9.png)<br/>
クリックするか、[**エクスポート**] をタップして、Excel の .csv ファイルにレポートのデータをエクスポートすることもできます。           <br/> ![Skype for Business のレポートのエクスポート] ボタン。](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> これは、すべてのユーザーのデータをエクスポートし、単純な並べ替えとフィルタ リングをさらに詳しく分析を行うことができます。少ない 2000 のユーザーを使っている場合は、並べ替えし、フィルター自体レポートのテーブル内でします。フィルターと並べ替えのために、2000 を超えるユーザーをした場合は、データをエクスポートする必要があります。 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>その他の Skype のビジネス レポートを表示したいですか。

- [Skype for Business デバイスの使用状況レポート](device-usage-report.md)などの Windows オペレーティング システム、デバイスを表示することができますおよび、モバイル デバイスで Skype for Business アプリがインストールされ、IM および会議を使用します。
    
- [Skype for Business 会議の開催者の活動レポート](conference-organizer-activity-report.md)ユーザーが IM、音声/ビデオ、アプリケーションの共有、Web、ダイヤルアウトの/-サード パーティの場合、およびで/ダイヤルアウト - Microsoft を使用する会議を整理する度合いを表示できます。
    
- [ピア ツー ピア アクティビティ レポートをビジネスの Skype](peer-to-peer-activity-report.md)ユーザーが共有、およびファイルを転送する、IM、音声/ビデオ、アプリケーションを使用してどの程度を表示できます。
    
- [Skype for Business ユーザーには、レポートがブロックされています。](users-blocked-report.md)PSTN 通話からブロックされている、組織のユーザーを表示できます。
    
- [Skype for Business PSTN の使用状況レポート](pstn-usage-report.md)分数で受信/送信の通話時間し、これらの呼び出しのコストを表示できます。

- [Skype for Business PSTN 分プール レポート](pstn-minute-pools-report.md)は、組織内の現在の月の中に使用される時間を分単位で表示できます。

- [Skype for Business セッションの詳細レポート](session-details-report.md)個々 のユーザーの通話エクスペリエンスの詳細を表示できます。

    
## <a name="related-topics"></a>関連トピック
[Office 365 管理センターでのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

