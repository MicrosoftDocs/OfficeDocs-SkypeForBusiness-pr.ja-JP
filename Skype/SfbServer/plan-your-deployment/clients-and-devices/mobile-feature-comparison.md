---
title: Skype for Business のモバイル クライアント機能の比較
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Summary: Review the feature support for the mobile client while planning for Skype for Business Server 2015.'
ms.openlocfilehash: 4287c5baf0642fab9d55d291470b2352f3da5932
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Skype for Business のモバイル クライアント機能の比較
 
**Summary:** Review the feature support for the mobile client while planning for Skype for Business Server 2015.
  
This article compares the features and capabilities among Skype for Business mobile clients and the Skype for Business desktop client in the following categories:
  
- サインイン、プッシュ通知、および一般的な機能
    
- 拡張プレゼンス
    
- 連絡先と連絡先グループ
    
- インスタント メッセージング (IM)
    
- Skype for Business to Skype for Business audio and video
    
- 会議
    
- テレフォニー
    
- 外部ユーザー
    
- アーカイブとコンプライアンス
    
-  先進認証
    
The following tables list the features that are available to Skype for Business users in an on-premises deployment of Skype for Business Server 2015. The same features are also available to Skype for Business Online and Microsoft Office 365 users, unless otherwise indicated in the table footnotes.
  
> [!NOTE]
> For online help and resources for end users, see [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> To compare the features available in other Skype for Business clients, see [Desktop client feature comparison for Skype for Business](desktop-feature-comparison.md). 
  
## <a name="sign-in-push-notifications-and-general-features"></a>サインイン、プッシュ通知、および一般的な機能

 
 | 機能  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business session remains signed in  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|プッシュ通知のサポート  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714;|&#x2714;|
|複数ユーザーのアカウント情報を同一デバイスにキャッシュ可能  <br/> |&#x2714;||||
|スクリーン リーダー/読み上げ機能  <br/> |&#x2714;|&#x2714; &#x2777;           English only  <br/> |&#x2714;|&#x2714;|
|アクセシビリティとしての外部キーボードの使用  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Microsoft カスタマー エクスペリエンス向上プログラムのサポート  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  On Windows Phone, Skype for Business signs out automatically after a period of inactivity, as follows:
  
- If the user has enabled push notifications, Skype for Business signs out after 10 days of inactivity.
    
- If the user has not enabled push notifications, Skype for Business signs out as soon as the user leaves the app.
    
On iOS devices, Skype for Business signs out automatically after the mobile client has not contacted the server for 10 days due to loss of network connectivity or other issues.
  
 &#x2777;  In app only.
  
 &#x2778;  Notifications are available when the app is running in the background.
  
## <a name="enhanced-presence-support"></a>拡張プレゼンスのサポート 


 | 機能  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|状態の公開および表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|予定表の空き時間情報に基づく状態の表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|状態メモおよび不在メッセージの表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|カスタムの場所の追加  <br/> |&#x2714;||||
|カスタムのメモの追加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|カレンダーの空き時間情報に基づく状態の公開   <br/> |&#x2714; &#x2776; ||||
|プレゼンス状態 (取り込み中、応答不可など) の手動設定  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  Skype for Business mobile clients do not update a user's presence based on the user's free/busy calendar information. If a mobile client user is also signed in to the Skype for Business desktop client, the desktop client updates the user's presence based on the user's free/busy calendar information. If the user is signed in to a mobile client only, the user's presence does not update based on free/busy calendar information.
  
## <a name="contacts-and-contact-groups-support"></a>連絡先と連絡先グループのサポート 


 | 機能  | Skype for Business Lync 2013 desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|連絡先リストの表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|連絡先グループの表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|よくやり取りする連絡先グループの表示  <br/> |&#x2714;||||
|連絡先リストの変更  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|連絡先を状態変更通知の対象としてマークする  <br/> |&#x2714;||||
|プライバシー関係の操作  <br/> |&#x2714;||||
|コーポレート アドレス帳の検索  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|連絡先リストの検索  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|連絡先グループの管理  <br/> |&#x2714;|||&#x2714;|
|配布グループの展開  <br/> |&#x2714;|&#x2714;||&#x2714;|
|応答グループの検索  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|連絡先の写真の表示/非表示  <br/> |&#x2714;|&#x2714;|||
|ホーム画面への連絡先のピン留め  <br/> ||&#x2714;|||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="instant-messaging-support"></a>インスタント メッセージングのサポート 


 | 機能  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|連絡先とのインスタント メッセージ (IM) の開始  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|マルチパーティ IM への参加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|[会話] ウィンドウからの別のユーザーの招待  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|現在の会話の表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|複数の IM 会話間での移動  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exchange での IM 会話の自動ログ  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|IM 会話の電子メールでの送信  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|連絡先への電子メールの開始  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|不在着信の IM 招待状の表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|受信 IM による振動  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776;  This device vibrates every time an IM is received even if the current message in the IM conversation is displayed
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business to Skype for Business audio and video


 | 機能  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-to-Skype for Business voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business-to-Skype for Business video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> 既定で、モバイル デバイスのビデオには WiFi 接続が必要です。 
  
## <a name="conferencing-support"></a>会議のサポート


 | 機能  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|ミーティング メッセージのリンクをクリックしてビデオまたは VoIP 会議に参加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|マルチパーティ IM への参加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ダイヤルアウト電話会議の使用 (サーバーがモバイル デバイスを呼び出す)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|ダイヤルイン音声会議の使用  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|会議ビデオの表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|マルチパーティのビデオの表示 (ギャラリー ビュー)  <br/> |&#x2714;||||
|会議ロビーでの待機  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|会議内発表者コントロールの使用  <br/> |&#x2714;||||
|電話会議の詳細な会議名簿へのアクセス  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|IM 会議の詳細な会議名簿へのアクセス  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|デスクトップまたはプログラムの共有  <br/> |&#x2714;||||
|共有デスクトップまたはプログラムの表示 (VbSS または RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|共有 PowerPoint ファイルの表示  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|PowerPoint ファイルのアップロードと発表  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|会議ツールの使用 (ホワイトボードの使用、投票の実行、ファイルの共有)  <br/> |&#x2714;||||
|会議リストの移動  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Join a meeting even if you don't have a Skype for Business account  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|会議の参加者に関する詳細情報の表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|クライアントまたはデバイスからの直接的な、複数の参加者とのスケジュールされていないグループ会話の開始   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  For Office 365 users, this feature requires Enterprise Voice, which is part of the E5 license.
  
 &#x2777;  Requires a WiFi connection by default.
  
## <a name="telephony-support"></a>テレフォニーのサポート


 | 機能  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|In Skype for Business, tap the call icon to call a contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|通話の転送  <br/> |&#x2714;|&#x2714;|&#x2714;||
|取次転送  <br/> |&#x2714; &#x2778; ||||
|着信転送の管理  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|チーム呼び出し設定の管理  <br/> |&#x2714; &#x2776; ||||
|代理人の管理  <br/> |&#x2714; &#x2776; ||||
|応答グループへの通話の開始  <br/> |&#x2714; &#x2776; ||||
|緊急サービスのサポート  <br/> |&#x2714; &#x2777; ||||
|別の連絡先の代理としての発信 (マネージャー/代理人のシナリオ)  <br/> |&#x2714; &#x2776; ||||
|Handle another contact's calls, if configured as a delegate  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|「勤務先から通話」の使用  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|ボイス メールへのアクセス  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Use the keypad in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776;  Available to Skype for Business Online and/or Office 365 E5 users, and users homed on Skype for Business Server 2015 or Lync 2013 with Enterprise Voice enabled.
  
 &#x2777;  For Skype for Business Online and/or Office 365 users, this feature is supported by Microsoft partners.
  
 &#x2778;  Windows Desktop client only.
  
## <a name="external-user-support"></a>外部ユーザーのサポート 


 | 機能  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|パブリック連絡先との IM の開始  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|フェデレーション連絡先との IM の開始  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|外部ユーザーとの 2 パーティの通話の実行  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|外部ユーザーとのマルチパーティの通話の実行  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use Call via Work to reach a federated contact on their mobile phone by calling their published work number  &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  By default, federated users are assigned the External Contacts privacy relationship. 公開された勤務先番号に電話をかけて、相手の携帯電話にあるフェデレーションからの連絡先にアクセスできるようにするには、フェデレーションからの連絡先側から手動で仕事仲間のプライバシー関係を割り当ててもらっている必要があります。
  
## <a name="address-book-integration"></a>アドレス帳の統合


 | 機能  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|デバイス アドレス帳の連絡先の呼び出し  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Make Skype for Business calls to contacts directly from device address book  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>アーカイブとコンプライアンスのサポート


 | 機能  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|クライアント側のアーカイブの提供  <br/> |&#x2714;||||
|クライアント側の記録の提供  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="modern-authentication"></a>先進認証

次の表に、先進認証のサポートを必要とする機能を示します。
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | 機能  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|先進認証  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|多要素認証  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|証明書ベースの認証  <br/> |&#x2714;(Domain-joined device only)  <br/> ||&#x2714;|&#x2714;|
|Mobile Application Management (via Intune)  <br/> |||&#x2714;|&#x2714;|
   

