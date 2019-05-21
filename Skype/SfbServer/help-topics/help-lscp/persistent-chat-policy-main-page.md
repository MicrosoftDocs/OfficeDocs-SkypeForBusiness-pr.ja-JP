---
title: 常設チャット ポリシー メイン ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: 常設チャットグループの常設チャットポリシーのページを使用すると、既定のグローバルポリシーの構成、展開用の追加のユーザーポリシーやサイトポリシーの作成など、グローバル、プール、サイト、またはユーザーレベルでポリシーを管理できます。 ユーザーが、ポリシーによって常設チャットサーバーを有効にしている場合は、常設チャットサーバー環境がクライアントに表示されます。
ms.openlocfilehash: ed4e8bbcb0856156148f459435b5cec857e9e223
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294173"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="55404-104">常設チャット ポリシー メイン ページ</span><span class="sxs-lookup"><span data-stu-id="55404-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="55404-105">**常設チャット**グループの**常設チャットポリシー**ページを使用すると、既定のグローバルポリシーを構成し、ユーザーに対して1つまたは複数の追加のユーザーとサイトポリシーを作成するなど、グローバル、プール、サイト、またはユーザーレベルでポリシーを管理できます。デプロイメント.</span><span class="sxs-lookup"><span data-stu-id="55404-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="55404-106">ユーザーが、ポリシーによって常設チャットサーバーを有効にしている場合は、常設チャットサーバー環境がクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="55404-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55404-107">トポロジでは、常設チャットサーバーのサイトポリシーは、ユーザーのプールごと、またはユーザーごとのサイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="55404-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="55404-108">グローバルポリシーは、常設チャットサーバーの展開時に自動的に作成され、構成はできますが、削除はできません。</span><span class="sxs-lookup"><span data-stu-id="55404-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="55404-109">グローバルポリシーはすべてのユーザーに適用されるため、ユーザーごとに設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="55404-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="55404-110">グローバルポリシーと共に、常設チャットサーバーのユーザーを有効にする、複数のサイトとユーザーのポリシーを作成して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="55404-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="55404-111">プールとサイトの常設チャットサーバーポリシーは、そのサイトのユーザーに対してのみ、グローバル常設チャットサーバーポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="55404-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="55404-112">ユーザーポリシーは、ユーザーポリシーが割り当てられているユーザーのグローバル、プール、サイトの各ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="55404-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55404-113">常設チャットサーバーを構成して使用するには、最初にトポロジビルダーを使用して、トポロジに常設チャットサーバーサポートを追加してから、トポロジを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55404-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="55404-114">詳細については、「 [Skype For Business server 2015 トポロジに常設チャットサーバーを追加する](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55404-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="55404-115">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="55404-115">Tasks that you can perform</span></span>

<span data-ttu-id="55404-116">[**常設チャットのポリシー**] ページでは、常設チャット サーバー ポリシーの有効化と管理のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="55404-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="55404-117">常設チャットのグローバルポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="55404-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="55404-118">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="55404-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="55404-119">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="55404-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="55404-120">Skype for Business Server コントロールパネルで、[**常設チャット**] をクリックし、[**常設チャットポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="55404-121">ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="55404-122">[**編集 常設チャットのポリシー - Global**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="55404-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="55404-123">グローバルという既定の名前を使用しない場合は、[**名前**] でグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="55404-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="55404-124">[**説明**] に、ユーザーポリシーの内容 ( _centralSiteName_のグローバルポリシーなど) の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="55404-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="55404-125">サイトポリシーまたはユーザーポリシーを通じて明確に制御されないすべてのサイトとユーザーの常設チャットを制御するには、[**常設チャットを有効に**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="55404-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="55404-126">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="55404-127">サイトの常設チャットポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="55404-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="55404-128">展開したサイトごとに、サイト固有の常設チャットポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="55404-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="55404-129">サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。</span><span class="sxs-lookup"><span data-stu-id="55404-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="55404-130">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="55404-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="55404-131">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="55404-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="55404-132">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="55404-133">[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="55404-134">[**サイトの選択**] でポリシーを適用するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="55404-135">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55404-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="55404-136">[**名前**] で、新しいサイト ポリシーの名前 (Redmond など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="55404-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="55404-137">[**説明**] にサイト ポリシーの内容の詳細 (「Redmond のチャット ルーム ポリシー」など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="55404-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="55404-138">サイト ポリシーによって特に制御されていないすべてのサイトの常設チャットを制御するには、[**常設チャットを有効にする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="55404-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="55404-139">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="55404-140">常設チャットのユーザーポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="55404-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="55404-141">Skype for Business Server コントロールパネルでは、ユーザーに割り当てることができるユーザーポリシーを定義する\*\*\*\* ことができます。</span><span class="sxs-lookup"><span data-stu-id="55404-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="55404-142">ユーザー ポリシーは、グローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーを割り当てられた特定のユーザーのみを対象にします。</span><span class="sxs-lookup"><span data-stu-id="55404-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="55404-143">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="55404-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="55404-144">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="55404-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="55404-145">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="55404-146">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="55404-147">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55404-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="55404-148">[**名前**] で、新しいユーザー ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="55404-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="55404-149">[**説明**] に、ユーザーポリシーの内容 (特定のユーザーの常設チャットポリシーなど) の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="55404-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="55404-150">ユーザーポリシーを通じて明確に制御されていないすべてのユーザーの常設チャットを制御するには、[**常設チャットを有効に**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="55404-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="55404-151">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="55404-152">常設チャットのユーザーポリシーをユーザーアカウントに適用するには</span><span class="sxs-lookup"><span data-stu-id="55404-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="55404-153">ユーザーが Skype for Business に対して有効になっている場合は、常設チャットサーバーの設定を有効または無効にするために、特定のユーザーに適切なポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="55404-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="55404-154">このトピックの手順を使用して、以前に作成した常設チャットのユーザーポリシーを1つ以上のユーザーアカウントまたはユーザーグループに適用します。</span><span class="sxs-lookup"><span data-stu-id="55404-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="55404-155">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="55404-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="55404-156">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="55404-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="55404-157">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="55404-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="55404-158">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="55404-159">[**常設チャットポリシー**] の [ **Lync Server ユーザーの編集**] で、適用する常設チャットのユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="55404-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="55404-160">\*\* \<自動\> \*\*設定では、既定の有効なポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="55404-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="55404-161">これらの設定はサーバーにより自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="55404-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="55404-162">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55404-162">Click **Commit**.</span></span>
    

