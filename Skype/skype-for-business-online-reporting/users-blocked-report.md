---
title: "Skype for Business ブロックしたユーザー レポート"
ms.author: tonysmit
author: tonysmit
ms.date: 11/24/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 0ac844b2-1b08-4e5a-addf-03cde7af7a40
description: "Learn about setting up Skype for Business Online domain federation with the domains you specify. "
---

# Skype for Business ブロックしたユーザー レポート

新しい Skype for Business **レポート** ダッシュボードには、組織内の Skype for Business 製品全体にわたるアクティビティの概要が表示されます。このダッシュボードでは、個々の製品レベルのレポートまで掘り下げ、各製品内のアクティビティについてより細かい洞察を得ることができます。たとえば、 **Skype for Business でブロックされているユーザー** レポートを使用して、PSTN 通話をブロックされている組織内のユーザーを確認できます。このレポートとその他の Skype for Business レポートでは、組織全体にわたる、PSTN 使用状況を含むアクティビティの詳細がわかります。
  
利用可能なその他のレポートについては、「[Office 365 管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)」で確認してください。
  
> [!NOTE]
> Office 365 管理センターに管理者としてログオンすると、すべての Skype for Business レポートを表示できます。 
  
## Skype for Business でブロックされているユーザーのレポートを取得する方法

- **Office 365 管理センター**、[ **管理センター**]、[ **Skype for Business 管理センター**]、[ **レポート**]、[ **ブロックされているユーザー**] の順に移動します。
    
## Skype for Business ブロックしたユーザー レポートを解析する

表示されている各列を見ると、ユーザーの **Skype for Business でブロックされているユーザー**を確認できます。
  
レポートは、このように表示されます。
  
![Block users report.](../images/3cc9009c-f24a-4bd0-b7a1-5fbb76353eaf.png)
  
|||
|:-----|:-----|
|**1** <br/> | この表は、発信をブロックされているすべてのユーザーのブレークダウンを示しています。また、電話システムか電話会議が割り当てられているすべてのユーザーを示しています。表では、列を追加したり、削除したりすることができます。 <br/>  [ **ユーザー ID**] は、ユーザーのサインインです。  <br/>  [ **電話番号**] は、ユーザーに割り当てられている番号です。  <br/>  [ **ブロック アクションの時刻**] は、ユーザーが発信をブロックされた時刻 (UTC) です。  <br/>  [ **ブロック アクション**] は、ユーザーをブロックする原因となったアクションの種類です。  <br/>  [ **ブロック アクションの理由**] は、ユーザーが発信をブロックされている理由です。  <br/> |
|**2** <br/> |1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。  <br/> |
|**3** <br/> |また、[ **Excel にエクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。  <br/> これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。  <br/> |
   
## Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](skype-for-business-activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](skype-for-business-device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype for Business 電話会議開催者アクティビティ レポート](skype-for-business-conference-organizer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サードパーティー、ダイヤルイン/アウト - Microsoft を使用した電話会議を開催しているかを確認できます。
    
- [Skype for Business 電話会議参加者アクティビティ レポート](skype-for-business-conference-participant-activity-report.md) - 参加者がいる IM、音声/ビデオ、アプリケーション共有、Web 会議、ダイヤルイン/ダイヤルアウト会議の数を確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポート](skype-for-business-peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype for Business PSTN 使用状況レポート](skype-for-business-pstn-usage-report.md) - 通話の着信/発信に費やした通話分数と、それらの通話の料金を確認できます。
    
- [Skype for Business ブロックしたユーザー レポート](skype-for-business-users-blocked-report.md) - 使用されているメディアの種類、セッションの期間、使用されたクライアント、電話会議 のURL などの詳細を確認できます。
    
## 関連項目

#### 

[Office 365 管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

