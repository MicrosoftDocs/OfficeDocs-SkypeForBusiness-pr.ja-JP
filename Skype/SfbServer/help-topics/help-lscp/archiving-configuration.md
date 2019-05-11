---
title: アーカイブ構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: アーカイブ ビジネス サーバー展開は、有効にすると、次のオプションを無効にするなど、Skype のオプションを制御するアーカイブ構成を使用するとします。
ms.openlocfilehash: ac03dd94a83a755c06e88b2abce27bde9625453a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887140"
---
# <a name="archiving-configuration"></a><span data-ttu-id="8c17d-103">アーカイブ構成</span><span class="sxs-lookup"><span data-stu-id="8c17d-103">Archiving Configuration</span></span>
 
<span data-ttu-id="8c17d-104">アーカイブ ビジネス サーバー展開は、有効にすると、次のオプションを無効にするなど、Skype のオプションを制御するアーカイブ構成を使用するとします。</span><span class="sxs-lookup"><span data-stu-id="8c17d-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="8c17d-105">アーカイブで障害が発生した場合にインスタント メッセージング (IM) または電話会議のセッションをブロックする</span><span class="sxs-lookup"><span data-stu-id="8c17d-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="8c17d-106">Exchange 2013 が置かれているユーザーに対して、Exchange 2013 のストレージとの統合</span><span class="sxs-lookup"><span data-stu-id="8c17d-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="8c17d-107">アーカイブされているデータを削除する</span><span class="sxs-lookup"><span data-stu-id="8c17d-107">Purging of archived data</span></span>
    
<span data-ttu-id="8c17d-108">アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト アーカイブ構成およびプール アーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="8c17d-109">**グローバル構成**ビジネス サーバーの展開のすべての Skype では既定では、グローバル構成が作成されます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="8c17d-110">グローバル構成を編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="8c17d-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="8c17d-111">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="8c17d-112">**サイト構成 (オプション)** 1 つまたは複数のサイト アーカイブ構成、アーカイブ オプションを特定のサイトの管理にあり、それぞれを構成できますを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="8c17d-113">サイト構成は、グローバル構成をオーバーライドしますが、アーカイブ サイトの構成で指定されているサイトに対してのみです。</span><span class="sxs-lookup"><span data-stu-id="8c17d-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="8c17d-114">編集したり、サイトの構成を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="8c17d-115">**プールの構成 (オプション)** 1 つまたは複数のプールのアーカイブ オプションを特定のプールの管理、アーカイブ構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="8c17d-116">プールの構成はグローバル構成およびサイトの構成より優先されますが、アーカイブ ・ プールの構成で指定されたプールにのみ。</span><span class="sxs-lookup"><span data-stu-id="8c17d-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="8c17d-117">プール構成を削除または編集できます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8c17d-118">アーカイブの構成に適用ユーザー Skype ビジネス サーバーが置かれていると、Microsoft Exchange などのアーカイブ ・ データを格納する Exchange を使用する場合は、ユーザーに所属している Exchange 2013 が Exchange 2013 に所属していたユーザーを少し異なる方法で実装されています。</span><span class="sxs-lookup"><span data-stu-id="8c17d-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="8c17d-119">相違点については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="8c17d-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="8c17d-p105">[**アーカイブ構成**] ページには、展開に構成されている各アーカイブ ポリシーが一覧表示されます。また、各アーカイブ構成の名前、対象範囲 (グローバル、サイト、プール)、および有効になっているアーカイブ オプションも示されます。[**アーカイブ構成**] ページからは、以下のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="8c17d-123">**新しい**次のオプションのアーカイブ構成の 1 つ以上を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="8c17d-124">サイト構成</span><span class="sxs-lookup"><span data-stu-id="8c17d-124">Site configuration</span></span>
    
  - <span data-ttu-id="8c17d-125">プール構成</span><span class="sxs-lookup"><span data-stu-id="8c17d-125">Pool configuration</span></span>
    
- <span data-ttu-id="8c17d-126">**編集**ページに記載されているアーカイブ構成のいずれかのオプションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="8c17d-127">このオプションを使用すると、以下を実行できます、します。</span><span class="sxs-lookup"><span data-stu-id="8c17d-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="8c17d-128">**詳細を表示します。** このオプションは、選択したアーカイブ構成のアーカイブのオプションを変更ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="8c17d-129">のみ、一度に 1 つのアーカイブ構成の詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="8c17d-130">**すべてを選択**このオプションでは、リストですべてのアーカイブ構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c17d-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="8c17d-131">**削除**このオプションは、選択したすべてのアーカイブ構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="8c17d-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="8c17d-132">**アクション**すばやく有効または IM セッションの構成を編集する代わりに、ページに記載されているすべての構成では、web 会議セッションのアーカイブを無効にするこのオプションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="8c17d-133">アーカイブ構成では、どのようなオプションが指定されている現在の**アクション**で使用できるオプションが異なります。</span><span class="sxs-lookup"><span data-stu-id="8c17d-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="8c17d-134">すべてのオプションは、使用可能な現在のオプションを除く、アーカイブ構成で有効にします。</span><span class="sxs-lookup"><span data-stu-id="8c17d-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="8c17d-135">オプションを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8c17d-135">Options include the following:</span></span>
    
  - <span data-ttu-id="8c17d-136">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="8c17d-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="8c17d-137">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="8c17d-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="8c17d-138">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="8c17d-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="8c17d-139">**更新**すべてのアーカイブ構成オプションの状態を確認するのには**アーカイブの構成**ページを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="8c17d-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="8c17d-140">アーカイブ機能および Exchange の統合などの機能の詳細について「[ビジネス サーバー 2015 の Skype でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)、[ビジネス サーバー 2015 Skype アーカイブの展開](../../deploy/deploy-archiving/deploy-archiving.md)、および[管理アーカイブの Skype での使用」を参照してください。ビジネス サーバー 2015年](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="8c17d-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

