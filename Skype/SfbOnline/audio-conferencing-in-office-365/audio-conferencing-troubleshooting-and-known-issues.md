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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Microsoft をダイヤルイン会議プロバイダーとして使用する場合の既知の問題の一覧、状態、およびいくつかの回避策についてご確認ください。 '
ms.openlocfilehash: fba5bfff687121c7b1b64c0e51233ccb576497e2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164524"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>電話会議のトラブルシューティングと既知の問題

 **この記事は、Microsoft を電話会議プロバイダーとして使用する Skype for Business ユーザーを対象としています。サードパーティ電話会議プロバイダー (ACP) を使用しているお客様には適用されません。**
  
## <a name="troubleshooting-and-known-issues"></a>トラブルシューティングと既知の問題

Microsoft を電話会議プロバイダーとして使用する電話会議では、最新の問題が追跡され、調査が行われており、今後の Microsoft 365 のリリースで機能が更新されたときに解決される可能性があります。
  
ここでは、電話会議をセットアップし、組織の Skype for Business を使っているユーザーに対して動作する場合に発生する可能性のある問題をトラブルシューティングするときの参考にしてください。

|**問題**|**動作/現象**|**既知の回避策**|**発見日**|
|:-----|:-----|:-----|:-----|
|会議の開始時に入退室の通知はオンになるが、会議の開始後すぐにオフになる。  <br/> |既定では、Skype for Business アプリまたはダイヤルインのいずれかから参加者が参加する場合でも、会議の入退室の通知は無効になります。Skype for Business アプリの [ **Skype 会議のオプション**] で、このお知らせを有効にできます。すべての参加者がダイヤルインで参加する会議では、参加者は参加者リストを利用できないため、入退室通知は既定で有効になります。通話による参加者のみの会議は開始時に入退室通知がオンになりますが、Skype for Business アプリを使う参加者が参加すると、この通知はオフになります。この通知がオフの場合、Skype for Business アプリの [ **Skype 会議のオプション**] を使ってオンに戻すことができます。 <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
|E5 ライセンスを割り当て、最初にユーザーをプロビジョニングするときに、メールボックスが有効でないユーザーに電話会議のようこそメールが配信されないことがある。  <br/> |これが発生した場合は、Skype for Business 管理センター の [ **電話会議**] を使用するか、PowerShell を使用してユーザーの電話会議情報をいつでも再送信することができます。 「[電話会議の設定が変更されたときにメールの送信を有効または無効](enable-or-disable-sending-emails-when-their-settings-change.md)にする」をご覧ください。  <br/> **注:** 電話会議の PIN をユーザーに再送信するには、PIN をリセットする必要があります。 これを行うには、Skype for Business 管理センター の [ **電話会議**] を使用するか、PowerShell を使用します。          |回避策なし。  <br/> |8/30/2017  <br/> |
|電話会議の通話が利用状況レポートに表示されるのに最大 24 時間かかる。  <br/> |将来のサービスの更新では、この点について機能強化が図られることが予定されています。  <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
|Skype for Business ユーザーが会議をロックした後で、発信者が会議ブリッジにダイヤルインしても、ユーザーがロビーで待っていることを知らせる通知がSkype for Business アプリにない。  <br/> |これは現在の設計上の仕様ですが、今後のサービス更新でこの機能のサポートに関するフィードバックを採用しています。  <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
|2019年3月1日より前に Skype for Business Server (オンプレミス) ユーザーによって電話会議ライセンスが割り当てられた場合、会議の出席依頼にダイヤルインの座標が表示されないことがあります。  <br/> |Teams 会議の Skype for Business Server ユーザーのプロビジョニングは、その日までサポートされませんでした。 これでサポートされるようになり、[会議](https://docs.microsoft.com/microsoftteams/meetings-first)のコンポーネントになりました。 ユーザーには Teams ライセンスが必要です。  <br/> |プロビジョニングパイプラインを再アクティブ化する必要があります。 ユーザーの電話会議ライセンスを削除し、数時間待ってから、ライセンスを再割り当てします。  <br/> |2019/3/1  <br/> |
   
## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
