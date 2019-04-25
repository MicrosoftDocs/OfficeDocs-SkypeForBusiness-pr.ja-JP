---
title: オンライン ビジネスのユーザーに特定の Skype のフリー ダイヤル番号を無効にします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
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
description: 管理者は、開催者が、ミーティングのフリー ダイヤル番号を使用する方法を制御できます。
ms.openlocfilehash: f553cc3abad8f4490d06099554c188881ef47e24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229283"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="f8ad3-103">オンライン ビジネスのユーザーに特定の Skype のフリー ダイヤル番号を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>
 
> [!Note]
> <span data-ttu-id="f8ad3-104">チームのユーザーの無効化のツールを必要としない番号の詳細については、[チームの特定のユーザーのフリー ダイヤル番号を無効にする](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="f8ad3-105">組織では、その Microsoft オーディオ会議用ブリッジにフリー ダイヤル番号が含まれる場合は、許可または特定の開催者の会議での使用を防止できます。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="f8ad3-106">既定では、組織内のすべてのユーザーはこれらの数値では、可能な場合、使えることの参加者が、会議に参加するためのフリー ダイヤル番号を使用するために有効です。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="f8ad3-107">これは、組織内の一部のユーザーに目的の動作ではない場合、フリー ダイヤル番号の有効化コントロールを使用して、会議でそれらの数値を使用して特定のユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="f8ad3-108">特定の開催者のフリー ダイヤル番号を無効にした場合。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="f8ad3-109">フリー ダイヤル番号は彼には含まれなく、または自分の会議への招待します。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="f8ad3-110">フリー ダイヤル番号は自分で参照されている"電話番号を検索] ページに表示されなくまたは自分の会議に招待します。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="f8ad3-111">参加者は、組織のすべてのフリー ダイヤル番号をダイヤルする場合、特定の開催者のミーティングに参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="f8ad3-112">すべての会議の開催者は自動的に再スケジュール、およびフリー ダイヤルの番号は、それらから削除されます。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="f8ad3-113">すべての開催者の電子メールの招待を再送信、その会議のすべての参加者にこれは。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="f8ad3-114">参加者は、有料電話番号を使用して、開催者の会議への参加を継続できます。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="f8ad3-115">特定のユーザーの無料電話番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="f8ad3-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="f8ad3-116">**マイクロソフトのチーム管理センター**。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="f8ad3-117">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f8ad3-118">**オーディオ会議**の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="f8ad3-119">**このユーザーからの要求を達成するためのフリー ダイヤル番号**は**無効**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="f8ad3-120">クリックして**を保存します**。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="f8ad3-121">**PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="f8ad3-121">**Using PowerShell**</span></span>  

<span data-ttu-id="f8ad3-122">セット CsOnlineDialInConferencingUser コマンドレットの AllowTollFreeDialIn パラメーターを使用するには有効またはこのコントロールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="f8ad3-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f8ad3-123">For example:</span></span> 

- <span data-ttu-id="f8ad3-124">セット CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="f8ad3-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
