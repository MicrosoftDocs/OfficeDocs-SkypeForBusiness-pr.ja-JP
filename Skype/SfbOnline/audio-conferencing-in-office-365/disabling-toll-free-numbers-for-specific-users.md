---
title: フリー ダイヤルの番号を特定のユーザーを無効にします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理者は、開催者が、ミーティングのフリー ダイヤル番号を使用する方法を制御できます。
ms.openlocfilehash: a63078256ac9ac52b3d405bd3cf1b63120fb77ce
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="3a066-103">フリー ダイヤルの番号を特定のユーザーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3a066-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="3a066-104">組織では、その Microsoft オーディオ会議用ブリッジにフリー ダイヤル番号が含まれる場合は、許可または特定の開催者の会議での使用を防止できます。</span><span class="sxs-lookup"><span data-stu-id="3a066-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="3a066-105">既定では、組織内のすべてのユーザーはこれらの数値では、可能な場合、使えることの参加者が、会議に参加するためのフリー ダイヤル番号を使用するために有効です。</span><span class="sxs-lookup"><span data-stu-id="3a066-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="3a066-106">これは、組織内の一部のユーザーに目的の動作ではない場合、フリー ダイヤル番号の有効化コントロールを使用して、会議でそれらの数値を使用して特定のユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="3a066-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="3a066-107">特定の開催者のフリー ダイヤル番号を無効にした場合。</span><span class="sxs-lookup"><span data-stu-id="3a066-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="3a066-108">フリー ダイヤル番号は彼には含まれなく、または自分の会議への招待します。</span><span class="sxs-lookup"><span data-stu-id="3a066-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="3a066-109">フリー ダイヤル番号は自分で参照されている"電話番号を検索] ページに表示されなくまたは自分の会議に招待します。</span><span class="sxs-lookup"><span data-stu-id="3a066-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="3a066-110">参加者は、組織のすべてのフリー ダイヤル番号をダイヤルする場合、特定の開催者のミーティングに参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a066-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="3a066-111">すべての会議の開催者は自動的に再スケジュール、およびフリー ダイヤルの番号は、それらから削除されます。</span><span class="sxs-lookup"><span data-stu-id="3a066-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="3a066-112">すべての開催者の電子メールの招待を再送信、その会議のすべての参加者にこれは。</span><span class="sxs-lookup"><span data-stu-id="3a066-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="3a066-113">参加者は、有料電話番号を使用して、開催者の会議への参加を継続できます。</span><span class="sxs-lookup"><span data-stu-id="3a066-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="3a066-114">フリー ダイヤルの番号を特定のユーザーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3a066-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="3a066-115">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="3a066-115">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="3a066-116">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a066-116">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="3a066-117">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a066-117">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="3a066-118">**会議ブリッジ**の横にあるメニューをクリックし、ドロップダウン リストで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a066-118">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="3a066-119">**会議ブリッジのプロバイダー**のウィンドウで**このユーザーのミーティングに参加するのには、組織の会議用ブリッジ内のフリー ダイヤル番号を使用して許可する**オフにします。</span><span class="sxs-lookup"><span data-stu-id="3a066-119">In the **Conference bridge provider** pane, turn off **Allow using toll-free numbers in the Conferencing bridge of your organization to join the meetings of this user**.</span></span> 

5. <span data-ttu-id="3a066-120">クリックして**を適用します**。</span><span class="sxs-lookup"><span data-stu-id="3a066-120">Click **Apply.**</span></span> 

<span data-ttu-id="3a066-121">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="3a066-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="3a066-122">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **のユーザー**、および利用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a066-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="3a066-123">In the Skype for Business admin center, in the left navigation go to Dial-in conferencing > Provider name drop-down, and then select the dial-in conferencing provider for the user.</span><span class="sxs-lookup"><span data-stu-id="3a066-123">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="3a066-124">**このユーザーのミーティングに参加するのにはフリー ダイヤルの番号を使用して許可する**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="3a066-124">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="3a066-125">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a066-125">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="3a066-126">**PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="3a066-126">**Using PowerShell**</span></span>  

<span data-ttu-id="3a066-127">セット CsOnlineDialInConferencingUser コマンドレットの AllowTollFreeDialIn パラメーターを使用するには有効またはこのコントロールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3a066-127">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="3a066-128">例:</span><span class="sxs-lookup"><span data-stu-id="3a066-128">For example:</span></span> 

 - <span data-ttu-id="3a066-129">セット CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="3a066-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
