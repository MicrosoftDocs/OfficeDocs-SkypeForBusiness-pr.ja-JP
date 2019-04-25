---
title: Skype for Business Server 2015 での常設チャットのユーザー ポリシーの構成
ms.reviewer: ''
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
ms.openlocfilehash: e082898d92e622827e2543316b07a8be224c56c3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225456"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="a18f2-104">Skype for Business Server 2015 での常設チャットのユーザー ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="a18f2-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a18f2-105">**の概要:** ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのユーザーが最初のポリシーを作成する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a18f2-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="a18f2-106">永続的なチャット ユーザーのポリシーでは、チャット ルームへのアクセスを許可されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="a18f2-107">次のレベルでの永続的なチャット サーバー ユーザーのポリシーを管理することができます: グローバル、サイト、またはユーザー。</span><span class="sxs-lookup"><span data-stu-id="a18f2-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="a18f2-108">最初に、グローバル ポリシーを構成して展開のすべてのユーザー用に常設チャットの設定を有効にしてから、ユーザー ポリシーおよびサイト ポリシーを追加作成して、特定のユーザーおよびサイトに対して常設チャットをオンにするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="a18f2-109">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a18f2-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="a18f2-110">グローバル ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a18f2-110">Configure the global policy</span></span>
    
- <span data-ttu-id="a18f2-111">サイト ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a18f2-111">Create a site policy</span></span>
    
- <span data-ttu-id="a18f2-112">ユーザー ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a18f2-112">Create a user policy</span></span>
    
- <span data-ttu-id="a18f2-113">ポリシーをユーザーまたはユーザー グループに適用する</span><span class="sxs-lookup"><span data-stu-id="a18f2-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="a18f2-114">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a18f2-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a18f2-115">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a18f2-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="a18f2-116">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a18f2-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="a18f2-117">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="a18f2-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="a18f2-118">グローバル ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a18f2-118">Configure the global policy</span></span>

<span data-ttu-id="a18f2-119">グローバル ポリシーを構成するには:</span><span class="sxs-lookup"><span data-stu-id="a18f2-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="a18f2-120">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a18f2-121">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a18f2-122">ビジネス サーバーのコントロール パネルの Skype では、**永続的なチャット**] をクリックし、**永続的なチャットのポリシー**] をクリックし、します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="a18f2-123">ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a18f2-124">[**編集 常設チャットのポリシー - Global**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="a18f2-125">グローバルという既定の名前を使用しない場合は、[**名前**] でグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="a18f2-126">[**説明**] に、ユーザー ポリシーとは (たとえば、 _centralSiteName_のグローバル ポリシー) の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="a18f2-127">すべてのサイトおよびサイト ポリシーまたはユーザー ポリシーによって特に制御のユーザーの永続的なチャットを制御するには、オンまたは**永続的なチャットを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="a18f2-128">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="a18f2-129">サイト ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a18f2-129">Create a site policy</span></span>

<span data-ttu-id="a18f2-130">展開した各サイトに対して、サイト固有の常設チャット ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a18f2-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="a18f2-131">サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。</span><span class="sxs-lookup"><span data-stu-id="a18f2-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="a18f2-132">サイト ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="a18f2-133">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a18f2-134">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a18f2-135">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="a18f2-136">[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="a18f2-137">[**サイトの選択**] でポリシーを適用するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="a18f2-138">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="a18f2-139">[**名前**] で、新しいサイト ポリシーの名前 (Redmond など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="a18f2-140">[**説明**] にサイト ポリシーの内容の詳細 (「Redmond のチャット ルーム ポリシー」など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="a18f2-141">サイト ポリシーによって特に制御されていないすべてのサイトの常設チャットを制御するには、[**常設チャットを有効にする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="a18f2-142">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="a18f2-143">ユーザー ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a18f2-143">Create a user policy</span></span>

<span data-ttu-id="a18f2-144">グローバル ポリシーと、ユーザーが属するサイトのポリシーよりも優先されるユーザー固有のポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a18f2-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="a18f2-145">ユーザー ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="a18f2-146">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a18f2-147">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a18f2-148">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="a18f2-149">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="a18f2-150">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="a18f2-151">[**名前**] で、新しいユーザー ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="a18f2-152">[**説明**] に、ユーザー ポリシーとは (たとえば、特定のユーザーの永続的なチャットのポリシーなど) に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="a18f2-153">ユーザー ポリシーでは、具体的には制御できないユーザーのためには、永続的なチャットを制御するには、オンまたは**永続的なチャットを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="a18f2-154">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="a18f2-155">ポリシーをユーザー アカウントに適用する</span><span class="sxs-lookup"><span data-stu-id="a18f2-155">Apply a policy to a user account</span></span>

<span data-ttu-id="a18f2-156">ポリシーを作成した後は、以下の手順でユーザー アカウントに適用できます。</span><span class="sxs-lookup"><span data-stu-id="a18f2-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="a18f2-157">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a18f2-158">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a18f2-159">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="a18f2-160">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a18f2-161">ポリシーで**永続的なチャット\*\*\*\*サーバー ユーザーのビジネスの Skype を編集**で、永続的なチャット ユーザー ポリシーを適用するを選択します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a18f2-162">**\<自動\>** の設定は、既定の有効なポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="a18f2-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="a18f2-163">これらの設定はサーバーにより自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a18f2-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="a18f2-164">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a18f2-164">Click **Commit**.</span></span>
    

