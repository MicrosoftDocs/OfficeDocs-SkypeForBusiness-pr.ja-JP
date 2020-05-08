---
title: 'Skype for Business とサードパーティの電話会議プロバイダーとの統合の終了プログラム '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: None
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: 2021年7月31日に、サードパーティの電話会議プロバイダー (サードパーティ ACP) との Skype for Business の統合が終了すると、生涯プログラムが終了します。
ms.openlocfilehash: 5b49bf573ad79cbdacbc538a0ef67faf1b2b634e
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164456"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a><span data-ttu-id="9e57f-103">Skype for Business とサードパーティの電話会議プロバイダーとの統合の終了プログラム</span><span class="sxs-lookup"><span data-stu-id="9e57f-103">End of life program for the integration of Skype for Business with third-party audio conferencing providers</span></span> 

<span data-ttu-id="9e57f-104">Microsoft は、Skype for Business とサードパーティの電話会議プロバイダー (ACPs) との統合に関して、サポート終了プログラムの開始を発表しました。</span><span class="sxs-lookup"><span data-stu-id="9e57f-104">Microsoft has announced the start of the end of life program for the integration of Skype for Business with third-party audio conferencing providers (ACPs).</span></span> 

<span data-ttu-id="9e57f-105">有効期限プログラムは、2021年7月31日に終了します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-105">The end of life program will conclude on July 31, 2021.</span></span> <span data-ttu-id="9e57f-106">プログラムが終了すると、サードパーティの電話会議プロバイダーとの Skype for Business の統合が機能しなくなり、その日 (2021 年7月31日) に次の変更が行われます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-106">When the program concludes, the integration of Skype for Business with third-party audio conferencing providers will stop working and the following changes will be observed on that date (July 31, 2021):</span></span>

- <span data-ttu-id="9e57f-107">サードパーティ ACP サービスによって提供されたダイヤルイン番号を使って、Skype for Business 会議に参加しようとしている参加者は、Skype for Business 会議に接続されなくなります。</span><span class="sxs-lookup"><span data-stu-id="9e57f-107">Participants who attempt to join any Skype for Business meeting via dial-in numbers provided by a third-party ACP service will no longer be connected to the Skype for Business meeting.</span></span>
 
- <span data-ttu-id="9e57f-108">サードパーティ ACP サービスが有効になっているユーザーは、新しい Skype for Business 会議への招待に自動的にダイヤルイン情報を含めなくなります。</span><span class="sxs-lookup"><span data-stu-id="9e57f-108">Users enabled for a third-party ACP service will no longer have their dial-in information automatically included in any new Skype for Business meeting invites.</span></span>

<span data-ttu-id="9e57f-109">最終版プログラムの開始時のお知らせの一部として、次の変更が有効になり、終了するまで継続して使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9e57f-109">As part of the announcement of the start of the end of life program, the following change have taken effect and will continue to be in place until the conclusion of the end of life program:</span></span> 

- <span data-ttu-id="9e57f-110">サードパーティ ACP サービスを使用するように構成された Skype for Business ユーザーがいない場合、サードパーティ ACP サービスを使用するようにユーザーを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="9e57f-110">Customers with no Skype for Business users configured to use a third-party ACP service will not be able to configure any users to use a third-party ACP service.</span></span>

- <span data-ttu-id="9e57f-111">サードパーティ ACP サービスを使用するように構成された Skype for Business ユーザーの既存のお客様は、有効期間が終了するまで、引き続き新しいユーザーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-111">Existing customers with Skype for Business users configured to use a third-party ACP service will continue to be able to add new users for the duration of the end of life period.</span></span> <span data-ttu-id="9e57f-112">サードパーティの ACP サービスを使用するために追加の Skype for Business ユーザーをセットアップしないことをお勧めします。2021年7月31日に変更が反映されるため、これらのサービスにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-112">Please note that we do not recommend setting up additional Skype for Business users to use a third-party ACP service, as the changes that will come into effect on July 31, 2021 will also apply to them.</span></span>

## <a name="preparing-for-this-change"></a><span data-ttu-id="9e57f-113">この変更の準備</span><span class="sxs-lookup"><span data-stu-id="9e57f-113">Preparing for this change</span></span>

<span data-ttu-id="9e57f-114">この変更を準備するために、影響を受ける組織に、2021年7月31日より前にこの計画された更新のユーザーに通知するようお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e57f-114">To prepare for this change, we encourage affected organizations to notify their enabled users of this planned update prior to July 31, 2021.</span></span> 

<span data-ttu-id="9e57f-115">2021年7月31日以降、ユーザーはオンライン会議を中断することなく、引き続き Skype for Business を使用することができます。ただし、組織では、Skype for Business または Microsoft Teams とのダイヤルイン音声会議が必要な場合は、Microsoft から提供された電話会議のユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e57f-115">After July 31, 2021, users can continue to use Skype for Business with no interruption to their online meetings; however, organizations will need to enable their users for Audio Conferencing provided by Microsoft if they require dial-in audio conferencing with Skype for Business or Microsoft Teams.</span></span> <span data-ttu-id="9e57f-116">Microsoft 電話会議の詳細については、「[電話会議](https://products.office.com/skype-for-business/audio-conferencing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-116">To learn more about Microsoft Audio Conferencing, see [Audio Conferencing](https://products.office.com/skype-for-business/audio-conferencing).</span></span> 

<span data-ttu-id="9e57f-117">組織の目的の終了状態に応じて、次の3つのパスに従うことができます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-117">Depending on the desired end state of an organization, there are three paths that can be followed:</span></span>

- <span data-ttu-id="9e57f-118">Microsoft 電話会議に移行します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-118">Migrate to Microsoft Audio Conferencing.</span></span> 
- <span data-ttu-id="9e57f-119">引き続き、サードパーティの電話会議プロバイダーを個別に使用します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-119">Continue to separately use a third-party audio conferencing provider.</span></span> 
- <span data-ttu-id="9e57f-120">すべてのダイヤルイン会議の使用を停止します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-120">Stop using dial-in conferencing altogether.</span></span>

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a><span data-ttu-id="9e57f-121">パス #1: Microsoft 電話会議に移行する</span><span class="sxs-lookup"><span data-stu-id="9e57f-121">Path #1: Migrate to Microsoft Audio Conferencing</span></span>   

<span data-ttu-id="9e57f-122">2021年7月31日より前に Microsoft 電話会議に移行して移行を完了すると、その日以降のサービスへの影響は発生しません。</span><span class="sxs-lookup"><span data-stu-id="9e57f-122">Organizations that decide to migrate to Microsoft Audio Conferencing and complete their migration prior to July 31, 2021, will not experience any service impact during or after that date.</span></span> <span data-ttu-id="9e57f-123">Microsoft 電話会議への移行により、次のような変更が組織に導入されます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-123">The migration to Microsoft Audio Conferencing will introduce the following changes to an organization:</span></span> 

- <span data-ttu-id="9e57f-124">サービスは、他のすべての Microsoft 365 または Office 365 サービスに課金されます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-124">The service will be billed with all other Microsoft 365 or Office 365 services.</span></span> 

- <span data-ttu-id="9e57f-125">標準サブスクリプションを購入した場合は、有料のダイヤルイン料金がユーザーごとの月額プランの料金に含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-125">If the standard subscription is purchased, toll dial-in cost will be included in the per-user monthly subscription cost.</span></span> 

- <span data-ttu-id="9e57f-126">各組織とそのユーザーに、新しいダイヤルイン電話番号のセットが提供されます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-126">A new set of dial-in phone numbers will be provided to each organization and its users.</span></span> <span data-ttu-id="9e57f-127">Microsoft 電話会議サービスの地理的な範囲を確認するには、「[電話会議と通話プランの国と地域の空き時間](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-127">To see the geographical coverage of Microsoft Audio Conferencing service, see [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).</span></span>
 
- <span data-ttu-id="9e57f-128">サードパーティ ACP を使って有効になっているユーザーによって既にスケジュールされている会議は、Microsoft 電話会議のダイヤルイン情報が含まれるように自動的に再スケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-128">Meetings that have already been scheduled by users enabled with a third-party ACP will be automatically rescheduled to include Microsoft Audio Conferencing dial-in information.</span></span>
 
- <span data-ttu-id="9e57f-129">各会議の会議 Id は動的になります。つまり、各会議には専用の会議 ID があります。</span><span class="sxs-lookup"><span data-stu-id="9e57f-129">The conference IDs of each meeting will be dynamic, meaning that each meeting will have its own dedicated conference ID.</span></span> <span data-ttu-id="9e57f-130">動的会議 Id を使用すると、セキュリティが強化され、バックツーバック会議の操作性が向上します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-130">Dynamic conference IDs provide enhanced security and an improved experience for back-to-back meetings.</span></span>

- <span data-ttu-id="9e57f-131">本サービスの使用にはすべて、電話会議サービスの利用規約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-131">All usage of the service is subject to the Audio Conferencing services use terms.</span></span> 

<span data-ttu-id="9e57f-132">Microsoft 音声会議への移行は簡単です。また、サービスのライセンスを取得した後のわずかな手順で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-132">Migrating to Microsoft Audio Conferencing is simple, and it can be done in just a couple of steps after acquiring the licenses for the service.</span></span> <span data-ttu-id="9e57f-133">Microsoft 電話会議に移行する方法については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-133">To learn about how to migrate to Microsoft Audio Conferencing, see:</span></span>

- [<span data-ttu-id="9e57f-134">Microsoft 365 または Office 365 で電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="9e57f-134">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
<span data-ttu-id="9e57f-135">**概要:**</span><span class="sxs-lookup"><span data-stu-id="9e57f-135">**Summary:**</span></span>

- <span data-ttu-id="9e57f-136">2021年7月31日より前に Microsoft 電話会議に移行して移行を完了する組織では、その日付以降、サービスへの影響は表示されません。</span><span class="sxs-lookup"><span data-stu-id="9e57f-136">Organizations that migrate to Microsoft Audio Conferencing and complete their migration before July 31, 2021, won’t see any impact to their service during or after that date.</span></span>

- <span data-ttu-id="9e57f-137">Microsoft 電話会議への移行の詳細については、「 [microsoft 365 または Office 365 で電話会議を試す、または購入](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-137">To learn more about migrating to Microsoft Audio Conferencing, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md).</span></span> 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="9e57f-138">パス #2: サードパーティ電話会議プロバイダーを個別に使用し続ける</span><span class="sxs-lookup"><span data-stu-id="9e57f-138">Path #2: Continue to separately use a third-party audio conferencing provider</span></span>

<span data-ttu-id="9e57f-139">2021年7月31日以降にサードパーティ acp を引き続き使用することを決定した組織は、Skype for Business 会議のオーディオ部分に参加するためにサードパーティ ACP ダイヤルイン情報を使用できなくなるため、サービスへの影響が発生します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-139">Organizations that decide to continue using a third-party ACP on and after July 31, 2021, will experience service impact because the third-party ACP dial-in information will no longer be able to be used to join the audio portion of a Skype for Business meeting.</span></span> 

<span data-ttu-id="9e57f-140">Skype for Business 会議で、一部の参加者に VoIP などの参加者を招待して、サードパーティ ACP 経由で音声を使用しないようにするには、ユーザーの会議で VoIP を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e57f-140">To prevent the fragmentation of audio in Skype for Business meetings by having some participants joining via VoIP and other via the third-party ACP, it’s recommended for these organizations to disable using VoIP on their users’ meetings.</span></span> <span data-ttu-id="9e57f-141">これにより、すべての参加者は、サードパーティ ACP を使って会議のオーディオ部分に参加する必要があります。会議の他のすべてのワークロード (チャットや画面共有など) は、Skype for Business で引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-141">This way, all participants will need to join the audio portion of a meeting using the third-party ACP and all other workloads of the meeting (such as chat or screen sharing) can continue to be supported over Skype for Business.</span></span> 

- <span data-ttu-id="9e57f-142">特定の開催者のすべての会議から VoIP を無効にするには、Set-csconferencingpolicy コマンドレットを使用して、自分の会議ポリシーの AllowIPAudio パラメーターを false に設定します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-142">To disable VoIP from all meetings of a given organizer, set the AllowIPAudio parameter of his or her Conferencing Policy to false via the Set-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="9e57f-143">詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-143">For additional information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
 
<span data-ttu-id="9e57f-144">スケジュールの観点と2021年7月31日時点では、サードパーティ ACP のダイヤルイン情報は、Skype for Business 会議の招待に自動的に含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="9e57f-144">In terms of scheduling, and as of July 31, 2021, the dial-in information of a third-party ACP will no longer be automatically included in Skype for Business meeting invites.</span></span> <span data-ttu-id="9e57f-145">ユーザーは、会議の一部としてこの情報を引き続き使用したい場合は、Skype for Business 会議の出席依頼にダイヤルイン情報を手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e57f-145">Users will need to manually add the dial-in information on their Skype for Business meeting invites if they wish to continue including this information as part of their meetings.</span></span> 

<span data-ttu-id="9e57f-146">2021年7月31日に、ユーザーの既存の会議が自動的に再スケジュールされ、サードパーティ ACP のダイヤルイン情報が削除されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-146">Please note that on July 31, 2021, the existing meetings of users will not be automatically rescheduled to remove any third-party ACP dial-in information.</span></span> <span data-ttu-id="9e57f-147">ユーザーの会議のために VoIP を有効にしておくことを決定した組織は、ユーザーに対してサードパーティ ACP の統合を無効にすることを検討してください。会議移行サービスを使って、サードパーティの電話会議のダイヤルイン情報を削除して、既に予定されている会議での音声の断片化を防ぐ必要があり</span><span class="sxs-lookup"><span data-stu-id="9e57f-147">Organizations that decide to keep VoIP enabled for the meetings of their users should consider disabling the integration of third-party ACP for their users and reschedule their meetings using the meeting migration service to remove the third-party audio conferencing dial-in information from their existing meetings and prevent the fragmentation of audio on already-scheduled meetings.</span></span> 

- <span data-ttu-id="9e57f-148">特定の開催者に対してサードパーティの電話会議の統合を無効にするには、CsUserAcp コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-148">To disable the integration of third-party audio conferencing for a given organizer, use the Remove-CsUserAcp cmdlet.</span></span> <span data-ttu-id="9e57f-149">詳細については、「 [CsUserAcp の削除](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-149">For additional information, see [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps).</span></span> 

- <span data-ttu-id="9e57f-150">サードパーティの電話会議プロバイダーとの統合を無効にした後で、ユーザーの会議を自動的に再スケジュールするには、「ユーザーに対して手動で会議移行を実行する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-150">To automatically reschedule the meetings of users after disabling the integration with a third-party audio conferencing provider, see “How do I run Meeting Migration manually for a user?”</span></span> <span data-ttu-id="9e57f-151">[「会議移行サービス (MMS) の](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)セットアップ」をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-151">in [Setting up the Meeting Migration Service (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).</span></span> 

<span data-ttu-id="9e57f-152">**概要:**</span><span class="sxs-lookup"><span data-stu-id="9e57f-152">**Summary:**</span></span>

- <span data-ttu-id="9e57f-153">2021年7月31日以降にサードパーティ acp を引き続き使用することにした場合、サードパーティ acp は Skype for Business 会議への参加には使用できず、新しい会議にサードパーティ ACP のダイヤルイン情報が含まれないため、このような影響があります。</span><span class="sxs-lookup"><span data-stu-id="9e57f-153">Organizations that decide to continue using a third-party ACP on and after July 31, 2021, will be affected because a third-party ACP won’t be able to be used to join a Skype for Business meeting and new meetings will not include third-party ACP dial-in information.</span></span> 

- <span data-ttu-id="9e57f-154">すべての影響を受けるユーザーのすべての会議について VoIP を無効にすることをお勧めします。これに2021より、VoIP 経由での参加者とサードパーティ ACP を介した参加者の間でオーディオが断片化されないようになります。</span><span class="sxs-lookup"><span data-stu-id="9e57f-154">It’s recommended that VoIP is disabled for all meetings of all affected users before July 31, 2021, to prevent the audio from being fragmented across participants joining via VoIP and via a third-party ACP.</span></span> 

    - <span data-ttu-id="9e57f-155">特定の開催者のすべての会議から VoIP を無効にするには、Set-csconferencingpolicy コマンドレットを使用して、ユーザーの会議ポリシーの AllowIPAudio パラメーターを false に設定します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-155">To disable VoIP from all meetings of a given organizer, set the AllowIPAudio parameter of the user’s Conferencing Policy to false via the Set-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="9e57f-156">詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-156">For additional information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
 
- <span data-ttu-id="9e57f-157">組織がすべての会議で VoIP を無効にしていない場合は、Skype for Business Online とサードパーティ ACP との統合を無効にすることをお勧めします。また、オーディオの断片化を防止するために、サードパーティ ACP のダイヤルイン情報を削除するように会議をスケジュールし直すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e57f-157">If an organization doesn’t disable VoIP for all meetings, it’s recommended for users to be disabled from using the Skype for Business Online integration with a third-party ACP and reschedule their meetings to remove the third-party ACP dial-in information to prevent fragmentation of audio.</span></span>

    - <span data-ttu-id="9e57f-158">特定の開催者に対してサードパーティの電話会議の統合を無効にするには、 [CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-158">To disable the integration of third-party audio conferencing for a given organizer, use the [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps) cmdlet.</span></span> 

    - <span data-ttu-id="9e57f-159">会議を自動的に再スケジュールするには、「ユーザーに対して手動で会議移行を実行する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-159">To automatically reschedule the meetings, see “How do I run Meeting Migration manually for a user?”</span></span> <span data-ttu-id="9e57f-160">[「会議移行サービス (MMS) の](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)セットアップ」をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-160">in [Setting up the Meeting Migration Service (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).</span></span>

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a><span data-ttu-id="9e57f-161">パス #3: ダイヤルイン会議の使用を中止する</span><span class="sxs-lookup"><span data-stu-id="9e57f-161">Path #3: Stop using dial-in conferencing altogether</span></span>

<span data-ttu-id="9e57f-162">ダイヤルイン会議の使用を中止する組織 (Microsoft とサードパーティ ACP によって提供されることはありません) は、Skype for Business 会議のオーディオ部分をサポートするために、VoIP を最大限に活用することができます。</span><span class="sxs-lookup"><span data-stu-id="9e57f-162">Organizations that decide to stop using dial-in conferencing completely (neither provided by Microsoft nor by a third-party ACP) can fully rely on VoIP to support the audio portion of a Skype for Business meeting.</span></span> 

<span data-ttu-id="9e57f-163">このような組織では、ユーザーがサードパーティの電話会議プロバイダーを使用して、会議移行サービスを使用して会議を自動的に再スケジュールして、ダイヤルイン会議の情報を削除しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e57f-163">These organizations would need to disable their users from using a third-party audio conferencing provider and have their meetings automatically rescheduled using the meeting migration service to remove their dial-in conferencing information.</span></span> 

- <span data-ttu-id="9e57f-164">特定の開催者に対してサードパーティの電話会議の統合を無効にするには、CsUserAcp コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-164">To disable the integration of third-party audio conferencing for a given organizer, use the Remove-CsUserAcp cmdlet.</span></span> <span data-ttu-id="9e57f-165">詳細については、「 [CsUserAcp の削除](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-165">For additional information, see [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps).</span></span> 

- <span data-ttu-id="9e57f-166">サードパーティの電話会議プロバイダーとの統合を無効にした後で、ユーザーの会議を自動的に再スケジュールするには、「ユーザーに対して手動で会議移行を実行する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-166">To automatically reschedule the meetings of users after disabling the integration with a third-party audio conferencing provider, see “How do I run Meeting Migration manually for a user?”</span></span> <span data-ttu-id="9e57f-167">[「会議移行サービス (MMS) の](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)セットアップ」をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-167">in [Setting up the Meeting Migration Service (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).</span></span> 

<span data-ttu-id="9e57f-168">**概要:**</span><span class="sxs-lookup"><span data-stu-id="9e57f-168">**Summary:**</span></span> 

- <span data-ttu-id="9e57f-169">2021年7月31日より前に、電話会議の使用を停止することを決定した組織には影響はありません。</span><span class="sxs-lookup"><span data-stu-id="9e57f-169">Organizations that decide to stop using audio conferencing altogether before July 31, 2021, will not be impacted.</span></span>

- <span data-ttu-id="9e57f-170">特定の開催者に対してサードパーティの電話会議の統合を無効にするには、CsUserAcp コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e57f-170">To disable the integration of third-party audio conferencing for a given organizer, use the Remove-CsUserAcp cmdlet.</span></span> <span data-ttu-id="9e57f-171">詳細については、「 [CsUserAcp の削除](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-171">For additional information, see [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps).</span></span> 

- <span data-ttu-id="9e57f-172">サードパーティの電話会議プロバイダーとの統合を無効にした後で、ユーザーの会議を自動的に再スケジュールするには、「ユーザーに対して手動で会議移行を実行する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-172">To automatically reschedule the meetings of users after disabling integration with third-party audio conferencing providers, see “How do I run Meeting Migration manually for a user?”</span></span> <span data-ttu-id="9e57f-173">[「会議移行サービス (MMS) の](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)セットアップ」をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="9e57f-173">in [Setting up the Meeting Migration Service (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).</span></span>
