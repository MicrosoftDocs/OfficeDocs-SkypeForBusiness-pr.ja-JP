---
title: アーカイブ構成を新規作成または既存の編集
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 展開のアーカイブ オプションを制御するには、アーカイブ構成を使用します。アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト構成およびプール構成が含まれます。
ms.openlocfilehash: 2167b0ccc65a9bfc6ae731add156fa0b0925eaf2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234846"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a><span data-ttu-id="04b1f-104">アーカイブ構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="04b1f-104">Archiving Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="04b1f-p102">展開のアーカイブ オプションを制御するには、アーカイブ構成を使用します。アーカイブ構成には、グローバル構成と、オプションで 1 つ以上のサイト構成およびプール構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-p102">You use Archiving configurations to control archiving options for your deployment. Archiving configurations include the global configuration, and, optionally, one or more site and pool configurations:</span></span>
  
- <span data-ttu-id="04b1f-107">**グローバル構成**グローバル構成が既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-107">**Global configuration** The global configuration is created by default.</span></span> <span data-ttu-id="04b1f-108">グローバル構成を編集することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="04b1f-108">You can edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="04b1f-109">削除しようとすると、すべてのオプションが既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="04b1f-110">**サイト構成 (オプション)** 1 つまたは複数のサイト アーカイブ構成、アーカイブ オプションを特定のサイトの管理にあり、それぞれを構成できますを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-110">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="04b1f-111">サイト構成は、グローバル構成をオーバーライドしますが、アーカイブ サイトの構成で指定されているサイトに対してのみです。</span><span class="sxs-lookup"><span data-stu-id="04b1f-111">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="04b1f-112">編集したり、サイトの構成を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-112">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="04b1f-113">**プールの構成 (オプション)** 1 つまたは複数プール アーカイブの構成、アーカイブ プールの特定のオプションのコントロールにすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="04b1f-113">**Pool configuration (optional)** You can specify one or more pool Archiving configurations, to control archiving options for a specific pool.</span></span> <span data-ttu-id="04b1f-114">プールの構成はグローバル構成およびサイトの構成より優先されますが、アーカイブ ・ プールの構成で指定されたプールにのみ。</span><span class="sxs-lookup"><span data-stu-id="04b1f-114">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="04b1f-115">プール構成を削除または編集できます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-115">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="04b1f-116">アーカイブの構成に適用するビジネス サーバーで、Skype に所属していたユーザーは、アーカイブ ・ データを格納する Exchange 2013 を使用する Microsoft Exchange の統合オプションを有効にした場合、Microsoft Exchange ユーザーに所属している Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="04b1f-116">Archiving configurations apply to users homed on Skype for Business Server, and, if you enable the Microsoft Exchange integration option to use Exchange 2013 to store archiving data in Microsoft Exchange, to users homed on Exchange 2013.</span></span> <span data-ttu-id="04b1f-117">ただし、いくつかのオプションは実装方法が少し異なる Exchange 2013 では、所属していたユーザーの次のセクションで説明したようです。</span><span class="sxs-lookup"><span data-stu-id="04b1f-117">However, some options are implemented slightly differently for users homed on Exchange 2013, as described in the next section.</span></span> 
  
<span data-ttu-id="04b1f-118">新規または既存のアーカイブ構成の設定を構成するには、次のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="04b1f-118">To configure the settings for a new or existing Archiving configuration, specify the following options:</span></span>
- <span data-ttu-id="04b1f-119">**名**各アーカイブ構成では、名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="04b1f-119">**Name** Each Archiving configuration requires a name.</span></span> <span data-ttu-id="04b1f-120">名前は、構成を追加または編集の種類によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-120">The name is determined by the type of configuration you are adding or editing:</span></span>
    
  - <span data-ttu-id="04b1f-121">**グローバル構成**既定の名前は、グローバルです。</span><span class="sxs-lookup"><span data-stu-id="04b1f-121">**Global configuration** The default name is Global.</span></span> <span data-ttu-id="04b1f-122">例: "Contoso 北米組織"。</span><span class="sxs-lookup"><span data-stu-id="04b1f-122">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="04b1f-123">**サイトの構成**一覧には、展開で使用可能なサイトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="04b1f-123">**Site configuration** The list contains the available sites in your deployment.</span></span> <span data-ttu-id="04b1f-124">1 つのサイトをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="04b1f-124">Click a single site to select it.</span></span> <span data-ttu-id="04b1f-125">例: "レドモンド データ センター"。</span><span class="sxs-lookup"><span data-stu-id="04b1f-125">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="04b1f-126">**プールの構成**特定のフロント エンド プールまたは Standard Edition Server の展開での名前を指定できます、適切な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="04b1f-126">**Pool configuration** Specify an appropriate name, which can be the name of a specific Front End pool or Standard Edition Server in your deployment.</span></span> <span data-ttu-id="04b1f-127">たとえば、マーケティング部門です。</span><span class="sxs-lookup"><span data-stu-id="04b1f-127">For example, Marketing Division.</span></span>
    
- <span data-ttu-id="04b1f-128">**説明**これは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="04b1f-128">**Description** This is optional.</span></span> <span data-ttu-id="04b1f-129">スコープ構成の使用などの追加情報の提供に使用します。</span><span class="sxs-lookup"><span data-stu-id="04b1f-129">Use it to provide additional details, such as the scope or use of the configuration.</span></span> <span data-ttu-id="04b1f-130">などの他のサイトの法務部門とを調整します。</span><span class="sxs-lookup"><span data-stu-id="04b1f-130">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="04b1f-131">**既定のアーカイブ設定**オプションを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="04b1f-131">**Archiving setting** Options include the following:</span></span>
    
  - <span data-ttu-id="04b1f-132">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="04b1f-132">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="04b1f-133">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="04b1f-133">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="04b1f-134">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="04b1f-134">**Disable archiving**</span></span>
    
- <span data-ttu-id="04b1f-135">**ブロック インスタント メッセージング (IM) または web 会議セッション アーカイブが失敗した場合**エラーを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="04b1f-135">**Block instant messaging (IM) or web conferencing sessions if archiving fails** Failures include the following:</span></span>
    
  - <span data-ttu-id="04b1f-136">**IM**データベース全体またはストレージ ・ サービスの問題、障害が発生可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04b1f-136">**IM** A failure could be a full database or problem with the storage service.</span></span> <span data-ttu-id="04b1f-137">この場合、アーカイブが有効になっているユーザーでは IM がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-137">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
  - <span data-ttu-id="04b1f-138">**会議**失敗すると、ファイル共有、またはストレージ ・ サービスに問題可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04b1f-138">**Conferencing** A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="04b1f-139">この場合、障害発生時にプール内でホストされているアクティブな会議がすべて制限モードに切り替えられ、新しい会議をアクティブにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="04b1f-139">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="04b1f-140">障害から回復した後、IM および会議は自動的に回復します。</span><span class="sxs-lookup"><span data-stu-id="04b1f-140">Both IM and conferencing automatically recover after the failures are corrected.</span></span>
    
- <span data-ttu-id="04b1f-141">**Microsoft Exchange の統合**Exchange 2013 をホームとしているユーザーがいる場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="04b1f-141">**Microsoft Exchange integration** Select this option if you have users who are homed on Exchange 2013.</span></span> <span data-ttu-id="04b1f-142">このオプションを使用するインプレース保持自分のメールボックスが設定されている場合、Exchange 2013 は、それらのユーザーのデータを格納する使用されます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-142">With this option, Exchange 2013 is used to store data for those users, if their mailboxes have been placed on In-Place Hold.</span></span> <span data-ttu-id="04b1f-143">すべてのユーザーは、Exchange 2013 のホームは場合、は、データのアーカイブを保存するための別の SQL Server データベースを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="04b1f-143">If all your users are homed on Exchange 2013, you do not need to set up separate SQL Server databases for storage of archiving data.</span></span>
    
- <span data-ttu-id="04b1f-144">**アーカイブ ・ データのパージを有効にします。** パージを有効にして、次のパージのオプションを指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="04b1f-144">**Enable purging of archiving data** Select this option to enable purging and specify purging options, which include the following:</span></span>
    
  - <span data-ttu-id="04b1f-145">指定した特定の日数の後で削除する。</span><span class="sxs-lookup"><span data-stu-id="04b1f-145">Purging after a specific number of days that you specify.</span></span>
    
  - <span data-ttu-id="04b1f-146">後のアーカイブ ・ データのパージがエクスポートされました (データを含む、Exchange にアップロードされている Microsoft Exchange の統合を有効にした場合)。</span><span class="sxs-lookup"><span data-stu-id="04b1f-146">Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="04b1f-147">Microsoft Exchange の統合を有効にした場合はユーザーの削除 Exchange 2013 が置かれているし、インプレース保持に自分のメールボックスを持つ Exchange によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-147">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes placed on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="04b1f-148">唯一の例外は、会議のファイルは、Lync Server のファイル共有に格納されているのです。</span><span class="sxs-lookup"><span data-stu-id="04b1f-148">The only exception is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="04b1f-149">これらのファイルは、アーカイブ データがエクスポートされた後でデータを削除するオプションを選択した場合はファイルがエクスポートされた後 (Exchange にアップロードされた後)、保持する最大日数を指定した場合は指定した最大日数経過後にのみファイル共有から削除されます。</span><span class="sxs-lookup"><span data-stu-id="04b1f-149">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span> 
  
<span data-ttu-id="04b1f-150">アーカイブ機能および Exchange の統合などの機能の詳細について「[ビジネス サーバー 2015 の Skype でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)、[ビジネス サーバー 2015 Skype アーカイブの展開](../../deploy/deploy-archiving/deploy-archiving.md)、および[管理アーカイブの Skype での使用」を参照してください。ビジネス サーバー 2015年](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="04b1f-150">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

