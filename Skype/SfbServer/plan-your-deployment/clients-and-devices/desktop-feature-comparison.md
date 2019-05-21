---
title: Skype for Business Server 2015 のデスクトップクライアント機能の比較
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: '概要: Skype for Business Server 2015 または Skype for Business Online の管理者は、これらの表を使用して、どの機能がどのクライアントでサポートされているかを理解することができます。'
ms.openlocfilehash: a1df39ed3a426c7e01e753222526b0f18f260f19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277378"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のデスクトップクライアント機能の比較

**概要:** Skype for Business Server 2015 または Skype for Business Online の管理者は、これらの表を使用して、どの機能がどのクライアントでサポートされているかを理解することができます。
  
 Skype for Business を展開またはアップグレードする前に、組織で既に使用されているクライアントを確認します。 以下の表を使用して、それらのクライアントに対する機能のサポートについて理解してください。 これによって、ユーザーへの変更点の伝達や、ロールアウト プロセスの調整、最新のクライアントにアップグレードするメリットの十分な理解が容易になります。
  
Skype for business Server 2015 で利用できる機能の一部は、Skype for Business Online では利用できません。詳細については、「[オンラインまたはハイブリッドのユーザーアカウントの制限](desktop-feature-comparison.md#Online-Hybrid)」を参照してください。 Skype for Business Online の管理者は、Skype for business [Online サービスの説明](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx)を参照して、利用可能なプランについてご確認ください。

Skype for business Server 2019 のクライアントサポートについては、「 [skype for business 2019 のデスクトップクライアント機能の比較」を](../../../SfBServer2019/plan/feature-comparison.md)参照してください。
  
次の表は、Skype for Business Server 2015 または Skype for Business Online と連携する各クライアントで使用できる機能を示しています。 スマートフォンおよびタブレットクライアントの機能比較については、「 [Skype For business のモバイルクライアント機能の比較](mobile-feature-comparison.md)」も参照してください。 ユーザーが使用できる機能は、組織が購入するクライアント アクセス ライセンスまたはユーザー サブスクリプション ライセンスによっても影響を受けます。 ユーザーに対して Full または Basic クライアントを展開するかどうかは、組織が購入を選択したライセンスまたはプランに応じて変わります。 詳細については、[ライセンスガイド](https://products.office.com/en-us/skype-for-business/it-pros)を参照してください。
  
> [!IMPORTANT]
> Skype for Business Server 2015 および Skype for Business Online は、以前にリリースされた Lync 2013、Lync 2010、Lync 2010 Mobile、Lync Phone Edition、Lync 2010 応答をサポートしています。 他のサーバーと共に使用した場合に、これらのクライアントについては、「 [Lync server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx)および[クライアント比較表 (lync Server 2010 の](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.14%29.aspx)クライアント比較表)」を参照してください。

> [!NOTE]
> **Lync 2010 アテンダント**クライアントは、Skype For business Online ではサポートされていません。

> [!NOTE]
> Skype for Business Web App browser クライアントと Skype 会議アプリの Windows 10 アプリでは、[会議のサポート](desktop-feature-comparison.md#BKMK_Conferencing)のみが提供されます。 これらのクライアントの詳細については、「[Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md)」を参照してください。
  
## <a name="enhanced-presence-support"></a>拡張プレゼンスのサポート

<a name="BKMK_EnhancedPresence"> </a>

次の表に、ユーザーがオンラインか、オフラインか、取り込み中かを単に示すだけではない、拡張プレゼンスの機能を示します。
  
|機能|Skype for Business 2015 または2016クライアント|Mac 版 Skype for Business|Lync 2013 クライアント|Lync Windows ストア アプリ|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator for Mac 2011|Lync for Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|状態の公開 |&#x2714;|&#x2714;&#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;&#x2776; |&#x2714;|&#x2714;|
|状態の表示   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|状態メモおよび不在メッセージの表示 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|カスタムの場所の追加 |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|カスタム メモの追加 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|自分の写真の任意のパブリックサイトの写真を使用する (Skype for Business Online では使用できません) |&#x2714;||&#x2714;|||||||

 &#x2776; 予定表の空き時間情報に基づく公開状態はサポートされません。
  
## <a name="contacts-and-contact-groups-support"></a>連絡先と連絡先グループのサポート

<a name="BKMK_Contacts"> </a>

次の表では、IM とプレゼンスの連絡先の管理に関連する機能について説明します。

|機能|Skype for Business 2015 または2016クライアント|Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|事前に入力された連絡先リスト |&#x2714;|||||||||
|連絡先リストの表示と変更 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|連絡先を状態変更通知の対象としてマークする |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|プライバシー関係の操作 |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|コーポレート アドレス帳の検索 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft Outlook の連絡先の検索 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|連絡先グループの管理 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|配布グループと Office 365 グループの拡張 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|応答グループの検索  <br/> (Skype for Business Online では使用できません) |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|最近の連絡先グループの表示 |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|現在の会話グループの表示 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|別のビューでの連絡先の表示 (タイルなど) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|連絡先をグループ、リレーションシップ、または新規 (連絡先リストに追加したユーザー) 別に並べ替える |&#x2714;||&#x2714;|グループで並べ替える |&#x2714;|&#x2714;||||
|連絡先を状態 (空き時間情報) で並べ替える |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Exchange の連絡先を検索、追加する |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>IM のサポート

<a name="BKMK_IMSupport"> </a>

次の表に、IM サポートに関する機能を示します。

|機能 | Skype for Business 2015 または2016クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|連絡先との IM の開始または連絡先への電子メール送信 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|複数の IM 会話間の移動/単一のタブ付きウィンドウでの複数の会話の管理 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Outlook での IM 会話のログ記録 |&#x2714;|& # x2714; サーバー側の会話履歴が有効になっている場合  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Communicator for Mac に保存 |Lync for Mac に保存 |
|準備された会話テンプレートの使用 |||||&#x2714;|&#x2714;||||
|スペル チェックを行う |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|スキル検索 (SharePoint Server との統合による)  <br/> (スキル検索には、オンプレミスの Skype for Business Server およびオンプレミスの SharePoint 2013 が必要です)。 |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|常設チャット (グループ チャット) の統合  <br/> (Skype for Business Online では使用できません) |&#x2714;||&#x2714;|||||||
|1回のクリックで、常設チャットルームを Skype for Business 会議にエスカレートする  <br/> (Skype for Business Online では使用できません) |&#x2714;||&#x2714;|||||||
|IM ウィンドウでの送信者と受信者のインライン画像 |&#x2714;||&#x2714;|&#x2714;||||||
|インク メッセージの送信 ||||&#x2714;||||||
|インク メッセージの受信 |&#x2714;||&#x2714;|&#x2714;||||||
|IM メッセージを「重要度 - 高」として設定 |&#x2714;||&#x2714;|||||||
|ピアツーピアの IM 会話でファイルを転送する |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>会議のサポート

<a name="BKMK_Conferencing"> </a>

次の表に、会議のサポートに関する機能を示します。
  
> [!NOTE]
> Skype for business Online スタンドアロンプラン1では、skype for Business 会議機能は使用できません。  プラン1は[廃止](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement)されます。

Skype 同士のセッションでは、Skype for Business Online Plan 1 ユーザーは、共有機能へのアクセス権を持つユーザーによって招待された場合に、デスクトップ共有とアプリケーション共有に参加できます。
詳細については、「 [Skype For Business Online サービスの説明](https://technet.microsoft.com/library/jj822172.aspx)」を参照してください。
  
|機能 | Skype for Business 2016 クライアント | Mac 版 Skype for Business | Skype for Business Web App | Skype for Business 2015 クライアント | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|コンピューター オーディオの追加 |&#x2714;|&#x2714;|& # x2714; (プラグインが必要) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ビデオの追加 |&#x2714;|&#x2714;|& # x2714; (プラグインが必要) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|マルチパーティのビデオの表示 (ギャラリー ビュー) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|ビデオベースの画面共有 |&#x2714;|&#x2714;|&#x2714;表示のみ |||||||||
|会議内発表者コントロールの使用 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|詳細な会議参加者一覧へのアクセス |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|マルチパーティ IM への参加 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|デスクトップの共有 (有効な場合) |&#x2714;|&#x2714;&#x2776; |&#x2714;&#x2776;(プラグインが必要です) |&#x2714;|&#x2714;||&#x2714;|||&#x2714;&#x2776; |&#x2714;&#x2776; |
|プログラムの共有 (有効な場合) |&#x2714;|表示のみ   |& # x2714; (プラグインが必要) |&#x2714;|&#x2714;||&#x2714;||||表示のみ |
|匿名参加者の追加 (有効な場合) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|ダイヤルイン音声会議の使用 |&#x2714;&#x2777; |&#x2714;|&#x2714;&#x2777; |&#x2714;|&#x2714;&#x2777; |&#x2714;&#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|今すぐミーティングによる会議の開始 |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Microsoft PowerPoint ファイルの追加と発表 |&#x2714;| &#x2778;注釈は使用できません |&#x2714;|&#x2714;|&#x2714;|発表のみ |&#x2714;|||| &#x2778;表示のみ、注釈は使用できません |
|Microsoft PowerPoint ファイル内の移動 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|OneNote 会議ノートの追加と編集 |&#x2714;||編集のみ (追加不可) |&#x2714;|&#x2714;|||||||
|ホワイトボードの使用 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|投票の実行 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|他のユーザーと共有するファイルをアップロードする |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|会議をスケジュールする |Outlook または Skype for Business Web Scheduler |Outlook または Skype for Business Web Scheduler |Skype for Business Web Scheduler |Outlook または Skype for Business Web Scheduler |Outlook または Lync Web Scheduler |Outlook または Lync Web Scheduler |Outlook ||||Outlook |
|Q&a&amp;マネージャー |&#x2714;|||||||||||
|出席者のビデオを無効にする|&#x2714;||&#x2714;|||||||||
 | |会議のインスタント メッセージを無効にする  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|参加者をミュートにする   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|全員を出席者にする |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Skype 会議ブロードキャストを実施する  |&#x2714;|||||||||||
|代理人が委任者のために会議を設定することができる  |&#x2714;|&#x2714;|&#x2714;|||||||||
|Skype for Business と Outlook の間で代理人を同期する |&#x2714;||&#x2714;|||||||||
|ビデオ スポットライトを設定する (ビデオのロック) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|共有画面の制御を渡す/取り戻す |&#x2714;||&#x2714;|||||||||

 &#x2776; Skype for Business For Mac、Lync for Mac 2011、または Communicator for Mac 2011 ユーザーが共有しているデスクトップを、参加者が制御することはできません。 Mac 版 Skype for Business、Lync for Mac 2011 および Communicator for Mac 2011 ユーザーは、Windows ユーザーが共有しているデスクトップを制御することはできません。 これは、OSX の Skype for Business Web App でも機能しません。
  
 &#x2777; Skype for Business Online の場合、この機能を使用するには、Microsoft PSTN 会議、Exchange ユニファイドメッセージング、またはサードパーティの電話会議プロバイダーが必要です。
  
 &#x2778; Lync for Mac 2011 クライアントは、Skype for Business Web App によって会議で共有されている場合、Microsoft Office 2013 PowerPoint プレゼンテーションを表示することはできません。
  
## <a name="voice-telephony-support"></a>音声 (テレフォニー) のサポート

<a name="BKMK_Telephony"> </a>

次の表に、音声サービスのサポートに関する機能を示します。
  
> [!NOTE]
> Skype for Business Voice (テレフォニー) 機能は、一部の Skype for Business Online のサブスクリプションプランに制限されています。 > 詳細については、「 [Skype For Business Online サービスの説明](https://technet.microsoft.com/library/jj822172.aspx)」を参照してください。
  
| 機能 | Skype for Business 2015 または2016クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|通話の開始 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|クリックによる連絡先との通話  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|通話の転送 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|着信転送の管理 |&#x2714;|&#x2714;|&#x2714;&#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|チーム呼び出し設定の管理 |&#x2714;||&#x2714;&#x2776; ||&#x2714;|&#x2714;||||
|代理人の管理 |&#x2714;|&#x2714;Skype for Business Server 2015 CU4 以降が必要です |&#x2714;&#x2776; ||&#x2714;||||&#x2714;|
|応答グループへの通話の開始 |&#x2714;||&#x2714;&#x2776; ||&#x2714;|&#x2714;||||
|緊急サービスのサポート (E-911)  |&#x2714;|&#x2714;Skype for Business Server 2015 CU6 以降が必要です |&#x2714;&#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|E-911 通話の SIP URI への IM 通知 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|E-911 通話の配布リストへの IM 通知 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|ボイス メールへの接続、あいさつの設定または変更 |&#x2714;|&#x2714;|&#x2714;&#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|不在着信通知 |&#x2714;|&#x2714;|&#x2714;&#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|別の連絡先の代理としての発信 (マネージャー/代理人シナリオ) |&#x2714;|&#x2714;|&#x2714;&#x2776; ||&#x2714;|||||
|代理人として構成されている場合の別のユーザーの通話の処理 |&#x2714;|&#x2714;|&#x2714;&#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|高頻度の通話の管理 |||||&#x2714;|&#x2714;||||
|コール パーク  |&#x2714;||&#x2714;&#x2776; |||||||
|グループ通話ピックアップ  |&#x2714;||&#x2714;&#x2776; ||||&#x2714;|||
|場所に基づくルーティング  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|応答グループ/チームの通話グループを管理する |&#x2714;||&#x2714;|||||||

 &#x2776; この機能は、Skype for Business Online では使用できません。
  
## <a name="external-users-support"></a>外部ユーザーのサポート

<a name="BKMK_ExternalUsers"> </a>

次の表に、PSTN に所属する外部ユーザーのサポートに関する機能を示します。

|機能 | Skype for Business 2015 または2016クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|パブリック連絡先との IM の開始  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|フェデレーションからの連絡先との IM の開始 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|外部ユーザーとの 2 パーティまたはマルチパーティの通話の実行  <br/> (Skype for Business Online では使用できません) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>記録のサポート

<a name="BKMK_Recording"> </a>

次の表に、会議のレコーディングのサポートに関する機能を示します。
  
| 未来/機能 * * | Skype for Business 2015 または2016クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|音声、ビデオ、アプリケーション共有、デスクトップ共有、アップロードされたコンテンツのクライアント側の記録 |&#x2714;&#x2776; ||&#x2714;&#x2776; ||&#x2714;|||||
|ファイル転送、共有 OneNote ページ、PowerPoint 注釈のクライアント側の記録 |&#x2714;&#x2777; ||&#x2714;&#x2777; ||&#x2714;|||||
|使用する記録解像度の選択 |&#x2714;||&#x2714;|||||||

 &#x2776; 一部の Skype for Business Online スタンドアロンプランでは記録できません。 レコーディングを使用するには、完全な Skype for Business クライアントの権限が必要です。
  
 &#x2777; Skype for Business Online では、ファイル転送、共有 OneNote ページ、PowerPoint の注釈の記録はできません。
  
## <a name="modern-authentication"></a>先進認証

<a name="BKMK_Recording"> </a>

次の表に、先進認証のサポートを必要とする機能を示します。
  
先進認証では、[先進認証でサポートされている Skype For business のトポロジ](../../plan-your-deployment/modern-authentication/topologies-supported.md)で説明するトポロジも必要となります。

| 機能 | Skype for Business 2015 または2016クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|先進認証 |&#x2714;|&#x2714;|&#x2714;|||||||
|複数要素の認証  |&#x2714;|&#x2714;|&#x2714;|||||||
|証明書ベースの認証  |& # x2714; (ドメインに参加しているデバイスのみ)| &#x2714;|& # x2714; (ドメインに参加しているデバイスのみ)  |||||||
|Kerberos 認証 |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>アーカイブ、コンプライアンス、ログのサポート

<a name="BKMK_Archiving"> </a>

次の表に、アーカイブ機能とログ機能のサポートに関する機能を示します。

| 機能 | Skype for Business 2015 または2016クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator for Mac 2011** | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook 会話履歴での IM 会話のアーカイブ |&#x2714;&#x2776; |& # x2714; サーバー側の会話履歴が有効になっている場合 |&#x2714;&#x2776; |&#x2714;&#x2776; |&#x2714;|&#x2714;||Communicator for Mac に保存 |Lync for Mac に保存 |
|音声、ビデオ、アプリケーション共有、デスクトップ共有、アップロードされたコンテンツのクライアント側のアーカイブ |&#x2714;&#x2776; ||&#x2714;&#x2776; ||&#x2714;|||||
|ファイル転送、共有 OneNote ページ、PowerPoint 注釈のクライアント側のアーカイブ  <br/> (Skype for Business Online では使用できません)|&#x2714;||&#x2714;||&#x2714;|||||
|タスクバーの Skype for Business アイコンからサインインする |&#x2714;||&#x2714;|||||||

 &#x2776; Skype for Business Online ユーザーの場合、この機能を使用するには Exchange Online が必要です。また、ユーザーの Exchange メールボックスのインプレースホールド属性によって制御されます。
  
## <a name="client-limitations"></a>クライアントの制限事項 

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Basic クライアントの制限事項

<a name="Full-Basic"> </a>

以下の機能は Full クライアントの場合に使用できるもので、Basic クライアントでは使用できません。

- チーム呼び出し設定の管理
- 代理人の管理
- 代理人として構成されている場合の別のユーザーの通話の処理
- 高頻度の通話の管理
- 応答グループへの通話の開始
- コール パーク
- あいさつの変更
- グループ通話ピックアップ
- 不在着信通知のメールは、ユーザーの状態が UM で無効になっていて、従来の Outlook クライアント (2013 以前) を使用している場合に生成されない

### <a name="online-or-hybrid-user-account-limitations"></a>オンラインまたはハイブリッドのユーザー アカウントの制限事項

<a name="Online-Hybrid"> </a>

ユーザー アカウントはオンラインまたはオンプレミスのいずれかとなり、そのどちらかによってユーザーが使用できる機能が変わります。 Skype for Business Online のアカウントを持つユーザーは、完全なクライアントを使用している場合でも、次の機能にアクセスできません。
  
- 拡張プレゼンス: パブリック サイトからマイ ピクチャへの写真の転用
- 連絡先: 応答グループの検索
- IM のサポート: 常設チャット (グループ チャット) の統合
- IM サポート: 常設チャットルームを1回のクリックで Skype for Business 会議にエスカレートする
- 外部ユーザー: 外部ユーザーとの 2 パーティまたはマルチパーティの通話の実行

## <a name="see-also"></a>関連項目

<a name="Types"> </a>

[クライアントおよびデバイスの計画](clients-and-devices.md)

[Windows インストーラー (MSI) を使用する Skype for Business の各バージョンに対する最新の更新プログラム](../../sfb-client-updates.md)
