---
title: Skype for Business Server 2015 用の Active Directory の準備
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '概要: ビジネス サーバー 2015 の Skype のインストールの場合、Active Directory ドメインを準備する方法を説明します。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 6dfd6452e2ff0296fdeb90bd4f81296efac2be62
ms.sourcegitcommit: 4eae947e339e728e5e1f338677860b910aafc029
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a><span data-ttu-id="19374-104">Skype for Business Server 2015 用の Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="19374-104">Prepare Active Directory for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="19374-105">**の概要:** ビジネス サーバー 2015 の Skype のインストールの場合、Active Directory ドメインを準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19374-105">**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="19374-106">[マイクロソフト評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)からサーバー 2015 をビジネス用には、Skype の無料試用版をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="19374-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="19374-107">Skype ビジネス サーバーは、Active Directory と緊密に動作します。</span><span class="sxs-lookup"><span data-stu-id="19374-107">Skype for Business Server works closely with Active Directory.</span></span> <span data-ttu-id="19374-108">Skype でビジネスのサーバーを使用する Active Directory ドメインを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19374-108">You must prepare the Active Directory domain to work with Skype for Business Server.</span></span> <span data-ttu-id="19374-109">このプロセスは展開ウィザードで行われ、ドメインに対して 1 回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="19374-109">This process is accomplished in the Deployment Wizard and is only done once for the domain.</span></span> <span data-ttu-id="19374-110">これは、プロセスではグループを作成してドメインを変更しますが、その処理は 1 回だけ必要であるためです。</span><span class="sxs-lookup"><span data-stu-id="19374-110">This is because the process creates groups and modifies the domain, and you need to do that only once.</span></span> <span data-ttu-id="19374-111">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="19374-111">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="19374-112">ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19374-112">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="19374-113">Active Directory の準備は、8 つの手順の 4 番目です。</span><span class="sxs-lookup"><span data-stu-id="19374-113">Preparing Active Directory is step 4 of 8.</span></span> <span data-ttu-id="19374-114">Active Directory の計画の詳細については、 [Skype のビジネス サーバー 2015 の環境の要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19374-114">For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span>
  
![概要図](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a><span data-ttu-id="19374-116">Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="19374-116">Prepare Active Directory</span></span>

<span data-ttu-id="19374-117">ビジネス サーバー 2015 の Skype は、Active Directory ドメイン サービス (AD DS) と緊密に統合します。</span><span class="sxs-lookup"><span data-stu-id="19374-117">Skype for Business Server 2015 is tightly integrated with Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="19374-118">ビジネス サーバー 2015 の Skype をインストールするには、最初に、Active Directory を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19374-118">Before Skype for Business Server 2015 can be installed for the first time, Active Directory must be prepared.</span></span> <span data-ttu-id="19374-119">展開ウィザードが**Active Directory の準備**をという名前のセクションでは、ビジネスのサーバーの Skype で使用するための Active Directory 環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="19374-119">The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19374-120">ビジネス サーバー 2015 の Skype では、追跡し、すべてのトポロジ内のサーバーと通信する (AD DS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="19374-120">Skype for Business Server 2015 uses (AD DS) to track and communicate with all of the servers in a topology.</span></span> <span data-ttu-id="19374-121">Skype ビジネス サーバーが正常に動作できるように、すべてのサーバーをドメインに参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19374-121">Every server must be joined to the domain so that Skype for Business Server can work properly.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="19374-122">"Active Directory の準備" の手順は、展開のドメインごとに 1 回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19374-122">The Prepare Active Directory procedure should be run only once for each domain in the deployment.</span></span> 
  
<span data-ttu-id="19374-123">**Active Directory の準備**手順に関するビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19374-123">Watch the video steps for **Prepare Active Directory**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a><span data-ttu-id="19374-124">展開ウィザードからの Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="19374-124">Prepare Active Directory from the Deployment Wizard</span></span>

1. <span data-ttu-id="19374-125">Active Directory ドメインの Schema Admins の資格情報を持つユーザーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="19374-125">Log on as a user with Schema Admins credentials for the Active Directory domain.</span></span>
    
2. <span data-ttu-id="19374-126">Skype をビジネス サーバーの展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="19374-126">Open Skype for Business Server Deployment Wizard.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="19374-127">ビジネス サーバーの展開ウィザードは、Skype によって作成されるログ ファイルを確認するには場合、は、展開ウィザードが実行しているコンピューターの手順を実行する AD DS ユーザーのユーザー ディレクトリ内にそれらを検索できます。</span><span class="sxs-lookup"><span data-stu-id="19374-127">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step.</span></span> <span data-ttu-id="19374-128">などの場合は、ユーザーとしてログオン ドメイン管理者、ドメイン、contoso.local、ログ ファイル内にある: C:\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="19374-128">For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  
3. <span data-ttu-id="19374-129">[**Active Directory の準備**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-129">Click the **Prepare Active Directory** link.</span></span>
    
4. <span data-ttu-id="19374-130">**ステップ 1: スキーマを準備します。**</span><span class="sxs-lookup"><span data-stu-id="19374-130">**Step 1: Prepare schema**</span></span>
    
    <span data-ttu-id="19374-131">a.</span><span class="sxs-lookup"><span data-stu-id="19374-131">a.</span></span> <span data-ttu-id="19374-132">手順 1 の前提条件を確認します。"手順 1" というタイトルの下にあるドロップダウンをクリックすると、この情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="19374-132">Review the prerequisites information for Step 1 which can be accessed by clicking the drop-down under the Step 1 title.</span></span>
    
    <span data-ttu-id="19374-133">b.</span><span class="sxs-lookup"><span data-stu-id="19374-133">b.</span></span> <span data-ttu-id="19374-134">手順 1 の [**実行**] をクリックして、スキーマの準備ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="19374-134">Click **Run** in Step 1 to launch the Prepare Schema wizard.</span></span>
    
    <span data-ttu-id="19374-135">c.</span><span class="sxs-lookup"><span data-stu-id="19374-135">c.</span></span> <span data-ttu-id="19374-136">手順は、展開ごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-136">Take note that the procedure should be run only once for each deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="19374-137">d.</span><span class="sxs-lookup"><span data-stu-id="19374-137">d.</span></span> <span data-ttu-id="19374-138">スキーマが準備されれば、[**ログの表示**] をクリックするとログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="19374-138">Once the schema has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="19374-139">e。</span><span class="sxs-lookup"><span data-stu-id="19374-139">e.</span></span> <span data-ttu-id="19374-140">[**完了**] をクリックしてスキーマの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。</span><span class="sxs-lookup"><span data-stu-id="19374-140">Click **Finish** to close the Prepare Schema wizard, and return to the Prepare Active Directory steps.</span></span>
    
5. <span data-ttu-id="19374-141">**手順 2: スキーマ パーティションのレプリケーションを確認します。**</span><span class="sxs-lookup"><span data-stu-id="19374-141">**Step 2: Verify replication of schema partition**</span></span>
    
    <span data-ttu-id="19374-142">a.</span><span class="sxs-lookup"><span data-stu-id="19374-142">a.</span></span> <span data-ttu-id="19374-143">ドメインのドメイン コントローラーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="19374-143">Log on to the domain controller for the domain.</span></span>
    
    <span data-ttu-id="19374-144">b.</span><span class="sxs-lookup"><span data-stu-id="19374-144">b.</span></span> <span data-ttu-id="19374-145">[**サーバー マネージャー**] の [**ツール**] ドロップダウン メニューから [**ADSI エディター**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="19374-145">Open **ADSI Edit** from the **Tools** drop-down menu in **Server Manager**.</span></span>
    
    <span data-ttu-id="19374-146">c.</span><span class="sxs-lookup"><span data-stu-id="19374-146">c.</span></span> <span data-ttu-id="19374-147">[**アクション**] メニューで、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-147">On the **Action** menu, click **Connect to**.</span></span>
    
    <span data-ttu-id="19374-148">d.</span><span class="sxs-lookup"><span data-stu-id="19374-148">d.</span></span> <span data-ttu-id="19374-149">[**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-149">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
    <span data-ttu-id="19374-150">e。</span><span class="sxs-lookup"><span data-stu-id="19374-150">e.</span></span> <span data-ttu-id="19374-151">スキーマ コンテナーで、**CN=ms-RTC-SIP-SchemaVersion** を検索します。</span><span class="sxs-lookup"><span data-stu-id="19374-151">Under the schema container, search for **CN=ms-RTC-SIP-SchemaVersion**.</span></span> <span data-ttu-id="19374-152">このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。</span><span class="sxs-lookup"><span data-stu-id="19374-152">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, the schema was successfully updated and replicated.</span></span> <span data-ttu-id="19374-153">このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。</span><span class="sxs-lookup"><span data-stu-id="19374-153">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, the schema was not modified or has not replicated.</span></span>
    
6. <span data-ttu-id="19374-154">**ステップ 3: 現在のフォレストを準備します。**</span><span class="sxs-lookup"><span data-stu-id="19374-154">**Step 3: Prepare current forest**</span></span>
    
    <span data-ttu-id="19374-155">a.</span><span class="sxs-lookup"><span data-stu-id="19374-155">a.</span></span> <span data-ttu-id="19374-156">手順 3 の前提条件を確認します。"手順 3" というタイトルの下にあるドロップダウンをクリックすると、この情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="19374-156">Review the prerequisites information for Step 3 which can be accessed by clicking the drop-down under the Step 3 title.</span></span>
    
    <span data-ttu-id="19374-157">b.</span><span class="sxs-lookup"><span data-stu-id="19374-157">b.</span></span> <span data-ttu-id="19374-158">手順 3 の [**実行**] をクリックして、現在のフォレストの準備ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="19374-158">Click **Run** in Step 3 to launch the Prepare Current Forest wizard.</span></span>
    
    <span data-ttu-id="19374-159">c.</span><span class="sxs-lookup"><span data-stu-id="19374-159">c.</span></span> <span data-ttu-id="19374-160">手順は、展開ごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-160">Take note that the procedure should be only run once per deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="19374-161">d.</span><span class="sxs-lookup"><span data-stu-id="19374-161">d.</span></span> <span data-ttu-id="19374-162">ユニバーサル グループを作成するドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="19374-162">Specify the domain where the universal groups will be created.</span></span> <span data-ttu-id="19374-163">サーバーがドメインの一部である場合は、[**ローカル ドメイン**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-163">If the server is part of the domain, you can choose **Local domain**, and click **Next**.</span></span>
    
    <span data-ttu-id="19374-164">e。</span><span class="sxs-lookup"><span data-stu-id="19374-164">e.</span></span> <span data-ttu-id="19374-165">フォレストが準備されれば、[**ログの表示**] をクリックするとログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="19374-165">Once the forest has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="19374-166">f。</span><span class="sxs-lookup"><span data-stu-id="19374-166">f.</span></span> <span data-ttu-id="19374-167">[**完了**] をクリックして現在のフォレストの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。</span><span class="sxs-lookup"><span data-stu-id="19374-167">Click **Finish** to close the Prepare Current Forest wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="19374-168">g です。</span><span class="sxs-lookup"><span data-stu-id="19374-168">g.</span></span> <span data-ttu-id="19374-169">PowerShell を起動する**アプリケーション**のページから**Skype ビジネス サーバー管理シェル**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-169">Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="19374-170">h。</span><span class="sxs-lookup"><span data-stu-id="19374-170">h.</span></span> <span data-ttu-id="19374-171">Get-CsAdForest、コマンドを入力し、 **Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="19374-171">Type the command Get-CsAdForest, and press **Enter**.</span></span>
    
    <span data-ttu-id="19374-172">私。</span><span class="sxs-lookup"><span data-stu-id="19374-172">i.</span></span> <span data-ttu-id="19374-173">結果が**LC_FORESTSETTINGS_STATE_READY**の場合は、フォレストが正常に準備されて、図に示すように。</span><span class="sxs-lookup"><span data-stu-id="19374-173">If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.</span></span>
    
     ![フォレスト レプリケーションの確認](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. <span data-ttu-id="19374-175">**手順 4: グローバル カタログのレプリケーションを確認します。**</span><span class="sxs-lookup"><span data-stu-id="19374-175">**Step 4: Verify replication of the global catalog**</span></span>
    
    <span data-ttu-id="19374-176">a.</span><span class="sxs-lookup"><span data-stu-id="19374-176">a.</span></span> <span data-ttu-id="19374-177">フォレストの準備を実行したフォレスト内のドメイン コントローラー (他のドメイン コントローラーからリモート サイトにあるドメイン コントローラーを推奨) で、[**Active Directory ユーザーとコンピューター**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="19374-177">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="19374-178">b.</span><span class="sxs-lookup"><span data-stu-id="19374-178">b.</span></span> <span data-ttu-id="19374-179">[**Active Directory ユーザーとコンピューター**] で、フォレストまたは子ドメインのドメイン名を展開します。</span><span class="sxs-lookup"><span data-stu-id="19374-179">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
    <span data-ttu-id="19374-180">c.</span><span class="sxs-lookup"><span data-stu-id="19374-180">c.</span></span> <span data-ttu-id="19374-181">左側のウィンドウの [**ユーザー**] コンテナーをクリックし、右側のウィンドウでユニバーサル グループ **CsAdministrator** を見つけます。</span><span class="sxs-lookup"><span data-stu-id="19374-181">Click the **Users** container on the left side pane, and look for the Universal group **CsAdministrator** in the right side pane.</span></span> <span data-ttu-id="19374-182">(先頭に Cs が付いた他の新しいユニバーサル グループと共に) CsAdministrator が表示されている場合、Active Directory のレプリケーションは成功しています。</span><span class="sxs-lookup"><span data-stu-id="19374-182">If CsAdministrator (among other new Universal groups that begin with Cs) is present, Active Directory replication has been successful.</span></span>
    
    <span data-ttu-id="19374-183">d.</span><span class="sxs-lookup"><span data-stu-id="19374-183">d.</span></span> <span data-ttu-id="19374-184">グループが表示されていない場合、レプリケーションを強制的に実行するか、15 分待ってから右側のウィンドウを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="19374-184">If the groups are not yet present, you can force the replication, or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="19374-185">グループが表示されている場合、レプリケーションは完了しています。</span><span class="sxs-lookup"><span data-stu-id="19374-185">When the groups are present, replication is complete.</span></span>
    
8. <span data-ttu-id="19374-186">**手順 5: 現在のドメインを準備します。**</span><span class="sxs-lookup"><span data-stu-id="19374-186">**Step 5: Prepare the current domain**</span></span>
    
    <span data-ttu-id="19374-187">a.</span><span class="sxs-lookup"><span data-stu-id="19374-187">a.</span></span> <span data-ttu-id="19374-188">手順 5 の前提条件の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="19374-188">Review the prerequisites information for Step 5.</span></span>
    
    <span data-ttu-id="19374-189">b.</span><span class="sxs-lookup"><span data-stu-id="19374-189">b.</span></span> <span data-ttu-id="19374-190">手順 5 の [**実行**] をクリックして、現在のドメインの準備ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="19374-190">Click **Run** in Step 5 to launch the Prepare Current Domain wizard.</span></span>
    
    <span data-ttu-id="19374-191">c.</span><span class="sxs-lookup"><span data-stu-id="19374-191">c.</span></span> <span data-ttu-id="19374-192">手順は、展開のドメインごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-192">Take note that the procedure should only be run once for each domain in the deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="19374-193">d.</span><span class="sxs-lookup"><span data-stu-id="19374-193">d.</span></span> <span data-ttu-id="19374-194">ドメインが準備されれば、[**ログの表示**] をクリックするとログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="19374-194">Once the domain has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="19374-195">e。</span><span class="sxs-lookup"><span data-stu-id="19374-195">e.</span></span> <span data-ttu-id="19374-196">[**完了**] をクリックして現在のドメインの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。</span><span class="sxs-lookup"><span data-stu-id="19374-196">Click **Finish** to close the Prepare Current Domain wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="19374-197">Skype ビジネス サーバー オブジェクトが見つかったら、それ以外の場合サービスがすべてのドメインで、次の手順を完了する必要があるされません。</span><span class="sxs-lookup"><span data-stu-id="19374-197">These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start.</span></span> <span data-ttu-id="19374-198">オブジェクトには、ユーザー、連絡先オブジェクト、管理グループなどのすべての種類の Active Directory オブジェクトや、他のすべての種類のオブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="19374-198">This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object.</span></span> <span data-ttu-id="19374-199">必要な場合は、ドメインを追加するだけ、Skype で、ビジネスのサーバー オブジェクトのセット CsUserReplicatorConfiguration ADDomainNamingContextList を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19374-199">You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.</span></span>
    
9. <span data-ttu-id="19374-200">**手順 6: ドメイン内のレプリケーションを確認します。**</span><span class="sxs-lookup"><span data-stu-id="19374-200">**Step 6: Verify replication in the domain**</span></span>
    
    <span data-ttu-id="19374-201">a.</span><span class="sxs-lookup"><span data-stu-id="19374-201">a.</span></span> <span data-ttu-id="19374-202">PowerShell を起動する**アプリケーション**のページから**ビジネス サーバー管理シェルの Skype**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-202">Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="19374-203">b.</span><span class="sxs-lookup"><span data-stu-id="19374-203">b.</span></span> <span data-ttu-id="19374-204">Get CsAdDomain コマンドを使用すると、ドメイン内のレプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="19374-204">Use the command Get-CsAdDomain to verify replication within the domain.</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
 
   ```

    > [!NOTE]
    > <span data-ttu-id="19374-205">Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。</span><span class="sxs-lookup"><span data-stu-id="19374-205">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> 
  
    <span data-ttu-id="19374-206">contoso.local ドメインのコマンドの実行例:</span><span class="sxs-lookup"><span data-stu-id="19374-206">Example of running the command for the contoso.local domain:</span></span>
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local

   ```

    > [!NOTE]
    > <span data-ttu-id="19374-p138">パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。設定をシステム コンテナーに保存する (構成コンテナーにグローバル設定を移行していないアップグレードの展開で一般的) 場合、使用する AD DS フォレストのルートに 1 つのドメイン コントローラーを定義します。グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。このパラメーターを指定しない場合、コマンドレットでは、設定が構成コンテナーに保存されていると見なして、Active Directory の任意のドメイン コントローラーを参照します。</span><span class="sxs-lookup"><span data-stu-id="19374-p138">By using the parameter GlobalSettingsDomainController, you can indicate where global settings are stored. If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your AD DS forest. If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest. If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="19374-211">c.</span><span class="sxs-lookup"><span data-stu-id="19374-211">c.</span></span> <span data-ttu-id="19374-212">結果が**LC_DOMAINSETTINGS_STATE_READY**の場合は、ドメインが正常に複製されます。</span><span class="sxs-lookup"><span data-stu-id="19374-212">If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.</span></span>
    
10. <span data-ttu-id="19374-213">**手順 7: ビジネス サーバーのコントロール パネルの管理アクセス権を Skype に提供するためのユーザーを追加します。**</span><span class="sxs-lookup"><span data-stu-id="19374-213">**Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**</span></span>
    
    <span data-ttu-id="19374-214">a.</span><span class="sxs-lookup"><span data-stu-id="19374-214">a.</span></span> <span data-ttu-id="19374-215">Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="19374-215">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
    <span data-ttu-id="19374-216">b.</span><span class="sxs-lookup"><span data-stu-id="19374-216">b.</span></span> <span data-ttu-id="19374-217">[**Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して [**ユーザー**] コンテナーをクリックし、CSAdministrator を右クリックして、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19374-217">Open **Active Directory Users and Computers**, expand your domain, click the **Users** container, right-click CSAdministrator, and choose **Properties**.</span></span>
    
    <span data-ttu-id="19374-218">c.</span><span class="sxs-lookup"><span data-stu-id="19374-218">c.</span></span> <span data-ttu-id="19374-219">[**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-219">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
    <span data-ttu-id="19374-220">d.</span><span class="sxs-lookup"><span data-stu-id="19374-220">d.</span></span> <span data-ttu-id="19374-221">[**メンバー**] タブで [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-221">On the **Members** tab, click **Add**.</span></span> <span data-ttu-id="19374-222">[**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="19374-222">In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**.</span></span> <span data-ttu-id="19374-223">CSAdministrators グループに追加するユーザー名またはグループ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="19374-223">Type the user name(s) or group name(s) to add to the group CSAdministrators.</span></span> <span data-ttu-id="19374-224">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-224">Click **OK**.</span></span>
    
    <span data-ttu-id="19374-225">e。</span><span class="sxs-lookup"><span data-stu-id="19374-225">e.</span></span> <span data-ttu-id="19374-226">[**メンバー**] タブで、選択したユーザーまたはグループが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19374-226">On the **Members** tab, confirm that the users or groups that you selected are present.</span></span> <span data-ttu-id="19374-227">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19374-227">Click **OK**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="19374-228">ビジネス サーバーのコントロール パネルの Skype は、役割ベースのアクセス制御ツールです。</span><span class="sxs-lookup"><span data-stu-id="19374-228">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="19374-229">CsAdministrator グループのメンバーシップは、利用可能なすべての構成機能のビジネス サーバーのコントロール パネルの [フル コントロールの Skype を使用しているユーザーを与えます。</span><span class="sxs-lookup"><span data-stu-id="19374-229">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available.</span></span> <span data-ttu-id="19374-230">特定の機能向けに設計されたその他の役割も使用できます。</span><span class="sxs-lookup"><span data-stu-id="19374-230">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="19374-231">使用できるロールの詳細については、 [Skype のビジネス サーバー 2015 の環境の要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19374-231">For details on the roles available, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> <span data-ttu-id="19374-232">管理グループのメンバーになるために Skype ビジネス サーバーに対して有効にするユーザーがないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19374-232">Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
    > [!CAUTION]
    > <span data-ttu-id="19374-233">セキュリティとロール ベースのアクセス制御の整合性を確保するため、ユーザーがビジネス サーバー配置の Skype の管理を実行するどのような役割を定義するグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="19374-233">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span> 
  
11. <span data-ttu-id="19374-234">ログオフし、再びログオン Windows ビジネス サーバー セキュリティ グループでは、新しい Skype のユーザーのセキュリティ トークンが更新されるようと、展開ウィザードを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="19374-234">Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.</span></span>
    
12. <span data-ttu-id="19374-235">図のように、[**Active Directory の準備**] の横に成功を示す緑色のチェックマークが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19374-235">Verify that you see a green checkmark next to **Prepare Active Director** to confirm success, as shown in the figure.</span></span>
    
     ![Active Directory の準備が完了しました。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a><span data-ttu-id="19374-237">関連項目</span><span class="sxs-lookup"><span data-stu-id="19374-237">See also</span></span>

#### 
[<span data-ttu-id="19374-238">ビジネス サーバー 2015 の Skype の active Directory ドメイン サービス</span><span class="sxs-lookup"><span data-stu-id="19374-238">Active Directory Domain Services for Skype for Business Server 2015</span></span>](../../plan-your-deployment/security/active-directory-domain-services.md)