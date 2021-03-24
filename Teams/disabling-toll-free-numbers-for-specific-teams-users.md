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
- seo-marvel-mar2020
description: 開催者が電話会議ブリッジ会議で無料電話番号を使用する方法を制御する方法について説明します。
ms.openlocfilehash: f9ab09396778b221ad7f5c016dbf7db76fcba030
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096347"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="df240-103">特定の Teams ユーザーの無料電話番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="df240-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="df240-104">組織の Microsoft 電話会議ブリッジに無料電話番号がある場合、特定の開催者の会議でその使用を許可または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="df240-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="df240-105">既定では、組織内のすべてのユーザーは、無料電話番号を使用することができます。つまり、それらの番号が使用可能な場合は、会議に参加するために参加者が使用できます。</span><span class="sxs-lookup"><span data-stu-id="df240-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="df240-106">この設定が組織の特定のユーザーに対しては必要ない場合、特定のユーザーが会議でそれらの番号を使用するのを無料電話番号有効化コントロールを使って制限できます。</span><span class="sxs-lookup"><span data-stu-id="df240-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="df240-107">特定の開催者の無料電話番号が無効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="df240-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="df240-108">対象の開催者が招待する会議で無料電話番号は含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="df240-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="df240-109">無料電話番号は、対象の開催者が招待する会議で参照される [電話番号の検索] ページにリストされなくなります。</span><span class="sxs-lookup"><span data-stu-id="df240-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="df240-110">参加者は、組織の無料電話番号をダイヤルしてその開催者の会議に参加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="df240-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="df240-111">その開催者のすべての会議は自動的に再スケジュールされ、無料電話番号が削除されます。</span><span class="sxs-lookup"><span data-stu-id="df240-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="df240-112">この場合、それらの会議の参加者すべてに開催者の電子メールの全招待状が再送信されます。</span><span class="sxs-lookup"><span data-stu-id="df240-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="df240-113">参加者は、電話番号 (有料) を使用して対象開催者の会議に引き続き参加できます。</span><span class="sxs-lookup"><span data-stu-id="df240-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="df240-114">特定のユーザーの無料電話番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="df240-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="df240-115">**Microsoft Teams 管理センター** から次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="df240-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="df240-116">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="df240-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="df240-117">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df240-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="df240-118">**[このユーザーからの会議出席依頼にフリー ダイヤルの番号を含める]** を **[オフ]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="df240-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="df240-119">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df240-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="df240-120">**PowerShell を使用する場合**</span><span class="sxs-lookup"><span data-stu-id="df240-120">**Using PowerShell**</span></span>  

<span data-ttu-id="df240-121">詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df240-121">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>