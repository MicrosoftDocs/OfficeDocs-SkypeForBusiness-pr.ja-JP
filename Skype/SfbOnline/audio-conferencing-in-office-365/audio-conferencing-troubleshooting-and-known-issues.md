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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ダイヤルイン会議プロバイダー、ステータス、およびいくつかの回避策として、Microsoft を使用する場合は、既知の問題の一覧を取得します。 '
ms.openlocfilehash: 997cc5007df35b307cb714b891bc60764bd4a645
ms.sourcegitcommit: d21e7ef1d4e36f4aced606e11837c693e8fd6410
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "23999176"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>電話会議のトラブルシューティングと既知の問題

 **この資料が、Skype のビジネス ユーザーが Microsoft を使用して、オーディオ会議プロバイダーとしてです。それは、サード ・ パーティ製の音声会議プロバイダー (ACP) を使用しているユーザーには適用されません。**
  
## <a name="troubleshooting-and-known-issues"></a>トラブルシューティングと既知の問題

Microsoft を電話会議プロバイダーとして使う電話会議には、現在追跡中で、積極的に調査が行われている問題があります。この問題は、Office 365 の今後のリリースで機能が更新されると解決される可能性があります。
  
ここでは、これを参照として使用オーディオ会議の設定を取得して、組織内のビジネスの Skype を使用するユーザーの作業に潜在的な問題をトラブルシューティングする場合。

|**問題**|**動作/現象**|**既知の回避策**|**発見日**|
|:-----|:-----|:-----|:-----|
|会議の開始時に入退室の通知はオンになるが、会議の開始後すぐにオフになる。  <br/> |既定では、Skype for Business アプリまたはダイヤルインのいずれかから参加者が参加する場合でも、会議の入退室の通知は無効になります。Skype for Business アプリの [ **Skype 会議のオプション**] で、このお知らせを有効にできます。すべての参加者がダイヤルインで参加する会議では、参加者は参加者リストを利用できないため、入退室通知は既定で有効になります。通話による参加者のみの会議は開始時に入退室通知がオンになりますが、Skype for Business アプリを使う参加者が参加すると、この通知はオフになります。この通知がオフの場合、Skype for Business アプリの [ **Skype 会議のオプション**] を使ってオンに戻すことができます。 <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
|E5 ライセンスを割り当て、最初にユーザーをプロビジョニングするときに、メールボックスが有効でないユーザーに電話会議のようこそメールが配信されないことがある。  <br/> |これが発生した場合は、Skype for Business 管理センター の [ **電話会議**] を使用するか、PowerShell を使用してユーザーの電話会議情報をいつでも再送信することができます。 [有効にするかオーディオ会議の設定を変更すると、送信メールを無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)を参照してください。  <br/> **注:** オーディオ会議の暗証番号 (pin) をユーザーに再送信するために、暗証番号 (pin) にリセットするのには。 これを行うには、Skype for Business 管理センター の [ **電話会議**] を使用するか、PowerShell を使用します。          |回避策なし。  <br/> |8/30/2017  <br/> |
|電話会議の通話が利用状況レポートに表示されるのに最大 24 時間かかる。  <br/> |将来のサービスの更新では、この点について機能強化が図られることが予定されています。  <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
|Skype for Business ユーザーが会議をロックした後で、発信者が会議ブリッジにダイヤルインしても、ユーザーがロビーで待っていることを知らせる通知がSkype for Business アプリにない。  <br/> |これは現在の設計上の仕様ですが、今後のサービス更新でこの機能のサポートに関するフィードバックを採用しています。  <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
   
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
