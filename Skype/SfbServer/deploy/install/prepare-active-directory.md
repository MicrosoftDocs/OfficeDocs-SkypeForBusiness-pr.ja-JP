---
title: Skype for Business Server 用の Active Directory の準備
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '概要: Skype for Business Server のインストール用に Active Directory ドメインを準備する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 6196855ffeaf33fbea11c47d56c620e3df9195ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801677"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a><span data-ttu-id="8b7df-104">Skype for Business Server 用の Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="8b7df-104">Prepare Active Directory for Skype for Business Server</span></span>
 
<span data-ttu-id="8b7df-105">**概要:** Skype for Business Server のインストール用に Active Directory ドメインを準備する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-105">**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server.</span></span> <span data-ttu-id="8b7df-106">Microsoft Evaluation Center から Skype for Business Server の無料試用版 [をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="8b7df-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="8b7df-107">Skype for Business Server は Active Directory と密接に関連して動作します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-107">Skype for Business Server works closely with Active Directory.</span></span> <span data-ttu-id="8b7df-108">Skype for Business Server を使用するには、Active Directory ドメインを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-108">You must prepare the Active Directory domain to work with Skype for Business Server.</span></span> <span data-ttu-id="8b7df-109">このプロセスは展開ウィザードで実行され、ドメインに対して 1 回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-109">This process is accomplished in the Deployment Wizard and is only done once for the domain.</span></span> <span data-ttu-id="8b7df-110">これは、プロセスによってグループが作成され、ドメインが変更され、1 回だけ行う必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="8b7df-110">This is because the process creates groups and modifies the domain, and you need to do that only once.</span></span> <span data-ttu-id="8b7df-111">手順 1. ~ 5. は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-111">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="8b7df-112">ただし、手順 6、7、および 8 を順番に実行し、図に示されている手順 1 ~ 5 の後に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-112">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="8b7df-113">Active Directory の準備は、手順 4/8 です。</span><span class="sxs-lookup"><span data-stu-id="8b7df-113">Preparing Active Directory is step 4 of 8.</span></span> <span data-ttu-id="8b7df-114">Active Directory の計画の詳細については [、「Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server [requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b7df-114">For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概要図](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a><span data-ttu-id="8b7df-116">Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="8b7df-116">Prepare Active Directory</span></span>

<span data-ttu-id="8b7df-117">Skype for Business Server は、Active Directory ドメイン サービス (AD DS) と緊密に統合されています。</span><span class="sxs-lookup"><span data-stu-id="8b7df-117">Skype for Business Server is tightly integrated with Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="8b7df-118">Skype for Business Server を初めてインストールする前に、Active Directory を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-118">Before Skype for Business Server can be installed for the first time, Active Directory must be prepared.</span></span> <span data-ttu-id="8b7df-119">「Active **Directory** の準備」というタイトルの展開ウィザードのセクションでは、Skype for Business Server で使用する Active Directory 環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-119">The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b7df-120">Skype for Business Server は(AD DS) を使用して、トポロジ内のすべてのサーバーを追跡および通信します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-120">Skype for Business Server uses (AD DS) to track and communicate with all of the servers in a topology.</span></span> <span data-ttu-id="8b7df-121">これらのサーバーの大部分は、Skype for Business Server が正常に動作するためにドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-121">The majority of these servers must be joined to the domain so that Skype for Business Server can work properly.</span></span> <span data-ttu-id="8b7df-122">エッジ やリバース プロキシなどのサーバーはドメインに参加しなけれな点に気を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-122">Keep in mind that servers such as Edge and Reverse Proxy should not be domain joined.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8b7df-123">Active Directory の準備手順は、展開内のドメインごとに 1 回だけ実行してください。</span><span class="sxs-lookup"><span data-stu-id="8b7df-123">The Prepare Active Directory procedure should be run only once for each domain in the deployment.</span></span> 
  
<span data-ttu-id="8b7df-124">Active Directory の準備に関するビデオ **の手順をご覧ください**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-124">Watch the video steps for **Prepare Active Directory**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a><span data-ttu-id="8b7df-125">展開ウィザードから Active Directory を準備する</span><span class="sxs-lookup"><span data-stu-id="8b7df-125">Prepare Active Directory from the Deployment Wizard</span></span>

1. <span data-ttu-id="8b7df-126">Active Directory ドメインの Schema Admins 資格情報を持つユーザーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="8b7df-126">Log on as a user with Schema Admins credentials for the Active Directory domain.</span></span>
    
2. <span data-ttu-id="8b7df-127">Skype for Business Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-127">Open Skype for Business Server Deployment Wizard.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8b7df-128">Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する場合は、展開ウィザードが実行されたコンピューターの手順を実行した AD DS ユーザーの Users ディレクトリでログ ファイルを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-128">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step.</span></span> <span data-ttu-id="8b7df-129">たとえば、ユーザーがドメイン contoso.local でドメイン管理者としてログオンした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-129">For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  
3. <span data-ttu-id="8b7df-130">[Active **Directory の準備] リンクをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-130">Click the **Prepare Active Directory** link.</span></span>
    
4. <span data-ttu-id="8b7df-131">**手順 1: スキーマを準備する**</span><span class="sxs-lookup"><span data-stu-id="8b7df-131">**Step 1: Prepare schema**</span></span>
    
    <span data-ttu-id="8b7df-132">a. </span><span class="sxs-lookup"><span data-stu-id="8b7df-132">a.</span></span> <span data-ttu-id="8b7df-133">手順 1 のタイトルの下のドロップダウンをクリックしてアクセスできる手順 1 の前提条件情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-133">Review the prerequisites information for Step 1 which can be accessed by clicking the drop-down under the Step 1 title.</span></span>
    
    <span data-ttu-id="8b7df-134">b.</span><span class="sxs-lookup"><span data-stu-id="8b7df-134">b.</span></span> <span data-ttu-id="8b7df-135">手順 **1** で [実行] をクリックして、スキーマの準備ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-135">Click **Run** in Step 1 to launch the Prepare Schema wizard.</span></span>
    
    <span data-ttu-id="8b7df-136">c.</span><span class="sxs-lookup"><span data-stu-id="8b7df-136">c.</span></span> <span data-ttu-id="8b7df-137">この手順は展開ごとに 1 回だけ実行し、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-137">Take note that the procedure should be run only once for each deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="8b7df-138">d. </span><span class="sxs-lookup"><span data-stu-id="8b7df-138">d.</span></span> <span data-ttu-id="8b7df-139">スキーマの準備が完了したら、[ログの表示] をクリックしてログ **を表示できます**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-139">Once the schema has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="8b7df-140">e. </span><span class="sxs-lookup"><span data-stu-id="8b7df-140">e.</span></span> <span data-ttu-id="8b7df-141">[ **完了]** をクリックしてスキーマの準備ウィザードを閉じ、Active Directory の準備の手順に戻ります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-141">Click **Finish** to close the Prepare Schema wizard, and return to the Prepare Active Directory steps.</span></span>
    
5. <span data-ttu-id="8b7df-142">**手順 2: スキーマ パーティションのレプリケーションを確認する**</span><span class="sxs-lookup"><span data-stu-id="8b7df-142">**Step 2: Verify replication of schema partition**</span></span>
    
    <span data-ttu-id="8b7df-143">a. </span><span class="sxs-lookup"><span data-stu-id="8b7df-143">a.</span></span> <span data-ttu-id="8b7df-144">ドメインのドメイン コントローラーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8b7df-144">Log on to the domain controller for the domain.</span></span>
    
    <span data-ttu-id="8b7df-145">b.</span><span class="sxs-lookup"><span data-stu-id="8b7df-145">b.</span></span> <span data-ttu-id="8b7df-146">サーバー **マネージャーの [ツール]\*\*\*\*ドロップダウン** メニューから ADSI Edit を **開きます**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-146">Open **ADSI Edit** from the **Tools** drop-down menu in **Server Manager**.</span></span>
    
    <span data-ttu-id="8b7df-147">c.</span><span class="sxs-lookup"><span data-stu-id="8b7df-147">c.</span></span> <span data-ttu-id="8b7df-148">**[アクション]** メニューで、**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b7df-148">On the **Action** menu, click **Connect to**.</span></span>
    
    <span data-ttu-id="8b7df-149">d. </span><span class="sxs-lookup"><span data-stu-id="8b7df-149">d.</span></span> <span data-ttu-id="8b7df-150">**[接続の設定]** ダイアログ ボックスの **[既知の名前付けコンテキストを選択する]** で、**[スキーマ]** を選択して **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b7df-150">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
    <span data-ttu-id="8b7df-151">e. </span><span class="sxs-lookup"><span data-stu-id="8b7df-151">e.</span></span> <span data-ttu-id="8b7df-152">スキーマ コンテナーで **、CN=ms-RTC-SIP-SchemaVersion を検索します**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-152">Under the schema container, search for **CN=ms-RTC-SIP-SchemaVersion**.</span></span> <span data-ttu-id="8b7df-153">このオブジェクトが存在し **、rangeUpper** 属性の値が 1150 で **rangeLower** 属性の値が 3 の場合、スキーマは正常に更新され、レプリケートされました。</span><span class="sxs-lookup"><span data-stu-id="8b7df-153">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, the schema was successfully updated and replicated.</span></span> <span data-ttu-id="8b7df-154">このオブジェクトが存在しない場合、または **rangeUpper** 属性と **rangeLower** 属性の値が指定されていない場合、スキーマは変更されていないか、レプリケートされていません。</span><span class="sxs-lookup"><span data-stu-id="8b7df-154">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, the schema was not modified or has not replicated.</span></span>
    
6. <span data-ttu-id="8b7df-155">**手順 3: 現在のフォレストを準備する**</span><span class="sxs-lookup"><span data-stu-id="8b7df-155">**Step 3: Prepare current forest**</span></span>
    
    <span data-ttu-id="8b7df-156">a. </span><span class="sxs-lookup"><span data-stu-id="8b7df-156">a.</span></span> <span data-ttu-id="8b7df-157">手順 3 の前提条件に関する情報を確認します。この情報には、手順 3 のタイトルの下にあるドロップダウンをクリックしてアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-157">Review the prerequisites information for Step 3 which can be accessed by clicking the drop-down under the Step 3 title.</span></span>
    
    <span data-ttu-id="8b7df-158">b.</span><span class="sxs-lookup"><span data-stu-id="8b7df-158">b.</span></span> <span data-ttu-id="8b7df-159">手順 **3** で [実行] をクリックして、現在のフォレストの準備ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-159">Click **Run** in Step 3 to launch the Prepare Current Forest wizard.</span></span>
    
    <span data-ttu-id="8b7df-160">c.</span><span class="sxs-lookup"><span data-stu-id="8b7df-160">c.</span></span> <span data-ttu-id="8b7df-161">この手順は展開ごとに 1 回だけ実行し、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-161">Take note that the procedure should be only run once per deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="8b7df-162">d. </span><span class="sxs-lookup"><span data-stu-id="8b7df-162">d.</span></span> <span data-ttu-id="8b7df-163">ユニバーサル グループを作成するドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-163">Specify the domain where the universal groups will be created.</span></span> <span data-ttu-id="8b7df-164">サーバーがドメインの一部である場合は、[ローカルドメイン] を選択し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-164">If the server is part of the domain, you can choose **Local domain**, and click **Next**.</span></span>
    
    <span data-ttu-id="8b7df-165">e. </span><span class="sxs-lookup"><span data-stu-id="8b7df-165">e.</span></span> <span data-ttu-id="8b7df-166">フォレストの準備が完了したら、[ログの表示] をクリックしてログ **を表示できます**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-166">Once the forest has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="8b7df-167">f.</span><span class="sxs-lookup"><span data-stu-id="8b7df-167">f.</span></span> <span data-ttu-id="8b7df-168">[ **完了]** をクリックして現在のフォレストの準備ウィザードを閉じ、Active Directory の準備の手順に戻ります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-168">Click **Finish** to close the Prepare Current Forest wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="8b7df-169">g. </span><span class="sxs-lookup"><span data-stu-id="8b7df-169">g.</span></span> <span data-ttu-id="8b7df-170">[**アプリ] ページから [Skype for Business Server 管理シェル**] をクリックして、PowerShell を起動します。 </span><span class="sxs-lookup"><span data-stu-id="8b7df-170">Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="8b7df-171">h.</span><span class="sxs-lookup"><span data-stu-id="8b7df-171">h.</span></span> <span data-ttu-id="8b7df-172">Get-CsAdForest コマンドを入力し **、Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-172">Type the command Get-CsAdForest, and press **Enter**.</span></span>
    
    <span data-ttu-id="8b7df-173">i.</span><span class="sxs-lookup"><span data-stu-id="8b7df-173">i.</span></span> <span data-ttu-id="8b7df-174">結果が **LC_FORESTSETTINGS_STATE_READY、次** の図に示すように、フォレストが正常に準備されています。</span><span class="sxs-lookup"><span data-stu-id="8b7df-174">If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.</span></span>
    
     ![フォレストのレプリケーションを確認します。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. <span data-ttu-id="8b7df-176">**手順 4: グローバル カタログのレプリケーションを確認する**</span><span class="sxs-lookup"><span data-stu-id="8b7df-176">**Step 4: Verify replication of the global catalog**</span></span>
    
    <span data-ttu-id="8b7df-177">a. </span><span class="sxs-lookup"><span data-stu-id="8b7df-177">a.</span></span> <span data-ttu-id="8b7df-178">ドメイン コントローラー (他のドメイン コントローラーからのリモート サイトが望ましい) で、フォレストの準備が実行されたフォレストで、Active Directory ユーザーとコンピューター **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-178">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="8b7df-179">b.</span><span class="sxs-lookup"><span data-stu-id="8b7df-179">b.</span></span> <span data-ttu-id="8b7df-180">**[Active Directory ユーザーとコンピューター]** で、フォレストまたは子ドメインのドメイン名を展開します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-180">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
    <span data-ttu-id="8b7df-181">c.</span><span class="sxs-lookup"><span data-stu-id="8b7df-181">c.</span></span> <span data-ttu-id="8b7df-182">左側の **ウィンドウで Users** コンテナーをクリックし、右側のウィンドウでユニバーサル グループ **CsAdministrator** を探します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-182">Click the **Users** container on the left side pane, and look for the Universal group **CsAdministrator** in the right side pane.</span></span> <span data-ttu-id="8b7df-183">CsAdministrator (Cs で始まる他の新しいユニバーサル グループ) が存在する場合、Active Directory のレプリケーションは成功しています。</span><span class="sxs-lookup"><span data-stu-id="8b7df-183">If CsAdministrator (among other new Universal groups that begin with Cs) is present, Active Directory replication has been successful.</span></span>
    
    <span data-ttu-id="8b7df-184">d. </span><span class="sxs-lookup"><span data-stu-id="8b7df-184">d.</span></span> <span data-ttu-id="8b7df-185">グループがまだ存在しない場合は、レプリケーションを強制するか、15 分待って右側のウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-185">If the groups are not yet present, you can force the replication, or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="8b7df-186">グループが表示されている場合、レプリケーションは完了しています。</span><span class="sxs-lookup"><span data-stu-id="8b7df-186">When the groups are present, replication is complete.</span></span>
    
8. <span data-ttu-id="8b7df-187">**手順 5: 現在のドメインを準備する**</span><span class="sxs-lookup"><span data-stu-id="8b7df-187">**Step 5: Prepare the current domain**</span></span>
    
    <span data-ttu-id="8b7df-188">a. </span><span class="sxs-lookup"><span data-stu-id="8b7df-188">a.</span></span> <span data-ttu-id="8b7df-189">手順 5 の前提条件の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-189">Review the prerequisites information for Step 5.</span></span>
    
    <span data-ttu-id="8b7df-190">b.</span><span class="sxs-lookup"><span data-stu-id="8b7df-190">b.</span></span> <span data-ttu-id="8b7df-191">手順 5 で [実行] をクリックして、現在のドメインの準備ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-191">Click **Run** in Step 5 to launch the Prepare Current Domain wizard.</span></span>
    
    <span data-ttu-id="8b7df-192">c.</span><span class="sxs-lookup"><span data-stu-id="8b7df-192">c.</span></span> <span data-ttu-id="8b7df-193">この手順は、展開内のドメインごとに 1 回だけ実行し、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-193">Take note that the procedure should only be run once for each domain in the deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="8b7df-194">d. </span><span class="sxs-lookup"><span data-stu-id="8b7df-194">d.</span></span> <span data-ttu-id="8b7df-195">ドメインの準備が完了したら、[ログの表示] をクリックしてログ **を表示できます**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-195">Once the domain has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="8b7df-196">e. </span><span class="sxs-lookup"><span data-stu-id="8b7df-196">e.</span></span> <span data-ttu-id="8b7df-197">[ **完了]** をクリックして現在のドメインの準備ウィザードを閉じ、Active Directory の準備の手順に戻ります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-197">Click **Finish** to close the Prepare Current Domain wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="8b7df-198">これらの手順は、Skype for Business Server オブジェクトが見つかったすべてのドメインで実行する必要があります。そうしないと、サービスが開始されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-198">These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start.</span></span> <span data-ttu-id="8b7df-199">これには、ユーザー、連絡先オブジェクト、管理グループ、その他の種類のオブジェクトなど、任意の種類の Active Directory オブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-199">This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object.</span></span> <span data-ttu-id="8b7df-200">必要に応Set-CsUserReplicatorConfiguration -ADDomainNamingContextList を使用して、Skype for Business Server オブジェクトを持つドメインのみを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-200">You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.</span></span>
    
9. <span data-ttu-id="8b7df-201">**手順 6: ドメイン内のレプリケーションを確認する**</span><span class="sxs-lookup"><span data-stu-id="8b7df-201">**Step 6: Verify replication in the domain**</span></span>
    
    <span data-ttu-id="8b7df-202">a. </span><span class="sxs-lookup"><span data-stu-id="8b7df-202">a.</span></span> <span data-ttu-id="8b7df-203">[アプリ **] ページから Skype for Business Server 管理シェル** をクリックして、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-203">Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="8b7df-204">b.</span><span class="sxs-lookup"><span data-stu-id="8b7df-204">b.</span></span> <span data-ttu-id="8b7df-205">コマンド プロンプトを使用Get-CsAdDomainドメイン内のレプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-205">Use the command Get-CsAdDomain to verify replication within the domain.</span></span>
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > <span data-ttu-id="8b7df-206">Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-206">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> 
  
    <span data-ttu-id="8b7df-207">contoso.local ドメインのコマンドを実行する例:</span><span class="sxs-lookup"><span data-stu-id="8b7df-207">Example of running the command for the contoso.local domain:</span></span>
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > <span data-ttu-id="8b7df-208">パラメーター GlobalSettingsDomainController を使用すると、グローバル設定を格納する場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-208">By using the parameter GlobalSettingsDomainController, you can indicate where global settings are stored.</span></span> <span data-ttu-id="8b7df-209">設定がシステム コンテナーに格納されている場合 (グローバル設定が構成コンテナーに移行されていないアップグレード展開で一般的)、AD DS フォレストのルートにドメイン コントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-209">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your AD DS forest.</span></span> <span data-ttu-id="8b7df-210">グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-210">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="8b7df-211">このパラメーターを指定しない場合、コマンドレットは設定が構成コンテナーに格納され、Active Directory 内の任意のドメイン コントローラーを参照すると想定します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-211">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="8b7df-212">c.</span><span class="sxs-lookup"><span data-stu-id="8b7df-212">c.</span></span> <span data-ttu-id="8b7df-213">結果が正しくレプリケート **LC_DOMAINSETTINGS_STATE_READY** ドメインは正常にレプリケートされています。</span><span class="sxs-lookup"><span data-stu-id="8b7df-213">If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.</span></span>
    
10. <span data-ttu-id="8b7df-214">**手順 7: Skype for Business Server コントロール パネルへの管理アクセスを提供するユーザーを追加する**</span><span class="sxs-lookup"><span data-stu-id="8b7df-214">**Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**</span></span>
    
    <span data-ttu-id="8b7df-215">a. </span><span class="sxs-lookup"><span data-stu-id="8b7df-215">a.</span></span> <span data-ttu-id="8b7df-216">Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="8b7df-216">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
    <span data-ttu-id="8b7df-217">b.</span><span class="sxs-lookup"><span data-stu-id="8b7df-217">b.</span></span> <span data-ttu-id="8b7df-218">**Active Directory ユーザー** とコンピューターを開き、ドメインを展開し **、Users** コンテナーをクリックして、CSAdministrator を右クリックして、[プロパティ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="8b7df-218">Open **Active Directory Users and Computers**, expand your domain, click the **Users** container, right-click CSAdministrator, and choose **Properties**.</span></span>
    
    <span data-ttu-id="8b7df-219">c.</span><span class="sxs-lookup"><span data-stu-id="8b7df-219">c.</span></span> <span data-ttu-id="8b7df-220">[**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b7df-220">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
    <span data-ttu-id="8b7df-221">d. </span><span class="sxs-lookup"><span data-stu-id="8b7df-221">d.</span></span> <span data-ttu-id="8b7df-222">[ **メンバー**] タブで [ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b7df-222">On the **Members** tab, click **Add**.</span></span> <span data-ttu-id="8b7df-223">[**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-223">In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**.</span></span> <span data-ttu-id="8b7df-224">CSAdministrators グループに追加するユーザー名またはグループ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-224">Type the user name(s) or group name(s) to add to the group CSAdministrators.</span></span> <span data-ttu-id="8b7df-225">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b7df-225">Click **OK**.</span></span>
    
    <span data-ttu-id="8b7df-226">e. </span><span class="sxs-lookup"><span data-stu-id="8b7df-226">e.</span></span> <span data-ttu-id="8b7df-227">[ **メンバー]** タブで、選択したユーザーまたはグループが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b7df-227">On the **Members** tab, confirm that the users or groups that you selected are present.</span></span> <span data-ttu-id="8b7df-228">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b7df-228">Click **OK**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8b7df-229">Skype for Business Server コントロール パネルは、役割ベースのアクセス制御ツールです。</span><span class="sxs-lookup"><span data-stu-id="8b7df-229">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="8b7df-230">CsAdministrator グループのメンバーシップにより、Skype for Business Server コントロール パネルを使用しているユーザーは、使用可能なすべての構成機能を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-230">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available.</span></span> <span data-ttu-id="8b7df-231">特定の機能向けに設計されたその他の役割も使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-231">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="8b7df-232">使用可能な役割の詳細については [、「Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server [requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b7df-232">For details on the roles available, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="8b7df-233">ユーザーを管理グループのメンバーにするために、Skype for Business Server を有効にする必要は必ずしもない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8b7df-233">Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
    > [!CAUTION]
    > <span data-ttu-id="8b7df-234">セキュリティと役割ベースのアクセス制御の整合性を維持するために、Skype for Business Server 展開の管理でユーザーが実行する役割を定義するグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-234">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span> 
  
11. <span data-ttu-id="8b7df-235">新しい Skype for Business Server セキュリティ グループを使用してセキュリティ トークンが更新された後、展開ウィザードを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="8b7df-235">Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.</span></span>
    
12. <span data-ttu-id="8b7df-236">図に示すように **、[Active Directory** の準備] の横に緑色のチェックマークが表示され、成功を確認します。</span><span class="sxs-lookup"><span data-stu-id="8b7df-236">Verify that you see a green checkmark next to **Prepare Active Directory** to confirm success, as shown in the figure.</span></span>
    
     ![Active Directory の準備が完了しました。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a><span data-ttu-id="8b7df-238">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b7df-238">See also</span></span>
 
[<span data-ttu-id="8b7df-239">Skype for Business Server 2015 の Active Directory ドメイン サービス</span><span class="sxs-lookup"><span data-stu-id="8b7df-239">Active Directory Domain Services for Skype for Business Server 2015</span></span>](../../plan-your-deployment/security/active-directory-domain-services.md)
