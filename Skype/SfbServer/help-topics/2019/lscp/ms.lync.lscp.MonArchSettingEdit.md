---
title: アーカイブ構成新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 展開のアーカイブ オプションを制御するには、アーカイブ構成を使用します。アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト構成およびプール構成が含まれます。
ms.openlocfilehash: 015a3e3f377fcf73d114aa3f6550534e49f94c0f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795026"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a><span data-ttu-id="57cff-104">アーカイブ構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="57cff-104">Archiving Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="57cff-p102">展開のアーカイブ オプションを制御するには、アーカイブ構成を使用します。アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト構成およびプール構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="57cff-p102">You use Archiving configurations to control archiving options for your deployment. Archiving configurations include the global configuration, and, optionally, one or more site and pool configurations:</span></span>
  
- <span data-ttu-id="57cff-107">**グローバル構成**グローバル構成が既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="57cff-107">**Global configuration** The global configuration is created by default.</span></span> <span data-ttu-id="57cff-108">グローバル構成を編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="57cff-108">You can edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="57cff-109">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="57cff-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="57cff-110">**サイトの構成 (オプション)** 特定のサイトのアーカイブオプションを制御するように構成できる、1つ以上のサイトアーカイブ構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="57cff-110">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="57cff-111">サイト構成は、グローバル構成よりも優先されますが、アーカイブサイト構成で指定したサイトに対してのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="57cff-111">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="57cff-112">サイトの構成を編集または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="57cff-112">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="57cff-113">**プール構成 (オプション)** 1つ以上のプールアーカイブ構成を指定して、特定のプールのアーカイブオプションを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="57cff-113">**Pool configuration (optional)** You can specify one or more pool Archiving configurations, to control archiving options for a specific pool.</span></span> <span data-ttu-id="57cff-114">プール構成は、グローバル構成とサイト構成を上書きしますが、アーカイブプール構成で指定されているプールについてのみ無効にします。</span><span class="sxs-lookup"><span data-stu-id="57cff-114">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="57cff-115">プール構成を編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="57cff-115">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="57cff-116">アーカイブ構成は、Skype for Business Server を使っているユーザーに適用されます。また、Microsoft Exchange 統合オプションを有効にしている場合は、exchange を使用して Microsoft exchange でアーカイブデータを exchange に保存することができます。</span><span class="sxs-lookup"><span data-stu-id="57cff-116">Archiving configurations apply to users homed on Skype for Business Server, and, if you enable the Microsoft Exchange integration option to use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange.</span></span> <span data-ttu-id="57cff-117">ただし、次のセクションで説明するように、一部のオプションは、Exchange を使用しているユーザーによって少し異なります。</span><span class="sxs-lookup"><span data-stu-id="57cff-117">However, some options are implemented slightly differently for users homed on Exchange, as described in the next section.</span></span> 
  
<span data-ttu-id="57cff-118">新規または既存のアーカイブ構成の設定を構成するには、次のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="57cff-118">To configure the settings for a new or existing Archiving configuration, specify the following options:</span></span>
- <span data-ttu-id="57cff-119">**名前**各アーカイブ構成には名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="57cff-119">**Name** Each Archiving configuration requires a name.</span></span> <span data-ttu-id="57cff-120">名前は、追加または編集する構成の種類によって決まります。</span><span class="sxs-lookup"><span data-stu-id="57cff-120">The name is determined by the type of configuration you are adding or editing:</span></span>
    
  - <span data-ttu-id="57cff-121">**グローバル構成**既定の名前はグローバルです。</span><span class="sxs-lookup"><span data-stu-id="57cff-121">**Global configuration** The default name is Global.</span></span> <span data-ttu-id="57cff-122">例: "Contoso 北米組織"。</span><span class="sxs-lookup"><span data-stu-id="57cff-122">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="57cff-123">**サイトの構成**この一覧には、展開で利用可能なサイトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="57cff-123">**Site configuration** The list contains the available sites in your deployment.</span></span> <span data-ttu-id="57cff-124">1 つのサイトをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="57cff-124">Click a single site to select it.</span></span> <span data-ttu-id="57cff-125">例: "レドモンド データ センター"。</span><span class="sxs-lookup"><span data-stu-id="57cff-125">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="57cff-126">**プールの構成**適切な名前を指定します。これは、展開で特定のフロントエンドプールまたは Standard Edition サーバーの名前にすることができます。</span><span class="sxs-lookup"><span data-stu-id="57cff-126">**Pool configuration** Specify an appropriate name, which can be the name of a specific Front End pool or Standard Edition Server in your deployment.</span></span> <span data-ttu-id="57cff-127">たとえば、[マーケティング部門] を選びます。</span><span class="sxs-lookup"><span data-stu-id="57cff-127">For example, Marketing Division.</span></span>
    
- <span data-ttu-id="57cff-128">**説明**これは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="57cff-128">**Description** This is optional.</span></span> <span data-ttu-id="57cff-129">これを使って、構成のスコープや使用などの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="57cff-129">Use it to provide additional details, such as the scope or use of the configuration.</span></span> <span data-ttu-id="57cff-130">たとえば、他のサイトの法務部門との調整を行います。</span><span class="sxs-lookup"><span data-stu-id="57cff-130">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="57cff-131">**アーカイブ設定**次のようなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="57cff-131">**Archiving setting** Options include the following:</span></span>
    
  - <span data-ttu-id="57cff-132">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="57cff-132">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="57cff-133">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="57cff-133">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="57cff-134">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="57cff-134">**Disable archiving**</span></span>
    
- <span data-ttu-id="57cff-135">**アーカイブに失敗した場合は、インスタントメッセージング (IM) または web 会議セッションをブロック**するエラーには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="57cff-135">**Block instant messaging (IM) or web conferencing sessions if archiving fails** Failures include the following:</span></span>
    
  - <span data-ttu-id="57cff-136">**IM** A エラーは、ストレージサービスのデータベース全体または問題の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57cff-136">**IM** A failure could be a full database or problem with the storage service.</span></span> <span data-ttu-id="57cff-137">この場合、アーカイブが有効になっているユーザーでは IM がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="57cff-137">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
  - <span data-ttu-id="57cff-138">**会議**エラーの原因として、ファイル共有が利用できないか、ストレージサービスに問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57cff-138">**Conferencing** A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="57cff-139">この場合、障害発生時にプール内でホストされているアクティブな会議がすべて制限モードに切り替えられ、新しい会議をアクティブにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="57cff-139">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="57cff-140">障害から回復した後、IM および会議は自動的に回復します。</span><span class="sxs-lookup"><span data-stu-id="57cff-140">Both IM and conferencing automatically recover after the failures are corrected.</span></span>
    
- <span data-ttu-id="57cff-141">**Microsoft Exchange の統合**Exchange を使っているユーザーがいる場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="57cff-141">**Microsoft Exchange integration** Select this option if you have users who are homed on Exchange.</span></span> <span data-ttu-id="57cff-142">このオプションを使うと、ユーザーのメールボックスがインプレースホールドに配置されている場合は、そのユーザーのデータを保存するために Exchange が使用されます。</span><span class="sxs-lookup"><span data-stu-id="57cff-142">With this option, Exchange is used to store data for those users, if their mailboxes have been placed on In-Place Hold.</span></span> <span data-ttu-id="57cff-143">すべてのユーザーが Exchange を使用している場合は、アーカイブデータの保存用に個別の SQL Server データベースを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="57cff-143">If all your users are homed on Exchange, you do not need to set up separate SQL Server databases for storage of archiving data.</span></span>
    
- <span data-ttu-id="57cff-144">**アーカイブデータの削除を有効にする**このオプションを選択して、パージを有効にし、次のようなパージオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="57cff-144">**Enable purging of archiving data** Select this option to enable purging and specify purging options, which include the following:</span></span>
    
  - <span data-ttu-id="57cff-145">指定した特定の日数の後で削除する。</span><span class="sxs-lookup"><span data-stu-id="57cff-145">Purging after a specific number of days that you specify.</span></span>
    
  - <span data-ttu-id="57cff-146">アーカイブデータがエクスポートされた後の削除 (Microsoft Exchange との統合を有効にした場合に、Exchange にアップロードされたデータが含まれます)。</span><span class="sxs-lookup"><span data-stu-id="57cff-146">Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="57cff-147">Microsoft Exchange の統合を有効にした場合、Exchange を使用しているユーザーとインプレースホールドに配置されたユーザーのメールボックスは、Exchange によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="57cff-147">If you enable Microsoft Exchange integration, purging for users homed on Exchange and with their mailboxes placed on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="57cff-148">唯一の例外は、Lync Server ファイル共有に保存されている会議ファイルです。</span><span class="sxs-lookup"><span data-stu-id="57cff-148">The only exception is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="57cff-149">これらのファイルは、アーカイブ データがエクスポートされた後でデータを削除するオプションを選択した場合はファイルがエクスポートされた後 (Exchange にアップロードされた後)、保持する最大日数を指定した場合は指定した最大日数経過後にのみファイル共有から削除されます。</span><span class="sxs-lookup"><span data-stu-id="57cff-149">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span> 
  
<span data-ttu-id="57cff-150">Exchange の統合を含むアーカイブ機能の詳細については、「skype for [Business server のアーカイブの計画](../../../plan-your-deployment/archiving/archiving.md)」、「skype for business server[のアーカイブの展開](../../../deploy/deploy-archiving/deploy-archiving.md)」、「 [skype for business Server でのアーカイブの管理](../../../manage/archiving/archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57cff-150">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

