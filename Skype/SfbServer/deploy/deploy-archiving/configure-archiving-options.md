---
title: Skype for Business Server のアーカイブ オプションを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: '概要: このトピックでは、Skype for Business Server の初期アーカイブ オプションを構成する方法について説明します。 アーカイブ構成は、最初にアーカイブを展開するときに設定しますが、展開後に構成を変更、追加、および削除できます。'
ms.openlocfilehash: 0a4803b821ee082a548b9f429b9596fd8019500f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815537"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="0be55-104">Skype for Business Server のアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="0be55-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="0be55-105">**概要:** このトピックでは、Skype for Business Server の初期アーカイブ オプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0be55-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="0be55-106">アーカイブ構成は、最初にアーカイブを展開するときに設定しますが、展開後に構成を変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="0be55-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="0be55-107">初期アーカイブ構成を構成するには、Skype for Business Server コントロール パネルを使用して以下を指定します。</span><span class="sxs-lookup"><span data-stu-id="0be55-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="0be55-108">Skype for Business Server を展開するときに既定で作成されるグローバル レベルの構成</span><span class="sxs-lookup"><span data-stu-id="0be55-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="0be55-109">特定のサイトに対するアーカイブの実装方法を指定するオプションのサイト レベルの構成</span><span class="sxs-lookup"><span data-stu-id="0be55-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="0be55-110">特定のプールに対してアーカイブを実装する方法を指定するオプションのプール レベル構成</span><span class="sxs-lookup"><span data-stu-id="0be55-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="0be55-111">次のオプションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0be55-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="0be55-112">アーカイブを有効にするか無効にするか</span><span class="sxs-lookup"><span data-stu-id="0be55-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="0be55-113">IM セッションをアーカイブするかどうか</span><span class="sxs-lookup"><span data-stu-id="0be55-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="0be55-114">Web 会議セッションをアーカイブするかどうか</span><span class="sxs-lookup"><span data-stu-id="0be55-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="0be55-115">アーカイブが使用できない場合にアクティビティをブロックするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0be55-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="0be55-116">Exchange 統合を使用するかどうか</span><span class="sxs-lookup"><span data-stu-id="0be55-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="0be55-117">データの削除とエクスポートを設定する方法</span><span class="sxs-lookup"><span data-stu-id="0be55-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="0be55-118">アーカイブを有効にする前に、すべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0be55-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="0be55-119">指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については [、「Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0be55-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="0be55-120">展開後にコントロール パネルまたは Windows PowerShell を使用して構成を管理する方法の詳細については [、「Skype for Business Server](../../manage/archiving/options.md)のアーカイブ オプションの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0be55-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="0be55-121">グローバル レベルのアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="0be55-121">Configure global level archiving options</span></span>

<span data-ttu-id="0be55-122">トポロジにアーカイブを追加してトポロジを公開すると、Skype for Business Server はアーカイブ用のグローバル構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="0be55-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="0be55-123">既定では、グローバル構成で有効になっているアーカイブ オプションはありません。</span><span class="sxs-lookup"><span data-stu-id="0be55-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="0be55-124">グローバル構成より優先されるサイト構成またはプール構成を設定しない限り、グローバル構成は、展開全体に対して有効化されるオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="0be55-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="0be55-125">アーカイブ オプションをグローバル レベルで構成するには:</span><span class="sxs-lookup"><span data-stu-id="0be55-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="0be55-126">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0be55-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0be55-127">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0be55-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0be55-128">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="0be55-129">[**アーカイブ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0be55-130">[**編集 アーカイブ設定 - Global**] の [**アーカイブ設定**] ドロップダウン リストで、次のいずれかのアーカイブ オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0be55-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="0be55-131">[**アーカイブを無効にする**]</span><span class="sxs-lookup"><span data-stu-id="0be55-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="0be55-132">[**IM セッションをアーカイブする**]</span><span class="sxs-lookup"><span data-stu-id="0be55-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="0be55-133">[**IM および Web 会議セッションをアーカイブする**]</span><span class="sxs-lookup"><span data-stu-id="0be55-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="0be55-134">また、[アーカイブ **設定の編集 - グローバル** ] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0be55-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="0be55-135">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0be55-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="0be55-136">アーカイブ データをMicrosoft Exchange Serverするには **、[Microsoft Exchange** 統合] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0be55-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="0be55-137">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0be55-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="0be55-138">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="0be55-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="0be55-139">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="0be55-140">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="0be55-141">サイト レベルのアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="0be55-141">Configure site level archiving options</span></span>

<span data-ttu-id="0be55-142">特定のサイトのアーカイブ オプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0be55-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="0be55-143">サイト構成はグローバル構成より優先されますが、サイト構成で指定されたサイトに対してだけ優先されます。</span><span class="sxs-lookup"><span data-stu-id="0be55-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="0be55-144">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0be55-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0be55-145">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0be55-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0be55-146">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="0be55-147">[**アーカイブ構成**] ページで、[**新規作成**] をクリックし、[**サイト構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="0be55-148">[**サイトの選択**] で、アーカイブ用に構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="0be55-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="0be55-149">[**新しいアーカイブ設定**] の [**アーカイブ設定**] ドロップダウン リスト ボックスで、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0be55-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="0be55-150">インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="0be55-151">IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="0be55-152">ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="0be55-153">[**新しいアーカイブ設定**] で、次の操作も実行します。</span><span class="sxs-lookup"><span data-stu-id="0be55-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="0be55-154">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0be55-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="0be55-155">アーカイブ データをMicrosoft Exchange Serverするには **、[Microsoft Exchange** 統合] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0be55-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="0be55-156">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0be55-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="0be55-157">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="0be55-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="0be55-158">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="0be55-159">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="0be55-160">プール レベルのアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="0be55-160">Configure pool level archiving options</span></span>

<span data-ttu-id="0be55-161">特定のプールのアーカイブ オプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0be55-161">You can specify archiving options for a specific pool.</span></span> <span data-ttu-id="0be55-162">プール構成はグローバル構成とサイト構成より優先されますが、プール構成で指定したプールにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0be55-162">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="0be55-163">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0be55-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0be55-164">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0be55-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0be55-165">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="0be55-166">[**アーカイブ構成**] ページで、[**新規**]、[**プール構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="0be55-167">[**サービスの選択**] で、アーカイブ用に構成するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="0be55-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="0be55-168">[**新規 アーカイブ設定**] の [**アーカイブ設定**] ドロップダウン リストで、次のアーカイブ オプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0be55-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="0be55-169">[**アーカイブを無効にする**]</span><span class="sxs-lookup"><span data-stu-id="0be55-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="0be55-170">[**IM セッションをアーカイブする**]</span><span class="sxs-lookup"><span data-stu-id="0be55-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="0be55-171">[**IM および Web 会議セッションをアーカイブする**]</span><span class="sxs-lookup"><span data-stu-id="0be55-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="0be55-172">また、[**新規 アーカイブ設定**] ページで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0be55-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="0be55-173">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0be55-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="0be55-174">アーカイブ データをMicrosoft Exchange Serverするには **、[Microsoft Exchange** 統合] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0be55-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="0be55-175">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0be55-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="0be55-176">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="0be55-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="0be55-177">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="0be55-178">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0be55-178">Click **Commit**.</span></span>
    

