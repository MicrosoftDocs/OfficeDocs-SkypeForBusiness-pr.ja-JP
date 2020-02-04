---
title: アーカイブポリシー新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: アーカイブポリシーを使用して、Skype for Business Server を使っているユーザーの展開での内部および外部通信のアーカイブを制御します。 アーカイブ ポリシーには、グローバル ポリシーとオプションの 1 つ以上のサイト ポリシーやユーザー ポリシーが含まれます。
ms.openlocfilehash: 1eb1f0060e80fbb7d325f5fbe1b7a247d6d006b6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691222"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="029de-104">アーカイブ ポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="029de-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="029de-105">アーカイブポリシーを使用して、Skype for Business Server を使っているユーザーの展開での内部および外部通信のアーカイブを制御します。</span><span class="sxs-lookup"><span data-stu-id="029de-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="029de-106">アーカイブ ポリシーには、グローバル ポリシーとオプションの 1 つ以上のサイト ポリシーやユーザー ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="029de-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="029de-107">**グローバルポリシー**グローバルポリシーは、既定ですべての Skype for Business Server 展開に作成されます。</span><span class="sxs-lookup"><span data-stu-id="029de-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="029de-108">グローバル ポリシーを編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="029de-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="029de-109">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="029de-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="029de-110">**サイトポリシー (オプション)** 1つまたは複数のサイトアーカイブポリシーを指定できます。各ポリシーは、特定のサイトの内部または外部通信のアーカイブを有効または無効にするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="029de-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="029de-111">サイト ポリシーはグローバル ポリシーより優先されますが、適用されるのはアーカイブ ポリシーに含まれるサイトのみです。</span><span class="sxs-lookup"><span data-stu-id="029de-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="029de-112">サイト ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="029de-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="029de-113">**ユーザーポリシー (オプション)** 1つまたは複数のユーザーアーカイブポリシーを指定できます。各ポリシーは、特定のユーザーの内部または外部通信のアーカイブを有効または無効にするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="029de-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="029de-114">ユーザー ポリシーはグローバル ポリシーまたはサイト ポリシーより優先されますが、適用されるのはユーザー ポリシーが割り当てられたユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="029de-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="029de-115">ユーザー ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="029de-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="029de-116">Microsoft Exchange でアーカイブデータを保存するために Exchange の統合を使用している場合、exchange のポリシーでは、Exchange を使用しているユーザーのアーカイブが制御されます。</span><span class="sxs-lookup"><span data-stu-id="029de-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="029de-117">これらのユーザーのアーカイブを有効にするには、ユーザーのメールボックスがインプレースホールドに配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="029de-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="029de-118">新規または既存のアーカイブ ポリシーの設定を構成するには、次のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="029de-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="029de-119">**名前**各アーカイブポリシーには名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="029de-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="029de-120">名前は、追加または編集するポリシーの種類によって決まります。</span><span class="sxs-lookup"><span data-stu-id="029de-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="029de-121">**グローバルポリシー**既定の名前はグローバルです。</span><span class="sxs-lookup"><span data-stu-id="029de-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="029de-122">よりわかりやすい名前に変更できます。</span><span class="sxs-lookup"><span data-stu-id="029de-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="029de-123">例: "Contoso 北米組織"。</span><span class="sxs-lookup"><span data-stu-id="029de-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="029de-124">**サイトポリシー**このダイアログボックスに表示されるサイトには、展開で利用可能なすべてのサイトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="029de-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="029de-125">1 つのサイトをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="029de-125">Click a single site to select it.</span></span> <span data-ttu-id="029de-126">例: "レドモンド データ センター"。</span><span class="sxs-lookup"><span data-stu-id="029de-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="029de-127">**ユーザーポリシー**特定のユーザーの名前、または組織内のユーザーグループやチームの名前など、適切な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="029de-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="029de-128">たとえば、法務部門などです。</span><span class="sxs-lookup"><span data-stu-id="029de-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="029de-129">**説明**これは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="029de-129">**Description** This is optional.</span></span> <span data-ttu-id="029de-130">この情報を使って、ポリシーのスコープまたは用途などの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="029de-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="029de-131">たとえば、他のサイトの法務部門との調整を行います。</span><span class="sxs-lookup"><span data-stu-id="029de-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="029de-132">**内部通信をアーカイブ**するこのチェックボックスをオンにすると、内部ネットワーク上の通信のアーカイブが有効になります。</span><span class="sxs-lookup"><span data-stu-id="029de-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="029de-133">既定では、この設定はどのポリシーでも有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="029de-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="029de-134">**外部通信をアーカイブ**するこのチェックボックスをオンにすると、リモートユーザー (匿名と PIC の設定ユーザーを含む)、フェデレーションパートナーなどの外部ユーザーを含む通信のアーカイブを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="029de-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="029de-135">既定では、この設定はどのポリシーでも有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="029de-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="029de-136">Exchange の統合を含むアーカイブ機能の詳細については、「skype for [Business server のアーカイブの計画](../../../plan-your-deployment/archiving/archiving.md)」、「skype for business server[のアーカイブの展開](../../../deploy/deploy-archiving/deploy-archiving.md)」、「 [skype for business Server でのアーカイブの管理](../../../manage/archiving/archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="029de-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

