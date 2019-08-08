---
title: Skype for Business Server のアーカイブポリシーを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: '概要: Skype for Business Server ユーザーの初期アーカイブポリシーを構成する方法については、このトピックを参照してください。'
ms.openlocfilehash: 4e1bf5d713201604df18db9d63c2057bfa5bb4e8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234553"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="9cc4c-103">Skype for Business Server のアーカイブポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="9cc4c-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="9cc4c-104">**概要:** このトピックでは、Skype for Business Server ユーザーの初期アーカイブポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="9cc4c-105">Skype for Business Server では、ポリシーを使って、内部通信のアーカイブを有効または無効にしたり、Skype for Business Server を使っているユーザーの外部通信を有効にしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="9cc4c-106">これには、次のポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-106">This includes the following:</span></span>
  
- <span data-ttu-id="9cc4c-107">Skype for Business Server を展開するときに既定で作成されるグローバルポリシー</span><span class="sxs-lookup"><span data-stu-id="9cc4c-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="9cc4c-108">特定のサイトに対するアーカイブの実装方法を指定するオプションのサイト レベルのポリシー。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="9cc4c-109">特定のユーザーに対してアーカイブを実装する方法を指定する、オプションのユーザーレベルポリシー</span><span class="sxs-lookup"><span data-stu-id="9cc4c-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="9cc4c-110">アーカイブ ポリシーは、最初はアーカイブの展開時にセットアップしますが、展開後に変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="9cc4c-111">Skype for Business Server コントロールパネルで、[**アーカイブと監視**] グループの [**アーカイブポリシー** ] ページを使用して、グローバル、サイト、ユーザーレベルでポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9cc4c-112">アーカイブの実装を制御するには、重要モード、削除オプション、IM と会議のどちらをアーカイブするかなどのオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="9cc4c-113">既定では、グローバル アーカイブ構成やサイトまたはプール アーカイブ構成で有効になっているオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="9cc4c-114">内部通信または外部通信のアーカイブを有効にする前に、すべての該当するオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="9cc4c-115">詳細については、「 [Skype For Business Server のアーカイブオプションを構成する](configure-archiving-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9cc4c-116">展開に対して Microsoft Exchange の統合を有効にすると、exchange を使用しているユーザーに対してアーカイブが有効になっているかどうかを制御するために、Exchange のインプレースホールドポリシーによって、Exchange を使用しているユーザーのメールボックスがインプレース保持されます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="9cc4c-117">グローバル、サイト、ユーザーのポリシーの階層など、アーカイブポリシーの動作について詳しくは、「 [Skype For Business Server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="9cc4c-118">展開後にポリシーを管理する方法の詳細については、「 [Skype For Business Server のアーカイブポリシーを管理](../../manage/archiving/policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="9cc4c-119">グローバル ポリシー</span><span class="sxs-lookup"><span data-stu-id="9cc4c-119">Global policy</span></span>

<span data-ttu-id="9cc4c-120">フロントエンドサーバーを展開すると、Skype for Business Server によってアーカイブ用のグローバルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="9cc4c-121">既定では、アーカイブはグローバルポリシーで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="9cc4c-122">グローバルポリシーは、サイトまたはユーザーのポリシーをセットアップしてグローバルポリシーを上書きするか、または Microsoft Exchange の統合を使用しているかどうかにかかわらず、展開全体の内部と外部の通信でアーカイブを有効にするかどうかを制御します。ユーザー。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="9cc4c-123">Microsoft Exchange 統合を使用している場合、グローバルポリシーは Exchange を使っているユーザーには適用されず、メールボックスはインプレース保持されます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="9cc4c-124">Skype for Business Server アーカイブデータベースのアーカイブのグローバルポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="9cc4c-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="9cc4c-125">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9cc4c-126">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9cc4c-127">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="9cc4c-128">[**アーカイブ ポリシー**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9cc4c-129">[**アーカイブ ポリシーの編集 - グローバル**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="9cc4c-130">"グローバル" という既定の名前を使用しない場合は、[**名前**] にグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="9cc4c-131">[**説明**] に、ポリシーについての情報を入力します (例: 区分の*名前*のグローバルポリシー)。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="9cc4c-132">サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの内部通信のアーカイブを制御するには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="9cc4c-133">サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="9cc4c-134">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="9cc4c-135">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="9cc4c-135">Site policies</span></span>

<span data-ttu-id="9cc4c-136">特定のサイトに対してそれぞれアーカイブ ポリシーを作成し、そのサイトに対してアーカイブを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="9cc4c-137">サイト ポリシーはグローバル ポリシーより優先されますが、サイト ポリシーよりもユーザー ポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="9cc4c-138">アーカイブポリシーが適用されるのは、Microsoft Exchange 統合を使用していない場合、または Microsoft Exchange 統合を使用していないが、Exchange を使っていないユーザーがいて、メールボックスがインプレースホールドに配置されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="9cc4c-139">サイトのアーカイブ ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="9cc4c-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="9cc4c-140">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9cc4c-141">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9cc4c-142">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="9cc4c-143">グローバル、サイト、ユーザーのポリシーの階層など、アーカイブポリシーの動作について詳しくは、「 [Skype For Business Server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="9cc4c-144">[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="9cc4c-145">[**サイトの選択**] でポリシーを適用するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="9cc4c-146">[**新しいアーカイブ ポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="9cc4c-147">[**名前**] で、サイト ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="9cc4c-148">[**説明**] にサイト ポリシーに関する情報を入力します (「Redmond のサイト ポリシー」など)。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="9cc4c-149">指定したサイトの内部通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="9cc4c-150">指定したサイトの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="9cc4c-151">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="9cc4c-152">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="9cc4c-152">User policies</span></span>

<span data-ttu-id="9cc4c-153">ユーザーのアーカイブ ポリシーを作成および構成し、そのポリシーを特定のユーザーまたはユーザー グループに適用することで、特定のユーザーに対してアーカイブを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="9cc4c-154">ユーザー ポリシーは、グローバル ポリシーやサイト ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="9cc4c-155">アーカイブポリシーが適用されるのは、Microsoft Exchange 統合を使用していない場合、または Microsoft Exchange 統合を使用していないが、Exchange を使っていないユーザーがいて、メールボックスがインプレースホールドに配置されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="9cc4c-156">Skype for Business Server を使用しているユーザーのアーカイブポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="9cc4c-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="9cc4c-157">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9cc4c-158">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9cc4c-159">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="9cc4c-160">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="9cc4c-161">[**新しいアーカイブ ポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="9cc4c-162">[**名前**] にユーザー ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="9cc4c-163">[**説明**] に、ユーザー ポリシーの内容に関する情報を入力します (「法務部門のユーザー ポリシー」など)。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="9cc4c-164">ユーザー ポリシーの内部通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="9cc4c-165">ユーザー ポリシーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="9cc4c-166">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-166">Click **Commit**.</span></span>
    
<span data-ttu-id="9cc4c-167">ユーザー ポリシーは、そのポリシーを割り当てたユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="9cc4c-168">Skype for Business Server のアーカイブポリシーをユーザーに適用する</span><span class="sxs-lookup"><span data-stu-id="9cc4c-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="9cc4c-169">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9cc4c-170">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9cc4c-171">左側のナビゲーション バーで [**ユーザー**] をクリックして、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="9cc4c-172">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9cc4c-173">[**アーカイブポリシー**] の [ **Skype for business Server ユーザーの編集**] で、適用するアーカイブユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9cc4c-174">\*\* \<自動\> \*\*設定では、既定のサーバーインストール設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="9cc4c-175">これらの設定はサーバーにより自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="9cc4c-176">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cc4c-176">Click **Commit**.</span></span>
    

