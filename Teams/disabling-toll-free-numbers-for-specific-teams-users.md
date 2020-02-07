---
title: 特定の Teams ユーザーの無料電話番号を無効にする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 管理者は、開催者が会議に無料の電話番号を使用する方法を制御できます。
ms.openlocfilehash: 7bc830529fc24a61be914998e923ad2d5288b7c5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837267"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="c78f1-103">特定の Teams ユーザーの無料電話番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="c78f1-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="c78f1-104">組織の Microsoft 電話会議ブリッジに無料の電話番号がある場合は、特定の開催者の会議での使用を許可または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="c78f1-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="c78f1-105">既定では、組織内のすべてのユーザーが無料電話番号を使用できるようになっています。つまり、それらの電話番号は、参加者が会議に参加するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c78f1-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="c78f1-106">組織内の一部のユーザーに対してこの操作を行う必要がない場合は、無料番号の有効化制御を利用して、特定のユーザーの会議でそれらの電話番号を使用しないように制限することができます。</span><span class="sxs-lookup"><span data-stu-id="c78f1-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="c78f1-107">特定の開催者に対して無料電話番号が無効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="c78f1-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="c78f1-108">無料電話番号は、会議の出席依頼に含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="c78f1-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="c78f1-109">無料電話番号は、会議の招待で参照されている [市内番号の検索] ページには表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c78f1-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="c78f1-110">組織の無料電話番号をダイヤルした場合、参加者は、指定された開催者の会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="c78f1-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="c78f1-111">開催者のすべての会議が自動的に再スケジュールされ、無料の電話番号が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c78f1-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="c78f1-112">この操作を行うと、開催者のすべてのメールの招待が、それらの会議の参加者全員に再送信されます。</span><span class="sxs-lookup"><span data-stu-id="c78f1-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="c78f1-113">参加者は、有料番号を使って開催者の会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="c78f1-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="c78f1-114">特定のユーザーの無料電話番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="c78f1-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="c78f1-115">**Microsoft Teams 管理センター**から:</span><span class="sxs-lookup"><span data-stu-id="c78f1-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="c78f1-116">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c78f1-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c78f1-117">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c78f1-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="c78f1-118">**[このユーザーからの会議出席依頼には無料電話番号を含める (オフ)」** に設定します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c78f1-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="c78f1-119">[**保存] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="c78f1-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="c78f1-120">**PowerShell を使用する場合**</span><span class="sxs-lookup"><span data-stu-id="c78f1-120">**Using PowerShell**</span></span>  

<span data-ttu-id="c78f1-121">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c78f1-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
