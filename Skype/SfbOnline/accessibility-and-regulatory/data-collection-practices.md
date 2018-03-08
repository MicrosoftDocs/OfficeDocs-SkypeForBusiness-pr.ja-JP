---
title: "データ収集方法"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: 
description: "Microsoft は、Skype for Business の使用方法と、ユーザーが問題が発生する詳細については、調査、使用、およびエラーのデータを収集します。データは、製品の改善の計画に使用されます。"
ms.openlocfilehash: f58a5650da1b6f489c63fdb5e5870321e0f06727
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Skype for Business とチームの Microsoft のデータ収集方法

Skype for Business Server 2015、Skype for Business Online Skype for Business とチームの Microsoft アプリとは、Microsoft がこれらの製品をどのように使用されているし、どのようなサインイン エラーなどのエラーが発生したを理解するためのデータを収集します。この情報は、状況を把握の新機能は、計画のトラブルシューティングを行うし、問題を解決するへのご協力役立ちます。
  
一部の利用状況のデータが自動的に収集された、中に他のデータを収集のみ管理者またはユーザーがでも使用できるようにします。データの収集は、次の 3 つのカテゴリに分類されます。
  
- データの調査
    
- 利用状況のデータ
    
- エラー報告データ
    
## <a name="census-data"></a>データの調査

提供、サポート、Skype for Business を向上させるためにのみ調査のデータを取得します。Microsoft チームと Skype for Business Online します。これには、デバイス、オペレーティング システムのバージョン、地域と言語の設定などの環境の情報が含まれます。また、サインインが試行および障害のカウンターも含まれます。収集される調査データの具体的な例を紹介します。

|**データ型**|**{例}**|**ノート**|
|:-----|:-----|:-----|
|アプリケーション  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|例  <br/> |EN-US (英語)  <br/> ||
|ユーザー Id  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |ID が 2 回ハッシュ: クライアントに 1 回、もう一度テレメトリ サービスにします。ハッシングに、により、ID は、特定のユーザーにリンクすることはできません。  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |デバイス ID は、ランダムに生成をデバイスにあり、テレメトリ サービスに送信する GUID です。  <br/> |
   
調査データではないには、組織またはユーザーを識別する情報が含まれています。詳細については、 [Skype for Business のプライバシーに関する声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)を参照してください。
  
調査データでは、既定でし、管理者またはエンドユーザーをオフにできません。
  
## <a name="usage-data"></a>利用状況のデータ

利用状況のデータには、通話を行ったの数、送信または受信した Im の番号、会議に参加した数、頻度の機能を使用するには、安定性の問題などの情報が含まれます。
  
利用状況のデータには、contoso.com など、組織を識別する情報が含まれます。利用状況データ収集の具体的な例を紹介します。
  
|**データ型**|**{例}**|**ノート**|
|:-----|:-----|:-----|
|IM の送信  <br/> |12  <br/> ||
|受信した IM  <br/> |5  <br/> ||
|会議に参加する (試行)  <br/> |5  <br/> ||
|会議に参加する (成功)  <br/> |4  <br/> ||
|通話と会議の議事録  <br/> |30 分  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Office 365 に登録されている組織の名前は、このため、解読がクリア テキストで送信されます。  <br/> |
   
利用状況データではないには、ユーザーを識別する情報が含まれています。
  
利用状況データの収集には、既定では社内管理者を使用するとで Skype for Business Server 2015 DisableAutomaticSendTracing グループ ポリシー設定を使用してを無効にできます。この設定をオフにすると、組織内のすべてのユーザーに影響します。詳細については、 [Skype for Business Server 2015 でクライアント ブートス トラップ ポリシーを構成する](https://technet.microsoft.com/EN-US/library/gg425941.aspx)を参照してください。
  
エンドユーザーをオンまたはオフに利用状況データの収集が有効にすることはできません。
  
Skype 会議のアプリと結合の起動ツールの web ページ、テレメトリを制御する方法はこのポリシーを使用してには。
  
設定 CsWebServiceConfiguration-MeetingUxEnableTelemetry $True
  
このポリシーは既定テレメトリ コレクションが既定でオフは false になります。この設定はプールあたりであり、そのサーバーでホストされている会議に参加する Skype 会議のアプリを使って接続するすべてのユーザーを制御します。
  
## <a name="error-reporting-data"></a>エラー報告データ

エラー報告データは、パフォーマンスと信頼性、デバイスの設定、ネットワーク接続の品質、エラー コード、エラーのログ、および例外に関する情報を含めることができます。エラー報告が収集されたデータの具体的な例を紹介します。

|**データ型**|**{例}**|**ノート**|
|:-----|:-----|:-----|
|メッセージの方向  <br/> |[受信  <br/> ||
|会話の状態  <br/> |アイドル状態します。  <br/> ||
|会話のスレッド ID  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|ユーザー Id  <br/> |amosmarble <br/> |ID は、テレメトリ サービスを格納する前にハッシュ、クリア テキストで送信します。  <br/> |
   
エラー報告データは、ユーザーの IP アドレスとセッション開始プロトコル Uniform Resource Identifier (SIP URI) などの個人情報もあります。収集される機能の詳細については、 [Skype for Business のプライバシーに関する声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)を参照してください。
  
エラーの報告には、次の 2 つが必要です。
  
- サーバー上で、または (これが既定の状態) テナント管理センターで、DisableAutomaticSendTracing グループ ポリシー設定は False に設定します。詳細については、 [Skype for Business Server 2015 でクライアント ブートス トラップ ポリシーを構成する](https://technet.microsoft.com/EN-US/library/gg425941.aspx)を参照してください。
    
- エンドユーザー個別に選択で、[全般] タブ (クリックして歯車アイコン、[オプション] ダイアログが表示される [全般] タブで開きます) から Skype for Business クライアントします。
    
     ![歯車アイコン](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![ビジネス データ コレクションのチェック ボックス、オプションでの Skype > [全般] ダイアログ](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Skype 会議のアプリでは、MeetingUxEnableTelemetry も制御エラー報告、Watson 設定は Windows でクラッシュが発生した、アップロードがクラッシュする情報を制御します。デスクトップ クライアント] ダイアログ ボックスで表示するように、Skype 会議のアプリのユーザー設定はありません。
  
詳細については、 [Skype for Business の [全般設定] のオプション](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)を参照してください。
  
ネットワークのセットアップに[Skype for Business Online のネットワークのセットアップ](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)を表示できます。
  
中国の 21 vianet が運営する Office 365 を使用している場合は、 [Skype for Business Online の 21 vianet が運営するためにネットワークをセットアップする](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)を参照してください。
  
## <a name="related-topics"></a>関連トピック
[カスタマー エクスペリエンス向上プログラム](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[電話会議とプランの呼び出しの国と地域の空き時間情報](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
