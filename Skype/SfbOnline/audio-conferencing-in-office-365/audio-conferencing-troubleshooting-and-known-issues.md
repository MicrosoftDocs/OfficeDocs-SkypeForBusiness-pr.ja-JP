---
title: "会議の音声のトラブルシューティングと既知の問題"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
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
- Strat_SB_PSTN
- Audio Conferencing
description: "ダイヤルイン会議プロバイダー、状態、および一部の回避策として Microsoft を使用する場合は、既知の問題の一覧を取得します。 "
ms.openlocfilehash: 9e566d0ba9f07aeecca222ef586f301b1cd6cf5f
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>会議の音声のトラブルシューティングと既知の問題

 **この記事は、Skype for Business および Microsoft チームのユーザーが自分の電話会議プロバイダーとして Microsoft を使用しています。サードパーティ電話会議プロバイダー (ACP) を使用しているユーザーには適用されません。**
  
## <a name="troubleshooting-and-known-issues"></a>トラブルシューティングと既知の問題

Office 365 の電話会議プロバイダーが現在の問題追跡や調査実際には、機能が将来的に更新されると可能性のある解決される Microsoft を使用している電話会議を解放します。
  
ここでは、この参照として使用電話会議をセットアップすると、組織内のビジネスまたは Microsoft チームのアプリ、Skype を使用するユーザーの作業の潜在的な問題をトラブルシューティングするとき。
  
### <a name="microsoft-teams-app"></a>Microsoft チーム アプリ

|**問題**|**動作/現象**|**既知の回避策:**|**検出日付**|
|:-----|:-----|:-----|:-----|
|PSTN 発信者の「差出人」番号と同じでは、会議の参加者一覧で、同じユーザーとして表示されます。  <br/> |複数 [PSTN 発信者の会議に参加する] とその発信者番号は 1 つの数値としてマスクは、会議リスト内の 1 つの呼び出し元として表示されます。  <br/> |回避策はありません。  <br/> |9/25/2017  <br/> |
|会議情報パネル表示されていない断続的にします。  <br/> |ユーザーが会議ブリッジの電話番号や電話会議 ID 探すにしようとしたときチーム クライアントで会議情報パネルを表示しない場合があります。  <br/> |会議の詳細または会議ブリッジの電話番号や電話会議 ID を表示する Outlook の予定表を表示します。  <br/> |9/25/2017  <br/> |
|アドインの Outlook から会議の出席依頼は、PSTN 座標を米国以外のロケールで文字を表示します。  <br/> |米国以外のロケールを使用してコンピューター上にチームが Microsoft Outlook のアドインを使用して、プライベート会議をスケジュールする場合、PSTN 座標は文字を含む可能性があります。  <br/> |回避策はありません。  <br/> |9/25/2017  <br/> |
|ダイヤル 5 桁以上を使用する必要があります。  <br/> |ダイヤル プランの正規化ルールは、E.164 に短い市外の正規化を利用している場合でも、ユーザーが会議のダイヤルアウトしようとして 5 以上の数字を入力する必要があります。  <br/> |ダイヤルアウト DID 番号または内線番号のではなく、ローカルの表示形式を入力します。  <br/> |9/25/2017  <br/> |
|コントロールにダイヤルアウト表示されていない断続的にします。  <br/> |ダイヤルアウト コントロールは、会議情報パネルを表示できないことがあります。  <br/> |回避策はありません。  <br/> |9/25/2017  <br/> |
|静的会議 ID が Microsoft チーム会議でサポートされていません。  <br/> |管理者は、静的会議 ID に動的会議 ID から既定の設定を上書きする場合は、この設定は、Microsoft チーム会議の反映されません。[組織内の電話会議を使用して動的な Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)を参照してください。<br/> |回避策はありません。  <br/> |9/25/2017  <br/> |
   
### <a name="skype-for-business-app"></a>Skype for Business アプリ

|**問題**|**動作/現象**|**既知の回避策:**|**検出日付**|
|:-----|:-----|:-----|:-----|
|開始と終了通知がオンになって、会議の開始時刻がすぐにオフにしているが、会議を開始します。  <br/> |両方の Skype for Business アプリから参加者への参加やにダイヤルインしたときに、既定では、会議の開始と終了通知が無効です。Skype for Business アプリでは、 **Skype 会議のオプション**のお知らせを有効にすることができます。すべての参加者がダイヤルインし、会議に参加する会議の開始と終了通知は既定で有効にすべての出席者に参加者のリストが使用できないようです。ときに、索引項目の通話の参加者のみと会議の開始し終了通知をオンにすると for Business アプリの Skype を使用している参加者の結合、通知が表示をオフになっています。オフのときは、戻る**Skype 会議のオプション**を Skype for Business アプリを使って、通知を有効にすることができます。<br/> |回避策はありません。  <br/> |8/30/2017  <br/> |
|ユーザーに提供 E5 ライセンスが割り当てられているを 2 回目場合、いないへの配信にユーザーのメールボックスが有効になっている場合、電話会議ようこそメールで可能な場合があります。  <br/> |この場合、PowerShell を使用して、skype for Business 管理センター**電話会議**を使用して、またはユーザーの電話会議の情報を常に再送信できます。[有効にするか音声会議の設定を変更するときに、送信メールを無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)を参照してください。<br/> **メモ:**ユーザーに電話会議の PIN を再送信をするために、暗証番号 (pin) にリセットします。PowerShell を使用して、Skype for Business 管理センターで**電話会議**を使用してこのも実行することができます。          |回避策はありません。  <br/> |8/30/2017  <br/> |
|会議の音声通話には、利用状況レポートに表示されるまで 24 時間をかかることがあります。  <br/> |お楽しみにしてサービスの今後の更新プログラムでこの領域を改善します。  <br/> |回避策はありません。  <br/> |8/30/2017  <br/> |
|発信者にダイヤルイン会議ブリッジ Skype for Business ユーザーで、会議がロックされた後ときに、Skype for Business アプリを示す通知が表示されたユーザーが待機しているロビー内ではありません。  <br/> |設計上、これは、現在は、将来のサービスの更新プログラムでこの機能をサポートに関するフィードバックを使用しました。  <br/> |回避策はありません。  <br/> |8/30/2017  <br/> |
   
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)
  

