---
title: チームの特定のユーザーのフリー ダイヤル番号を無効にします。
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
description: 管理者は、開催者が、ミーティングのフリー ダイヤル番号を使用する方法を制御できます。
ms.openlocfilehash: 6d37fdb6e85f6c1325c4ebea179ad54aab91fa4c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887381"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="26d5a-103">チームの特定のユーザーのフリー ダイヤル番号を無効にします。</span><span class="sxs-lookup"><span data-stu-id="26d5a-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="26d5a-104">組織では、その Microsoft オーディオ会議用ブリッジにフリー ダイヤル番号が含まれる場合は、許可または特定の開催者の会議での使用を防止できます。</span><span class="sxs-lookup"><span data-stu-id="26d5a-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="26d5a-105">既定では、組織内のすべてのユーザーはこれらの数値では、可能な場合、使えることの参加者が、会議に参加するためのフリー ダイヤル番号を使用するために有効です。</span><span class="sxs-lookup"><span data-stu-id="26d5a-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="26d5a-106">これは、組織内の一部のユーザーに目的の動作ではない場合、フリー ダイヤル番号の有効化コントロールを使用して、会議でそれらの数値を使用して特定のユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="26d5a-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="26d5a-107">特定の開催者のフリー ダイヤル番号を無効にした場合。</span><span class="sxs-lookup"><span data-stu-id="26d5a-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="26d5a-108">フリー ダイヤル番号は彼には含まれなく、または自分の会議への招待します。</span><span class="sxs-lookup"><span data-stu-id="26d5a-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="26d5a-109">フリー ダイヤル番号は自分で参照されている"電話番号を検索] ページに表示されなくまたは自分の会議に招待します。</span><span class="sxs-lookup"><span data-stu-id="26d5a-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="26d5a-110">参加者は、組織のすべてのフリー ダイヤル番号をダイヤルする場合、特定の開催者のミーティングに参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="26d5a-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="26d5a-111">すべての会議の開催者は自動的に再スケジュール、およびフリー ダイヤルの番号は、それらから削除されます。</span><span class="sxs-lookup"><span data-stu-id="26d5a-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="26d5a-112">すべての開催者の電子メールの招待を再送信、その会議のすべての参加者にこれは。</span><span class="sxs-lookup"><span data-stu-id="26d5a-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="26d5a-113">参加者は、有料電話番号を使用して、開催者の会議への参加を継続できます。</span><span class="sxs-lookup"><span data-stu-id="26d5a-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="26d5a-114">特定のユーザーのフリーダイヤル番号を無効にする</span><span class="sxs-lookup"><span data-stu-id="26d5a-114">Disabling toll-free numbers for specific users</span></span> 

1. <span data-ttu-id="26d5a-115">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="26d5a-115">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="26d5a-116">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26d5a-116">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="26d5a-117">**オーディオ会議**の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26d5a-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="26d5a-118">**このユーザーからの会議出席依頼のフリー ダイヤル番号は、** オフにします。</span><span class="sxs-lookup"><span data-stu-id="26d5a-118">Turn off **Include toll-free numbers in meeting requests from this user**.</span></span> 

5. <span data-ttu-id="26d5a-119">クリックして**を保存します**。</span><span class="sxs-lookup"><span data-stu-id="26d5a-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="26d5a-120">**PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="26d5a-120">**Using PowerShell**</span></span>  

<span data-ttu-id="26d5a-121">詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26d5a-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
