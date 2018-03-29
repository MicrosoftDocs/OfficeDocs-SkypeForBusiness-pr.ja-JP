---
title: アーカイブ ポリシー
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: アーカイブ ポリシーを使用して有効にして、無効にするには、ユーザーのアーカイブ サーバーのビジネスの Skype が置かれています。 それぞれのアーカイブ ポリシーでは、次のどちらかまたは両方のアーカイブを有効化または無効化できます。
ms.openlocfilehash: eea3f7eb71bcf3928e2976b9468cea6bf94b4ab1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-policy"></a><span data-ttu-id="653b4-104">アーカイブ ポリシー</span><span class="sxs-lookup"><span data-stu-id="653b4-104">Archiving Policy</span></span>
 
<span data-ttu-id="653b4-105">アーカイブ ポリシーを使用して有効にして、無効にするには、ユーザーのアーカイブ サーバーのビジネスの Skype が置かれています。</span><span class="sxs-lookup"><span data-stu-id="653b4-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="653b4-106">それぞれのアーカイブ ポリシーでは、次のどちらかまたは両方のアーカイブを有効化または無効化できます。</span><span class="sxs-lookup"><span data-stu-id="653b4-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="653b4-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="653b4-107">Internal communications</span></span>
    
- <span data-ttu-id="653b4-108">外部通信 (内部ネットワークの外部のユーザーが 1 人以上含まれる通信)</span><span class="sxs-lookup"><span data-stu-id="653b4-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="653b4-109">アーカイブ ポリシーには、グローバル ポリシーと、オプションで 1 つ以上のサイト アーカイブ ポリシーおよびユーザー アーカイブ ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="653b4-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="653b4-110">**グローバル ポリシー**既定ではすべての展開では、グローバル ポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="653b4-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="653b4-111">グローバル ポリシーを編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="653b4-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="653b4-112">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="653b4-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="653b4-113">**(省略可能) のサイト ポリシー**1 つまたは複数サイト アーカイブ ポリシーを有効にして、1 つのサイトの内部または外部通信のアーカイブを無効にするを構成するそれぞれのことができますを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="653b4-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="653b4-114">サイト ポリシーは、グローバル ポリシーをオーバーライドしますが、アーカイブ サイト ポリシーで指定されているサイトに対してのみです。</span><span class="sxs-lookup"><span data-stu-id="653b4-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="653b4-115">サイト ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="653b4-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="653b4-116">**(省略可能) ユーザーのポリシー**1 つまたは複数ユーザー アーカイブ ポリシーを有効にして、特定のユーザーまたはユーザー グループ用の内部または外部通信のアーカイブを無効にするを構成するそれぞれのことを指定できます。</span><span class="sxs-lookup"><span data-stu-id="653b4-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="653b4-117">ユーザー ポリシーは、グローバル ポリシーおよびサイト ポリシーは、ユーザーとユーザー ・ レベルのアーカイブ ポリシーの割り当て対象となるユーザー グループについては、オーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="653b4-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="653b4-118">ユーザー ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="653b4-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="653b4-119">アーカイブ ・ ポリシーの適用にのみユーザーは、Skype ビジネス サーバーのホームです。</span><span class="sxs-lookup"><span data-stu-id="653b4-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="653b4-120">格納する Exchange の統合を使用する場合 Microsoft Exchange では、Exchange 2013 のポリシーでは、内のデータをアーカイブするアーカイブをユーザー コントロールが置かれている Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="653b4-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="653b4-121">それらのユーザーのアーカイブを有効にするには、インプレース保持をユーザーのメールボックスを配置しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="653b4-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="653b4-p107">[**アーカイブ ポリシー**] ページには、展開に構成されている各アーカイブ ポリシーが一覧表示されます。また、各アーカイブ ポリシーの名前、対象範囲 (グローバル、サイト、ユーザー)、および有効になっているアーカイブ オプションも示されます。[**アーカイブ ポリシー**] ページからは、以下のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="653b4-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="653b4-125">**新しい**次の省略可能なアーカイブ ・ ポリシーのそれぞれの 1 つ以上を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="653b4-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="653b4-126">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="653b4-126">Site policy</span></span>
    
  - <span data-ttu-id="653b4-127">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="653b4-127">User policy</span></span>
    
- <span data-ttu-id="653b4-128">**編集**ページに記載されているアーカイブ ・ ポリシーのいずれかのオプションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="653b4-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="653b4-129">このオプションを使用すると、以下を実行できます、します。</span><span class="sxs-lookup"><span data-stu-id="653b4-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="653b4-130">[**詳細の表示**]   アーカイブ ポリシーのアーカイブ オプションを変更できるダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="653b4-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="653b4-131">[**すべて選択**]   一覧のアーカイブ ポリシーをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="653b4-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="653b4-132">[**削除**]   選択したすべてのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="653b4-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="653b4-133">**アクション**すばやく有効またはポリシーを編集する代わりに、ページに記載されているすべてのポリシーで、内部または外部通信のアーカイブを無効にするこのオプションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="653b4-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="653b4-134">アーカイブ ポリシーでどのようなオプションが指定されている現在の**アクション**で使用できるオプションが異なります。</span><span class="sxs-lookup"><span data-stu-id="653b4-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="653b4-135">すべてのオプションは、使用可能な現在のオプションを除く、アーカイブ ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="653b4-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="653b4-136">オプションを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="653b4-136">Options include the following:</span></span>
    
  - <span data-ttu-id="653b4-137">**内部通信のアーカイブを有効にする**</span><span class="sxs-lookup"><span data-stu-id="653b4-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="653b4-138">**内部通信のアーカイブを無効にする**</span><span class="sxs-lookup"><span data-stu-id="653b4-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="653b4-139">**外部通信のアーカイブを有効にする**</span><span class="sxs-lookup"><span data-stu-id="653b4-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="653b4-140">**外部通信のアーカイブを無効にする**</span><span class="sxs-lookup"><span data-stu-id="653b4-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="653b4-141">**更新**すべてのアーカイブ ポリシーのオプションの状態を確認するのには**アーカイブ ポリシー**ページを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="653b4-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="653b4-142">アーカイブ機能および Exchange の統合などの機能の詳細について「[ビジネス サーバー 2015 の Skype でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)、[ビジネス サーバー 2015 Skype アーカイブの展開](../../deploy/deploy-archiving/deploy-archiving.md)、および[管理アーカイブの Skype での使用」を参照してください。ビジネス サーバー 2015年](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="653b4-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

