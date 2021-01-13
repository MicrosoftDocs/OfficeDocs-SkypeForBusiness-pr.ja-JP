---
title: Skype for Business Server のアーカイブ ポリシーを構成する
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
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: '概要: このトピックでは、Skype for Business Server ユーザーの初期アーカイブ ポリシーを構成する方法について説明します。'
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820857"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="94af6-103">Skype for Business Server のアーカイブ ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="94af6-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="94af6-104">**概要:** このトピックでは、Skype for Business Server ユーザーの初期アーカイブ ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94af6-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="94af6-105">Skype for Business Server では、ポリシーを使用して、Skype for Business Server にホームを持つユーザーの内部通信および外部通信のアーカイブを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="94af6-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="94af6-106">エクスポートできるものには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="94af6-106">This includes the following:</span></span>
  
- <span data-ttu-id="94af6-107">Skype for Business Server を展開するときに既定で作成されるグローバル ポリシー</span><span class="sxs-lookup"><span data-stu-id="94af6-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="94af6-108">特定のサイトに対してアーカイブを実装する方法を指定するオプションのサイト レベルポリシー</span><span class="sxs-lookup"><span data-stu-id="94af6-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="94af6-109">特定のユーザーに対してアーカイブを実装する方法を指定するオプションのユーザー レベルのポリシー</span><span class="sxs-lookup"><span data-stu-id="94af6-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="94af6-110">アーカイブ ポリシーは、アーカイブの展開時に最初に設定しますが、展開後にポリシーを変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="94af6-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="94af6-111">Skype for Business Server コントロール パネルでは、アーカイブおよび監視グループの[アーカイブ ポリシー] ページを使用して、グローバル レベル、サイト レベル、およびユーザー レベルのポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="94af6-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94af6-112">アーカイブの実装を制御するには、IM または会議をアーカイブするかどうか、重要モードの使用、削除オプションなどのオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94af6-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="94af6-113">既定では、グローバル アーカイブ構成またはサイトまたはプールのアーカイブ構成では、どのオプションも有効になりません。</span><span class="sxs-lookup"><span data-stu-id="94af6-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="94af6-114">内部通信または外部通信のアーカイブを有効にする前に、すべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94af6-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="94af6-115">詳細については [、「Skype for Business Server のアーカイブ オプションを構成する」を参照してください](configure-archiving-options.md)。</span><span class="sxs-lookup"><span data-stu-id="94af6-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="94af6-116">展開に対して Microsoft Exchange 統合を有効にした場合、Exchange In-Place 保持ポリシーは、Exchange にホームを置き、メールボックスが In-Place Hold に設定されているユーザーに対してアーカイブを有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="94af6-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="94af6-117">グローバル ポリシー、サイト ポリシー、ユーザー ポリシーの階層など、アーカイブ ポリシーがどのように機能するのかについては [、「Plan for archiving in Skype for Business Server」](../../plan-your-deployment/archiving/archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94af6-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="94af6-118">展開後にポリシーを管理する方法の詳細については、「Skype for Business Server でアーカイブ ポリシーを管理 [する」を参照してください](../../manage/archiving/policies.md)。</span><span class="sxs-lookup"><span data-stu-id="94af6-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="94af6-119">グローバル ポリシー</span><span class="sxs-lookup"><span data-stu-id="94af6-119">Global policy</span></span>

<span data-ttu-id="94af6-120">フロントエンド サーバーを展開すると、Skype for Business Server はアーカイブ用のグローバル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="94af6-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="94af6-121">既定では、グローバル ポリシーではアーカイブは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="94af6-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="94af6-122">グローバル ポリシーは、グローバル ポリシーを上書きするサイト ポリシーまたはユーザー ポリシーを設定しない限り、または一部またはすべてのユーザーに Microsoft Exchange 統合を使用しない限り、展開全体で内部通信と外部通信に対してアーカイブを有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="94af6-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="94af6-123">Microsoft Exchange 統合を使用する場合、グローバル ポリシーは、Exchange にホームとして設定され、メールボックスが In-Place保持に設定されているユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="94af6-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="94af6-124">Skype for Business Server アーカイブ データベースのアーカイブ用のグローバル ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="94af6-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="94af6-125">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="94af6-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94af6-126">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="94af6-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="94af6-127">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="94af6-128">[**アーカイブ ポリシー**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="94af6-129">[**アーカイブ ポリシーの編集 - グローバル**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94af6-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="94af6-130">"グローバル" という既定の名前を使用しない場合は、[**名前**] にグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="94af6-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="94af6-131">[ **説明]** に、ポリシーの内容に関する情報 (例: divisionName のグローバル ポリシー  *) を指定します*  。</span><span class="sxs-lookup"><span data-stu-id="94af6-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="94af6-132">サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの内部通信のアーカイブを制御するには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="94af6-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="94af6-133">サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="94af6-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="94af6-134">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="94af6-135">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="94af6-135">Site policies</span></span>

<span data-ttu-id="94af6-136">特定のサイトのアーカイブを有効または無効にするには、各サイトのアーカイブ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="94af6-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="94af6-137">サイト ポリシーはグローバル ポリシーより優先されますが、ユーザー ポリシーはサイト ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="94af6-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="94af6-138">アーカイブ ポリシーは、Microsoft Exchange 統合を使用しない場合、または Microsoft Exchange 統合を使用しているが、Exchange にホームではなく、メールボックスが In-Place Hold に設定されている一部のユーザーが含む場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="94af6-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="94af6-139">サイトのアーカイブ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="94af6-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="94af6-140">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="94af6-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94af6-141">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="94af6-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="94af6-142">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="94af6-143">グローバル ポリシー、サイト ポリシー、ユーザー ポリシーの階層など、アーカイブ ポリシーがどのように機能するのかについては [、「Plan for archiving in Skype for Business Server」](../../plan-your-deployment/archiving/archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94af6-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="94af6-144">[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="94af6-145">[ **サイトの選択]** で、ポリシーを適用するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="94af6-146">**[新しいアーカイブ ポリシー]** で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="94af6-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="94af6-147">[ **名前]** で、サイト ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="94af6-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="94af6-148">[ **説明]** に、サイト ポリシーの内容に関する情報 (たとえば、Redmond のサイト ポリシー) を入力します。</span><span class="sxs-lookup"><span data-stu-id="94af6-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="94af6-149">指定したサイトの内部通信のアーカイブを制御するには、[内部通信のアーカイブ] **チェック ボックスを** オンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="94af6-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="94af6-150">指定したサイトの外部通信のアーカイブを制御するには、[外部通信をアーカイブする] **チェック ボックスを** オンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="94af6-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="94af6-151">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="94af6-152">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="94af6-152">User policies</span></span>

<span data-ttu-id="94af6-153">ユーザーのアーカイブ ポリシーを作成および構成し、そのポリシーを特定のユーザーまたはユーザー グループに適用することで、特定のユーザーのアーカイブを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="94af6-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="94af6-154">ユーザー ポリシーは、グローバル ポリシーやサイト ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="94af6-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="94af6-155">アーカイブ ポリシーは、Microsoft Exchange 統合を使用しない場合、または Microsoft Exchange 統合を使用しているが、Exchange にホームではなく、メールボックスが In-Place Hold に設定されている一部のユーザーが含む場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="94af6-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="94af6-156">Skype for Business Server にホームのユーザーのアーカイブ ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="94af6-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="94af6-157">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="94af6-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94af6-158">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="94af6-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="94af6-159">左側のナビゲーション バーで、**[監視とアーカイブ]** をクリックし、**[アーカイブ ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="94af6-160">**[新規]** をクリックし、**[ユーザー ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="94af6-161">[**新しいアーカイブ ポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="94af6-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="94af6-162">[**名前**] にユーザー ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="94af6-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="94af6-163">[**説明**] に、ユーザー ポリシーの内容に関する情報を入力します (「法務部門のユーザー ポリシー」など)。</span><span class="sxs-lookup"><span data-stu-id="94af6-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="94af6-164">ユーザー ポリシーの内部通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="94af6-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="94af6-165">ユーザー ポリシーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="94af6-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="94af6-166">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-166">Click **Commit**.</span></span>
    
<span data-ttu-id="94af6-167">ユーザー ポリシーは、そのポリシーを割り当てたユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="94af6-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="94af6-168">ユーザーに Skype for Business Server アーカイブ ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="94af6-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="94af6-169">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="94af6-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94af6-170">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="94af6-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="94af6-171">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="94af6-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="94af6-172">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="94af6-173">[**アーカイブ ポリシー] の [Skype for Business Server** ユーザーの編集] で、適用するアーカイブ ユーザー ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="94af6-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="94af6-174">この **\<Automatic\>** 設定では、既定のサーバー インストール設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="94af6-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="94af6-175">これらの設定はサーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="94af6-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="94af6-176">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94af6-176">Click **Commit**.</span></span>
    

