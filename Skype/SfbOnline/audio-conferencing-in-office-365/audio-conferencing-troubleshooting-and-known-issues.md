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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229186"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a><span data-ttu-id="dfb59-103">電話会議のトラブルシューティングと既知の問題</span><span class="sxs-lookup"><span data-stu-id="dfb59-103">Audio Conferencing troubleshooting and known issues</span></span>

 <span data-ttu-id="dfb59-104">**この資料が、Skype のビジネス ユーザーが Microsoft を使用して、オーディオ会議プロバイダーとしてです。それは、サード ・ パーティ製の音声会議プロバイダー (ACP) を使用しているユーザーには適用されません。**</span><span class="sxs-lookup"><span data-stu-id="dfb59-104">**This article is for Skype for Business users using Microsoft as their audio conferencing provider. It does not apply to customers who are using a third-party audio conferencing provider (ACP).**</span></span>
  
## <a name="troubleshooting-and-known-issues"></a><span data-ttu-id="dfb59-105">トラブルシューティングと既知の問題</span><span class="sxs-lookup"><span data-stu-id="dfb59-105">Troubleshooting and known issues</span></span>

<span data-ttu-id="dfb59-106">Microsoft を電話会議プロバイダーとして使う電話会議には、現在追跡中で、積極的に調査が行われている問題があります。この問題は、Office 365 の今後のリリースで機能が更新されると解決される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfb59-106">Audio Conferencing that uses Microsoft as the audio conferencing provider has current issues that are being tracked and actively investigated and will be potentially resolved when the feature is updated in future releases of Office 365.</span></span>
  
<span data-ttu-id="dfb59-107">ここでは、これを参照として使用オーディオ会議の設定を取得して、組織内のビジネスの Skype を使用するユーザーの作業に潜在的な問題をトラブルシューティングする場合。</span><span class="sxs-lookup"><span data-stu-id="dfb59-107">For now, use this as a reference when you are troubleshooting potential issues with getting Audio Conferencing set up and working for the people using Skype for Business in your organization.</span></span>

|<span data-ttu-id="dfb59-108">**問題**</span><span class="sxs-lookup"><span data-stu-id="dfb59-108">**Issue**</span></span>|<span data-ttu-id="dfb59-109">**動作/現象**</span><span class="sxs-lookup"><span data-stu-id="dfb59-109">**Behavior/Symptoms**</span></span>|<span data-ttu-id="dfb59-110">**既知の回避策**</span><span class="sxs-lookup"><span data-stu-id="dfb59-110">**Known workaround**</span></span>|<span data-ttu-id="dfb59-111">**発見日**</span><span class="sxs-lookup"><span data-stu-id="dfb59-111">**Discovery date**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dfb59-112">会議の開始時に入退室の通知はオンになるが、会議の開始後すぐにオフになる。</span><span class="sxs-lookup"><span data-stu-id="dfb59-112">Entry and exit notifications are turned on when a meeting starts, but they're turned off shortly after the meeting starts.</span></span>  <br/> |<span data-ttu-id="dfb59-p101">既定では、Skype for Business アプリまたはダイヤルインのいずれかから参加者が参加する場合でも、会議の入退室の通知は無効になります。Skype for Business アプリの [ **Skype 会議のオプション**] で、このお知らせを有効にできます。すべての参加者がダイヤルインで参加する会議では、参加者は参加者リストを利用できないため、入退室通知は既定で有効になります。通話による参加者のみの会議は開始時に入退室通知がオンになりますが、Skype for Business アプリを使う参加者が参加すると、この通知はオフになります。この通知がオフの場合、Skype for Business アプリの [ **Skype 会議のオプション**] を使ってオンに戻すことができます。 </span><span class="sxs-lookup"><span data-stu-id="dfb59-p101">By default, entry and exit notifications are disabled for meetings where participants join from both Skype for Business apps and when they dial in. You can enable the announcements in the **Skype Meeting Options** in the Skype for Business app. For a meeting where all participants dial in and join a meeting, entry and exit notifications are enabled by default as the participant roster isn't available to any participant. When a meeting has started with only participants calling in, the entry and exit notifications will be turned on, but when a participant joins using a Skype for Business app, the notifications will be turned off. When turned off, the notifications can be enabled back using **Skype Meeting Options** in the Skype for Business app. </span></span><br/> |<span data-ttu-id="dfb59-118">回避策なし。</span><span class="sxs-lookup"><span data-stu-id="dfb59-118">No workaround.</span></span>  <br/> |<span data-ttu-id="dfb59-119">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="dfb59-119">8/30/2017</span></span>  <br/> |
|<span data-ttu-id="dfb59-120">E5 ライセンスを割り当て、最初にユーザーをプロビジョニングするときに、メールボックスが有効でないユーザーに電話会議のようこそメールが配信されないことがある。</span><span class="sxs-lookup"><span data-stu-id="dfb59-120">If a user is provisioned the first time by being assigned an E5 license, it might be possible for the Audio Conferencing welcome email to not be delivered to the user if the mailbox isn't enabled.</span></span>  <br/> |<span data-ttu-id="dfb59-121">これが発生した場合は、Skype for Business 管理センター の [ **電話会議**] を使用するか、PowerShell を使用してユーザーの電話会議情報をいつでも再送信することができます。</span><span class="sxs-lookup"><span data-stu-id="dfb59-121">If this happens, you can always resend the audio conferencing information of the user using **Audio conferencing** in the Skype for Business admin center or using PowerShell.</span></span> <span data-ttu-id="dfb59-122">[有効にするかオーディオ会議の設定を変更すると、送信メールを無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfb59-122">See [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>  <br/> <span data-ttu-id="dfb59-123">**注:** オーディオ会議の暗証番号 (pin) をユーザーに再送信するために、暗証番号 (pin) にリセットするのには。</span><span class="sxs-lookup"><span data-stu-id="dfb59-123">**Note:** In order to resend the audio conferencing PIN to the user, the PIN has to be reset.</span></span> <span data-ttu-id="dfb59-124">これを行うには、Skype for Business 管理センター の [ **電話会議**] を使用するか、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfb59-124">This can also be done by using **Audio conferencing** in the Skype for Business admin center or by using PowerShell.</span></span>          |<span data-ttu-id="dfb59-125">回避策なし。</span><span class="sxs-lookup"><span data-stu-id="dfb59-125">No workaround.</span></span>  <br/> |<span data-ttu-id="dfb59-126">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="dfb59-126">8/30/2017</span></span>  <br/> |
|<span data-ttu-id="dfb59-127">電話会議の通話が利用状況レポートに表示されるのに最大 24 時間かかる。</span><span class="sxs-lookup"><span data-stu-id="dfb59-127">Audio conferencing calls could take up to 24 hours to show in the usage reports.</span></span>  <br/> |<span data-ttu-id="dfb59-128">将来のサービスの更新では、この点について機能強化が図られることが予定されています。</span><span class="sxs-lookup"><span data-stu-id="dfb59-128">We're looking forward to making improvements on this area in future service updates.</span></span>  <br/> |<span data-ttu-id="dfb59-129">回避策なし。</span><span class="sxs-lookup"><span data-stu-id="dfb59-129">No workaround.</span></span>  <br/> |<span data-ttu-id="dfb59-130">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="dfb59-130">8/30/2017</span></span>  <br/> |
|<span data-ttu-id="dfb59-131">Skype for Business ユーザーが会議をロックした後で、発信者が会議ブリッジにダイヤルインしても、ユーザーがロビーで待っていることを知らせる通知がSkype for Business アプリにない。</span><span class="sxs-lookup"><span data-stu-id="dfb59-131">When a caller dials in to a conference bridge after the meeting has been locked by a Skype for Business user, there isn't a notification in the Skype for Business app stating that the user is waiting in the lobby.</span></span>  <br/> |<span data-ttu-id="dfb59-132">これは現在の設計上の仕様ですが、今後のサービス更新でこの機能のサポートに関するフィードバックを採用しています。</span><span class="sxs-lookup"><span data-stu-id="dfb59-132">This is currently by design, but we've taken the feedback in regard to supporting this capability in future service updates.</span></span>  <br/> |<span data-ttu-id="dfb59-133">回避策なし。</span><span class="sxs-lookup"><span data-stu-id="dfb59-133">No workaround.</span></span>  <br/> |<span data-ttu-id="dfb59-134">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="dfb59-134">8/30/2017</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="dfb59-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfb59-135">Related topics</span></span>

[<span data-ttu-id="dfb59-136">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="dfb59-136">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
