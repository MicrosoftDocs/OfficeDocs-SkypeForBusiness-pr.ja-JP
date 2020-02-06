---
title: Skype for Business Server 用 Active Directory の準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server のインストール用に Active Directory ドメインを準備する方法について説明します。 Skype for Business Server の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: 5fce66e50bd8e51ce6af2ff266e0f4f46164c26e
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791725"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a><span data-ttu-id="1a7f4-104">Skype for Business Server 用 Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="1a7f4-104">Prepare Active Directory for Skype for Business Server</span></span>
 
<span data-ttu-id="1a7f4-105">**概要:** Skype for Business Server のインストール用に Active Directory ドメインを準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-105">**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server.</span></span> <span data-ttu-id="1a7f4-106">[Microsoft の評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)から Skype For business Server の無料トライアルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="1a7f4-107">Skype for Business Server は Active Directory と密接に連携しています。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-107">Skype for Business Server works closely with Active Directory.</span></span> <span data-ttu-id="1a7f4-108">Skype for Business Server を使用するには、Active Directory ドメインを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-108">You must prepare the Active Directory domain to work with Skype for Business Server.</span></span> <span data-ttu-id="1a7f4-109">このプロセスは展開ウィザードで行われ、ドメインに対して 1 回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-109">This process is accomplished in the Deployment Wizard and is only done once for the domain.</span></span> <span data-ttu-id="1a7f4-110">これは、プロセスではグループを作成してドメインを変更しますが、その処理は 1 回だけ必要であるためです。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-110">This is because the process creates groups and modifies the domain, and you need to do that only once.</span></span> <span data-ttu-id="1a7f4-111">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-111">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="1a7f4-112">ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-112">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="1a7f4-113">Active Directory の準備は、8 つの手順の 4 番目です。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-113">Preparing Active Directory is step 4 of 8.</span></span> <span data-ttu-id="1a7f4-114">Active Directory の計画について詳しくは、「skype for business [server の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」または「 [Skype for business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-114">For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概要図](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a><span data-ttu-id="1a7f4-116">Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="1a7f4-116">Prepare Active Directory</span></span>

<span data-ttu-id="1a7f4-117">Skype for Business Server は、Active Directory ドメインサービス (AD DS) と密接に統合されています。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-117">Skype for Business Server is tightly integrated with Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="1a7f4-118">Skype for Business Server を初めてインストールするには、Active Directory を準備しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-118">Before Skype for Business Server can be installed for the first time, Active Directory must be prepared.</span></span> <span data-ttu-id="1a7f4-119">[ **Active directory の準備**] というタイトルの展開ウィザードのセクションでは、Skype For business Server で使用する active directory 環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-119">The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a7f4-120">Skype for Business Server は (AD DS) を使って、トポロジ内のすべてのサーバーを追跡し、通信します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-120">Skype for Business Server uses (AD DS) to track and communicate with all of the servers in a topology.</span></span> <span data-ttu-id="1a7f4-121">Skype for Business Server が正常に動作するためには、これらのサーバーの大半がドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-121">The majority of these servers must be joined to the domain so that Skype for Business Server can work properly.</span></span> <span data-ttu-id="1a7f4-122">エッジとリバースプロキシなどのサーバーは、ドメインに参加しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-122">Keep in mind that servers such as Edge and Reverse Proxy should not be domain joined.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1a7f4-123">"Active Directory の準備" の手順は、展開のドメインごとに 1 回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-123">The Prepare Active Directory procedure should be run only once for each domain in the deployment.</span></span> 
  
<span data-ttu-id="1a7f4-124">**Active Directory の準備**手順に関するビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-124">Watch the video steps for **Prepare Active Directory**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a><span data-ttu-id="1a7f4-125">展開ウィザードからの Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="1a7f4-125">Prepare Active Directory from the Deployment Wizard</span></span>

1. <span data-ttu-id="1a7f4-126">Active Directory ドメインの Schema Admins の資格情報を持つユーザーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-126">Log on as a user with Schema Admins credentials for the Active Directory domain.</span></span>
    
2. <span data-ttu-id="1a7f4-127">Skype for Business Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-127">Open Skype for Business Server Deployment Wizard.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="1a7f4-128">Skype for Business Server 展開ウィザードによって作成されたログファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターで、手順を実行した AD DS ユーザーの Users ディレクトリにあることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-128">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step.</span></span> <span data-ttu-id="1a7f4-129">たとえば、ドメインのドメイン管理者としてログオンしているユーザーの場合、ログファイルは次の場所にあります。 C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-129">For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  
3. <span data-ttu-id="1a7f4-130">[**Active Directory の準備**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-130">Click the **Prepare Active Directory** link.</span></span>
    
4. <span data-ttu-id="1a7f4-131">**手順 1: スキーマの準備**</span><span class="sxs-lookup"><span data-stu-id="1a7f4-131">**Step 1: Prepare schema**</span></span>
    
    <span data-ttu-id="1a7f4-132">a.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-132">a.</span></span> <span data-ttu-id="1a7f4-133">手順 1 の前提条件を確認します。"手順 1" というタイトルの下にあるドロップダウンをクリックすると、この情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-133">Review the prerequisites information for Step 1 which can be accessed by clicking the drop-down under the Step 1 title.</span></span>
    
    <span data-ttu-id="1a7f4-134">b.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-134">b.</span></span> <span data-ttu-id="1a7f4-135">手順 1 の [**実行**] をクリックして、スキーマの準備ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-135">Click **Run** in Step 1 to launch the Prepare Schema wizard.</span></span>
    
    <span data-ttu-id="1a7f4-136">c.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-136">c.</span></span> <span data-ttu-id="1a7f4-137">手順は、展開ごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-137">Take note that the procedure should be run only once for each deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="1a7f4-138">d.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-138">d.</span></span> <span data-ttu-id="1a7f4-139">スキーマが準備されれば、[**ログの表示**] をクリックするとログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-139">Once the schema has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="1a7f4-140">•.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-140">e.</span></span> <span data-ttu-id="1a7f4-141">[**完了**] をクリックしてスキーマの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-141">Click **Finish** to close the Prepare Schema wizard, and return to the Prepare Active Directory steps.</span></span>
    
5. <span data-ttu-id="1a7f4-142">**手順 2: スキーマ パーティションのレプリケーションの確認**</span><span class="sxs-lookup"><span data-stu-id="1a7f4-142">**Step 2: Verify replication of schema partition**</span></span>
    
    <span data-ttu-id="1a7f4-143">a.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-143">a.</span></span> <span data-ttu-id="1a7f4-144">ドメインのドメイン コントローラーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-144">Log on to the domain controller for the domain.</span></span>
    
    <span data-ttu-id="1a7f4-145">b.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-145">b.</span></span> <span data-ttu-id="1a7f4-146">[**サーバー マネージャー**] の [**ツール**] ドロップダウン メニューから [**ADSI エディター**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-146">Open **ADSI Edit** from the **Tools** drop-down menu in **Server Manager**.</span></span>
    
    <span data-ttu-id="1a7f4-147">c.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-147">c.</span></span> <span data-ttu-id="1a7f4-148">[**アクション**] メニューで、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-148">On the **Action** menu, click **Connect to**.</span></span>
    
    <span data-ttu-id="1a7f4-149">d.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-149">d.</span></span> <span data-ttu-id="1a7f4-150">[**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-150">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
    <span data-ttu-id="1a7f4-151">•.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-151">e.</span></span> <span data-ttu-id="1a7f4-152">スキーマ コンテナーで、**CN=ms-RTC-SIP-SchemaVersion** を検索します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-152">Under the schema container, search for **CN=ms-RTC-SIP-SchemaVersion**.</span></span> <span data-ttu-id="1a7f4-153">このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-153">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, the schema was successfully updated and replicated.</span></span> <span data-ttu-id="1a7f4-154">このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-154">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, the schema was not modified or has not replicated.</span></span>
    
6. <span data-ttu-id="1a7f4-155">**手順 3: 現在のフォレストの準備**</span><span class="sxs-lookup"><span data-stu-id="1a7f4-155">**Step 3: Prepare current forest**</span></span>
    
    <span data-ttu-id="1a7f4-156">a.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-156">a.</span></span> <span data-ttu-id="1a7f4-157">手順 3 の前提条件を確認します。"手順 3" というタイトルの下にあるドロップダウンをクリックすると、この情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-157">Review the prerequisites information for Step 3 which can be accessed by clicking the drop-down under the Step 3 title.</span></span>
    
    <span data-ttu-id="1a7f4-158">b.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-158">b.</span></span> <span data-ttu-id="1a7f4-159">手順 3 の [**実行**] をクリックして、現在のフォレストの準備ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-159">Click **Run** in Step 3 to launch the Prepare Current Forest wizard.</span></span>
    
    <span data-ttu-id="1a7f4-160">c.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-160">c.</span></span> <span data-ttu-id="1a7f4-161">手順は、展開ごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-161">Take note that the procedure should be only run once per deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="1a7f4-162">d.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-162">d.</span></span> <span data-ttu-id="1a7f4-163">ユニバーサル グループを作成するドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-163">Specify the domain where the universal groups will be created.</span></span> <span data-ttu-id="1a7f4-164">サーバーがドメインの一部である場合は、[**ローカル ドメイン**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-164">If the server is part of the domain, you can choose **Local domain**, and click **Next**.</span></span>
    
    <span data-ttu-id="1a7f4-165">•.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-165">e.</span></span> <span data-ttu-id="1a7f4-166">フォレストが準備されれば、[**ログの表示**] をクリックするとログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-166">Once the forest has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="1a7f4-167">f.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-167">f.</span></span> <span data-ttu-id="1a7f4-168">[**完了**] をクリックして現在のフォレストの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-168">Click **Finish** to close the Prepare Current Forest wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="1a7f4-169">agdlp.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-169">g.</span></span> <span data-ttu-id="1a7f4-170">[**アプリ**] ページで [ **Skype For Business Server 管理シェル**] をクリックして PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-170">Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="1a7f4-171">ア.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-171">h.</span></span> <span data-ttu-id="1a7f4-172">コマンドの Get-CsAdForest を入力して、 **enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-172">Type the command Get-CsAdForest, and press **Enter**.</span></span>
    
    <span data-ttu-id="1a7f4-173">私。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-173">i.</span></span> <span data-ttu-id="1a7f4-174">結果が**LC_FORESTSETTINGS_STATE_READY**場合は、図に示すように、フォレストが正常に準備されています。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-174">If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.</span></span>
    
     ![フォレスト レプリケーションの確認](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. <span data-ttu-id="1a7f4-176">**手順 4: グローバル カタログのレプリケーションの確認**</span><span class="sxs-lookup"><span data-stu-id="1a7f4-176">**Step 4: Verify replication of the global catalog**</span></span>
    
    <span data-ttu-id="1a7f4-177">a.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-177">a.</span></span> <span data-ttu-id="1a7f4-178">フォレストの準備を実行したフォレスト内のドメイン コントローラー (他のドメイン コントローラーからリモート サイトにあるドメイン コントローラーを推奨) で、[**Active Directory ユーザーとコンピューター**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-178">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="1a7f4-179">b.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-179">b.</span></span> <span data-ttu-id="1a7f4-180">[**Active Directory ユーザーとコンピューター**] で、フォレストまたは子ドメインのドメイン名を展開します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-180">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
    <span data-ttu-id="1a7f4-181">c.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-181">c.</span></span> <span data-ttu-id="1a7f4-182">左側のウィンドウの [**ユーザー**] コンテナーをクリックし、右側のウィンドウでユニバーサル グループ **CsAdministrator** を見つけます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-182">Click the **Users** container on the left side pane, and look for the Universal group **CsAdministrator** in the right side pane.</span></span> <span data-ttu-id="1a7f4-183">(先頭に Cs が付いた他の新しいユニバーサル グループと共に) CsAdministrator が表示されている場合、Active Directory のレプリケーションは成功しています。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-183">If CsAdministrator (among other new Universal groups that begin with Cs) is present, Active Directory replication has been successful.</span></span>
    
    <span data-ttu-id="1a7f4-184">d.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-184">d.</span></span> <span data-ttu-id="1a7f4-185">グループが表示されていない場合、レプリケーションを強制的に実行するか、15 分待ってから右側のウィンドウを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-185">If the groups are not yet present, you can force the replication, or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="1a7f4-186">グループが表示されている場合、レプリケーションは完了しています。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-186">When the groups are present, replication is complete.</span></span>
    
8. <span data-ttu-id="1a7f4-187">**手順 5: 現在のドメインの準備**</span><span class="sxs-lookup"><span data-stu-id="1a7f4-187">**Step 5: Prepare the current domain**</span></span>
    
    <span data-ttu-id="1a7f4-188">a.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-188">a.</span></span> <span data-ttu-id="1a7f4-189">手順 5 の前提条件の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-189">Review the prerequisites information for Step 5.</span></span>
    
    <span data-ttu-id="1a7f4-190">b.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-190">b.</span></span> <span data-ttu-id="1a7f4-191">手順 5 の [**実行**] をクリックして、現在のドメインの準備ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-191">Click **Run** in Step 5 to launch the Prepare Current Domain wizard.</span></span>
    
    <span data-ttu-id="1a7f4-192">c.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-192">c.</span></span> <span data-ttu-id="1a7f4-193">手順は、展開のドメインごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-193">Take note that the procedure should only be run once for each domain in the deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="1a7f4-194">d.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-194">d.</span></span> <span data-ttu-id="1a7f4-195">ドメインが準備されれば、[**ログの表示**] をクリックするとログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-195">Once the domain has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="1a7f4-196">•.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-196">e.</span></span> <span data-ttu-id="1a7f4-197">[**完了**] をクリックして現在のドメインの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-197">Click **Finish** to close the Prepare Current Domain wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="1a7f4-198">これらの手順は、Skype for Business Server オブジェクトが検出されたすべてのドメインで完了する必要があります。そうでないと、サービスが開始されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-198">These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start.</span></span> <span data-ttu-id="1a7f4-199">オブジェクトには、ユーザー、連絡先オブジェクト、管理グループなどのすべての種類の Active Directory オブジェクトや、他のすべての種類のオブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-199">This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object.</span></span> <span data-ttu-id="1a7f4-200">Set-CsUserReplicatorConfiguration-ADDomainNamingContextList を使って、必要に応じて、Skype for Business Server オブジェクトでドメインのみを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-200">You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.</span></span>
    
9. <span data-ttu-id="1a7f4-201">**手順 6: ドメイン内のレプリケーションの確認**</span><span class="sxs-lookup"><span data-stu-id="1a7f4-201">**Step 6: Verify replication in the domain**</span></span>
    
    <span data-ttu-id="1a7f4-202">a.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-202">a.</span></span> <span data-ttu-id="1a7f4-203">[**アプリ**] ページから**Skype For Business Server 管理シェル**をクリックして PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-203">Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="1a7f4-204">b.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-204">b.</span></span> <span data-ttu-id="1a7f4-205">コマンドの Get-CsAdDomain を使用して、ドメイン内の複製を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-205">Use the command Get-CsAdDomain to verify replication within the domain.</span></span>
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > <span data-ttu-id="1a7f4-206">Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-206">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> 
  
    <span data-ttu-id="1a7f4-207">contoso.local ドメインのコマンドの実行例:</span><span class="sxs-lookup"><span data-stu-id="1a7f4-207">Example of running the command for the contoso.local domain:</span></span>
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > <span data-ttu-id="1a7f4-p138">パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。設定をシステム コンテナーに保存する (構成コンテナーにグローバル設定を移行していないアップグレードの展開で一般的) 場合、使用する AD DS フォレストのルートに 1 つのドメイン コントローラーを定義します。グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。このパラメーターを指定しない場合、コマンドレットでは、設定が構成コンテナーに保存されていると見なして、Active Directory の任意のドメイン コントローラーを参照します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-p138">By using the parameter GlobalSettingsDomainController, you can indicate where global settings are stored. If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your AD DS forest. If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest. If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="1a7f4-212">c.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-212">c.</span></span> <span data-ttu-id="1a7f4-213">結果が**LC_DOMAINSETTINGS_STATE_READY**場合は、ドメインが正常に複製されています。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-213">If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.</span></span>
    
10. <span data-ttu-id="1a7f4-214">**手順 7: Skype for Business Server コントロール パネルへの管理アクセスを提供するためのユーザーの追加**</span><span class="sxs-lookup"><span data-stu-id="1a7f4-214">**Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**</span></span>
    
    <span data-ttu-id="1a7f4-215">a.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-215">a.</span></span> <span data-ttu-id="1a7f4-216">Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-216">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
    <span data-ttu-id="1a7f4-217">b.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-217">b.</span></span> <span data-ttu-id="1a7f4-218">[**Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して [**ユーザー**] コンテナーをクリックし、CSAdministrator を右クリックして、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-218">Open **Active Directory Users and Computers**, expand your domain, click the **Users** container, right-click CSAdministrator, and choose **Properties**.</span></span>
    
    <span data-ttu-id="1a7f4-219">c.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-219">c.</span></span> <span data-ttu-id="1a7f4-220">[**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-220">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
    <span data-ttu-id="1a7f4-221">d.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-221">d.</span></span> <span data-ttu-id="1a7f4-222">[**メンバー**] タブで [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-222">On the **Members** tab, click **Add**.</span></span> <span data-ttu-id="1a7f4-223">[**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-223">In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**.</span></span> <span data-ttu-id="1a7f4-224">CSAdministrators グループに追加するユーザー名またはグループ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-224">Type the user name(s) or group name(s) to add to the group CSAdministrators.</span></span> <span data-ttu-id="1a7f4-225">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-225">Click **OK**.</span></span>
    
    <span data-ttu-id="1a7f4-226">•.</span><span class="sxs-lookup"><span data-stu-id="1a7f4-226">e.</span></span> <span data-ttu-id="1a7f4-227">[**メンバー**] タブで、選択したユーザーまたはグループが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-227">On the **Members** tab, confirm that the users or groups that you selected are present.</span></span> <span data-ttu-id="1a7f4-228">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-228">Click **OK**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="1a7f4-229">Skype for Business Server コントロールパネルは、役割ベースのアクセス制御ツールです。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-229">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="1a7f4-230">CsAdministrator グループのメンバーシップにより、Skype for Business Server コントロールパネルを使用しているユーザーは、使用可能なすべての構成機能に対してフルコントロールを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-230">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available.</span></span> <span data-ttu-id="1a7f4-231">特定の機能向けに設計されたその他の役割も使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-231">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="1a7f4-232">利用可能な役割の詳細については、「skype for business [server の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」および「 [Skype for business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-232">For details on the roles available, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="1a7f4-233">管理グループのメンバーになるためには、ユーザーが Skype for Business Server を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-233">Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
    > [!CAUTION]
    > <span data-ttu-id="1a7f4-234">セキュリティとロールベースのアクセス制御の整合性を維持するために、ユーザーが Skype for Business Server 展開の管理で実行する役割を定義するグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-234">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span> 
  
11. <span data-ttu-id="1a7f4-235">[ログオフ] をクリックして、新しい Skype for Business Server セキュリティグループでセキュリティトークンが更新されるように、Windows に再度ログオンします。次に、展開ウィザードをもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-235">Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.</span></span>
    
12. <span data-ttu-id="1a7f4-236">図に示すように、[ **Active Directory の準備**] の横に緑色のチェックマークが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a7f4-236">Verify that you see a green checkmark next to **Prepare Active Directory** to confirm success, as shown in the figure.</span></span>
    
     ![Active Directory の準備が完了しました。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a><span data-ttu-id="1a7f4-238">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a7f4-238">See also</span></span>
 
[<span data-ttu-id="1a7f4-239">Active Directory Domain Services for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1a7f4-239">Active Directory Domain Services for Skype for Business Server 2015</span></span>](../../plan-your-deployment/security/active-directory-domain-services.md)
