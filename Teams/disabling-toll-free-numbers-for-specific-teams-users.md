---
title: 特定の Teams ユーザーの無料電話番号を無効にする
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理者は、開催者が自分たちの会議で無料電話番号を使用することができるかを制御することができます。
ms.openlocfilehash: 6d37fdb6e85f6c1325c4ebea179ad54aab91fa4c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887381"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="2666f-103">特定の Teams ユーザーの無料電話番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="2666f-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="2666f-104">Microsoft の電話会議ブリッジでの無料電話番号を所属する組織が持っている場合、特定の開催者の会議においてそれらの無料電話番号を使用することを許可したり禁止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2666f-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="2666f-105">既定では、組織内のすべてのユーザーが無料電話番号を使用できる状態になっています。それらの番号は、利用可能な場合、出席者が会議に参加するために使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2666f-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="2666f-106">これが組織内の一部のユーザーにとって望ましくない動作である場合は、無料電話番号を有効化する制御によって特定のユーザーのみに無料電話番号の使用を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="2666f-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="2666f-107">該当する開催者に対して無料電話番号が無効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="2666f-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="2666f-108">その開催者の招待状に、無料電話番号は記載されなくなります。</span><span class="sxs-lookup"><span data-stu-id="2666f-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="2666f-109">無料電話番号は、開催者の招待状に参照先として含まれる「電話番号の検索」ページにリストされなくなります。</span><span class="sxs-lookup"><span data-stu-id="2666f-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="2666f-110">出席者は、指定された開催者の会議に、組織の無料電話番号にダイヤルして参加することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="2666f-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="2666f-111">開催者のすべての会議は自動的に再スケジュールされ、無料電話番号はそれらの会議から削除されます。</span><span class="sxs-lookup"><span data-stu-id="2666f-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="2666f-112">これにより、開催者のすべてのメールの招待状が、該当する会議の出席者に再送信されます。</span><span class="sxs-lookup"><span data-stu-id="2666f-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="2666f-113">出席者は、有料電話番号を使用して、引き続きその開催者の会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="2666f-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="2666f-114">特定のユーザーの無料電話番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="2666f-114">Disabling toll-free numbers for specific users</span></span> 

1. <span data-ttu-id="2666f-115">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2666f-115">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="2666f-116">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2666f-116">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="2666f-117">[**電話会議**] の隣で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2666f-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="2666f-118">[**Include toll-free numbers in meeting requests from this user (このユーザーからの会議依頼に無料電話番号を含める)**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="2666f-118">Turn off **Include toll-free numbers in meeting requests from this user**.</span></span> 

5. <span data-ttu-id="2666f-119">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2666f-119">Click **Save**.</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="2666f-120">**PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="2666f-120">**Using Windows PowerShell**</span></span>  

<span data-ttu-id="2666f-121">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2666f-121">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
