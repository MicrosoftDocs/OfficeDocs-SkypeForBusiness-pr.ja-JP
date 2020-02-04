---
title: 'Lync Server 2013: スキーマの準備の実行'
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
ms.openlocfilehash: 06b02981e9baa589801839c8fd8c871ae35b0dde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="06c02-102">Lync Server 2013 での Active Directory スキーマの準備の実行</span><span class="sxs-lookup"><span data-stu-id="06c02-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06c02-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="06c02-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="06c02-104">セットアップまたは Lync Server 管理シェルコマンドレットを使用して、Active Directory スキーマを準備することができます。</span><span class="sxs-lookup"><span data-stu-id="06c02-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="06c02-105">Active Directory スキーマを拡張するコマンドレットは、**インストール-CsAdServerSchema**です。</span><span class="sxs-lookup"><span data-stu-id="06c02-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06c02-106">スキーマ準備コマンドレット (<STRONG>Install: CsAdServerSchema</STRONG>) では、スキーママスターにアクセスする必要があります。これには、リモートレジストリサービスが実行されており、リモートレジストリキーが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c02-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="06c02-107">スキーママスターでリモートレジストリサービスを有効にできない場合は、スキーママスターでコマンドレットをローカルで実行できます。</span><span class="sxs-lookup"><span data-stu-id="06c02-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="06c02-108">レジストリのリモートアクセスの詳細については、Microsoft サポート技術情報の記事314837「レジストリへのリモートアクセスを管理<A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06c02-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="06c02-109">スキーマの準備が完了したら、フォレストの準備に進む前に、スキーマパーティションがレプリケートされていることを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="06c02-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="06c02-110">詳細については、「 [Lync Server 2013 での Active Directory スキーマのレプリケーションを確認](lync-server-2013-verifying-schema-replication.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06c02-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="06c02-111">セットアップを使用して現在のフォレストのスキーマを準備するには</span><span class="sxs-lookup"><span data-stu-id="06c02-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="06c02-112">Schema Admins グループのメンバーとして、またはスキーママスターの管理者権限を持つ、フォレスト内のサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="06c02-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="06c02-113">Lync Server 2013 インストールフォルダーまたはメディアから setup.exe を実行して、展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="06c02-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="06c02-114">Microsoft Visual C++ 再頒布可能パッケージをインストールするかどうかを確認するメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="06c02-115">[Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="06c02-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="06c02-116">既定の場所を選ぶか、目的の場所を**参照**し、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="06c02-117">[使用許諾契約] ページで、[**使用許諾契約書に同意**します] をオンにし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="06c02-118">インストーラーによって Lync Server のコアコンポーネントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="06c02-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="06c02-119">展開ウィザードの準備ができたら、[ **Active Directory の準備**] をクリックし、展開の状態が決定されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="06c02-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="06c02-120">**手順 1: スキーマを準備**して、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="06c02-121">[**スキーマの準備**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="06c02-122">[**コマンドの実行**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="06c02-123">[**アクション**] 列で、[**スキーマの準備**] を展開し、各タスクの最後で\*\* \<成功\> **の実行結果を確認して、スキーマの準備が正常に完了したことを確認します。次に、[**完了\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="06c02-124">Active Directory のレプリケーションが完了するまで待つか、レプリケーションを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="06c02-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="06c02-125">スキーマの変更が他のすべてのドメインコントローラーにレプリケートされていることを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="06c02-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="06c02-126">詳細については、「 [Lync Server 2013 での Active Directory スキーマのレプリケーションを確認](lync-server-2013-verifying-schema-replication.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06c02-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="06c02-127">コマンドレットを使用して現在のフォレストのスキーマを準備するには</span><span class="sxs-lookup"><span data-stu-id="06c02-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="06c02-128">フォレスト内のコンピューターに Schema Admins グループのメンバーとしてログオンし、スキーママスターの管理者権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="06c02-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="06c02-129">Lync Server のコアコンポーネントは、次のようにインストールします。</span><span class="sxs-lookup"><span data-stu-id="06c02-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="06c02-130">Lync Server 2013 のインストールフォルダーまたはメディアから setup.exe を実行して、Lync Server 展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="06c02-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="06c02-131">Microsoft Visual C++ 再頒布可能パッケージをインストールするかどうかを確認するメッセージが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="06c02-132">[Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="06c02-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="06c02-133">既定の場所を選ぶか、目的の場所を**参照**し、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="06c02-134">[使用許諾契約] ページで、[**使用許諾契約書に同意**します] をオンにし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="06c02-135">インストーラーは、Lync Server 2013 コアコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="06c02-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="06c02-136">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="06c02-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="06c02-137">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="06c02-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="06c02-138">Ldf パラメーターを指定しない場合、既定値は、レジストリから読み取った Lync Server 2013 インストールパスです。</span><span class="sxs-lookup"><span data-stu-id="06c02-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="06c02-139">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="06c02-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="06c02-140">次のコマンドレットを使用して、スキーマの準備が完了するのを確認します。</span><span class="sxs-lookup"><span data-stu-id="06c02-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="06c02-141">スキーマ**\_の\_\_** 準備が正常に完了した場合、このコマンドレットは、スキーマのバージョンの現在の値を返します。</span><span class="sxs-lookup"><span data-stu-id="06c02-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="06c02-142">Active Directory のレプリケーションが完了するまで待つか、レプリケーションを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="06c02-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="06c02-143">スキーマの変更が他のすべてのドメインコントローラーにレプリケートされていることを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="06c02-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="06c02-144">詳細については、「 [Lync Server 2013 での Active Directory スキーマのレプリケーションを確認](lync-server-2013-verifying-schema-replication.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06c02-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06c02-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="06c02-145">See Also</span></span>


[<span data-ttu-id="06c02-146">Lync Server 2013 での Active Directory スキーマのレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="06c02-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="06c02-147">Lync Server 2013 での Active Directory スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="06c02-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

