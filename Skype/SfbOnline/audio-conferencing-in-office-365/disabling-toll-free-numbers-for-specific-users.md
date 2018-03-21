---
title: "フリー ダイヤルの番号を特定のユーザーを無効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "管理者は、開催者が、ミーティングのフリー ダイヤル番号を使用する方法を制御できます。"
ms.openlocfilehash: fb4b0f8725608928e686307845871b4f5c1976d9
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="ec2ae-103">フリー ダイヤルの番号を特定のユーザーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="ec2ae-104">組織では、その Microsoft オーディオ会議用ブリッジにフリー ダイヤル番号が含まれる場合は、許可または特定の開催者の会議での使用を防止できます。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="ec2ae-105">既定では、組織内のすべてのユーザーはこれらの数値では、可能な場合、使えることの参加者が、会議に参加するためのフリー ダイヤル番号を使用するために有効です。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="ec2ae-106">これは、組織内の一部のユーザーに目的の動作ではない場合、フリー ダイヤル番号の有効化コントロールを使用して、会議でそれらの数値を使用して特定のユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="ec2ae-107">特定の開催者のフリー ダイヤル番号を無効にした場合。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="ec2ae-108">フリー ダイヤル番号は彼には含まれなく、または自分の会議への招待します。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="ec2ae-109">フリー ダイヤル番号は自分で参照されている"電話番号を検索] ページに表示されなくまたは自分の会議に招待します。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="ec2ae-110">参加者は、組織のすべてのフリー ダイヤル番号をダイヤルする場合、特定の開催者のミーティングに参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="ec2ae-111">すべての会議の開催者は自動的に再スケジュール、およびフリー ダイヤルの番号は、それらから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="ec2ae-112">すべての開催者の電子メールの招待を再送信、その会議のすべての参加者にこれは。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="ec2ae-113">参加者は、有料電話番号を使用して、開催者の会議への参加を継続できます。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users-using-the-skype-for-business-admin-center"></a><span data-ttu-id="ec2ae-114">ビジネス管理センターは、Skype を使用して特定のユーザー用のフリー ダイヤルの番号を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-114">Disabling toll-free numbers for specific users using the Skype for Business admin center</span></span> 
 1. <span data-ttu-id="ec2ae-115">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="ec2ae-115">Go to the **Office 365 admin center** > **Skype for Business**.</span></span> 
 2. <span data-ttu-id="ec2ae-116">ビジネス管理センターでは、左側のナビゲーションでは、Skype で**電話会議**に移動する > **のユーザー**、および利用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-116">In the Skype for Business admin center, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 
 3. <span data-ttu-id="ec2ae-117">In the Skype for Business admin center, in the left navigation go to Dial-in conferencing > Provider name drop-down, and then select the dial-in conferencing provider for the user.</span><span class="sxs-lookup"><span data-stu-id="ec2ae-117">In the Action pane, click **Edit**.</span></span> 
 4. <span data-ttu-id="ec2ae-118">確認するか、**このユーザーのミーティングに参加するのにはフリー ダイヤルの番号を使用して許可する**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-118">Check or clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 5. <span data-ttu-id="ec2ae-119">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-119">Click **Save**.</span></span> 
 
## <a name="disabling-toll-free-numbers-for-specific-users-using-powershell"></a><span data-ttu-id="ec2ae-120">PowerShell を使用して特定のユーザー用のフリー ダイヤルの番号を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-120">Disabling toll-free numbers for specific users using PowerShell</span></span>  

<span data-ttu-id="ec2ae-121">セット CsOnlineDialInConferencingUser コマンドレットの AllowTollFreeDialIn パラメーターを使用するには有効またはこのコントロールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ec2ae-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="ec2ae-122">例:</span><span class="sxs-lookup"><span data-stu-id="ec2ae-122">For example:</span></span> 

 - <span data-ttu-id="ec2ae-123">セット CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="ec2ae-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
