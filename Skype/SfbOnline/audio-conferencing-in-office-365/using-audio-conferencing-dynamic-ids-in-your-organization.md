---
title: 組織で電話会議の動的な Id を使用します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
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
description: '各 Skype は、さまざまな会議 Id を持つビジネスおよびマイクロソフトのチームの会議には、オーディオ会議サービスを更新しています。 提供するため静的会議 Id が大幅に向上が、動的な会議 Id:'
ms.openlocfilehash: 418e6f486b8108791930c7843bfed8bdc56e83ef
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a><span data-ttu-id="e40b7-104">組織で電話会議の動的な Id を使用します。</span><span class="sxs-lookup"><span data-stu-id="e40b7-104">Using Audio Conferencing dynamic IDs in your organization</span></span>

<span data-ttu-id="e40b7-105">各 Skype は、さまざまな会議 Id を持つビジネスおよびマイクロソフトのチームの会議には、オーディオ会議サービスを更新しています。</span><span class="sxs-lookup"><span data-stu-id="e40b7-105">The Audio Conferencing service is being updated to provide each Skype for Business and Microsoft Teams meeting with different conference IDs.</span></span> <span data-ttu-id="e40b7-106">提供するため静的会議 Id が大幅に向上が、動的な会議 Id:</span><span class="sxs-lookup"><span data-stu-id="e40b7-106">Dynamic conference IDs are a significant improvement over static conference IDs, because they provide:</span></span>
  
- <span data-ttu-id="e40b7-107">**強化されたセキュリティ**会議 Id は、ビジネスまたはマイクロソフトのチーム会議の各 Skype に固有し、会議が予定されている場合に生成されます。</span><span class="sxs-lookup"><span data-stu-id="e40b7-107">**Enhanced security** The conference IDs are unique for each Skype for Business or Microsoft Teams meeting and are generated when the meeting is being scheduled.</span></span>
    
- <span data-ttu-id="e40b7-108">**連続した会議および隣り合った会議向けのエクスペリエンスの向上** 単一の開催者の会議には、特定のダイヤルイン情報が提供されます。これにより、会議が相互に連続してスケジュールされている場合に、1 つの会議の電話参加者を別の会議の参加者と区別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e40b7-108">**A better experience for back-to-back and side-to-side meetings** Meetings for a single organizer are given specific dial-in information that prevents phone participants of one meeting from being mixed with participants of another one when they're scheduled next to each other.</span></span>
    
- <span data-ttu-id="e40b7-109">**シームレスな移行** 組織が動的会議 ID に対して有効化されている場合でも、静的会議 ID ですでに組織でスケジュールされているすべての会議はそのまま有効です。</span><span class="sxs-lookup"><span data-stu-id="e40b7-109">**A seamless transition** When your organization is enabled for dynamic conference IDs, all the meetings that have been already scheduled in your organization with static conference IDs will continue to work.</span></span>
    
> [!TIP]
> <span data-ttu-id="e40b7-110">動的 Id のみユーザーが利用できるが有効になっている * * オーディオ会議 * * し、microsoft が自社のオーディオ会議プロバイダーとして設定します。</span><span class="sxs-lookup"><span data-stu-id="e40b7-110">Dynamic IDs are only available to users who are enabled for ** Audio Conferencing** and have Microsoft set as their audio conferencing provider.</span></span> <span data-ttu-id="e40b7-111">ユーザーの[オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](assign-microsoft-as-the-audio-conferencing-provider.md)ができます。</span><span class="sxs-lookup"><span data-stu-id="e40b7-111">You can [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md) for your users.</span></span>
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a><span data-ttu-id="e40b7-112">どのような変更は自分の所属組織内のユーザーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40b7-112">What changes will the users in my organization see?</span></span>

<span data-ttu-id="e40b7-113">動的な会議 Id が有効になって、組織、ビジネスまたはマイクロソフトのチームが会議のすべての新しい Skype の電話会議は会議 Id が異なる場合がありますがある可能な組織内のユーザーによってスケジュールは、静的な会議 ID が前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40b7-113">After dynamic conference IDs have been enabled for your organization, any new Skype for Business or Microsoft Teams meeting that is scheduled by users in your organization who are enabled for Audio Conferencing will have conference IDs that will be different from the static conference ID they had before.</span></span> <span data-ttu-id="e40b7-114">静的が開催する前に会議 Id に参加する前に、会議の出席依頼に新しい会議 ID を使用する必要があります会議に参加するユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40b7-114">Organizers who had static conference IDs before need to remind the users joining their meetings that they now need to use a new conference ID in the meeting's invite before they can join it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e40b7-115">組織が影響を及ぼすことがなく会議をスケジュールするのには、引き続き、静的な会議 Id を持つ Id は引き続き動的の会議の有効にする前に静的な会議 Id を持つユーザーによってスケジュールされている会議。</span><span class="sxs-lookup"><span data-stu-id="e40b7-115">Meetings that were scheduled by a user with static conference IDs before the organization was enabled for dynamic conference IDs will continue to have the static conference IDs, so they'll continue to schedule meetings without any impact.</span></span> 
  
<span data-ttu-id="e40b7-116">これらの例は、同じユーザーによって編成されているビジネス ・ ミーティング用の 2 つの Skype の新しいエクスペリエンスを示していますが、両方が 2 つの異なる会議 Id:</span><span class="sxs-lookup"><span data-stu-id="e40b7-116">These examples show you the new experience for two Skype for Business meetings that have been organized by the same user but will both now have two different conference IDs:</span></span> 
  
 <span data-ttu-id="e40b7-117">**会議 #1** は 9:00 AM から 10:00 AM までスケジュールされ、会議 ID は 93907123 です。</span><span class="sxs-lookup"><span data-stu-id="e40b7-117">**Meeting #1** has been scheduled from 9:00 AM to 10:00 AM and it has 93907123 as its conference ID:</span></span>
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 <span data-ttu-id="e40b7-119">**会議 #2** は同じユーザーによって 10:00 AM から 11:00 AM までスケジュールされ、会議 ID は 16353789 です。</span><span class="sxs-lookup"><span data-stu-id="e40b7-119">**Meeting #2** has been scheduled by the same user from 10:00 AM to 11:00 AM and it has 16353789 as its conference ID:</span></span>
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a><span data-ttu-id="e40b7-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e40b7-121">Related topics</span></span>

- [<span data-ttu-id="e40b7-122">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="e40b7-122">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [<span data-ttu-id="e40b7-123">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="e40b7-123">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
