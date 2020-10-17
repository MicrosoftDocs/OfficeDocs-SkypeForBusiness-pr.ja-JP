---
title: 'Lync Server 2013: スキーマの準備の実行'
description: 'Lync Server 2013: スキーマの準備を実行しています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0991bbff7f54f8b8b9eb01fc87f752e00f3dcbfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569363"
---
# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="efc8c-103">Lync Server 2013 での Active Directory スキーマの準備の実行</span><span class="sxs-lookup"><span data-stu-id="efc8c-103">Running Active Directory schema preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efc8c-104">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="efc8c-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="efc8c-105">セットアップまたは Lync Server 管理シェルコマンドレットを使用して、Active Directory スキーマを準備することができます。</span><span class="sxs-lookup"><span data-stu-id="efc8c-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="efc8c-106">Active Directory スキーマを拡張するコマンドレットは **Install-CsAdServerSchema** です。</span><span class="sxs-lookup"><span data-stu-id="efc8c-106">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="efc8c-107">スキーマ準備コマンドレット (<STRONG>Install-CsAdServerSchema</STRONG>) はスキーママスターにアクセスする必要があります。これには、リモートレジストリサービスが実行されていて、リモートレジストリキーが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc8c-107">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="efc8c-108">スキーママスターでリモートレジストリサービスを有効にできない場合は、スキーママスターでローカルにコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="efc8c-108">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="efc8c-109">レジストリのリモートアクセスの詳細については、Microsoft サポート技術情報の記事314837「レジストリへのリモートアクセスを管理する方法」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A> 。</span><span class="sxs-lookup"><span data-stu-id="efc8c-109">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="efc8c-110">スキーマの準備が完了したら、スキーマ パーティションがレプリケートされたことを手動で確認してから、フォレストの準備に進んでください。</span><span class="sxs-lookup"><span data-stu-id="efc8c-110">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="efc8c-111">詳細については、「 [Lync Server 2013 での Active Directory スキーマレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efc8c-111">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="efc8c-112">セットアップを使用して、現在のフォレストのスキーマを準備するには</span><span class="sxs-lookup"><span data-stu-id="efc8c-112">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="efc8c-113">Schema Admins グループのメンバーとして、さらに、スキーマ マスターにおける管理者権限を使用して、フォレスト内のサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-113">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="efc8c-114">Lync Server 2013 インストールフォルダーまたはメディアから、Setup.exe を実行して展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="efc8c-114">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="efc8c-115">Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-115">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="efc8c-116">[Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="efc8c-116">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="efc8c-117">既定の場所を選択するか、または好みの場所を **[参照]** で選択し、**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-117">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="efc8c-118">[使用許諾契約書] ページで **[使用許諾契約書に同意します]** チェック ボックスをオンにし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-118">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="efc8c-119">インストーラーによって Lync Server コアコンポーネントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="efc8c-119">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="efc8c-120">展開ウィザードの準備ができたら、[**Active Directory の準備**] をクリックし、展開状態が判別されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="efc8c-120">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="efc8c-121">[**ステップ 1: スキーマの準備**] で、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-121">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="efc8c-122">[**スキーマの準備**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-122">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="efc8c-123">[**コマンドの実行**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-123">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="efc8c-124">[ **アクション** ] 列で [ **スキーマ**の準備] を展開し、 **\<Success\>** 各タスクの最後に実行結果を検索して、スキーマの準備が正常に完了したことを確認し、ログを閉じて、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-124">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="efc8c-125">Active Directory レプリケーションが完了するのを待機するか、レプリケーションを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="efc8c-125">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="efc8c-126">スキーマの変更が他のすべてのドメイン コントローラーにレプリケートされたことを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="efc8c-126">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="efc8c-127">詳細については、「 [Lync Server 2013 での Active Directory スキーマレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efc8c-127">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="efc8c-128">コマンドレットを使用して現在のフォレストのスキーマを準備するには</span><span class="sxs-lookup"><span data-stu-id="efc8c-128">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="efc8c-129">Schema Admins グループのメンバーとして、さらに、スキーマ マスターにおける管理者の権限を使用して、フォレスト内のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-129">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="efc8c-130">Lync Server コアコンポーネントを次のようにインストールします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-130">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="efc8c-131">Lync Server 2013 インストールフォルダーまたはメディアから、Setup.exe を実行して Lync Server 展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="efc8c-131">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="efc8c-132">Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-132">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="efc8c-133">[Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="efc8c-133">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="efc8c-134">既定の場所を選択するか、または好みの場所を **[参照]** で選択し、**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-134">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="efc8c-135">[使用許諾契約書] ページで **[使用許諾契約書に同意します]** チェック ボックスをオンにし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-135">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="efc8c-136">インストーラーによって Lync Server 2013 のコアコンポーネントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="efc8c-136">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="efc8c-137">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="efc8c-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="efc8c-138">実行</span><span class="sxs-lookup"><span data-stu-id="efc8c-138">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="efc8c-139">Ldf パラメーターを指定しない場合、既定値は、レジストリから読み取った Lync Server 2013 のインストールパスになります。</span><span class="sxs-lookup"><span data-stu-id="efc8c-139">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="efc8c-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="efc8c-140">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="efc8c-141">次のコマンドレットを使用し、スキーマの準備が完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="efc8c-141">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="efc8c-142">スキーマの準備が成功した場合、このコマンドレットは **スキーマ \_ バージョン \_ 状態の \_ CURRENT** の値を返します。</span><span class="sxs-lookup"><span data-stu-id="efc8c-142">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="efc8c-143">Active Directory レプリケーションが完了するのを待機するか、レプリケーションを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="efc8c-143">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="efc8c-144">スキーマの変更が他のすべてのドメイン コントローラーにレプリケートされたことを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="efc8c-144">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="efc8c-145">詳細については、「 [Lync Server 2013 での Active Directory スキーマレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efc8c-145">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efc8c-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="efc8c-146">See Also</span></span>


[<span data-ttu-id="efc8c-147">Lync Server 2013 での Active Directory スキーマのレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="efc8c-147">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="efc8c-148">Lync Server 2013 での Active Directory スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="efc8c-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

