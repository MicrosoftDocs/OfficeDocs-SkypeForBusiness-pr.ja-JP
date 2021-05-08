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
description: 'ダイヤルイン会議プロバイダー、状態、およびいくつかの回避策として Microsoft を使用する場合の既知の問題の一覧を取得します。 '
ms.openlocfilehash: 71d363ff98fc4590fb6d96cc3e8a8cb77b1fa24c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237193"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>電話会議のトラブルシューティングと既知の問題

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 **この記事は、電話Skype for Business Microsoft を使用しているユーザーを特定する方法について説明します。サード パーティの電話会議プロバイダー (ACP) を使用しているお客様には適用されません。**
  
## <a name="troubleshooting-and-known-issues"></a>トラブルシューティングと既知の問題

Microsoft を電話会議プロバイダーとして使用する電話会議には、現在の問題が追跡され、積極的に調査中であり、Microsoft 365 の将来のリリースで機能が更新された場合に解決される可能性があります。
  
ここでは、電話会議をセットアップし、組織内の Skype for Business を使用しているユーザーのために作業する際の潜在的な問題のトラブルシューティングを行う場合は、参照として使用してください。

|**問題**|**動作/現象**|**既知の回避策**|**発見日**|
|:-----|:-----|:-----|:-----|
|会議の開始時に入退室の通知はオンになるが、会議の開始後すぐにオフになる。  <br/> |既定では、Skype for Business アプリまたはダイヤルインのいずれかから参加者が参加する場合でも、会議の入退室の通知は無効になります。Skype for Business アプリの [ **Skype 会議のオプション**] で、このお知らせを有効にできます。すべての参加者がダイヤルインで参加する会議では、参加者は参加者リストを利用できないため、入退室通知は既定で有効になります。通話による参加者のみの会議は開始時に入退室通知がオンになりますが、Skype for Business アプリを使う参加者が参加すると、この通知はオフになります。この通知がオフの場合、Skype for Business アプリの [ **Skype 会議のオプション**] を使ってオンに戻すことができます。 <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
|E5 ライセンスを割り当て、最初にユーザーをプロビジョニングするときに、メールボックスが有効でないユーザーに電話会議のようこそメールが配信されないことがある。  <br/> |これが発生した場合は、Skype for Business 管理センター の [ **電話会議**] を使用するか、PowerShell を使用してユーザーの電話会議情報をいつでも再送信することができます。 「 [電話会議の設定が変更された場合にメールの送信を有効または無効にする」を参照してください](enable-or-disable-sending-emails-when-their-settings-change.md)。  <br/> **注:** ユーザーに電話会議 PIN を再送信するには、PIN をリセットする必要があります。 これを行うには、Skype for Business 管理センター の [ **電話会議**] を使用するか、PowerShell を使用します。          |回避策なし。  <br/> |8/30/2017  <br/> |
|電話会議の通話が利用状況レポートに表示されるのに最大 24 時間かかる。  <br/> |将来のサービスの更新では、この点について機能強化が図られることが予定されています。  <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
|Skype for Business ユーザーが会議をロックした後で、発信者が会議ブリッジにダイヤルインしても、ユーザーがロビーで待っていることを知らせる通知がSkype for Business アプリにない。  <br/> |これは現在の設計上の仕様ですが、今後のサービス更新でこの機能のサポートに関するフィードバックを採用しています。  <br/> |回避策なし。  <br/> |8/30/2017  <br/> |
|2019 年 3 月 1 日より前に電話会議ライセンスを割り当てられた Skype for Business Server (オンプレム) ユーザーは、会議の招待にダイヤルが調整されていない可能性があります。  <br/> |電話Skype for Business Server会議Teamsユーザーのプロビジョニングは、その日までサポートされていませんでした。 現在はサポートされ、会議の最初の [コンポーネントです](/microsoftteams/meetings-first)。 ユーザーは、ライセンスを持Teamsがあります。  <br/> |プロビジョニング パイプラインを再アクティブ化する必要があります。 ユーザーの電話会議ライセンスを削除し、数時間待ってライセンスを再割り当てします。  <br/> |2019/3/1  <br/> |
   
## <a name="related-topics"></a>関連トピック

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
