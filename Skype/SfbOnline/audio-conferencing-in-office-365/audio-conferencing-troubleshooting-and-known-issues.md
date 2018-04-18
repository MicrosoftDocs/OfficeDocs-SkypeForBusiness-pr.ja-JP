---
title: 電話会議のトラブルシューティングと既知の問題
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'ダイヤルイン会議プロバイダー、ステータス、およびいくつかの回避策として、Microsoft を使用する場合は、既知の問題の一覧を取得します。 '
ms.openlocfilehash: 6e5c4382d49cb0a38244802da6ed97b7aea81ce8
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>電話会議のトラブルシューティングと既知の問題

 [] **この記事は、電話会議プロバイダーとして Microsoft を利用している Skype for Business ユーザーと Microsoft Teams ユーザーを対象としています。サードパーティーの電話会議プロバイダー (ACP) を利用しているお客様は対象ではありません。**
  
## <a name="troubleshooting-and-known-issues"></a>トラブルシューティングと既知の問題

Microsoft を電話会議プロバイダーとして使う電話会議には、現在追跡中で、積極的に調査が行われている問題があります。この問題は、Office 365 の今後のリリースで機能が更新されると解決される可能性があります。
  
当面この情報は、電話会議のセットアップと、組織内の Skype for Business または Microsoft Teams アプリを使用するユーザーの処理で発生する可能性のある問題をトラブルシューティングするときの参考用としてください。
  
### <a name="microsoft-teams-app"></a>Microsoft Teams アプリ

|**問題**|**動作/現象**|**既知の回避策**|**発見日**|
|:-----|:-----|:-----|:-----|
|同じ発信元電話番号の PSTN 発信者が、会議の参加者リストで同じユーザーとして表示される。  <br/> |複数の PSTN 発信者が会議に参加すると、それらの発信者番号が単一の番号としてマスキングされている場合、会議の参加者リストに単一の発信者として表示されてしまいます。  <br/> |回避策なし。  <br/> |9/25/2017  <br/> |
|会議情報パネルが断続的に表示されない。  <br/> |ユーザーが会議ブリッジの電話番号または会議 ID を調べようと試みるときに、会議情報パネルが Teams クライアントに表示されない場合があります。  <br/> |会議の詳細または Outlook の予定表を参照して、会議ブリッジの電話番号または会議 ID を確認してください。  <br/> |9/25/2017  <br/> |
|Outlook アドインからの会議の招待が、非 US ロケールに対する PSTN 調整で文字化けして表示される。  <br/> |非 US ロケールで設定されたコンピューター上の Microsoft Teams で Outlook アドインを使用してプライベート会議をスケジュールするときに、PSTN 調整で文字化けが発生することがあります。  <br/> |回避策なし。  <br/> |9/25/2017  <br/> |
|ダイヤル アウトで 5 桁以上の数字を使う必要がある。  <br/> |会議からダイヤル アウトを試みるユーザーは、短縮桁ダイヤルを E.164 に正規化するダイヤル プランの正規化ルールが利用可能である場合でも、5 桁以上の数字を入力する必要があります。  <br/> |社内の内線番号ではなく、完全な DID 番号またはローカルの電話番号の形式で入力してダイヤル アウトしてください。  <br/> |9/25/2017  <br/> |
|ダイヤル アウトのコントロールが断続的に表示されない。  <br/> |ダイヤル アウトのコントロールが会議情報パネルで表示されない場合がある。  <br/> |回避策なし。  <br/> |9/25/2017  <br/> |
|静的会議 ID が Microsoft Teams 会議でサポートされない。  <br/> |管理者は、動的な会議 ID から静的な会議 ID を既定の設定をオーバーライドする場合この設定は、マイクロソフトのチーム会議に反映されません。[組織内のオーディオ会議を使用して動的な Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)を参照してください。<br/> |回避策なし。  <br/> |9/25/2017  <br/> |
|PSTN 会議の座標がオンプレミス ユーザーのビジネスの Skype をご利用いただけません  <br/> |ユーザーが、Skype のビジネス、オンプレミス ユーザー、ビジネス オンライン、オーディオ会議、およびその他のチームは、Skype で割り当てられている場合、チームを使用してスケジュールされているすべての会議には、PSTN 会議の座標は含まれません。 <br/> |回避策なし。  <br/> |2018/2/1  <br/> |
   
### <a name="skype-for-business-app"></a>Skype for Business アプリ

|**問題**|**動作/現象**|**既知の回避策**|**発見日**|
|:-----|:-----|:-----|:-----|
|会議の開始時に入退室の通知はオンになるが、会議の開始後すぐにオフになる。  <br/> |既定では、Skype for Business アプリまたはダイヤルインのいずれかから参加者が参加する場合でも、会議の入退室の通知は無効になります。Skype for Business アプリの [ **Skype 会議のオプション**] で、このお知らせを有効にできます。すべての参加者がダイヤルインで参加する会議では、参加者は参加者リストを利用できないため、入退室通知は既定で有効になります。通話による参加者のみの会議は開始時に入退室通知がオンになりますが、Skype for Business アプリを使う参加者が参加すると、この通知はオフになります。この通知がオフの場合、Skype for Business アプリの [ **Skype 会議のオプション**] を使ってオンに戻すことができます。<br/> |回避策なし。  <br/> |8/30/2017  <br/> |
|E5 ライセンスを割り当て、最初にユーザーをプロビジョニングするときに、メールボックスが有効でないユーザーに電話会議のようこそメールが配信されないことがある。  <br/> |これが発生した場合は、Skype for Business 管理センター の [ **電話会議**] を使用するか、PowerShell を使用してユーザーの電話会議情報をいつでも再送信することができます。 [有効にするかオーディオ会議の設定を変更すると、送信メールを無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)を参照してください。  <br/> **注:**オーディオ会議の暗証番号 (pin) をユーザーに再送信するために、暗証番号 (pin) にリセットするのには。 これを行うには、Skype for Business 管理センター の [ **電話会議**] を使用するか、PowerShell を使用します。          |回避策なし。  <br/> |8/30/2017  <br/> |
|電話会議の通話が利用状況レポートに表示されるのに最大 24 時間かかる。  <br/> |将来のサービスの更新では、この点について機能強化が図られることが予定されています。  <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
|Skype for Business ユーザーが会議をロックした後で、発信者が会議ブリッジにダイヤルインしても、ユーザーがロビーで待っていることを知らせる通知がSkype for Business アプリにない。  <br/> |これは現在の設計上の仕様ですが、今後のサービス更新でこの機能のサポートに関するフィードバックを採用しています。  <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
   
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
