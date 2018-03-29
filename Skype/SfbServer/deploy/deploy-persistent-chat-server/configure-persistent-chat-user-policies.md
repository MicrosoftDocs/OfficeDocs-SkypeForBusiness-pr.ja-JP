---
title: Skype for Business Server 2015 での常設チャットのユーザー ポリシーの構成
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: '概要: ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのユーザーが最初のポリシーを作成する方法については、このトピックを読みます。 永続的なチャット ユーザーのポリシーでは、チャット ルームへのアクセスを許可されているかどうかを決定します。'
ms.openlocfilehash: 01ed6eb048f1949c93260c554eb58d0c76c5259f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="d83c2-104">Skype for Business Server 2015 での常設チャットのユーザー ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="d83c2-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d83c2-105">**の概要:**ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのユーザーが最初のポリシーを作成する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d83c2-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="d83c2-106">永続的なチャット ユーザーのポリシーでは、チャット ルームへのアクセスを許可されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="d83c2-107">次のレベルでの永続的なチャット サーバー ユーザーのポリシーを管理することができます: グローバル、サイト、またはユーザー。</span><span class="sxs-lookup"><span data-stu-id="d83c2-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="d83c2-108">最初に、グローバル ポリシーを構成して展開のすべてのユーザー用に常設チャットの設定を有効にしてから、ユーザー ポリシーおよびサイト ポリシーを追加作成して、特定のユーザーおよびサイトに対して常設チャットをオンにするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="d83c2-109">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d83c2-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="d83c2-110">グローバル ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="d83c2-110">Configure the global policy</span></span>
    
- <span data-ttu-id="d83c2-111">サイト ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d83c2-111">Create a site policy</span></span>
    
- <span data-ttu-id="d83c2-112">ユーザー ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d83c2-112">Create a user policy</span></span>
    
- <span data-ttu-id="d83c2-113">ポリシーをユーザーまたはユーザー グループに適用する</span><span class="sxs-lookup"><span data-stu-id="d83c2-113">Apply a policy to a user or user group</span></span>
    
## <a name="configure-the-global-policy"></a><span data-ttu-id="d83c2-114">グローバル ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="d83c2-114">Configure the global policy</span></span>

<span data-ttu-id="d83c2-115">グローバル ポリシーを構成するには:</span><span class="sxs-lookup"><span data-stu-id="d83c2-115">To configure the global policy:</span></span>
  
1. <span data-ttu-id="d83c2-116">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-116">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d83c2-117">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d83c2-118">ビジネス サーバーのコントロール パネルの Skype では、**永続的なチャット**] をクリックし、**永続的なチャットのポリシー**] をクリックし、します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-118">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="d83c2-119">ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-119">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d83c2-120">[**編集 常設チャットのポリシー - Global**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-120">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="d83c2-121">グローバルという既定の名前を使用しない場合は、[**名前**] でグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-121">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="d83c2-122">[**説明**] に、ユーザー ポリシーとは (たとえば、 _centralSiteName_のグローバル ポリシー) の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-122">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="d83c2-123">すべてのサイトおよびサイト ポリシーまたはユーザー ポリシーによって特に制御のユーザーの永続的なチャットを制御するには、オンまたは**永続的なチャットを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-123">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="d83c2-124">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-124">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="d83c2-125">サイト ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d83c2-125">Create a site policy</span></span>

<span data-ttu-id="d83c2-126">展開した各サイトに対して、サイト固有の常設チャット ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d83c2-126">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="d83c2-127">サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。</span><span class="sxs-lookup"><span data-stu-id="d83c2-127">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="d83c2-128">サイト ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-128">To create a site policy:</span></span>
  
1. <span data-ttu-id="d83c2-129">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d83c2-130">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d83c2-131">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="d83c2-132">[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="d83c2-133">[**サイトの選択**] でポリシーを適用するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="d83c2-134">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="d83c2-135">[**名前**] で、新しいサイト ポリシーの名前 (Redmond など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="d83c2-136">[**説明**] にサイト ポリシーの内容の詳細 (「Redmond のチャット ルーム ポリシー」など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="d83c2-137">サイト ポリシーによって特に制御されていないすべてのサイトの常設チャットを制御するには、[**常設チャットを有効にする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="d83c2-138">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-138">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="d83c2-139">ユーザー ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d83c2-139">Create a user policy</span></span>

<span data-ttu-id="d83c2-140">グローバル ポリシーと、ユーザーが属するサイトのポリシーよりも優先されるユーザー固有のポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d83c2-140">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="d83c2-141">ユーザー ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-141">To create a user policy:</span></span>
  
1. <span data-ttu-id="d83c2-142">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d83c2-143">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d83c2-144">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="d83c2-145">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="d83c2-146">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="d83c2-147">[**名前**] で、新しいユーザー ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="d83c2-148">[**説明**] に、ユーザー ポリシーとは (たとえば、特定のユーザーの永続的なチャットのポリシーなど) に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="d83c2-149">ユーザー ポリシーでは、具体的には制御できないユーザーのためには、永続的なチャットを制御するには、オンまたは**永続的なチャットを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="d83c2-150">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-150">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="d83c2-151">ポリシーをユーザー アカウントに適用する</span><span class="sxs-lookup"><span data-stu-id="d83c2-151">Apply a policy to a user account</span></span>

<span data-ttu-id="d83c2-152">ポリシーを作成した後は、以下の手順でユーザー アカウントに適用できます。</span><span class="sxs-lookup"><span data-stu-id="d83c2-152">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="d83c2-153">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-153">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d83c2-154">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-154">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d83c2-155">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-155">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="d83c2-156">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-156">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d83c2-157">ポリシーで**永続的なチャット****サーバー ユーザーのビジネスの Skype を編集**で、永続的なチャット ユーザー ポリシーを適用するを選択します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-157">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d83c2-158">**\<自動\>**の設定は、既定の有効なポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="d83c2-158">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="d83c2-159">これらの設定はサーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d83c2-159">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="d83c2-160">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d83c2-160">Click **Commit**.</span></span>
    

