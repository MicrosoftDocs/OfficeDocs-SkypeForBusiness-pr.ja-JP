---
title: アーカイブ構成の新規作成または既存の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: アーカイブ構成を使用して、展開のアーカイブ オプションを制御します。 アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト構成およびプール構成が含まれます。
ms.openlocfilehash: 77d1be61be3a1bad063bb7f32957937f182094e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812257"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a><span data-ttu-id="03ff5-104">アーカイブ構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="03ff5-104">Archiving Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="03ff5-105">アーカイブ構成を使用して、展開のアーカイブ オプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="03ff5-105">You use Archiving configurations to control archiving options for your deployment.</span></span> <span data-ttu-id="03ff5-106">アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト構成およびプール構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-106">Archiving configurations include the global configuration, and, optionally, one or more site and pool configurations:</span></span>
  
- <span data-ttu-id="03ff5-107">**グローバル構成** グローバル構成は既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-107">**Global configuration** The global configuration is created by default.</span></span> <span data-ttu-id="03ff5-108">グローバル構成を編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="03ff5-108">You can edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="03ff5-109">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="03ff5-110">**サイトの構成 (オプション)** 特定のサイトのアーカイブ オプションを制御するために構成できる、1 つ以上のサイト アーカイブ構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-110">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="03ff5-111">サイト構成はグローバル構成より優先されますが、アーカイブ サイト構成で指定されたサイトに対してだけ優先されます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-111">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="03ff5-112">サイト構成を編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-112">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="03ff5-113">**プールの構成 (オプション)** 1 つ以上のプール アーカイブ構成を指定して、特定のプールのアーカイブ オプションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-113">**Pool configuration (optional)** You can specify one or more pool Archiving configurations, to control archiving options for a specific pool.</span></span> <span data-ttu-id="03ff5-114">プール構成はグローバル構成とサイト構成より優先されますが、アーカイブ プール構成で指定されたプールに対してだけ優先されます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-114">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="03ff5-115">プール構成を編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-115">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="03ff5-116">アーカイブ構成は、Skype for Business Server にホームのユーザーに適用され、Microsoft Exchange 統合オプションを有効にして Exchange を使用してアーカイブ データを Microsoft Exchange に保存する場合は、Exchange にホームのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-116">Archiving configurations apply to users homed on Skype for Business Server, and, if you enable the Microsoft Exchange integration option to use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange.</span></span> <span data-ttu-id="03ff5-117">ただし、一部のオプションは、次のセクションで説明するように、Exchange にホームを持つユーザーに対して少し異なる方法で実装されます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-117">However, some options are implemented slightly differently for users homed on Exchange, as described in the next section.</span></span> 
  
<span data-ttu-id="03ff5-118">新規または既存のアーカイブ構成の設定を構成するには、次のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="03ff5-118">To configure the settings for a new or existing Archiving configuration, specify the following options:</span></span>
- <span data-ttu-id="03ff5-119">**名前** 各アーカイブ構成には名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="03ff5-119">**Name** Each Archiving configuration requires a name.</span></span> <span data-ttu-id="03ff5-120">名前は、追加または編集する構成の種類によって決まります。</span><span class="sxs-lookup"><span data-stu-id="03ff5-120">The name is determined by the type of configuration you are adding or editing:</span></span>
    
  - <span data-ttu-id="03ff5-121">**グローバル構成** 既定の名前は Global です。</span><span class="sxs-lookup"><span data-stu-id="03ff5-121">**Global configuration** The default name is Global.</span></span> <span data-ttu-id="03ff5-122">例: "Contoso 北米組織"。</span><span class="sxs-lookup"><span data-stu-id="03ff5-122">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="03ff5-123">**サイトの構成** 一覧には、展開で使用可能なサイトが含まれている。</span><span class="sxs-lookup"><span data-stu-id="03ff5-123">**Site configuration** The list contains the available sites in your deployment.</span></span> <span data-ttu-id="03ff5-124">1 つのサイトをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="03ff5-124">Click a single site to select it.</span></span> <span data-ttu-id="03ff5-125">例: "レドモンド データ センター"。</span><span class="sxs-lookup"><span data-stu-id="03ff5-125">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="03ff5-126">**プールの構成** 適切な名前を指定します。この名前には、展開内の特定のフロントエンド プールまたは Standard Edition サーバーの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-126">**Pool configuration** Specify an appropriate name, which can be the name of a specific Front End pool or Standard Edition Server in your deployment.</span></span> <span data-ttu-id="03ff5-127">たとえば、「マーケティング部門」とします。</span><span class="sxs-lookup"><span data-stu-id="03ff5-127">For example, Marketing Division.</span></span>
    
- <span data-ttu-id="03ff5-128">**説明** これはオプションです。</span><span class="sxs-lookup"><span data-stu-id="03ff5-128">**Description** This is optional.</span></span> <span data-ttu-id="03ff5-129">構成の範囲や使用など、追加の詳細を提供するために使用します。</span><span class="sxs-lookup"><span data-stu-id="03ff5-129">Use it to provide additional details, such as the scope or use of the configuration.</span></span> <span data-ttu-id="03ff5-130">たとえば、他のサイトの法務部門と調整します。</span><span class="sxs-lookup"><span data-stu-id="03ff5-130">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="03ff5-131">**アーカイブ設定** 次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="03ff5-131">**Archiving setting** Options include the following:</span></span>
    
  - <span data-ttu-id="03ff5-132">[**IM セッションをアーカイブする**]</span><span class="sxs-lookup"><span data-stu-id="03ff5-132">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="03ff5-133">[**IM および Web 会議セッションをアーカイブする**]</span><span class="sxs-lookup"><span data-stu-id="03ff5-133">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="03ff5-134">[**アーカイブを無効にする**]</span><span class="sxs-lookup"><span data-stu-id="03ff5-134">**Disable archiving**</span></span>
    
- <span data-ttu-id="03ff5-135">**アーカイブに失敗した場合のインスタント メッセージング (IM)** セッションまたは Web 会議セッションのブロックエラーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="03ff5-135">**Block instant messaging (IM) or web conferencing sessions if archiving fails** Failures include the following:</span></span>
    
  - <span data-ttu-id="03ff5-136">**IM** A failure could be a full database or problem with the storage service.</span><span class="sxs-lookup"><span data-stu-id="03ff5-136">**IM** A failure could be a full database or problem with the storage service.</span></span> <span data-ttu-id="03ff5-137">この場合、アーカイブが有効になっているユーザーでは IM がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-137">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
  - <span data-ttu-id="03ff5-138">**会議** ファイル共有が使用できないか、記憶域サービスに問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03ff5-138">**Conferencing** A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="03ff5-139">この場合、障害発生時にプールにホストされているすべてのアクティブな会議が制限モードに切り替えられ、新しい会議をアクティブ化できません。</span><span class="sxs-lookup"><span data-stu-id="03ff5-139">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="03ff5-140">障害から回復した後、IM および会議は自動的に回復します。</span><span class="sxs-lookup"><span data-stu-id="03ff5-140">Both IM and conferencing automatically recover after the failures are corrected.</span></span>
    
- <span data-ttu-id="03ff5-141">**Microsoft Exchange の統合** Exchange にホームを持つユーザーが含まれる場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="03ff5-141">**Microsoft Exchange integration** Select this option if you have users who are homed on Exchange.</span></span> <span data-ttu-id="03ff5-142">このオプションでは、Exchange を使用して、メールボックスが保留リストに設定されている場合に、それらのユーザーのデータIn-Placeされます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-142">With this option, Exchange is used to store data for those users, if their mailboxes have been placed on In-Place Hold.</span></span> <span data-ttu-id="03ff5-143">すべてのユーザーが Exchange にホームである場合は、アーカイブ データを保存するために個別の SQL Server データベースを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03ff5-143">If all your users are homed on Exchange, you do not need to set up separate SQL Server databases for storage of archiving data.</span></span>
    
- <span data-ttu-id="03ff5-144">**アーカイブ データの削除を有効にする** 削除を有効にするには、このオプションを選択し、次のような削除オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="03ff5-144">**Enable purging of archiving data** Select this option to enable purging and specify purging options, which include the following:</span></span>
    
  - <span data-ttu-id="03ff5-145">指定した特定の日数の後で削除する。</span><span class="sxs-lookup"><span data-stu-id="03ff5-145">Purging after a specific number of days that you specify.</span></span>
    
  - <span data-ttu-id="03ff5-146">アーカイブ データがエクスポートされた後の削除 (Microsoft Exchange 統合を有効にした場合、Exchange にアップロードされたデータが含まれます)。</span><span class="sxs-lookup"><span data-stu-id="03ff5-146">Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03ff5-147">Microsoft Exchange 統合を有効にした場合、Exchange にホームとして、およびメールボックスが保持されているユーザーの削除は、Exchange によってIn-Place制御されます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-147">If you enable Microsoft Exchange integration, purging for users homed on Exchange and with their mailboxes placed on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="03ff5-148">唯一の例外は、Lync Server ファイル共有に格納されている会議ファイルです。</span><span class="sxs-lookup"><span data-stu-id="03ff5-148">The only exception is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="03ff5-149">これらのファイルは、アーカイブ データがエクスポートされた後でデータを削除するオプションを選択した場合はファイルがエクスポートされた後 (Exchange にアップロードされた後)、保持する最大日数を指定した場合は指定した最大日数経過後にのみファイル共有から削除されます。</span><span class="sxs-lookup"><span data-stu-id="03ff5-149">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span> 
  
<span data-ttu-id="03ff5-150">Exchange 統合を含むアーカイブ機能の詳細については [、「Plan for archiving in Skype for Business Server,](../../../plan-your-deployment/archiving/archiving.md) [Deploy archiving for Skype for Business Server,](../../../deploy/deploy-archiving/deploy-archiving.md)and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03ff5-150">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

