---
title: アーカイブ構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 4d618e8fe31b0bdef85c4ef2cbd606818850cadc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200971"
---
# <a name="archiving-configuration"></a><span data-ttu-id="a15b3-103">アーカイブ構成</span><span class="sxs-lookup"><span data-stu-id="a15b3-103">Archiving Configuration</span></span>
 
<span data-ttu-id="a15b3-104">アーカイブ ビジネス サーバー展開は、有効にすると、次のオプションを無効にするなど、Skype のオプションを制御するアーカイブ構成を使用するとします。</span><span class="sxs-lookup"><span data-stu-id="a15b3-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="a15b3-105">アーカイブで障害が発生した場合にインスタント メッセージング (IM) または電話会議のセッションをブロックする</span><span class="sxs-lookup"><span data-stu-id="a15b3-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="a15b3-106">Exchange 2013 が置かれているユーザーに対して、Exchange 2013 のストレージとの統合</span><span class="sxs-lookup"><span data-stu-id="a15b3-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="a15b3-107">アーカイブされているデータを削除する</span><span class="sxs-lookup"><span data-stu-id="a15b3-107">Purging of archived data</span></span>
    
<span data-ttu-id="a15b3-108">アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト アーカイブ構成およびプール アーカイブ構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="a15b3-109">**グローバル構成**ビジネス サーバーの展開のすべての Skype では既定では、グローバル構成が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="a15b3-110">グローバル構成を編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="a15b3-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="a15b3-111">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="a15b3-112">**サイト構成 (オプション)** 1 つまたは複数のサイト アーカイブ構成、アーカイブ オプションを特定のサイトの管理にあり、それぞれを構成できますを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="a15b3-113">サイト構成は、グローバル構成をオーバーライドしますが、アーカイブ サイトの構成で指定されているサイトに対してのみです。</span><span class="sxs-lookup"><span data-stu-id="a15b3-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="a15b3-114">編集したり、サイトの構成を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="a15b3-115">**プールの構成 (オプション)** 1 つまたは複数のプールのアーカイブ オプションを特定のプールの管理、アーカイブ構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="a15b3-116">プールの構成はグローバル構成およびサイトの構成より優先されますが、アーカイブ ・ プールの構成で指定されたプールにのみ。</span><span class="sxs-lookup"><span data-stu-id="a15b3-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="a15b3-117">プール構成を削除または編集できます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a15b3-118">アーカイブの構成に適用ユーザー Skype ビジネス サーバーが置かれていると、Microsoft Exchange などのアーカイブ ・ データを格納する Exchange を使用する場合は、ユーザーに所属している Exchange 2013 が Exchange 2013 に所属していたユーザーを少し異なる方法で実装されています。</span><span class="sxs-lookup"><span data-stu-id="a15b3-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="a15b3-119">相違点については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="a15b3-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="a15b3-p105">[**アーカイブ構成**] ページには、展開に構成されている各アーカイブ ポリシーが一覧表示されます。また、各アーカイブ構成の名前、対象範囲 (グローバル、サイト、プール)、および有効になっているアーカイブ オプションも示されます。[**アーカイブ構成**] ページからは、以下のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="a15b3-123">**新しい**次のオプションのアーカイブ構成の 1 つ以上を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="a15b3-124">サイト構成</span><span class="sxs-lookup"><span data-stu-id="a15b3-124">Site configuration</span></span>
    
  - <span data-ttu-id="a15b3-125">プール構成</span><span class="sxs-lookup"><span data-stu-id="a15b3-125">Pool configuration</span></span>
    
- <span data-ttu-id="a15b3-126">**編集**ページに記載されているアーカイブ構成のいずれかのオプションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="a15b3-127">このオプションを使用すると、以下を実行できます、します。</span><span class="sxs-lookup"><span data-stu-id="a15b3-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="a15b3-128">**詳細を表示します。** このオプションは、選択したアーカイブ構成のアーカイブのオプションを変更ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="a15b3-129">のみ、一度に 1 つのアーカイブ構成の詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="a15b3-130">**すべてを選択**このオプションでは、リストですべてのアーカイブ構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="a15b3-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="a15b3-131">**削除**このオプションは、選択したすべてのアーカイブ構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="a15b3-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="a15b3-132">**アクション**すばやく有効または IM セッションの構成を編集する代わりに、ページに記載されているすべての構成では、web 会議セッションのアーカイブを無効にするこのオプションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="a15b3-133">アーカイブ構成では、どのようなオプションが指定されている現在の**アクション**で使用できるオプションが異なります。</span><span class="sxs-lookup"><span data-stu-id="a15b3-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="a15b3-134">すべてのオプションは、使用可能な現在のオプションを除く、アーカイブ構成で有効にします。</span><span class="sxs-lookup"><span data-stu-id="a15b3-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="a15b3-135">オプションを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a15b3-135">Options include the following:</span></span>
    
  - <span data-ttu-id="a15b3-136">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="a15b3-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="a15b3-137">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="a15b3-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="a15b3-138">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="a15b3-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="a15b3-139">**更新**すべてのアーカイブ構成オプションの状態を確認するのには**アーカイブの構成**ページを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="a15b3-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="a15b3-140">アーカイブ機能および Exchange の統合などの機能の詳細について「[ビジネス サーバー 2015 の Skype でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)、[ビジネス サーバー 2015 Skype アーカイブの展開](../../deploy/deploy-archiving/deploy-archiving.md)、および[管理アーカイブの Skype での使用」を参照してください。ビジネス サーバー 2015年](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="a15b3-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

