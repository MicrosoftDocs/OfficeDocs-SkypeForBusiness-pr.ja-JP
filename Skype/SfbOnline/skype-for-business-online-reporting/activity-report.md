---
title: Activity report
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
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
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: fd167f9effb06bca43362fa4e9db3652ae8d15a4
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
# <a name="activity-report"></a>Activity report

[] 新しい Office 365 の [ **レポート**] ダッシュボードには、組織内の Office 365 製品全体にわたるアクティビティの概要が表示されます。 It enables you to drill in to individual product-level reports to give you more granular insight about the activities within each product. For example, you can use the **Skype for Business activity** report to see how much your users are using peer-to-peer or organized conferencing sessions, or how much they're participating in conferencing sessions. 

Check out the [Reports overview](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) to learn more.
  
This report, along with the other Skype for Business reports, gives you details on activity across your organization. これらの詳細は、組織でその他のビジネス上の決定を調査、計画、実行しているときに役立ちます。
  
> [!NOTE]
> You can see all of the Skype for Business reports when you log on as an administrator in the Office 365 admin center. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>How to get to the Skype for Business activity report

1. Go to the **Office 365 admin center** > **Reports** > **Usage**.
    
2. On the **Usage** page, click **Skype for Business activity** on the **Select a report list** on the left, or click the **Skype for Business activity** widget.
    
     ![Skype for Business DashBoard Widget.](../images/3925bc24-18fd-471e-8e93-edf5ccd3cdb7.png)
  
    > [!IMPORTANT]
    > Depending on the Office 365 subscription you have, you might not see all the products and reports shown here. 
  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpret the Skype for Business activity report

You can get a view into your user's Skype for Business activity by looking at the **Activity** and **Users** charts.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>
The **Skype for Business Activity** report can be viewed for trends over the last 7 days, 30 days, 90 days, or 180 days.

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![Number 2](../images/sfbcallout2.png)<br/>
各レポートには、このレポートが生成された日付が表示されます。 The reports usually reflect a 24- to 48-hour latency from time of activity. 
***
![Number 3](../images/sfbcallout3.png)<br/>
Use the interactive chart data on the **Activity** chart to understand usage trends and to see the number of conference activities that are being held in your organization. It will show you the total number and types of **Peer-to-peer sessions**, **Organized** and **Participated** in conference sessions across your organization. 
***
![Number 4](../images/sfbcallout4.png)<br/>
Use the interactive chart data on the **Users** chart to understand usage trends and to see the number of unique users that are participating in conference activities that are being held in your organization. It will show you the total number of users along with the types of **Peer-to-peer sessions**, **Organized**, and **Participated** in conference sessions.
***
![Number 5](../images/sfbcallout5.png)<br/>
凡例の項目をクリックして、グラフに表示する系列をフィルター処理できます。 For example, on the **Activity** chart, click or tap **Peer-to-peer sessions**, **Organized**, or **Participated** to see only the info related to each one. この選択を変更しても、グリッド テーブルの情報は変更されません。 
***
![Number 6](../images/sfbcallout6.png)<br/>
各グラフには、「X」軸（水平）と「Y」軸（垂直）があります。
*    On the **Activity** chart, the Y axis is the total number of peer-to-peer, organized, and participated in conference sessions that are held.
*    On the **Users** activity chart, the Y axis is the number of unique users attending in each type of peer-to-peer, organized, and participated in conference.

どちらのグラフも、X 軸はこの特定のレポートで選択した日付範囲です。 
***
![Number 7](../images/sfbcallout7.png)<br/>
The table shows you a breakdown of all the conferencing activities per user. This shows all users who have Skype for Business assigned to them and their conferencing activities. 表には、追加の列を追加することができます。
*    **Username** is the name of the user.
*    [ **削除済み**] はユーザーのライセンスが削除されたことを示します。 <br/> <br/> **Note:** Activity for a deleted user will still display in a report as long as he or she was licensed at some time during the selected time period. [ **削除済み** ] 列は、アクティブではない状態になったユーザーが引き続きレポート内のデータに影響している可能性に注意するのに役立ちます。<br/><br/>
*    [ **削除日**] は、ユーザーのライセンスが削除された日付です。
*    **Last activity date (UTC)** is the latest time the user engaged in a peer to peer session, or organized a conference or participated in a conference.
*    **Peer-to-peer** shows the total number of peer-to-peer conference sessions that the user used.
*    **Organized conferences** shows the total number of conferences that were organized by that user.
*    **Participated-in conferences** shows the total number of conferences that this user participated in.
*    **Product assigned** is the Office 365 products that are assigned to this user.<br/>

If your organization's policies prevent you from viewing reports where user information is identifiable, you can change the privacy setting for all these reports. Check out the **Hide user details in the reports** section in the [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Number 8](../images/sfbcallout8.png)<br/>
Click or tap the **Columns** icon in any of the columns to add or remove columns from the report.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Number 9](../images/sfbcallout9.png)<br/>
また、[ **エクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。           <br/> ![Skype for Business Reporting Export Button.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 If you have fewer than 2000 users, you can sort and filter within the table in the report itself. ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business device usage report](device-usage-report.md) You can to see the devices, including Windows-based operating systems and mobile devices, that have the Skype for Business app installed and are using it for IM and meetings.
    
- [Skype for Business 電話会議開催者アクティビティ レポート](conference-organizer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サード パーティ、ダイヤルイン/アウト - Microsoft を使用した電話会議を開催しているかを確認できます。
    
- [Skype for Business peer-to-peer activity report](peer-to-peer-activity-report.md) You can see how much your users are using IM, audio/video, application sharing, and transferring files.
    
- [Skype for Business users blocked report](users-blocked-report.md) You can see the users in your organization that have been blocked from making PSTN calls.
    
- [Skype for Business PSTN usage report](pstn-usage-report.md) You can see the number of minutes spent in inbound/outbound calls and cost for these calls.

- [Skype for Business PSTN minute pools report](pstn-minute-pools-report.md) you can see the number of minutes consumed during the current month within your organization.

- [Skype for Business session details report](session-details-report.md) You can see details about individual user's call experiences.

    
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
[Office 365 管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 