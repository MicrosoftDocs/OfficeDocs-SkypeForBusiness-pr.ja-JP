---
title: Skype for Business Server 2015 のデスクトップ クライアント機能の比較
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: '概要: Skype for Business Server 2015 または Skype for Business Online 管理者は、これらのテーブルを使用して、どのクライアントでサポートされている機能を理解できます。'
ms.openlocfilehash: 6c23f924ef950f869cb2e337e59edda28715d11d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109293"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のデスクトップ クライアント機能の比較

**概要:** Skype for Business Server 2015 または Skype for Business Online 管理者は、これらのテーブルを使用して、どのクライアントでサポートされている機能を理解できます。
  
 Skype for Business を展開またはアップグレードする前に、組織で既に使用されているクライアントを確認してください。 これらのクライアントに対する機能サポートの影響を理解するには、以下の表を参照してください。 これは、ユーザーへの変更の伝達、ロールアウト プロセスのペース調整、および最新のクライアントへのアップグレードの利点の完全な理解に役立ちます。
  
Skype for Business Server 2015 で利用できる一部の機能は、Skype for Business Online では利用できません。詳細については、「Online または [Hybrid](desktop-feature-comparison.md#Online-Hybrid) ユーザー アカウントの制限」を参照してください。 Skype for Business Online 管理者は、利用可能なさまざまなプランについて、「[Skype for Business Online サービスの説明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)」を参照することをお勧めします。

Skype for Business Server 2019 のクライアント サポートについては [、「Skype for Business 2019](../../../SfBServer2019/plan/feature-comparison.md) のデスクトップ クライアント機能の比較」を参照してください。
  
次の表に、Skype for Business Server 2015 または Skype for Business Online で動作する各クライアントで使用できる機能を示します。 また、「Skype for Business for smart [phone and tablet client](mobile-feature-comparison.md) feature comparisons」の「モバイル クライアント機能の比較」も参照してください。 組織が購入するクライアント アクセス ライセンスまたはユーザー サブスクリプション ライセンスは、ユーザーが利用できる機能にも影響します。 Full クライアントまたは Basic クライアントをユーザーに展開するかどうかは、組織が購入するライセンスまたは計画によって異なります。 詳細については [、「ライセンス ガイド」](https://products.office.com/skype-for-business/it-pros) を参照してください。
  
> [!IMPORTANT]
> Skype for Business Server 2015 および Skype for Business Online では、以前にリリースされた Lync 2013、Lync 2010、Lync 2010 Mobile、Lync Phone Edition、Lync 2010 Attendant がサポートされています。 これらのクライアントを他のサーバーと一緒に使用する場合の詳細については [、「Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-desktop-client-comparison-tables) のクライアント比較テーブル」および [「Lync Server 2010](/previous-versions/office/skype-server-2010/gg425836(v=ocs.14))のクライアント比較テーブル」を参照してください。

> [!NOTE]
> **Lync 2010 Attendant** クライアントは、Skype for Business Online ではサポートされていません。

> [!NOTE]
> Skype for Business Web App ブラウザー クライアントと Skype Meetings App Windows 10 アプリは、会議のサポート [のみを提供します](desktop-feature-comparison.md#BKMK_Conferencing)。 これらのクライアント [の詳細については、「Plan for Meetings クライアント (Web App および Meetings App)」](meetings-clients.md) を参照してください。
  
## <a name="enhanced-presence-support"></a>拡張プレゼンスのサポート

<a name="BKMK_EnhancedPresence"> </a>

次の表では、ユーザーがオンライン、オフライン、ビジーなどの簡単な表示を超えた拡張プレゼンス機能について説明します。
  
|機能/機能|Skype for Business 2015 または 2016 クライアント|Mac 版 Skype for Business|Lync 2013 クライアント|Lync Windows ストア アプリ|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator for Mac 2011|Lync for Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|発行の状態 |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|状態の表示   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|状態メモおよび不在メッセージの表示 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|カスタムの場所の追加 |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|カスタム メモの追加 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|[マイ ピクチャ] のパブリック サイトの写真を使用する (Skype for Business Online では使用できません) |&#x2714;||&#x2714;|||||||

 &#x2776; 予定表の空き時間情報に基づく発行状態はサポートされていません。
  
## <a name="contacts-and-contact-groups-support"></a>連絡先と連絡先グループのサポート

<a name="BKMK_Contacts"> </a>

この表では、IM とプレゼンスの連絡先の管理に関連する機能について説明します。

|機能/機能|Skype for Business 2015 または 2016 クライアント|Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|事前入力された連絡先リスト |&#x2714;|||||||||
|連絡先リストの表示と変更 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|連絡先を状態変更通知の対象としてマークする |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|プライバシー関係の操作 |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|コーポレート アドレス帳の検索 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft Outlook の連絡先の検索 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|連絡先グループの管理 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|配布グループと Microsoft 365 グループの展開 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|応答グループの検索  <br/> (Skype for Business Online では使用できません) |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|最近の連絡先グループの表示 |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|現在の会話グループの表示 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|別の連絡先ビューの表示 (並べて表示など) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|グループ、リレーションシップ、または新規で連絡先を並べ替える (連絡先リストに追加したユーザー) |&#x2714;||&#x2714;|グループ別の並べ替え |&#x2714;|&#x2714;||||
|[状態] で連絡先を並べ替える (可用性) |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Exchange 連絡先を検索して追加する |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>IM サポート

<a name="BKMK_IMSupport"> </a>

この表では、IM サポートに関連する機能について説明します。

|機能/機能 | Skype for Business 2015 または 2016 クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|連絡先への IM の開始または電子メールの送信 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|複数の IM 会話間を移動する/1 つのタブ付きウィンドウで複数の会話を追跡する |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Outlook での IM 会話のログ記録 |&#x2714;|&#x2714;サーバー側の会話履歴が有効になっている場合  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Communicator for Mac に保存 |Lync for Mac に保存 |
|準備された会話テンプレートの使用 |||||&#x2714;|&#x2714;||||
|スペル チェック |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|スキル検索 (SharePoint Server 統合を使用)  <br/> (スキル検索には、オンプレミスの Skype for Business Server とオンプレミスの SharePoint 2013 が必要です)。 |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|常設チャット (グループ チャット) の統合  <br/> (Skype for Business Online では使用できません) |&#x2714;||&#x2714;|||||||
|常設チャット ルームを Skype for Business Meeting に 1 回のクリックでエスカレートする  <br/> (Skype for Business Online では使用できません) |&#x2714;||&#x2714;|||||||
|IM ウィンドウの送信者と受信者のインライン画像 |&#x2714;||&#x2714;|&#x2714;||||||
|インク メッセージの送信 ||||&#x2714;||||||
|インク メッセージの受信 |&#x2714;||&#x2714;|&#x2714;||||||
|IM メッセージの重要度を高く設定する |&#x2714;||&#x2714;|||||||
|ピアツーピア IM の会話でファイルを転送する |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>会議のサポート

<a name="BKMK_Conferencing"> </a>

次の表では、会議のサポートに関連する機能について説明します。
  
> [!NOTE]
> Skype for Business 会議機能は、Skype for Business Online スタンドアロン プラン 1 では使用できません。  プラン 1 は廃止 [されます](../../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement.md)。

Skype-to-Skype セッションでは、共有機能にアクセスできるユーザーが招待した場合、Skype for Business Online プラン 1 のユーザーがデスクトップ共有とアプリケーション共有に参加できます。
詳細については [、「Skype for Business Online Service Description」を参照してください](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。
  
|機能/機能 | Skype for Business 2016 クライアント | Mac 版 Skype for Business | Skype for Business の Web アプリ | Skype for Business 2015 クライアント | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|コンピューター オーディオの追加 |&#x2714;|&#x2714;|&#x2714;(プラグインが必要) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ビデオの追加 |&#x2714;|&#x2714;|&#x2714;(プラグインが必要) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|マルチパーティ ビデオの表示 (ギャラリー ビュー) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|ビデオベースの画面共有 |&#x2714;|&#x2714;|&#x2714;ビューのみ |||||||||
|会議内発表者コントロールの使用 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|詳細な会議名簿へのアクセス |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|マルチパーティ IM への参加 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|デスクトップの共有 (有効な場合) |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (プラグインが必要) |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|プログラムの共有 (有効な場合) |&#x2714;|表示のみ   |&#x2714;(プラグインが必要) |&#x2714;|&#x2714;||&#x2714;||||表示のみ |
|匿名参加者の追加 (有効な場合) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|ダイヤルイン オーディオ会議を使用する |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|会議を開始する |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Microsoft PowerPoint ファイルの追加と提示 |&#x2714;| &#x2778;注釈は使用できません |&#x2714;|&#x2714;|&#x2714;|表示のみ |&#x2714;|||| &#x2778;表示のみ、注釈は使用できません |
|Microsoft PowerPoint ファイルを移動する |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|OneNote 会議メモの追加と編集 |&#x2714;||編集のみ (追加しない) |&#x2714;|&#x2714;|||||||
|ホワイトボードの使用 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|投票の実行 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|ファイルをアップロードして他のユーザーと共有する |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|会議または電話会議の予約 |Outlook または Skype for Business Web スケジューラ |Outlook または Skype for Business Web スケジューラ |Skype for Business Web スケジューラー |Outlook または Skype for Business Web スケジューラ |Outlook または Lync Web スケジューラ |Outlook または Lync Web スケジューラ |Outlook ||||Outlook |
|Q &amp; A マネージャー |&#x2714;|||||||||||
|出席者ビデオを無効にする|&#x2714;||&#x2714;|||||||||
 | |会議 IM を無効にする  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|対象ユーザーをミュートする   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|全員を出席者にする |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Skype 会議ブロードキャストの生成  |&#x2714;|||||||||||
|代理人は委任者に代わって会議をスケジュールできます  |&#x2714;|&#x2714;|&#x2714;|||||||||
|Skype for Business と Outlook の間で代理人を同期する |&#x2714;||&#x2714;|||||||||
|ビデオ スポットライトの設定 (ビデオのロック) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|画面共有の制御を与える/取る |&#x2714;||&#x2714;|||||||||

 &#x2776;参加者は、Skype for Business on Mac、Lync for Mac 2011、またはユーザーが共有するデスクトップCommunicator for Mac 2011制御できない。 Skype for Business on Mac、Lync for Mac 2011、Communicator for Mac 2011ユーザーは Windows ユーザーが共有するデスクトップを制御できない。 これは、Max OSX の Skype for Business Web App でも機能しません。
  
 &#x2777; Skype for Business Online の場合、この機能には Microsoft PSTN 会議、Exchange ユニファイド メッセージング、またはサードパーティの電話会議プロバイダーが必要です。
  
 &#x2778; Lync for Mac 2011 クライアントは、Skype for Business Web App で会議で共有されている Microsoft Office 2013 PowerPoint プレゼンテーションを表示できません。
  
## <a name="voice-telephony-support"></a>音声 (テレフォニー) のサポート

<a name="BKMK_Telephony"> </a>

この表では、音声サービスのサポートに関連する機能について説明します。
  
> [!NOTE]
> Skype for Business Voice (テレフォニー) 機能は、特定の Skype for Business Online サブスクリプション プランに制限されています。 詳細については [、「Skype for Business Online Service Description」を参照してください](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。
  
| 機能/機能 | Skype for Business 2015 または 2016 クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|通話を開始する |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|クリックによる連絡先との通話  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|通話の転送 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|着信転送の管理 |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|チーム呼び出し設定の管理 |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|代理人の管理 |&#x2714;|&#x2714;Skype for Business Server 2015 CU4 以降が必要 |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|応答グループへの通話の開始 |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|緊急サービスのサポート (E-911)  |&#x2714;|&#x2714;Skype for Business Server 2015 CU6 以降が必要 |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|E-911 呼び出しの SIP URI への IM 通知 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|E-911 通話の配布リストへの IM 通知 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|ボイス メールへの接続、案内応答の設定または変更 |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|呼び出しの通知が表示されません |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|別の連絡先の代理としての発信 (マネージャー/代理人シナリオ) |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|代理人として構成されている場合の別のユーザーの通話の処理 |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|高頻度の通話の管理 |||||&#x2714;|&#x2714;||||
|コール パーク  |&#x2714;||&#x2714; &#x2776; |||||||
|グループ通話のピックアップ  |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|場所ベースのルーティング  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|応答グループ/チーム通話グループの管理 |&#x2714;||&#x2714;|||||||
|応答自動応答呼び出し |&#x2714;||&#x2714;|||||||

&#x2776;この機能は、Skype for Business Online では使用できません。
  
## <a name="external-users-support"></a>外部ユーザーのサポート

<a name="BKMK_ExternalUsers"> </a>

この表では、PSTN に接続されている外部ユーザーのサポートに関連する機能について説明します。

|機能/機能 | Skype for Business 2015 または 2016 クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|パブリック連絡先との IM の開始  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|フェデレーションからの連絡先との IM の開始 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|外部ユーザーとの 2 パーティまたはマルチパーティの通話の実行  <br/> (Skype for Business Online では使用できません) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>レコーディングのサポート

<a name="BKMK_Recording"> </a>

次の表では、会議の記録のサポートに関連する機能について説明します。
  
| Future/capability** | Skype for Business 2015 または 2016 クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|オーディオ、ビデオ、アプリケーション共有、デスクトップ共有、アップロードされたコンテンツのクライアント側の記録 |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|ファイル転送、共有 OneNote ページ、および PowerPoint 注釈のクライアント側の記録 |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|優先録音解像度の選択 |&#x2714;||&#x2714;|||||||

 &#x2776; Skype for Business Online スタンドアロン プランでは、レコーディングが使用できません。 記録には、Skype for Business クライアントの完全な権限が必要です。
  
 &#x2777; Skype for Business Online では、ファイル転送、共有 OneNote ページ、および PowerPoint 注釈の記録は使用できません。
  
## <a name="modern-authentication"></a>先進認証

<a name="BKMK_Recording"> </a>

次の表では、最新の認証をサポートする必要がある機能について説明します。
  
モダン認証では、モダン認証でサポートされる Skype for Business トポロジで説明されている [トポロジも必要です](../../plan-your-deployment/modern-authentication/topologies-supported.md)。

| 機能/機能 | Skype for Business 2015 または 2016 クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|先進認証 |&#x2714;|&#x2714;|&#x2714;|||||||
|多要素認証  |&#x2714;|&#x2714;|&#x2714;|||||||
|Cert -Based Authentication  |&#x2714;(ドメインに参加しているデバイスのみ)| &#x2714;|&#x2714;(ドメインに参加しているデバイスのみ)  |||||||
|Kerberos 認証 |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>アーカイブ、コンプライアンス、およびログのサポート

<a name="BKMK_Archiving"> </a>

次の表では、アーカイブ機能とログ機能のサポートに関連する機能について説明します。

| 機能/機能 | Skype for Business 2015 または 2016 クライアント | Mac 版 Skype for Business | Lync 2013 クライアント | Lync Windows ストア アプリ | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator for Mac 2011** | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook の会話履歴での IM 会話のアーカイブ |&#x2714; &#x2776; |&#x2714;サーバー側の会話履歴が有効になっている場合 |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Communicator for Mac に保存 |Lync for Mac に保存 |
|オーディオ、ビデオ、アプリケーション共有、デスクトップ共有、アップロードされたコンテンツのクライアント側アーカイブ |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|ファイル転送、共有 OneNote ページ、および PowerPoint 注釈のクライアント側アーカイブ  <br/> (Skype for Business Online では使用できません)|&#x2714;||&#x2714;||&#x2714;|||||
|タスク バーの Skype for Business アイコンからサインイン ログにアクセスする |&#x2714;||&#x2714;|||||||

 &#x2776; Skype for Business Online ユーザーの場合、この機能は Exchange Online を必要とし、ユーザーの Exchange メールボックスと Hold 属性In-Place制御されます。
  
## <a name="client-limitations"></a>クライアントの制限

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Basic クライアント制限

<a name="Full-Basic"> </a>

以下の機能はフル クライアントを使用して使用できます。Basic クライアントでは使用できません。

- チーム呼び出し設定の管理
- 代理人の管理
- 代理人として構成されている場合の別のユーザーの通話の処理
- 高頻度の通話の管理
- 応答グループへの通話の開始
- コール パーク
- 案内応答の変更
- グループ通話のピックアップ
- ユーザーの状態が UM が無効で、従来の Outlook クライアント (2013 以前) を使用している場合、呼び出し通知メールが生成されない

### <a name="online-or-hybrid-user-account-limitations"></a>オンラインまたはハイブリッド のユーザー アカウントの制限

<a name="Online-Hybrid"> </a>

ユーザー アカウントは、オンラインまたはオンプレミスのいずれかであり、そのユーザーが利用できる機能に影響を与える可能性があります。 Skype for Business Online のアカウントを持つユーザーは、フル クライアントを使用しても、次の機能にアクセスできません。
  
- 拡張プレゼンス: マイ ピクチャに任意のパブリック サイトの写真を使用する
- 連絡先: 応答グループの検索
- IM サポート: 常設チャット (グループ チャット) の統合
- IM サポート: 常設チャット ルームを Skype for Business Meeting に 1 回のクリックでエスカレートする
- 外部ユーザー: 外部ユーザーと 2 者通話またはマルチパーティ通話を実行する

## <a name="see-also"></a>関連項目

<a name="Types"> </a>

[クライアントとデバイスを計画する](clients-and-devices.md)

[Windows インストーラー (MSI) を使用しているバージョンの Skype for Business の最新の更新プログラム](../../sfb-client-updates.md)