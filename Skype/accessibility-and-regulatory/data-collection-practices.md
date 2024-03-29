---
title: "Skype for Business と Microsoft Teams のデータ収集方法"
ms.author: tonysmit
author: tonysmit
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
description: "Microsoft collects census, usage, and error data to understand how Skype for Business is being used and where users encounter problems. The data is used to plan product improvements."
---

# Skype for Business と Microsoft Teams のデータ収集方法

Skype for Business Server 2015、Skype for Business Online、Skype for Business クライアントは、これらの製品の使用方法と、サインイン エラーなどの発生したエラーの種類を Microsoft が理解するために役立つデータを収集します。Microsoft は、使用パターンの理解、将来の機能の計画、問題の領域のトラブルシューティングと修正のためにこれらの情報を活用できます。
  
一部の使用データは自動的に収集されますが、管理者またはユーザーによって許可された場合にのみ収集できるデータもあります。収集されるデータは、次の 3 つのカテゴリに分類されます。
  
- 全数調査データ
    
- 使用状況データ
    
- エラー報告データ
    
## 全数調査データ

全数調査データは、Skype for Business と Skype for Business Online の提供、サポート、改善のみを目的として取得されます。これには、デバイスとオペレーティング システムのバージョン、地域と言語の設定などの環境情報が含まれます。サインイン試行と失敗のカウンターも含まれます。次に、収集される全数調査データの具体例をいくつか示します。
  
|
|
|****データ型****|****例****|****メモ****|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |ID は、2 回ハッシュされます (クライアントで 1 回、利用統計情報サービスでもう一回)。ハッシュによって、ID を特定のユーザーに結び付けることができなくなります。  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |デバイス ID は、デバイス上でランダムに生成される GUID であり、利用統計情報サービスに送信されます。  <br/> |
   
全数調査データには、組織またはユーザーを特定できる情報は含まれていません。詳細については、「[Skype for Business のプライバシーに関する声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)」をご覧ください。
  
全数調査データは、既定でオンになり、管理者やエンド ユーザーがオフにすることはできません。
  
## 使用状況データ

使用状況データには、発信した通話の回数、送受信した IM の数、参加した会議の数、機能を使用した頻度、安定性の問題などの情報が含まれます。
  
使用状況データには、contoso.com などの組織を特定できる情報が含まれる場合もあります。次に、収集される使用状況データの具体例をいくつか示します。
  
|
|
|****データ型****|****例****|****メモ****|
|:-----|:-----|:-----|
|IM Sent (送信済み IM)  <br/> |12  <br/> ||
|IM Received (受信済み IM)  <br/> |5  <br/> ||
|Join a meeting (attempts) (会議への参加 (試行))  <br/> |5  <br/> ||
|Join a meeting (success) (会議への参加 (成功))  <br/> |4  <br/> ||
|Call/meeting minutes (通話/会議の時間)  <br/> |30 mins (30 分)  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |これは、Office 365 に登録されている組織の名前で、テキスト形式で送信されるため暗号化されません。  <br/> |
   
使用状況データには、ユーザーを特定できる情報は含まれていません。
  
使用状況データの収集は、既定でオンになりますが、オンプレミスの管理者が、Skype for Business Server 2015 の DisableAutomaticSendTracing グループ ポリシー設定を使用してオフにすることができます。この設定をオフにすると、組織のすべてのユーザーが影響を受けます。「[Skype for Business Server 2015 でのクライアント ブートストラップ ポリシーの構成](https://technet.microsoft.com/EN-US/library/gg425941.aspx)」を参照してください。
  
エンド ユーザーは使用状況データの収集のオンとオフを切り替えることはできません。
  
Skype 会議アプリと Join Launcher Web ページでは、利用統計情報は次のポリシーによって制御されます。
  
Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
  
このポリシーの既定値は False であるため、利用統計情報は既定では収集されません。この設定はプールごとに行われ、Skype 会議アプリを使用してそのサーバーでホストされる会議に接続するすべてのユーザーを制御します。
  
## エラー報告データ

エラー報告データには、パフォーマンスと信頼性、デバイスの構成、ネットワーク接続の品質、エラー コード、エラー ログ、例外などの情報が含まれることがあります。次に、収集されるエラー報告データの具体例をいくつか示します。
  
|
|
|****データ型****|****例****||
|:-----|:-----|:-----|
|Message direction (メッセージの方向)  <br/> |Incoming (受信)  <br/> ||
|Conversation state (会話の状態)  <br/> |Idle (アイドル)  <br/> ||
|Conversation thread ID (会話スレッド ID)  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> ||この ID はテキスト形式で送信され、利用統計情報サービスでハッシュされてから保存されます。  <br/> |
   
エラー報告データには、ユーザーの IP アドレスや SIP URI (Session Initiation Protocol Uniform Resource Identifier) などの個人を特定できる情報が含まれる場合もあります。収集されるデータの詳細な説明については、「[Skype for Business のプライバシーに関する声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)」を参照してください。
  
エラー報告には次の 2 つが必要です。
  
- サーバーまたはテナント管理センターで DisableAutomaticSendTracing グループ ポリシー設定を False に設定する必要があります (これが既定の状態です)。詳細については、「[Skype for Business Server 2015 でのクライアント ブートストラップ ポリシーの構成](https://technet.microsoft.com/EN-US/library/gg425941.aspx)」を参照してください。
    
- エンド ユーザーが Skype for Business クライアントの [全般] タブで個別に選択します (歯車アイコンをクリックすると、[オプション] ダイアログ ボックスに [全般] タブが表示されます)。
    
     ![歯車アイコン](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype for Business data collection checkbox in the Options > General dialog](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Skype 会議アプリでは、MeetingUxEnableTelemetry によってエラー報告も制御されます。ただし、Windows のクラッシュに関しては Watson 設定によってクラッシュ情報のアップロードが制御されます。Skype 会議アプリには、デスクトップ クライアントのダイアログ ボックスのようにユーザー設定はありません。
  
詳細については、「[Skype for Business の全般オプションを設定する](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)」を参照してください。
  
「[Skype for Business Online 向けにネットワークをセットアップする](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)」を参照してネットワークをセットアップできます。
  
中国の 21Vianet によって運営されている Office 365 を使用している場合は、「[Set up your network for Lync Online](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)」を参照してください。
  
## 関連トピック

[カスタマー エクスペリエンス向上プログラム](https://www.microsoft.com/products/ceip/en-US/default.mspx)
  
[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  

