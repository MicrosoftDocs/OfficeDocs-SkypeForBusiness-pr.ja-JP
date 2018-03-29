---
title: Skype for Business Server 2015 でのユーザー単位の PIN ポリシーの割り当て
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: '概要: ステージの AV と OAuth の証明書サーバー 2015 のビジネス用の Skype のです。'
ms.openlocfilehash: fd794fa3bc689a04967ac52b66c3ef905926cd18
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="ae171-103">Skype for Business Server 2015 でのユーザー単位の PIN ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="ae171-103">Assign a per-user PIN policy in Skype for Business Server 2015</span></span>

<span data-ttu-id="ae171-104">**の概要:**ステージ AV と OAuth の証明書サーバー 2015 のビジネス用の Skype のです。</span><span class="sxs-lookup"><span data-stu-id="ae171-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ae171-105">ダイヤルイン会議の個人識別番号 (PIN) ポリシーは、個々 のビジネス サーバーのコントロール パネルの Skype で構成可能なユーザー アカウントの設定のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="ae171-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="ae171-p101">ユーザーは 1 つまたは複数のユーザー単位の PIN ポリシーを展開できますが、この展開はオプションです。また、グローバルレベルの PIN ポリシーまたはサイトレベルの PIN ポリシーだけを展開することもできます。ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。特定のサイトレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、ダイヤルイン会議での PIN の使用に関するユーザーの権限およびアクセス許可により、グローバルレベルの PIN ポリシーで定義された既定の設定が自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ae171-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="ae171-110">ユーザー単位の PIN ポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーを割り当て、特定のユーザーが作成したか、特定のユーザーが使用する PIN にサーバーが課す制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae171-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="ae171-111">ユーザー単位の PIN ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="ae171-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="ae171-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ae171-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ae171-113">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ae171-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ae171-114">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ae171-115">ユーザーを探すには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae171-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="ae171-116">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="ae171-117">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="ae171-118">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="ae171-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="ae171-119">a.</span><span class="sxs-lookup"><span data-stu-id="ae171-119">a.</span></span> <span data-ttu-id="ae171-120">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="ae171-121">b.</span><span class="sxs-lookup"><span data-stu-id="ae171-121">b.</span></span> <span data-ttu-id="ae171-122">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae171-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="ae171-123">c.</span><span class="sxs-lookup"><span data-stu-id="ae171-123">c.</span></span> <span data-ttu-id="ae171-124">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="ae171-125">d.</span><span class="sxs-lookup"><span data-stu-id="ae171-125">d.</span></span> <span data-ttu-id="ae171-126">選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="ae171-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ae171-127">クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="ae171-128">e。</span><span class="sxs-lookup"><span data-stu-id="ae171-128">e.</span></span> <span data-ttu-id="ae171-129">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="ae171-130">検索結果のユーザーをクリックして、[**アクション**] をクリックしてから、[**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ae171-131">同じユーザー単位の PIN ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[**アクション**] をクリックしてから [**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="ae171-132">[**ポリシーの割り当て**] の [**PIN ポリシー**] で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae171-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae171-133">**ポリシーの割り当て**] ダイアログ ボックスを使用して構成することができます複数のポリシーがあるため**\<は、してください\>**のすべてのポリシー] ダイアログ ボックスで既定で選択します。</span><span class="sxs-lookup"><span data-stu-id="ae171-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="ae171-134">この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="ae171-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="ae171-135">Skype ビジネス サーバーの 2015 グローバル レベルのポリシーを自動的に選択するを許可するか、サイト レベルのポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="ae171-135">Allow Skype for Business Server 2015 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="ae171-136">[**PIN ポリシー**] ページであらかじめ定義した、ユーザー単位の PIN ポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="ae171-137">割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [**表示**] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae171-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="ae171-138">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae171-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ae171-139">Windows PowerShell コマンドレットを使用して、ユーザー単位の PIN ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ae171-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ae171-140">Windows PowerShell と**与える CsPinPolicy**コマンドレットを使用してユーザー単位の PIN ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ae171-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="ae171-141">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ae171-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ae171-142">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae171-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ae171-143">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="ae171-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="ae171-144">ユーザー単位の PIN ポリシーを単一のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="ae171-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="ae171-145">次のコマンドは、ユーザー単位の PIN ポリシー RedmondPinPolicy をユーザー「Ken Myer」に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ae171-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="ae171-146">ユーザー単位の PIN ポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="ae171-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="ae171-147">次のコマンドは、ユーザー単位の PIN ポリシー RedmondUsersPinPolicy を Redmond 市で働くすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ae171-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="ae171-148">詳細については、このコマンドで使用される、LdapFilter パラメーターは、 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae171-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="ae171-149">ユーザー単位の PIN ポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="ae171-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="ae171-p110">次のコマンドは、Ken Myer に割り当てられたユーザー単位の PIN ポリシーを割り当て解除します。ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="ae171-p110">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="ae171-153">詳細については、[補助金 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae171-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ae171-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae171-154">See also</span></span>

#### 

[<span data-ttu-id="ae171-155">ビジネス サーバー 2015 の Skype の新しい暗証番号 (pin) ポリシーを作成する.</span><span class="sxs-lookup"><span data-stu-id="ae171-155">Create a new PIN policy in Skype for Business Server 2015</span></span>](create-a-new-pin-policy.md)

