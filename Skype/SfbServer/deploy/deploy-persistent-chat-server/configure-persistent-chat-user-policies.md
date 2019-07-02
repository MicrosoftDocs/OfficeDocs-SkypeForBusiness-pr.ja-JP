---
title: Skype for Business Server 2015 での常設チャットのユーザー ポリシーの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: '概要: このトピックでは、Skype for Business Server 2015 で常設チャットサーバーの初期ユーザーポリシーを作成する方法について説明します。 常設チャットのユーザーポリシーは、チャットルームへのアクセスがユーザーに許可されているかどうかを決定します。'
ms.openlocfilehash: 3f2a55f3a411fc3020ebe9af57d456f00dd74ef4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418124"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="eef93-104">Skype for Business Server 2015 での常設チャットのユーザー ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="eef93-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="eef93-105">**概要:** このトピックでは、Skype for Business Server 2015 で常設チャットサーバー用の初期ユーザーポリシーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eef93-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="eef93-106">常設チャットのユーザーポリシーは、チャットルームへのアクセスがユーザーに許可されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="eef93-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="eef93-107">常設チャットサーバーのユーザーポリシーは、グローバル、サイト、またはユーザーの各レベルで管理できます。</span><span class="sxs-lookup"><span data-stu-id="eef93-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="eef93-108">最初に、グローバル ポリシーを構成して展開のすべてのユーザー用に常設チャットの設定を有効にしてから、ユーザー ポリシーおよびサイト ポリシーを追加作成して、特定のユーザーおよびサイトに対して常設チャットをオンにするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="eef93-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="eef93-109">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eef93-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="eef93-110">グローバル ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="eef93-110">Configure the global policy</span></span>
    
- <span data-ttu-id="eef93-111">サイト ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="eef93-111">Create a site policy</span></span>
    
- <span data-ttu-id="eef93-112">ユーザー ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="eef93-112">Create a user policy</span></span>
    
- <span data-ttu-id="eef93-113">ポリシーをユーザーまたはユーザー グループに適用する</span><span class="sxs-lookup"><span data-stu-id="eef93-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="eef93-114">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="eef93-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="eef93-115">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="eef93-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="eef93-116">詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eef93-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="eef93-117">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="eef93-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="eef93-118">グローバル ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="eef93-118">Configure the global policy</span></span>

<span data-ttu-id="eef93-119">グローバル ポリシーを構成するには:</span><span class="sxs-lookup"><span data-stu-id="eef93-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="eef93-120">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="eef93-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="eef93-121">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="eef93-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="eef93-122">Skype for Business Server コントロールパネルで、[**常設チャット**] をクリックし、[**常設チャットポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="eef93-123">ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="eef93-124">[**編集 常設チャットのポリシー - Global**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eef93-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="eef93-125">グローバルという既定の名前を使用しない場合は、[**名前**] でグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="eef93-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="eef93-126">[**説明**] に、ユーザーポリシーの内容 ( _centralSiteName_のグローバルポリシーなど) の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="eef93-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="eef93-127">サイトポリシーまたはユーザーポリシーを通じて明確に制御されないすべてのサイトとユーザーの常設チャットを制御するには、[**常設チャットを有効に**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="eef93-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="eef93-128">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="eef93-129">サイト ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="eef93-129">Create a site policy</span></span>

<span data-ttu-id="eef93-130">展開した各サイトに対して、サイト固有の常設チャット ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="eef93-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="eef93-131">サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。</span><span class="sxs-lookup"><span data-stu-id="eef93-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="eef93-132">サイト ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eef93-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="eef93-133">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="eef93-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="eef93-134">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="eef93-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="eef93-135">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="eef93-136">[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="eef93-137">[**サイトの選択**] でポリシーを適用するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="eef93-138">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="eef93-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="eef93-139">[**名前**] で、新しいサイト ポリシーの名前 (Redmond など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="eef93-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="eef93-140">[**説明**] にサイト ポリシーの内容の詳細 (「Redmond のチャット ルーム ポリシー」など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="eef93-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="eef93-141">サイト ポリシーによって特に制御されていないすべてのサイトの常設チャットを制御するには、[**常設チャットを有効にする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="eef93-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="eef93-142">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="eef93-143">ユーザー ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="eef93-143">Create a user policy</span></span>

<span data-ttu-id="eef93-144">グローバル ポリシーと、ユーザーが属するサイトのポリシーよりも優先されるユーザー固有のポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="eef93-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="eef93-145">ユーザー ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eef93-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="eef93-146">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="eef93-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="eef93-147">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="eef93-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="eef93-148">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="eef93-149">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="eef93-150">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="eef93-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="eef93-151">[**名前**] で、新しいユーザー ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="eef93-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="eef93-152">[**説明**] に、ユーザーポリシーの内容 (特定のユーザーの常設チャットポリシーなど) の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="eef93-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="eef93-153">ユーザーポリシーを通じて明確に制御されていないすべてのユーザーの常設チャットを制御するには、[**常設チャットを有効に**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="eef93-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="eef93-154">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="eef93-155">ポリシーをユーザー アカウントに適用する</span><span class="sxs-lookup"><span data-stu-id="eef93-155">Apply a policy to a user account</span></span>

<span data-ttu-id="eef93-156">ポリシーを作成した後は、以下の手順でユーザー アカウントに適用できます。</span><span class="sxs-lookup"><span data-stu-id="eef93-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="eef93-157">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="eef93-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="eef93-158">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="eef93-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="eef93-159">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="eef93-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="eef93-160">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="eef93-161">[**常設チャットポリシー**] の [ **Skype For business Server ユーザーの編集**] で、適用する常設チャットのユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="eef93-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eef93-162">\*\* \<自動\> \*\*設定では、既定の有効なポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="eef93-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="eef93-163">これらの設定はサーバーにより自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="eef93-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="eef93-164">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eef93-164">Click **Commit**.</span></span>
    

