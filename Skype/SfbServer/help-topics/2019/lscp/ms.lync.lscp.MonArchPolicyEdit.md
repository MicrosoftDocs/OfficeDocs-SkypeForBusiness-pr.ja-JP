---
title: アーカイブ ・ ポリシーを新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: ビジネス サーバーの Skype は、ホーム ユーザーのために、配置での内部および外部通信のアーカイブを制御するのにには、アーカイブ ポリシーを使用します。 アーカイブ ポリシーには、グローバル ポリシーとオプションの 1 つ以上のサイト ポリシーやユーザー ポリシーが含まれます。
ms.openlocfilehash: 119242c12ea4db94fa3a67c03573177254aa7238
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891188"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="9fa66-104">アーカイブ ポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="9fa66-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="9fa66-105">ビジネス サーバーの Skype は、ホーム ユーザーのために、配置での内部および外部通信のアーカイブを制御するのにには、アーカイブ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9fa66-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="9fa66-106">アーカイブ ポリシーには、グローバル ポリシーとオプションの 1 つ以上のサイト ポリシーやユーザー ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9fa66-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="9fa66-107">**グローバル ポリシー**ビジネス サーバーの展開のすべての Skype では既定では、グローバル ポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9fa66-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="9fa66-108">グローバル ポリシーを編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="9fa66-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="9fa66-109">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="9fa66-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="9fa66-110">**サイトのポリシー (オプション)** 1 つまたは複数サイト アーカイブ ポリシーを有効にして、特定のサイトの内部または外部通信のアーカイブを無効にするを構成するそれぞれのことを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9fa66-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="9fa66-111">サイト ポリシーはグローバル ポリシーより優先されますが、適用されるのはアーカイブ ポリシーに含まれるサイトのみです。</span><span class="sxs-lookup"><span data-stu-id="9fa66-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="9fa66-112">サイト ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9fa66-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="9fa66-113">**(省略可能) ユーザーのポリシー**1 つまたは複数ユーザー アーカイブ ポリシーを有効にして、特定のユーザー用の内部または外部通信のアーカイブを無効にするを構成するそれぞれのことを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9fa66-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="9fa66-114">ユーザー ポリシーはグローバル ポリシーまたはサイト ポリシーより優先されますが、適用されるのはユーザー ポリシーが割り当てられたユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="9fa66-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="9fa66-115">ユーザー ポリシーは編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9fa66-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9fa66-116">Microsoft Exchange などのアーカイブ ・ データを格納する Exchange の統合を使用し、コントロールのアーカイブ ポリシーを交換する場合は、Exchange のユーザーが配置されています。</span><span class="sxs-lookup"><span data-stu-id="9fa66-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="9fa66-117">それらのユーザーのアーカイブを有効にするには、インプレース保持をユーザーのメールボックスを配置しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="9fa66-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="9fa66-118">新規または既存のアーカイブ ポリシーの設定を構成するには、次のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fa66-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="9fa66-119">**名**各アーカイブ ・ ポリシーには、名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="9fa66-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="9fa66-120">名前は、追加または編集するポリシーの種類によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="9fa66-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="9fa66-121">**グローバル ポリシー**既定の名前は、グローバルです。</span><span class="sxs-lookup"><span data-stu-id="9fa66-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="9fa66-122">わかりやすい名前に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9fa66-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="9fa66-123">例: "Contoso 北米組織"。</span><span class="sxs-lookup"><span data-stu-id="9fa66-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="9fa66-124">**サイト ポリシー**このダイアログ ボックスに記載されているサイトには、展開で使用可能なすべてのサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9fa66-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="9fa66-125">1 つのサイトをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="9fa66-125">Click a single site to select it.</span></span> <span data-ttu-id="9fa66-126">例: "レドモンド データ センター"。</span><span class="sxs-lookup"><span data-stu-id="9fa66-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="9fa66-127">**ユーザーのポリシー**特定のユーザーの名前またはユーザーのグループまたは組織内のチームの名前など、適切な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9fa66-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="9fa66-128">たとえば、法務部。</span><span class="sxs-lookup"><span data-stu-id="9fa66-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="9fa66-129">**説明**これは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9fa66-129">**Description** This is optional.</span></span> <span data-ttu-id="9fa66-130">スコープまたはポリシーを使用するなどの追加情報の提供に使用します。</span><span class="sxs-lookup"><span data-stu-id="9fa66-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="9fa66-131">などの他のサイトの法務部門とを調整します。</span><span class="sxs-lookup"><span data-stu-id="9fa66-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="9fa66-132">**内部通信をアーカイブ**内部ネットワーク上の通信のアーカイブを有効にするには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="9fa66-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="9fa66-133">既定では、どのポリシーでこれが無効です。</span><span class="sxs-lookup"><span data-stu-id="9fa66-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="9fa66-134">**外部通信をアーカイブ**(PIC 設定し、匿名ユーザーを含む)、リモート ユーザーなどの外部ユーザーを含めるし、パートナーのフェデレーション通信のアーカイブを有効にするには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="9fa66-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="9fa66-135">既定では、どのポリシーでこれが無効です。</span><span class="sxs-lookup"><span data-stu-id="9fa66-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="9fa66-136">アーカイブ機能および Exchange の統合などの機能の詳細について「 [Skype ビジネス サーバーでアーカイブするための計画](../../../plan-your-deployment/archiving/archiving.md)、 [Skype ビジネス サーバー用のアーカイブの展開](../../../deploy/deploy-archiving/deploy-archiving.md)、および[管理は、ビジネス Skype アーカイブの使用」を参照してください。サーバー](../../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="9fa66-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

