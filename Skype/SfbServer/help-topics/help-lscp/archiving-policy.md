---
title: アーカイブ ポリシー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: Skype for Business Server を使用しているユーザーのアーカイブを有効または無効にするには、アーカイブポリシーを使います。 それぞれのアーカイブ ポリシーでは、次のどちらかまたは両方のアーカイブを有効化または無効化できます。
ms.openlocfilehash: c0bd80dcbe2c140d861829ff5bd1476d070423ba
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687020"
---
# <a name="archiving-policy"></a><span data-ttu-id="9da9d-104">アーカイブ ポリシー</span><span class="sxs-lookup"><span data-stu-id="9da9d-104">Archiving Policy</span></span>
 
<span data-ttu-id="9da9d-105">Skype for Business Server を使用しているユーザーのアーカイブを有効または無効にするには、アーカイブポリシーを使います。</span><span class="sxs-lookup"><span data-stu-id="9da9d-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="9da9d-106">それぞれのアーカイブ ポリシーでは、次のどちらかまたは両方のアーカイブを有効化または無効化できます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="9da9d-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="9da9d-107">Internal communications</span></span>
    
- <span data-ttu-id="9da9d-108">外部通信 (内部ネットワークの外部のユーザーが 1 人以上含まれる通信)</span><span class="sxs-lookup"><span data-stu-id="9da9d-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="9da9d-109">アーカイブ ポリシーには、グローバル ポリシーと、オプションで 1 つ以上のサイト アーカイブ ポリシーおよびユーザー アーカイブ ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="9da9d-110">**グローバルポリシー**グローバルポリシーは、既定ですべての展開に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="9da9d-111">グローバル ポリシーを編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="9da9d-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="9da9d-112">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="9da9d-113">**サイトポリシー (オプション)** 1つまたは複数のサイトアーカイブポリシーを指定できます。各ポリシーを構成して、1つのサイトの内部または外部通信のアーカイブを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="9da9d-114">サイトポリシーはグローバルポリシーを上書きしますが、アーカイブサイトポリシーで指定したサイトに対してのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="9da9d-115">サイト ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="9da9d-116">**ユーザーポリシー (オプション)** 特定のユーザーまたはユーザーグループに対して、内部または外部の通信のアーカイブを有効または無効にするように構成できる1つ以上のユーザーアーカイブポリシーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="9da9d-117">ユーザーポリシーはグローバルポリシーとサイトポリシーを上書きしますが、ユーザーレベルのアーカイブポリシーを割り当てるユーザーおよびユーザーグループに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="9da9d-118">ユーザー ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9da9d-119">アーカイブポリシーは、Skype for Business Server をホームとしているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="9da9d-120">Exchange の統合機能を使用して、アーカイブデータを Microsoft Exchange に保存する場合は、exchange 2013 でホームとして使用するユーザーのアーカイブを Exchange 2013 ポリシーで制御します。</span><span class="sxs-lookup"><span data-stu-id="9da9d-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="9da9d-121">これらのユーザーのアーカイブを有効にするには、ユーザーのメールボックスがインプレースホールドに配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da9d-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="9da9d-p107">[**アーカイブ ポリシー**] ページには、展開に構成されている各アーカイブ ポリシーが一覧表示されます。また、各アーカイブ ポリシーの名前、対象範囲 (グローバル、サイト、ユーザー)、および有効になっているアーカイブ オプションも示されます。[**アーカイブ ポリシー**] ページからは、以下のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="9da9d-125">**新規**次のオプションのアーカイブポリシーの1つ以上を追加できます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="9da9d-126">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="9da9d-126">Site policy</span></span>
    
  - <span data-ttu-id="9da9d-127">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="9da9d-127">User policy</span></span>
    
- <span data-ttu-id="9da9d-128">**編集**ページに表示されているアーカイブポリシーのオプションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="9da9d-129">このオプションを使うと、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="9da9d-130">[**詳細の表示**]   アーカイブ ポリシーのアーカイブ オプションを変更できるダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="9da9d-131">[**すべて選択**]   一覧のアーカイブ ポリシーをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="9da9d-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="9da9d-132">[**削除**]   選択したすべてのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="9da9d-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="9da9d-133">**操作**このオプションを使うと、ポリシーを編集するのではなく、ページに一覧表示されているポリシーで、内部または外部の通信のアーカイブをすばやく有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="9da9d-134">[**アクション**] で利用可能なオプションは、アーカイブポリシーで現在指定されているオプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9da9d-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="9da9d-135">アーカイブポリシーに現在適用されているオプションを除き、すべてのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="9da9d-136">次のようなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="9da9d-136">Options include the following:</span></span>
    
  - <span data-ttu-id="9da9d-137">**内部通信のアーカイブを有効にする**</span><span class="sxs-lookup"><span data-stu-id="9da9d-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="9da9d-138">**内部通信のアーカイブを無効にする**</span><span class="sxs-lookup"><span data-stu-id="9da9d-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="9da9d-139">**外部通信のアーカイブを有効にする**</span><span class="sxs-lookup"><span data-stu-id="9da9d-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="9da9d-140">**外部通信のアーカイブを無効にする**</span><span class="sxs-lookup"><span data-stu-id="9da9d-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="9da9d-141">**更新**[**アーカイブポリシー** ] ページを更新して、すべてのアーカイブポリシーのオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9da9d-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="9da9d-142">Exchange の統合を含むアーカイブ機能の詳細については、「skype for [Business server 2015 でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」、「skype [for business server 2015 の](../../deploy/deploy-archiving/deploy-archiving.md)アーカイブの展開」、「 [skype for business server 2015 でのアーカイブの管理](../../manage/archiving/archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9da9d-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

