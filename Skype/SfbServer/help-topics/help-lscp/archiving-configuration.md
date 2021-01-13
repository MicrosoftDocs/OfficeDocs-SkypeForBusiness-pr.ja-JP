---
title: アーカイブ構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: アーカイブ構成を使用して、Skype for Business Server 展開のアーカイブ オプションを制御します。たとえば、次のオプションを有効または無効にします。
ms.openlocfilehash: 96a01579f43833017978fc6067b5a86f9e9951aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827007"
---
# <a name="archiving-configuration"></a><span data-ttu-id="8a647-103">アーカイブ構成</span><span class="sxs-lookup"><span data-stu-id="8a647-103">Archiving Configuration</span></span>
 
<span data-ttu-id="8a647-104">アーカイブ構成を使用して、次のオプションを有効または無効にするなど、Skype for Business Server 展開のアーカイブ オプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="8a647-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="8a647-105">アーカイブで障害が発生した場合にインスタント メッセージング (IM) または電話会議のセッションをブロックする</span><span class="sxs-lookup"><span data-stu-id="8a647-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="8a647-106">Exchange 2013 にホームを置くユーザー向け Exchange 2013 ストレージとの統合</span><span class="sxs-lookup"><span data-stu-id="8a647-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="8a647-107">アーカイブされているデータを削除する</span><span class="sxs-lookup"><span data-stu-id="8a647-107">Purging of archived data</span></span>
    
<span data-ttu-id="8a647-108">アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト アーカイブ構成およびプール アーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a647-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="8a647-109">**グローバル構成** グローバル構成は、すべての Skype for Business Server 展開で既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="8a647-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="8a647-110">グローバル構成を編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a647-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="8a647-111">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="8a647-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="8a647-112">**サイトの構成 (オプション)** 特定のサイトのアーカイブ オプションを制御するために構成できる、1 つ以上のサイト アーカイブ構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8a647-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="8a647-113">サイト構成はグローバル構成より優先されますが、アーカイブ サイト構成で指定されたサイトに対してだけ優先されます。</span><span class="sxs-lookup"><span data-stu-id="8a647-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="8a647-114">サイト構成を編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="8a647-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="8a647-115">**プールの構成 (オプション)** 1 つ以上のプール アーカイブ構成を指定して、特定のプールのアーカイブ オプションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="8a647-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="8a647-116">プール構成はグローバル構成とサイト構成より優先されますが、アーカイブ プール構成で指定されたプールに対してだけ優先されます。</span><span class="sxs-lookup"><span data-stu-id="8a647-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="8a647-117">プール構成を編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="8a647-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8a647-118">アーカイブ構成は、Skype for Business Server にホームのユーザーに適用され、Exchange を使用して Microsoft Exchange にアーカイブ データを保存する場合は、Exchange 2013 にホームのユーザーに適用されますが、Exchange 2013 にホームを持つユーザーに対して実装が若干異なります。</span><span class="sxs-lookup"><span data-stu-id="8a647-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="8a647-119">違いについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="8a647-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="8a647-p105">[**アーカイブ構成**] ページには、展開に構成されている各アーカイブ ポリシーが一覧表示されます。また、各アーカイブ構成の名前、対象範囲 (グローバル、サイト、プール)、および有効になっているアーカイブ オプションも示されます。[**アーカイブ構成**] ページからは、以下のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a647-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="8a647-123">**新規** 次のオプションのアーカイブ構成を 1 つ以上追加できます。</span><span class="sxs-lookup"><span data-stu-id="8a647-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="8a647-124">サイト構成</span><span class="sxs-lookup"><span data-stu-id="8a647-124">Site configuration</span></span>
    
  - <span data-ttu-id="8a647-125">プール構成</span><span class="sxs-lookup"><span data-stu-id="8a647-125">Pool configuration</span></span>
    
- <span data-ttu-id="8a647-126">**編集** ページに一覧表示されているアーカイブ構成のオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8a647-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="8a647-127">このオプションを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8a647-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="8a647-128">**詳細の表示** このオプションを選択すると、選択したアーカイブ構成のアーカイブ オプションを変更できるダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="8a647-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="8a647-129">一度に表示できるアーカイブ構成の詳細は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="8a647-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="8a647-130">**すべて選択** このオプションは、リスト内のすべてのアーカイブ構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a647-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="8a647-131">**削除** このオプションを選択すると、選択したアーカイブ構成すべてが削除されます。</span><span class="sxs-lookup"><span data-stu-id="8a647-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="8a647-132">**アクション** このオプションを使用すると、構成を編集する代わりに、ページに一覧表示されている任意の構成で IM セッションまたは Web 会議セッションのアーカイブをすばやく有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="8a647-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="8a647-133">[操作] で使用 **できるオプション** は、アーカイブ構成で現在指定されているオプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8a647-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="8a647-134">アーカイブ構成で現在有効なオプションを除き、すべてのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a647-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="8a647-135">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8a647-135">Options include the following:</span></span>
    
  - <span data-ttu-id="8a647-136">[**IM セッションをアーカイブする**]</span><span class="sxs-lookup"><span data-stu-id="8a647-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="8a647-137">[**IM および Web 会議セッションをアーカイブする**]</span><span class="sxs-lookup"><span data-stu-id="8a647-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="8a647-138">[**アーカイブを無効にする**]</span><span class="sxs-lookup"><span data-stu-id="8a647-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="8a647-139">**更新** [アーカイブ構成 **] ページを更新** して、すべてのアーカイブ構成のオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8a647-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="8a647-140">Exchange 統合を含むアーカイブ機能の詳細については [、「Plan for archiving in Skype for Business Server 2015,](../../plan-your-deployment/archiving/archiving.md) [Deploy archiving for Skype for Business Server 2015,](../../deploy/deploy-archiving/deploy-archiving.md)and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a647-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

