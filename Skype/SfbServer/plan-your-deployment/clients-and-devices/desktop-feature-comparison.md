---
title: Skype for Business のデスクトップ クライアント機能の比較
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Summary: Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.'
ms.openlocfilehash: 0ce6457bea83c775ca5cf9373a5724f95785ddb1
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="desktop-client-feature-comparison-for-skype-for-business"></a>Skype for Business のデスクトップ クライアント機能の比較
 
**Summary:** Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.
  
 Before you deploy or upgrade to Skype for Business, check which clients are already in use in your organization. Use the tables below to understand the feature support impact on those clients. これによって、ユーザーへの変更点の伝達や、ロールアウト プロセスの調整、最新のクライアントにアップグレードするメリットの十分な理解が容易になります。
  
Some features available with Skype for Business Server 2015 are not available in Skype for Business Online, see [Online or Hybrid user account limitations](desktop-feature-comparison.md#Online-Hybrid) for specifics. Skype for Business Online Admins may want to refer to [Skype for Business Online Service Description](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) for information on the different plans available to them.
  
The following tables show the features that are available with each client that works with Skype for Business Server 2015 or Skype for Business Online. You may also want to refer to [Mobile client feature comparison for Skype for Business](mobile-feature-comparison.md) for smart phone and tablet client feature comparisons. ユーザーが使用できる機能は、組織が購入するクライアント アクセス ライセンスまたはユーザー サブスクリプション ライセンスによっても影響を受けます。 ユーザーに対して Full または Basic クライアントを展開するかどうかは、組織が購入を選択したライセンスまたはプランに応じて変わります。 See the [Licensing Guide](https://products.office.com/en-us/skype-for-business/it-pros) for more details.
  
> [!IMPORTANT]
> Skype for Business Server 2015 and Skype for Business Online support the following previously released clients: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Phone Edition, and Lync 2010 Attendant. For information about these clients when used with other servers, see the [Client comparison tables for Lync Server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) and [Client comparison tables for Lync Server 2010](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.14%29.aspx). 
  
> [!NOTE]
> The **Lync 2010 Attendant** client is not supported in Skype for Business Online.
  
> [!NOTE]
> The Skype for Business Web App browser client and Skype Meetings App Windows 10 app only provide [Meetings support](desktop-feature-comparison.md#BKMK_Conferencing). Refer to [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md) for more about these clients.
  
## <a name="enhanced-presence-support"></a>拡張プレゼンスのサポート
<a name="BKMK_EnhancedPresence"> </a>

次の表に、ユーザーの状態を単純にオンライン、オフライン、取り込み中などとして示すだけではない、拡張プレゼンスの機能を示します。 
  
|機能|Skype for Business 2015 または 2016 クライアント|Mac 用 Skype For Business|Lync 2013 client|Lync Windows ストア アプリ|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator for Mac 2011|Lync for Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|状態の公開  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|状態の表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|状態メモおよび不在メッセージの表示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|カスタムの場所の追加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|カスタムのメモの追加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|パブリック サイトからマイ ピクチャへの写真の転用  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||

 &#x2776;  Does not support publishing status based on calendar free/busy information.
  
## <a name="contacts-and-contact-groups-support"></a>連絡先および連絡先グループのサポート
<a name="BKMK_Contacts"> </a>

次の表に、IM とプレゼンスの連絡先管理に関する機能を示します。 
  

|機能|Skype for Business 2015 または 2016 クライアント|Mac 用 Skype For Business | Lync 2013 client | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|事前に入力された連絡先リスト  <br/> |&#x2714;|||||||||
|連絡先リストの表示と変更  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|連絡先を状態変更通知の対象としてマークする  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|プライバシー関係の操作  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|コーポレート アドレス帳の検索  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft Outlook の連絡先の検索  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|連絡先グループの管理  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|配布グループと Office 365 グループの拡張  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|応答グループの検索  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|最近の連絡先グループの表示  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|現在の会話グループの表示  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|別の連絡先ビューの表示 (タイルなど)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Sort contacts by Group, Relationship, or New (people who've added you to their Contacts list)  <br/> |&#x2714;||&#x2714;|グループで並べ替える  <br/> |&#x2714;|&#x2714;||||
|連絡先を状態 (空き時間情報) で並べ替える  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Exchange の連絡先を検索、追加する  <br/> |&#x2714;||&#x2714;||||||&#x2714;|
   
## <a name="im-support"></a>IM のサポート
<a name="BKMK_IMSupport"> </a>

次の表に、IM サポートに関する機能を示します。
  

|機能 | Skype for Business 2015 または 2016 クライアント | Mac 用 Skype For Business | Lync 2013 client | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|連絡先との IM の開始または連絡先への電子メール送信  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|複数の IM 会話間の移動/単一のタブ付きウィンドウでの複数の会話の管理  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Outlook での IM 会話のログ記録  <br/> |&#x2714;|&#x2714;If server side conversation history is turned on  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Communicator for Mac に保存  <br/> |Lync for Mac に保存  <br/> |
|準備された会話テンプレートの使用  <br/> |||||&#x2714;|&#x2714;||||
|スペル チェックの実行  <br/> |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Skill search (with SharePoint Server integration)  <br/> (On-premises Skype for Business Server and on-premises SharePoint 2013 are required for skill search.)  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|常設チャット (グループ チャット) の統合  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|Escalate a Persistent Chat room to a Skype for Business Meeting with one click  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|IM ウィンドウでの送信者と受信者のインライン画像  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|インク メッセージの送信  <br/> ||||&#x2714;||||||
|インク メッセージの受信  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|IM メッセージを「重要度 - 高」として設定  <br/> |&#x2714;||&#x2714;|||||||
   
## <a name="meetings-support"></a>会議のサポート
<a name="BKMK_Conferencing"> </a>

次の表に、会議のサポートに関する機能を示します。
  
> [!NOTE]
>  Skype for Business meeting features aren't available in Skype for Business Online Standalone Plan 1.

Skype 間のセッションで、Skype for Business Online プラン 1 のユーザーは、共有機能にアクセスできるユーザーから招待を受けた場合にデスクトップ共有とアプリケーション共有に参加できます。   
For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
|機能 | Skype for Business 2016 client | Mac 用 Skype For Business | Skype for Business Web App | Skype for Business 2015 client | Lync 2013 client | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|コンピューター オーディオの追加  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ビデオの追加  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|マルチパーティのビデオの表示 (ギャラリー ビュー)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|ビデオベースの画面共有  <br/> |&#x2714;|&#x2714;Only for users homed on Skype for Business Online  <br/> |&#x2714;View-only  <br/> |||||||||
|会議内発表者コントロールの使用  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|詳細な会議参加者一覧へのアクセス  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|マルチパーティ IM への参加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|デスクトップの共有 (有効な場合)  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|プログラムの共有 (有効な場合)  <br/> |&#x2714;|表示のみ  <br/> |&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;||||表示のみ  <br/> |
|匿名参加者の追加 (有効な場合)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|ダイヤルイン音声会議の使用  <br/> |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|今すぐ会議を使用した会議の開始  <br/> |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Microsoft PowerPoint ファイルの追加と発表  <br/> |&#x2714;| &#x2778; View only, annotations not available  <br/> |&#x2714;|&#x2714;|&#x2714;|発表のみ  <br/> |&#x2714;|||| &#x2778; View only, annotations not available  <br/> |
|Microsoft PowerPoint ファイル内の移動  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|OneNote 会議ノートの追加と編集  <br/> |&#x2714;||編集のみ (追加不可)  <br/> |&#x2714;|&#x2714;|||||||
|ホワイトボードの使用  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|投票の実行  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|他のユーザーと共有するファイルのアップロード  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|会議のスケジュール  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook  <br/> ||||Outlook  <br/> |
|Q&amp;A Manager  <br/> |&#x2714;|||||||||||
|出席者のビデオを無効にする  <br/> |&#x2714;||&#x2714;|||||||||
|会議のインスタント メッセージを無効にする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|参加者をミュートにする  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|全員を出席者にする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Skype 会議ブロードキャストの実施  <br/> |&#x2714;|||||||||||
|代理人が委任者のために会議を設定できる  <br/> |&#x2714;|Skype for Business Online のみ <br/>|&#x2714;|||||||||
|Skype for Business と Outlook との間での代理人の同期  <br/> |&#x2714;||&#x2714;|||||||||
|ビデオベースの画面共有  <br/> |&#x2714;| Skype for Business Online のみ <br/> |&#x2714;||&#x2714;|||||||
|ビデオ スポットライトの設定 (ビデオのロック)  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|共有画面の制御を渡す/取り戻す  <br/> |&#x2714;||&#x2714;|||||||||
   
 &#x2776;  Participants can't control desktops that are shared by Skype for Business on Mac, Lync for Mac 2011, or Communicator for Mac 2011 users. Skype for Business on Mac, Lync for Mac 2011 and Communicator for Mac 2011 users can't control desktops shared by Windows users. This also won't work for Skype for Business Web App on Max OSX.
  
 &#x2777;  For Skype for Business Online, this feature requires Microsoft PSTN Conferencing, Exchange Unified Messaging, or a 3rd party audio conferencing provider.
  
 &#x2778;  The Lync for Mac 2011 client cannot view Microsoft Office 2013 PowerPoint presentations when they have been shared in a conference by the Skype for Business Web App.
  
## <a name="voice-telephony-support"></a>音声 (テレフォニー) のサポート
<a name="BKMK_Telephony"> </a>

次の表に、音声サービスのサポートに関する機能を示します。
  
> [!NOTE]
> Skype for Business Voice (Telephony) features are limited to certain Skype for Business Online subscription plans. > For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
 | 機能 | Skype for Business 2015 または 2016 クライアント | Mac 用 Skype For Business | Lync 2013 client | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|通話の開始  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|クリック操作での連絡先との通話  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|通話の転送  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|着信転送の管理  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|チーム呼び出し設定の管理  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|代理人の管理  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU4 or later  <br/> |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|応答グループへの通話の開始  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|緊急サービスのサポート (E-911)  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU6 or later  <br/> |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|E-911 通話の SIP URI への IM 通知  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|E-911 通話の配布リストへの IM 通知  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|ボイス メールへの接続、応答メッセージの設定または変更  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|不在着信通知  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|別の連絡先の代理としての発信 (マネージャー/代理人のシナリオ)  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|代理人として構成されている場合の別のユーザーの通話の処理  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|高頻度の通話の管理  <br/> |||||&#x2714;|&#x2714;||||
|コール パーク  <br/> |&#x2714;||&#x2714; &#x2776; |||||||
|グループ通話ピックアップ  <br/> |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|場所に基づくルーティング  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|応答グループ/チームの通話グループの管理  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  This feature isn't available in Skype for Business Online.
  
## <a name="external-users-support"></a>外部ユーザーのサポート
<a name="BKMK_ExternalUsers"> </a>

次の表に、PSTN に所属する外部ユーザーのサポートに関する機能を示します。
  

|機能 | Skype for Business 2015 または 2016 クライアント | Mac 用 Skype For Business | Lync 2013 client | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|パブリック連絡先との IM の開始  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|フェデレーション連絡先との IM の開始  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|外部ユーザーとの 2 パーティまたはマルチパーティの通話の実行  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
## <a name="recording-support"></a>記録のサポート
<a name="BKMK_Recording"> </a>

次の表に、会議のレコーディングのサポートに関する機能を示します。
  
| Future/capability** | Skype for Business 2015 または 2016 クライアント | Mac 用 Skype For Business | Lync 2013 client | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|音声、ビデオ、アプリケーション共有、デスクトップ共有、アップロードされたコンテンツのクライアント側の記録  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|ファイル転送、共有 OneNote ページ、PowerPoint 注釈のクライアント側の記録  <br/> |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|優先する記録解像度の選択  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  Recording is unavailable in certain Skype for Business Online standalone plans. 記録には、完全な Skype for Business クライアントの権限が必要です。
  
 &#x2777;  Recording of file transfers, shared OneNote pages, and PowerPoint annotations is unavailable in Skype for Business Online.
  
## <a name="modern-authentication"></a>先進認証
<a name="BKMK_Recording"> </a>

次の表に、先進認証のサポートを必要とする機能を示します。 
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | 機能 | Skype for Business 2015 または 2016 クライアント | Mac 用 Skype For Business | Lync 2013 client | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|先進認証  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|多要素認証  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|証明書ベースの認証  <br/> |&#x2714;(Domain-joined device only)  <br/> |&#x2714;|&#x2714;(Domain-joined device only)  <br/> |||||||
   
## <a name="archiving-compliance-and-logging-support"></a>アーカイブ、コンプライアンス、ログのサポート
<a name="BKMK_Archiving"> </a>

次の表に、アーカイブ機能とログ機能のサポートに関する機能を示します。
  

 | 機能 | Skype for Business 2015 または 2016 クライアント | Mac 用 Skype For Business | Lync 2013 client | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator for Mac 2011** | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook 会話履歴での IM 会話のアーカイブ  <br/> |&#x2714; &#x2776; |&#x2714;If server side conversation history is turned on  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Communicator for Mac に保存  <br/> |Lync for Mac に保存  <br/> |
|音声、ビデオ、アプリケーション共有、デスクトップ共有、アップロードされたコンテンツのクライアント側のアーカイブ  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|ファイル転送、共有 OneNote ページ、PowerPoint 注釈のクライアント側のアーカイブ  <br/> (unavailable in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|||||
|Access sign-in logs from Skype for Business icon in the task bar  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  For Skype for Business Online users, this feature requires Exchange Online and is controlled by the user's Exchange mailbox In-Place Hold attribute.
  
## <a name="client-limitations"></a>クライアントの制限事項 
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Basic クライアントの制限事項
<a name="Full-Basic"> </a>

以下の機能は Full クライアントの場合に使用できるもので、Basic クライアントでは使用できません。 
  
- チーム呼び出し設定の管理
    
- 代理人の管理
    
- 別の連絡先の代理としての発信 (マネージャー/代理人シナリオ)
    
- 代理人として構成されている場合の別のユーザーの通話の処理
    
- 高頻度の通話の管理
    
- 応答グループへの通話の開始
    
- コール パーク
    
- あいさつの変更
    
- グループ通話ピックアップ
    
### <a name="online-or-hybrid-user-account-limitations"></a>オンラインまたはハイブリッドのユーザー アカウントの制限事項
<a name="Online-Hybrid"> </a>

ユーザー アカウントはオンラインまたはオンプレミスのいずれかとなり、そのどちらかによってユーザーが使用できる機能が変わります。 Users with accounts on Skype for Business Online will not have access to the following features, even with the Full client: 
  
- 拡張プレゼンス: パブリック サイトからマイ ピクチャへの写真の転用
    
- 連絡先: 応答グループの検索
    
- IM のサポート: 常設チャット (グループ チャット) の統合
    
- IM Support: Escalate a Persistent Chat room to a Skype for Business Meeting with one click
    
- 外部ユーザー: 外部ユーザーとの 2 パーティまたはマルチパーティの通話の実行
    
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="Types"> </a>

[Plan for clients and devices](clients-and-devices.md)

