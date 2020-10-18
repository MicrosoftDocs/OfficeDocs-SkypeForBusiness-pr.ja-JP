---
title: 'Lync Server 2013: ドメインの準備の実行'
description: 'Lync Server 2013: ドメインの準備を実行しています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f2c4ebe94d07ed2d1fd9be013cd8e88204312f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577783"
---
# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="711e1-103">Lync Server 2013 のドメインの準備を実行する</span><span class="sxs-lookup"><span data-stu-id="711e1-103">Running domain preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="711e1-104">_**トピックの最終更新日:** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="711e1-104">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="711e1-105">セットアップまたは Lync Server 管理シェルコマンドレットを使用して、ドメインを準備することができます。</span><span class="sxs-lookup"><span data-stu-id="711e1-105">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="711e1-106">ドメインを準備するコマンドレットは、 **-CsAdDomain を有効に**します。</span><span class="sxs-lookup"><span data-stu-id="711e1-106">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="711e1-107">「ドメインの準備」は、Lync Server 2013 用の Active Directory ドメインサービスを準備するための最後の手順です。</span><span class="sxs-lookup"><span data-stu-id="711e1-107">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="711e1-108">セットアップを使用してドメインを準備するには</span><span class="sxs-lookup"><span data-stu-id="711e1-108">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="711e1-109">Domain Admins グループのメンバーとしてドメイン内の任意のサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="711e1-109">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="711e1-110">Lync Server 2013 インストールフォルダーまたはメディアから、Setup.exe を実行して Lync Server 展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="711e1-110">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="711e1-111">[**Active Directory の準備**] をクリックし、展開状態が判別されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="711e1-111">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="711e1-112">[**手順 5: 現在のドメインの準備**] で、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="711e1-112">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="711e1-113">[ **ドメインの準備** ] ページで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="711e1-113">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="711e1-114">[**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="711e1-114">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="711e1-115">[ **アクション** ] 列の下にある [ **ドメインの準備**] を展開し、 **\<Success\>** 各タスクの最後に実行結果を検索して、ドメインの準備が正常に完了したことを確認し、ログを閉じて、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="711e1-115">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="711e1-116">Active Directory のレプリケーションが完了するまで待機するか、フォレストのルートドメインコントローラーの [Active Directory サイトとサービス] スナップインに一覧表示されているすべてのドメインコントローラーへのレプリケーションを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="711e1-116">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="711e1-117">コマンドレットを使用してドメインを準備するには</span><span class="sxs-lookup"><span data-stu-id="711e1-117">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="711e1-118">Domain Admins グループのメンバーとしてドメイン内の任意のサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="711e1-118">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="711e1-119">Lync Server コアコンポーネントを次のようにインストールします。</span><span class="sxs-lookup"><span data-stu-id="711e1-119">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="711e1-120">Lync Server 2013 インストールフォルダーまたはメディアから、Setup.exe を実行して Lync Server 展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="711e1-120">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="711e1-121">Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="711e1-121">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="711e1-122">[Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="711e1-122">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="711e1-123">既定の場所を選択するか、または好みの場所を **[参照]** で選択し、**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="711e1-123">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="711e1-124">[使用許諾契約書] ページで **[使用許諾契約書に同意します]** チェック ボックスをオンにし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="711e1-124">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="711e1-125">インストーラーによって Lync Server 2013 のコアコンポーネントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="711e1-125">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="711e1-126">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="711e1-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="711e1-127">実行</span><span class="sxs-lookup"><span data-stu-id="711e1-127">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="711e1-128">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="711e1-128">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="711e1-129">ドメイン パラメーターを指定しない場合、既定はローカル ドメインです。</span><span class="sxs-lookup"><span data-stu-id="711e1-129">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="711e1-130">ドメインの準備が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="711e1-130">Verify that domain preparation was successful.</span></span> <span data-ttu-id="711e1-131">実行</span><span class="sxs-lookup"><span data-stu-id="711e1-131">Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="711e1-132">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="711e1-132">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="711e1-133">パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="711e1-133">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="711e1-134">設定がシステムコンテナーに格納されている場合 (これは、構成コンテナーにグローバル設定が移行されていないアップグレード展開で一般的に使用されます)、Active Directory フォレストのルートにドメインコントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="711e1-134">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="711e1-135">グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="711e1-135">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="711e1-136">このパラメーターを指定しない場合、コマンドレットは、設定が構成コンテナーに格納されていると見なし、AD DS の任意のドメインコントローラーを参照し &nbsp; ます。</span><span class="sxs-lookup"><span data-stu-id="711e1-136">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="711e1-137">**Domain**パラメーターを指定しない場合、既定値はローカルドメインになります。</span><span class="sxs-lookup"><span data-stu-id="711e1-137">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="711e1-138">このコマンドレットは、ドメインの準備が正常に完了した場合に、 \*\*LC \_ domainsettings \_ 状態 \_ \*\* の値を返します。</span><span class="sxs-lookup"><span data-stu-id="711e1-138">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="711e1-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="711e1-139">See Also</span></span>


[<span data-ttu-id="711e1-140">Lync Server 2013 のコマンドレットを使用してドメインの準備を元に戻す</span><span class="sxs-lookup"><span data-stu-id="711e1-140">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="711e1-141">Lync Server 2013 のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="711e1-141">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

