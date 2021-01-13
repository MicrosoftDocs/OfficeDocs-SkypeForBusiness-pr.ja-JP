---
title: アーカイブ ポリシーの新規作成または既存の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: アーカイブ ポリシーを使用して、Skype for Business Server にホームを持つユーザーの展開での内部通信と外部通信のアーカイブを制御します。 アーカイブ ポリシーには、グローバル ポリシーとオプションの 1 つ以上のサイト ポリシーやユーザー ポリシーが含まれます。
ms.openlocfilehash: 71ffa03d0d3af8ea98fcc9ded17d4e3498e1705e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820317"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="2b63a-104">アーカイブ ポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="2b63a-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="2b63a-105">アーカイブ ポリシーを使用して、Skype for Business Server にホームを持つユーザーの展開での内部通信と外部通信のアーカイブを制御します。</span><span class="sxs-lookup"><span data-stu-id="2b63a-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="2b63a-106">アーカイブ ポリシーには、グローバル ポリシーとオプションの 1 つ以上のサイト ポリシーやユーザー ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b63a-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="2b63a-107">**グローバル ポリシー** グローバル ポリシーは、すべての Skype for Business Server 展開で既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="2b63a-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="2b63a-108">グローバル ポリシーを編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b63a-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="2b63a-109">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2b63a-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="2b63a-110">**サイト ポリシー (オプション)** 特定のサイトの内部通信または外部通信のアーカイブを有効または無効に構成できる 1 つ以上のサイト アーカイブ ポリシーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2b63a-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="2b63a-111">サイト ポリシーはグローバル ポリシーより優先されますが、適用されるのはアーカイブ ポリシーに含まれるサイトのみです。</span><span class="sxs-lookup"><span data-stu-id="2b63a-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="2b63a-112">サイト ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="2b63a-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="2b63a-113">**ユーザー ポリシー (オプション)** 特定のユーザーの内部通信または外部通信のアーカイブを有効または無効に構成できる、1 つ以上のユーザー アーカイブ ポリシーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2b63a-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="2b63a-114">ユーザー ポリシーはグローバル ポリシーまたはサイト ポリシーより優先されますが、適用されるのはユーザー ポリシーが割り当てられたユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="2b63a-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="2b63a-115">ユーザーポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="2b63a-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2b63a-116">Exchange 統合を使用してアーカイブ データを Microsoft Exchange に保存する場合、Exchange ポリシーは Exchange にホームのユーザーのアーカイブを制御します。</span><span class="sxs-lookup"><span data-stu-id="2b63a-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="2b63a-117">これらのユーザーのアーカイブを有効にするには、ユーザーのメールボックスを保持のIn-Placeがあります。</span><span class="sxs-lookup"><span data-stu-id="2b63a-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="2b63a-118">新規または既存のアーカイブ ポリシーの設定を構成するには、次のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2b63a-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="2b63a-119">**名前** 各アーカイブ ポリシーには名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="2b63a-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="2b63a-120">名前は、追加または編集するポリシーの種類によって決まります。</span><span class="sxs-lookup"><span data-stu-id="2b63a-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="2b63a-121">**グローバル ポリシー** 既定の名前は Global です。</span><span class="sxs-lookup"><span data-stu-id="2b63a-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="2b63a-122">わかりやすい名前に変更できます。</span><span class="sxs-lookup"><span data-stu-id="2b63a-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="2b63a-123">例: "Contoso 北米組織"。</span><span class="sxs-lookup"><span data-stu-id="2b63a-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="2b63a-124">**サイト ポリシー** このダイアログ ボックスに表示されるサイトには、展開で使用可能なすべてのサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b63a-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="2b63a-125">1 つのサイトをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="2b63a-125">Click a single site to select it.</span></span> <span data-ttu-id="2b63a-126">例: "レドモンド データ センター"。</span><span class="sxs-lookup"><span data-stu-id="2b63a-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="2b63a-127">**ユーザー ポリシー** 特定のユーザーの名前、組織内のユーザー グループまたはチームの名前など、適切な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b63a-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="2b63a-128">たとえば、「法務部門」とします。</span><span class="sxs-lookup"><span data-stu-id="2b63a-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="2b63a-129">**説明** これはオプションです。</span><span class="sxs-lookup"><span data-stu-id="2b63a-129">**Description** This is optional.</span></span> <span data-ttu-id="2b63a-130">ポリシーの範囲や使用など、追加の詳細を提供するために使用します。</span><span class="sxs-lookup"><span data-stu-id="2b63a-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="2b63a-131">たとえば、他のサイトの法務部門と調整します。</span><span class="sxs-lookup"><span data-stu-id="2b63a-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="2b63a-132">**内部通信をアーカイブする** 内部ネットワーク上の通信のアーカイブを有効にするには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2b63a-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="2b63a-133">既定では、これはどのポリシーでも有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="2b63a-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="2b63a-134">**外部通信をアーカイブする** このチェック ボックスをオンにすると、リモート ユーザー (匿名ユーザーや PIC 設定ユーザーを含む) やフェデレーション パートナーなどの外部ユーザーが含まれる通信のアーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2b63a-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="2b63a-135">既定では、これはどのポリシーでも有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="2b63a-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="2b63a-136">Exchange 統合を含むアーカイブ機能の詳細については [、「Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md)でのアーカイブの計画」、Skype for [Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)のアーカイブの展開、および Skype for [Business Server](../../../manage/archiving/archiving.md)でのアーカイブの管理を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b63a-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

