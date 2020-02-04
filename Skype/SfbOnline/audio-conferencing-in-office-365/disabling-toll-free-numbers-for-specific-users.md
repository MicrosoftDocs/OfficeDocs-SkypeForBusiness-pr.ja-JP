---
title: 特定の Skype for Business Online ユーザーの無料電話番号を無効にする
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 管理者は、開催者が会議に無料の電話番号を使用する方法を制御できます。
ms.openlocfilehash: 42323afd397612c3cdc0549bdcc33b16cfdae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695682"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="6b824-103">特定の Skype for Business Online ユーザーの無料電話番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="6b824-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>
 
> [!Note]
> <span data-ttu-id="6b824-104">Teams ユーザーに対して、ツールを使用しない番号を無効にする方法については、「[特定の teams ユーザーに対して無料電話番号を無効にする](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b824-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="6b824-105">組織の Microsoft 電話会議ブリッジに無料の電話番号がある場合は、特定の開催者の会議での使用を許可または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="6b824-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="6b824-106">既定では、組織内のすべてのユーザーが無料電話番号を使用できるようになっています。つまり、それらの電話番号は、参加者が会議に参加するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b824-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="6b824-107">組織内の一部のユーザーに対してこの操作を行う必要がない場合は、無料番号の有効化制御を利用して、特定のユーザーの会議でそれらの電話番号を使用しないように制限することができます。</span><span class="sxs-lookup"><span data-stu-id="6b824-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="6b824-108">特定の開催者に対して無料電話番号が無効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="6b824-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="6b824-109">無料電話番号は、会議の出席依頼に含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="6b824-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="6b824-110">無料電話番号は、会議の招待で参照されている [市内番号の検索] ページには表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="6b824-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="6b824-111">組織の無料電話番号をダイヤルした場合、参加者は、指定された開催者の会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b824-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="6b824-112">開催者のすべての会議が自動的に再スケジュールされ、無料の電話番号が削除されます。</span><span class="sxs-lookup"><span data-stu-id="6b824-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="6b824-113">この操作を行うと、開催者のすべてのメールの招待が、それらの会議の参加者全員に再送信されます。</span><span class="sxs-lookup"><span data-stu-id="6b824-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="6b824-114">参加者は、有料番号を使って開催者の会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="6b824-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="6b824-115">特定のユーザーの無料電話番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="6b824-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="6b824-116">**Microsoft Teams 管理センター**から:</span><span class="sxs-lookup"><span data-stu-id="6b824-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="6b824-117">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b824-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="6b824-118">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b824-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="6b824-119">**[このユーザーからの会議出席依頼には無料電話番号を含める (オフ)」** に設定します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6b824-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="6b824-120">[**保存] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="6b824-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="6b824-121">**PowerShell を使用する場合**</span><span class="sxs-lookup"><span data-stu-id="6b824-121">**Using PowerShell**</span></span>  

<span data-ttu-id="6b824-122">このコントロールを有効または無効にするには、Get-csonlinedialinconferencinguser コマンドレットの AllowTollFreeDialIn パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b824-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="6b824-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6b824-123">For example:</span></span> 

- <span data-ttu-id="6b824-124">Set-Get-csonlinedialinconferencinguser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="6b824-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
