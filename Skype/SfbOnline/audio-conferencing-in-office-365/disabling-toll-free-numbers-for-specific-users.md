---
title: 特定のオンライン ユーザーの無料電話番号Skype for Business無効にする
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
description: 管理者は、開催者が会議に無料電話番号を使用する方法を制御できます。
ms.openlocfilehash: 4fae54e3ed140ab876e6fadef10907e40f59057e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238512"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="573fd-103">特定のオンライン ユーザーの無料電話番号Skype for Business無効にする</span><span class="sxs-lookup"><span data-stu-id="573fd-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> <span data-ttu-id="573fd-104">ユーザーのツールフリー番号を無効にする方法についてはTeams特定のユーザーに対する無料電話番号の無効化に関する[Teams参照してください](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)。</span><span class="sxs-lookup"><span data-stu-id="573fd-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="573fd-105">組織の Microsoft 電話会議ブリッジに無料電話番号がある場合、特定の開催者の会議でその使用を許可または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="573fd-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="573fd-106">既定では、組織内のすべてのユーザーは、無料電話番号を使用することができます。つまり、それらの番号が使用可能な場合は、会議に参加するために参加者が使用できます。</span><span class="sxs-lookup"><span data-stu-id="573fd-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="573fd-107">この設定が組織の特定のユーザーに対しては必要ない場合、特定のユーザーが会議でそれらの番号を使用するのを無料電話番号有効化コントロールを使って制限できます。</span><span class="sxs-lookup"><span data-stu-id="573fd-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="573fd-108">特定の開催者の無料電話番号が無効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="573fd-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="573fd-109">対象の開催者が招待する会議で無料電話番号は含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="573fd-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="573fd-110">無料電話番号は、対象の開催者が招待する会議で参照される [電話番号の検索] ページにリストされなくなります。</span><span class="sxs-lookup"><span data-stu-id="573fd-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="573fd-111">参加者は、組織の無料電話番号をダイヤルしてその開催者の会議に参加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="573fd-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="573fd-112">その開催者のすべての会議は自動的に再スケジュールされ、無料電話番号が削除されます。</span><span class="sxs-lookup"><span data-stu-id="573fd-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="573fd-113">この場合、それらの会議の参加者すべてに開催者の電子メールの全招待状が再送信されます。</span><span class="sxs-lookup"><span data-stu-id="573fd-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="573fd-114">参加者は、電話番号 (有料) を使用して対象開催者の会議に引き続き参加できます。</span><span class="sxs-lookup"><span data-stu-id="573fd-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="573fd-115">特定のユーザーの無料電話番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="573fd-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="573fd-116">**Microsoft Teams 管理センター** から次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="573fd-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="573fd-117">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="573fd-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="573fd-118">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="573fd-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="573fd-119">**[このユーザーからの会議出席依頼にフリー ダイヤルの番号を含める]** を **[オフ]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="573fd-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="573fd-120">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="573fd-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="573fd-121">**PowerShell を使用する場合**</span><span class="sxs-lookup"><span data-stu-id="573fd-121">**Using PowerShell**</span></span>  

<span data-ttu-id="573fd-122">このコントロールを有効または無効にするには、Set-CsOnlineDialInConferencingUser コマンドレットの AllowTollFreeDialIn パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="573fd-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="573fd-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="573fd-123">For example:</span></span> 

- <span data-ttu-id="573fd-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="573fd-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
