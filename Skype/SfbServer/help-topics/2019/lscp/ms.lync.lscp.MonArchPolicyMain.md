---
title: アーカイブ ポリシー
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: アーカイブ ポリシーを使用して有効にして、無効にするには、ユーザーのアーカイブ サーバーのビジネスの Skype が置かれています。 それぞれのアーカイブ ポリシーでは、次のどちらかまたは両方のアーカイブを有効化または無効化できます。
ms.openlocfilehash: 4af5b5d8eb0f59d6899a73b7de6516d665fe041e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884797"
---
# <a name="archiving-policy"></a><span data-ttu-id="9abda-104">アーカイブ ポリシー</span><span class="sxs-lookup"><span data-stu-id="9abda-104">Archiving Policy</span></span>
 
<span data-ttu-id="9abda-105">アーカイブ ポリシーを使用して有効にして、無効にするには、ユーザーのアーカイブ サーバーのビジネスの Skype が置かれています。</span><span class="sxs-lookup"><span data-stu-id="9abda-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="9abda-106">それぞれのアーカイブ ポリシーでは、次のどちらかまたは両方のアーカイブを有効化または無効化できます。</span><span class="sxs-lookup"><span data-stu-id="9abda-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="9abda-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="9abda-107">Internal communications</span></span>
    
- <span data-ttu-id="9abda-108">外部通信 (内部ネットワークの外部のユーザーが 1 人以上含まれる通信)</span><span class="sxs-lookup"><span data-stu-id="9abda-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="9abda-109">アーカイブ ポリシーには、グローバル ポリシーと、オプションで 1 つ以上のサイト アーカイブ ポリシーおよびユーザー アーカイブ ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9abda-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="9abda-110">**グローバル ポリシー**既定ではすべての展開では、グローバル ポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9abda-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="9abda-111">グローバル ポリシーを編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="9abda-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="9abda-112">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="9abda-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="9abda-113">**(省略可能) のサイト ポリシー**1 つまたは複数サイト アーカイブ ポリシーを有効にして、1 つのサイトの内部または外部通信のアーカイブを無効にするを構成するそれぞれのことができますを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9abda-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="9abda-114">サイト ポリシーは、グローバル ポリシーをオーバーライドしますが、アーカイブ サイト ポリシーで指定されているサイトに対してのみです。</span><span class="sxs-lookup"><span data-stu-id="9abda-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="9abda-115">サイト ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9abda-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="9abda-116">**(省略可能) ユーザーのポリシー**1 つまたは複数ユーザー アーカイブ ポリシーを有効にして、特定のユーザーまたはユーザー グループ用の内部または外部通信のアーカイブを無効にするを構成するそれぞれのことを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9abda-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="9abda-117">ユーザー ポリシーは、グローバル ポリシーおよびサイト ポリシーは、ユーザーとユーザー ・ レベルのアーカイブ ポリシーの割り当て対象となるユーザー グループについては、オーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="9abda-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="9abda-118">ユーザー ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9abda-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9abda-119">アーカイブ ・ ポリシーの適用にのみユーザーは、Skype ビジネス サーバーのホームです。</span><span class="sxs-lookup"><span data-stu-id="9abda-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="9abda-120">Microsoft Exchange などのアーカイブ ・ データを格納する Exchange の統合を使用し、コントロールのアーカイブ ポリシーを交換する場合は、Exchange のユーザーが配置されています。</span><span class="sxs-lookup"><span data-stu-id="9abda-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="9abda-121">それらのユーザーのアーカイブを有効にするには、インプレース保持をユーザーのメールボックスを配置しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="9abda-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="9abda-p107">[**アーカイブ ポリシー**] ページには、展開に構成されている各アーカイブ ポリシーが一覧表示されます。また、各アーカイブ ポリシーの名前、対象範囲 (グローバル、サイト、ユーザー)、および有効になっているアーカイブ オプションも示されます。[**アーカイブ ポリシー**] ページからは、以下のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9abda-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="9abda-125">**新しい**次の省略可能なアーカイブ ・ ポリシーのそれぞれの 1 つ以上を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="9abda-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="9abda-126">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="9abda-126">Site policy</span></span>
    
  - <span data-ttu-id="9abda-127">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="9abda-127">User policy</span></span>
    
- <span data-ttu-id="9abda-128">**編集**ページに記載されているアーカイブ ・ ポリシーのいずれかのオプションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9abda-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="9abda-129">このオプションを使用すると、以下を実行できます、します。</span><span class="sxs-lookup"><span data-stu-id="9abda-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="9abda-130">[**詳細の表示**]   アーカイブ ポリシーのアーカイブ オプションを変更できるダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="9abda-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="9abda-131">[**すべて選択**]   一覧のアーカイブ ポリシーをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="9abda-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="9abda-132">[**削除**]   選択したすべてのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="9abda-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="9abda-133">**アクション**すばやく有効またはポリシーを編集する代わりに、ページに記載されているすべてのポリシーで、内部または外部通信のアーカイブを無効にするこのオプションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9abda-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="9abda-134">アーカイブ ポリシーでどのようなオプションが指定されている現在の**アクション**で使用できるオプションが異なります。</span><span class="sxs-lookup"><span data-stu-id="9abda-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="9abda-135">すべてのオプションは、使用可能な現在のオプションを除く、アーカイブ ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9abda-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="9abda-136">オプションを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="9abda-136">Options include the following:</span></span>
    
  - <span data-ttu-id="9abda-137">**内部通信のアーカイブを有効にする**</span><span class="sxs-lookup"><span data-stu-id="9abda-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="9abda-138">**内部通信のアーカイブを無効にする**</span><span class="sxs-lookup"><span data-stu-id="9abda-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="9abda-139">**外部通信のアーカイブを有効にする**</span><span class="sxs-lookup"><span data-stu-id="9abda-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="9abda-140">**外部通信のアーカイブを無効にする**</span><span class="sxs-lookup"><span data-stu-id="9abda-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="9abda-141">**更新**すべてのアーカイブ ポリシーのオプションの状態を確認するのには**アーカイブ ポリシー**ページを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="9abda-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="9abda-142">アーカイブ機能および Exchange の統合などの機能の詳細について「 [Skype ビジネス サーバーでアーカイブするための計画](../../../plan-your-deployment/archiving/archiving.md)、 [Skype ビジネス サーバー用のアーカイブの展開](../../../deploy/deploy-archiving/deploy-archiving.md)、および[管理は、ビジネス Skype アーカイブの使用」を参照してください。サーバー](../../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="9abda-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

