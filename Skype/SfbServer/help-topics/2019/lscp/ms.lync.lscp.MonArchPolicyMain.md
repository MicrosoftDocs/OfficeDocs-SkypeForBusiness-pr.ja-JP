---
title: アーカイブ ポリシー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: アーカイブ ポリシーを使用して、Skype for Business Server にホームのユーザーのアーカイブを有効または無効にします。 それぞれのアーカイブ ポリシーでは、次のどちらかまたは両方のアーカイブを有効化または無効化できます。
ms.openlocfilehash: 041fc71da18ff38b14e82ce9d2ab14f366326b29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833617"
---
# <a name="archiving-policy"></a><span data-ttu-id="999f0-104">アーカイブ ポリシー</span><span class="sxs-lookup"><span data-stu-id="999f0-104">Archiving Policy</span></span>
 
<span data-ttu-id="999f0-105">アーカイブ ポリシーを使用して、Skype for Business Server にホームのユーザーのアーカイブを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="999f0-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="999f0-106">それぞれのアーカイブ ポリシーでは、次のどちらかまたは両方のアーカイブを有効化または無効化できます。</span><span class="sxs-lookup"><span data-stu-id="999f0-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="999f0-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="999f0-107">Internal communications</span></span>
    
- <span data-ttu-id="999f0-108">外部通信 (内部ネットワークの外部のユーザーが 1 人以上含まれる通信)</span><span class="sxs-lookup"><span data-stu-id="999f0-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="999f0-109">アーカイブ ポリシーには、グローバル ポリシーと、オプションで 1 つ以上のサイト アーカイブ ポリシーおよびユーザー アーカイブ ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="999f0-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="999f0-110">**グローバル ポリシー** グローバル ポリシーは、すべての展開で既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="999f0-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="999f0-111">グローバル ポリシーを編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="999f0-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="999f0-112">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="999f0-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="999f0-113">**サイト ポリシー (オプション)** 1 つ以上のサイト アーカイブ ポリシーを指定して、1 つのサイトの内部通信または外部通信のアーカイブを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="999f0-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="999f0-114">サイト ポリシーはグローバル ポリシーより優先されますが、アーカイブ サイト ポリシーで指定されたサイトに対してだけ優先されます。</span><span class="sxs-lookup"><span data-stu-id="999f0-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="999f0-115">サイト ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="999f0-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="999f0-116">**ユーザー ポリシー (オプション)** 特定のユーザーまたはユーザー グループの内部通信または外部通信のアーカイブを有効または無効に構成できる、1 つ以上のユーザー アーカイブ ポリシーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="999f0-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="999f0-117">ユーザー ポリシーはグローバル ポリシーとサイト ポリシーより優先されますが、ユーザー レベルのアーカイブ ポリシーを割り当てるユーザーおよびユーザー グループに対してだけ優先されます。</span><span class="sxs-lookup"><span data-stu-id="999f0-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="999f0-118">ユーザーポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="999f0-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="999f0-119">アーカイブ ポリシーは、Skype for Business Server にホームのユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="999f0-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="999f0-120">Exchange 統合を使用してアーカイブ データを Microsoft Exchange に保存する場合、Exchange ポリシーは Exchange にホームのユーザーのアーカイブを制御します。</span><span class="sxs-lookup"><span data-stu-id="999f0-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="999f0-121">これらのユーザーのアーカイブを有効にするには、ユーザーのメールボックスを保持のIn-Placeがあります。</span><span class="sxs-lookup"><span data-stu-id="999f0-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="999f0-p107">[**アーカイブ ポリシー**] ページには、展開に構成されている各アーカイブ ポリシーが一覧表示されます。また、各アーカイブ ポリシーの名前、対象範囲 (グローバル、サイト、ユーザー)、および有効になっているアーカイブ オプションも示されます。[**アーカイブ ポリシー**] ページからは、以下のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="999f0-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="999f0-125">**新規** 次のオプションのアーカイブ ポリシーを 1 つ以上追加できます。</span><span class="sxs-lookup"><span data-stu-id="999f0-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="999f0-126">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="999f0-126">Site policy</span></span>
    
  - <span data-ttu-id="999f0-127">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="999f0-127">User policy</span></span>
    
- <span data-ttu-id="999f0-128">**編集** ページに一覧表示されているアーカイブ ポリシーのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="999f0-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="999f0-129">このオプションを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="999f0-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="999f0-130">[**詳細の表示**]   アーカイブ ポリシーのアーカイブ オプションを変更できるダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="999f0-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="999f0-131">[**すべて選択**]   一覧のアーカイブ ポリシーをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="999f0-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="999f0-132">[**削除**]   選択したすべてのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="999f0-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="999f0-133">**アクション** このオプションを使用すると、ポリシーを編集する代わりに、ページに表示されている任意のポリシーで内部通信または外部通信のアーカイブをすばやく有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="999f0-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="999f0-134">[操作] で使用 **できるオプション** は、アーカイブ ポリシーで現在指定されているオプションによって異なっています。</span><span class="sxs-lookup"><span data-stu-id="999f0-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="999f0-135">アーカイブ ポリシーで現在有効なオプションを除き、すべてのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="999f0-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="999f0-136">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="999f0-136">Options include the following:</span></span>
    
  - <span data-ttu-id="999f0-137">**内部通信のアーカイブを有効にする**</span><span class="sxs-lookup"><span data-stu-id="999f0-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="999f0-138">**内部通信のアーカイブを無効にする**</span><span class="sxs-lookup"><span data-stu-id="999f0-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="999f0-139">**外部通信のアーカイブを有効にする**</span><span class="sxs-lookup"><span data-stu-id="999f0-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="999f0-140">**外部通信のアーカイブを無効にする**</span><span class="sxs-lookup"><span data-stu-id="999f0-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="999f0-141">**更新** [アーカイブ ポリシー **] ページを更新** して、すべてのアーカイブ ポリシーのオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="999f0-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="999f0-142">Exchange 統合を含むアーカイブ機能の詳細については [、「Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md)でのアーカイブの計画」、Skype for [Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)のアーカイブの展開、および Skype for [Business Server](../../../manage/archiving/archiving.md)でのアーカイブの管理を参照してください。</span><span class="sxs-lookup"><span data-stu-id="999f0-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

