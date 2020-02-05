---
title: Skype for Business Server のアーカイブオプションを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: '概要: Skype for Business Server の最初のアーカイブオプションを構成する方法については、このトピックをお読みください。 アーカイブの展開時にアーカイブ構成を最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。'
ms.openlocfilehash: f663b310d4c82594976f2f0fc99b8ddd9baf035f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769200"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="33834-104">Skype for Business Server のアーカイブオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="33834-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="33834-105">**概要:** このトピックでは、Skype for Business Server の最初のアーカイブオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33834-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="33834-106">アーカイブの展開時にアーカイブ構成を最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="33834-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="33834-107">初期のアーカイブ構成を構成するには、Skype for Business Server コントロールパネルを使用して、次の内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="33834-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="33834-108">Skype for Business Server を展開するときに既定で作成されるグローバルレベルの構成</span><span class="sxs-lookup"><span data-stu-id="33834-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="33834-109">(オプション) 特定のサイトにアーカイブを実装する方法を指定するサイト レベルの構成</span><span class="sxs-lookup"><span data-stu-id="33834-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="33834-110">特定のプールに対するアーカイブの実装方法を指定するオプションのプールレベル構成</span><span class="sxs-lookup"><span data-stu-id="33834-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="33834-111">構成する必要があるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="33834-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="33834-112">アーカイブの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="33834-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="33834-113">IM セッションをアーカイブするかどうか</span><span class="sxs-lookup"><span data-stu-id="33834-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="33834-114">Web 会議セッションをアーカイブするかどうか</span><span class="sxs-lookup"><span data-stu-id="33834-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="33834-115">アーカイブを使用できない場合にアクティビティをブロックするかどうか</span><span class="sxs-lookup"><span data-stu-id="33834-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="33834-116">Exchange 統合を使用するかどうか</span><span class="sxs-lookup"><span data-stu-id="33834-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="33834-117">データの削除とエクスポートをどのようにセットアップするか</span><span class="sxs-lookup"><span data-stu-id="33834-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="33834-118">適切なオプションをすべて指定してからアーカイブを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="33834-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="33834-119">アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」をご覧ください。「 [Skype For Business Server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33834-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="33834-120">展開後に [コントロールパネル] または Windows PowerShell を使用して構成を管理する方法の詳細については、「 [Skype For Business Server でアーカイブオプションを管理](../../manage/archiving/options.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33834-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="33834-121">グローバル レベルのアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="33834-121">Configure global level archiving options</span></span>

<span data-ttu-id="33834-122">トポロジにアーカイブを追加してトポロジを公開すると、Skype for Business Server はアーカイブ用のグローバル構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="33834-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="33834-123">既定では、グローバル構成で有効になっているアーカイブ オプションはありません。</span><span class="sxs-lookup"><span data-stu-id="33834-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="33834-124">グローバル構成より優先されるサイト構成またはプール構成を設定しない限り、グローバル構成は、展開全体に対して有効化されるオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="33834-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="33834-125">グローバル レベルでアーカイブ オプションを構成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="33834-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="33834-126">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="33834-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="33834-127">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="33834-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="33834-128">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="33834-129">[**アーカイブ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="33834-130">[**編集アーカイブ設定 - Global**] の [**アーカイブ設定**] ボックスの一覧で、次のいずれかのアーカイブ オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="33834-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="33834-131">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="33834-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="33834-132">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="33834-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="33834-133">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="33834-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="33834-134">また、[**アーカイブ設定の編集-グローバル**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="33834-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="33834-135">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="33834-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="33834-136">アーカイブデータの保存に Microsoft Exchange Server を使用するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="33834-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="33834-137">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="33834-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="33834-138">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="33834-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="33834-139">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="33834-140">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="33834-141">サイト レベルのアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="33834-141">Configure site level archiving options</span></span>

<span data-ttu-id="33834-142">特定のサイトのアーカイブ オプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="33834-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="33834-143">サイト構成はグローバル構成より優先されますが、その対象はサイト構成に指定されているサイトに限定されます。</span><span class="sxs-lookup"><span data-stu-id="33834-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="33834-144">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="33834-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="33834-145">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="33834-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="33834-146">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="33834-147">[**アーカイブ構成**] ページで、[**新規作成**] をクリックし、[**サイト構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="33834-148">[**サイトの選択**] で、アーカイブ用に構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="33834-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="33834-149">[**新しいアーカイブ設定**] の [**アーカイブ設定**] ボックスの一覧で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="33834-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="33834-150">インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="33834-151">IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="33834-152">ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="33834-153">[**新しいアーカイブ設定**] で、次の操作も実行します。</span><span class="sxs-lookup"><span data-stu-id="33834-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="33834-154">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="33834-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="33834-155">アーカイブデータの保存に Microsoft Exchange Server を使用するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="33834-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="33834-156">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="33834-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="33834-157">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="33834-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="33834-158">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="33834-159">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="33834-160">プール レベルのアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="33834-160">Configure pool level archiving options</span></span>

<span data-ttu-id="33834-p106">特定のプールのアーカイブ オプションを指定できます。プール構成はグローバル構成とサイト構成より優先されますが、その対象はプール構成に指定されているプールに限定されます。</span><span class="sxs-lookup"><span data-stu-id="33834-p106">You can specify archiving options for a specific pool. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="33834-163">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="33834-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="33834-164">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="33834-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="33834-165">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="33834-166">[**アーカイブ構成**] ページで、[**新規**]、[**プール構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="33834-167">[**サービスの選択**] で、アーカイブ用に構成するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="33834-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="33834-168">[**新規アーカイブ設定**] の [**アーカイブ設定**] ボックスの一覧で、次のアーカイブ オプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="33834-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="33834-169">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="33834-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="33834-170">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="33834-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="33834-171">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="33834-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="33834-172">また、[**新規アーカイブ設定**] ページで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="33834-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="33834-173">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="33834-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="33834-174">アーカイブデータの保存に Microsoft Exchange Server を使用するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="33834-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="33834-175">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="33834-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="33834-176">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="33834-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="33834-177">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="33834-178">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33834-178">Click **Commit**.</span></span>
    

