---
title: アーカイブ構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: アーカイブ構成を使用して、次のオプションを有効または無効にするなど、Skype for Business Server の展開のアーカイブオプションを制御します。
ms.openlocfilehash: c8c0b9ba6937dbc0e898da417ce87d6efc25477d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823210"
---
# <a name="archiving-configuration"></a><span data-ttu-id="de79d-103">アーカイブ構成</span><span class="sxs-lookup"><span data-stu-id="de79d-103">Archiving Configuration</span></span>
 
<span data-ttu-id="de79d-104">アーカイブ構成を使用して、次のオプションを有効または無効にするなど、Skype for Business Server の展開のアーカイブオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="de79d-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="de79d-105">アーカイブで障害が発生した場合にインスタント メッセージング (IM) または電話会議のセッションをブロックする</span><span class="sxs-lookup"><span data-stu-id="de79d-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="de79d-106">Exchange 2013 を使用しているユーザー用の Exchange 2013 ストレージとの統合</span><span class="sxs-lookup"><span data-stu-id="de79d-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="de79d-107">アーカイブされているデータを削除する</span><span class="sxs-lookup"><span data-stu-id="de79d-107">Purging of archived data</span></span>
    
<span data-ttu-id="de79d-108">アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト アーカイブ構成およびプール アーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de79d-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="de79d-109">**グローバル構成**グローバル構成は、既定ですべての Skype for Business Server 展開に作成されます。</span><span class="sxs-lookup"><span data-stu-id="de79d-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="de79d-110">グローバル構成を編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="de79d-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="de79d-111">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="de79d-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="de79d-112">**サイトの構成 (オプション)** 特定のサイトのアーカイブオプションを制御するように構成できる、1つ以上のサイトアーカイブ構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="de79d-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="de79d-113">サイト構成は、グローバル構成よりも優先されますが、アーカイブサイト構成で指定したサイトに対してのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="de79d-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="de79d-114">サイトの構成を編集または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="de79d-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="de79d-115">**プール構成 (オプション)** 1つ以上のプールアーカイブ構成を指定して、特定のプールのアーカイブオプションを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="de79d-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="de79d-116">プール構成は、グローバル構成とサイト構成を上書きしますが、アーカイブプール構成で指定されているプールについてのみ無効にします。</span><span class="sxs-lookup"><span data-stu-id="de79d-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="de79d-117">プール構成を編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="de79d-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="de79d-118">アーカイブ構成は、Skype for Business Server を使用しているユーザーに適用されます。また、exchange を使って Microsoft Exchange にアーカイブデータを保存する場合は、exchange 2013 を使用しているユーザー2013に対しては異なる方法で実装されます。</span><span class="sxs-lookup"><span data-stu-id="de79d-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="de79d-119">相違点については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="de79d-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="de79d-p105">[**アーカイブ構成**] ページには、展開に構成されている各アーカイブ ポリシーが一覧表示されます。また、各アーカイブ構成の名前、対象範囲 (グローバル、サイト、プール)、および有効になっているアーカイブ オプションも示されます。[**アーカイブ構成**] ページからは、以下のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="de79d-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="de79d-123">**新規**次のオプションのアーカイブ構成を1つ以上追加できます。</span><span class="sxs-lookup"><span data-stu-id="de79d-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="de79d-124">サイト構成</span><span class="sxs-lookup"><span data-stu-id="de79d-124">Site configuration</span></span>
    
  - <span data-ttu-id="de79d-125">プール構成</span><span class="sxs-lookup"><span data-stu-id="de79d-125">Pool configuration</span></span>
    
- <span data-ttu-id="de79d-126">**編集**ページに表示されているアーカイブ構成のオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="de79d-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="de79d-127">このオプションを使うと、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="de79d-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="de79d-128">**詳細を表示**このオプションでは、選択したアーカイブ構成のアーカイブオプションを変更できるダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de79d-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="de79d-129">一度に表示できるのは、1つのアーカイブ構成の詳細のみです。</span><span class="sxs-lookup"><span data-stu-id="de79d-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="de79d-130">**すべて選択**このオプションでは、リスト内のすべてのアーカイブ構成が選択されます。</span><span class="sxs-lookup"><span data-stu-id="de79d-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="de79d-131">**削除**このオプションでは、選択したすべてのアーカイブ構成が削除されます。</span><span class="sxs-lookup"><span data-stu-id="de79d-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="de79d-132">**操作**このオプションを使うと、構成を編集するのではなく、ページに一覧表示されている任意の構成で、IM セッションまたは web 会議セッションのアーカイブをすばやく有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="de79d-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="de79d-133">[**アクション**] で利用可能なオプションは、アーカイブ構成で現在指定されているオプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="de79d-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="de79d-134">アーカイブ構成で現在有効になっているオプションを除き、すべてのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="de79d-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="de79d-135">次のようなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="de79d-135">Options include the following:</span></span>
    
  - <span data-ttu-id="de79d-136">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="de79d-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="de79d-137">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="de79d-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="de79d-138">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="de79d-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="de79d-139">**更新**[**アーカイブ構成**] ページを更新して、すべてのアーカイブ構成のオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="de79d-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="de79d-140">Exchange の統合を含むアーカイブ機能の詳細については、「skype for [Business server 2015 でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」、「skype [for business server 2015 の](../../deploy/deploy-archiving/deploy-archiving.md)アーカイブの展開」、「 [skype for business server 2015 でのアーカイブの管理](../../manage/archiving/archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de79d-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

