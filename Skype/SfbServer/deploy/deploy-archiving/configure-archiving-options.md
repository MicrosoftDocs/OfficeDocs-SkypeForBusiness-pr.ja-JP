---
title: Skype のビジネス サーバー用のアーカイブのオプションを構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: '概要: ビジネス サーバーの Skype の初期のアーカイブ ・ オプションを構成する方法については、このトピックを読みます。 最初に設定する構成をアーカイブ、アーカイブを展開するが、変更、追加、および展開後の構成を削除することができます。'
ms.openlocfilehash: 186ebae95c3d4d27ef634c0ca9ae1bc99bbfa253
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020415"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="d6cce-104">Skype のビジネス サーバー用のアーカイブのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="d6cce-105">**の概要:** ビジネス サーバーの Skype の初期のアーカイブ ・ オプションを構成する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6cce-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="d6cce-106">最初に設定する構成をアーカイブ、アーカイブを展開するが、変更、追加、および展開後の構成を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d6cce-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="d6cce-107">構成するには、アーカイブ構成では、初期使用する Skype ビジネス サーバーのコントロール パネルの以下を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="d6cce-108">ビジネス サーバーに対して Skype を展開するときに既定で作成されるグローバル レベルの構成</span><span class="sxs-lookup"><span data-stu-id="d6cce-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="d6cce-109">(オプション) 特定のサイトにアーカイブを実装する方法を指定するサイト レベルの構成</span><span class="sxs-lookup"><span data-stu-id="d6cce-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="d6cce-110">特定のプールのアーカイブの実装方法を指定するオプションのプールレベルの構成</span><span class="sxs-lookup"><span data-stu-id="d6cce-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="d6cce-111">構成する必要があるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d6cce-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="d6cce-112">アーカイブの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="d6cce-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="d6cce-113">IM セッションをアーカイブするかどうか</span><span class="sxs-lookup"><span data-stu-id="d6cce-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="d6cce-114">Web 会議セッションをアーカイブするかどうか</span><span class="sxs-lookup"><span data-stu-id="d6cce-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="d6cce-115">アーカイブを使用できない場合にアクティビティをブロックするかどうか</span><span class="sxs-lookup"><span data-stu-id="d6cce-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="d6cce-116">Exchange 統合を使用するかどうか</span><span class="sxs-lookup"><span data-stu-id="d6cce-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="d6cce-117">データの削除とエクスポートをどのようにセットアップするか</span><span class="sxs-lookup"><span data-stu-id="d6cce-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="d6cce-118">適切なオプションをすべて指定してからアーカイブを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="d6cce-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="d6cce-119">方法の詳細については、アーカイブの構成は、実装するオプションを指定することを含むとアーカイブ構成の階層構造は、 [Skype のビジネス サーバーでアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6cce-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="d6cce-120">詳細を管理する方法については、コントロール パネルを使用するか、Windows PowerShell を使用して、展開後の構成では、 [Skype のビジネス サーバーでアーカイブ ・ オプションを管理](../../manage/archiving/options.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6cce-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="d6cce-121">グローバル レベルのアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="d6cce-121">Configure global level archiving options</span></span>

<span data-ttu-id="d6cce-122">トポロジにアーカイブを追加し、トポロジを公開すると、Business Server の Skype はアーカイブのグローバル設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="d6cce-123">既定では、グローバル構成で有効になっているアーカイブ オプションはありません。</span><span class="sxs-lookup"><span data-stu-id="d6cce-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="d6cce-124">グローバル構成より優先されるサイト構成またはプール構成を設定しない限り、グローバル構成は、展開全体に対して有効化されるオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="d6cce-125">グローバル レベルでアーカイブ オプションを構成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d6cce-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="d6cce-126">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d6cce-127">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d6cce-128">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="d6cce-129">[**アーカイブ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d6cce-130">[**編集アーカイブ設定 - Global**] の [**アーカイブ設定**] ボックスの一覧で、次のいずれかのアーカイブ オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="d6cce-131">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="d6cce-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="d6cce-132">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="d6cce-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="d6cce-133">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="d6cce-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="d6cce-134">**編集・ アーカイブの設定 - グローバル**] ページでは、次のように操作します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="d6cce-135">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="d6cce-136">アーカイブ ・ データを格納する Microsoft Exchange Server を使用するには、 **Microsoft Exchange の統合**] チェック ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="d6cce-137">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d6cce-138">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="d6cce-139">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="d6cce-140">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="d6cce-141">サイト レベルのアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="d6cce-141">Configure site level archiving options</span></span>

<span data-ttu-id="d6cce-142">特定のサイトのアーカイブ オプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6cce-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="d6cce-143">サイト構成はグローバル構成より優先されますが、その対象はサイト構成に指定されているサイトに限定されます。</span><span class="sxs-lookup"><span data-stu-id="d6cce-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="d6cce-144">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d6cce-145">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d6cce-146">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="d6cce-147">[**アーカイブ構成**] ページで、[**新規作成**] をクリックし、[**サイト構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="d6cce-148">[**サイトの選択**] で、アーカイブ用に構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="d6cce-149">[**新しいアーカイブ設定**] の [**アーカイブ設定**] ボックスの一覧で、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="d6cce-150">インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="d6cce-151">IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="d6cce-152">ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="d6cce-153">[**新しいアーカイブ設定**] で、次の操作も実行します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="d6cce-154">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="d6cce-155">アーカイブ ・ データを格納する Microsoft Exchange Server を使用するには、 **Microsoft Exchange の統合**] チェック ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="d6cce-156">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d6cce-157">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="d6cce-158">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="d6cce-159">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="d6cce-160">プール レベルのアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="d6cce-160">Configure pool level archiving options</span></span>

<span data-ttu-id="d6cce-p106">特定のプールのアーカイブ オプションを指定できます。プール構成はグローバル構成とサイト構成より優先されますが、その対象はプール構成に指定されているプールに限定されます。</span><span class="sxs-lookup"><span data-stu-id="d6cce-p106">You can specify archiving options for a specific pool. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="d6cce-163">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d6cce-164">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d6cce-165">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="d6cce-166">[**アーカイブ構成**] ページで、[**新規**]、[**プール構成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="d6cce-167">[**サービスの選択**] で、アーカイブ用に構成するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="d6cce-168">[**新規アーカイブ設定**] の [**アーカイブ設定**] ボックスの一覧で、次のアーカイブ オプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="d6cce-169">**[アーカイブを無効にする]**</span><span class="sxs-lookup"><span data-stu-id="d6cce-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="d6cce-170">**[IM セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="d6cce-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="d6cce-171">**[IM および Web 会議セッションをアーカイブする]**</span><span class="sxs-lookup"><span data-stu-id="d6cce-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="d6cce-172">また、[**新規アーカイブ設定**] ページで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="d6cce-173">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="d6cce-174">アーカイブ ・ データを格納する Microsoft Exchange Server を使用するには、 **Microsoft Exchange の統合**] チェック ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="d6cce-175">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d6cce-176">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6cce-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="d6cce-177">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="d6cce-178">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cce-178">Click **Commit**.</span></span>
    

