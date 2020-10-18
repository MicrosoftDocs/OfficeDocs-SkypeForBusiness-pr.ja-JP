---
title: 'Lync Server 2013: フォレストの準備の実行'
description: 'Lync Server 2013: フォレストの準備を実行しています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad3ef2d7583d541701d6606946ca1df1bbd8cf23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577763"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="6c5b5-103">Lync Server 2013 のフォレストの準備の実行</span><span class="sxs-lookup"><span data-stu-id="6c5b5-103">Running forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c5b5-104">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6c5b5-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="6c5b5-105">セットアップまたは Lync Server 管理シェルコマンドレットを使用して、フォレストを準備することができます。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="6c5b5-106">フォレストを準備するコマンドレットは **Enable-CsAdForest** です。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-106">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="6c5b5-107">フォレストの準備が完了したら、ドメインの準備を実行する前に、グローバル設定がレプリケートされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-107">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="6c5b5-108">セットアップを使用してフォレストを準備するには</span><span class="sxs-lookup"><span data-stu-id="6c5b5-108">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="6c5b5-109">ドメインに参加しているコンピューターに、フォレストのルート ドメインの Enterprise Admins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-109">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="6c5b5-110">Lync Server 2013 インストールフォルダーまたはメディアから、Setup.exe を実行して展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-110">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="6c5b5-111">[**Active Directory の準備**] をクリックし、展開状態が判別されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-111">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="6c5b5-112">[**ステップ 3: 現在のフォレストの準備**] で、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-112">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="6c5b5-113">[**フォレストの準備**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-113">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c5b5-114">フォレストの準備 Lync Server 2013 のユニバーサルグループを配置する場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-114">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="6c5b5-115">組織の要件と一致する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-115">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="6c5b5-116">[**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-116">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="6c5b5-117">[ **アクション** ] 列で [ **フォレストの準備**] を展開し、 **\<Success\>** 各タスクの最後に実行結果を検索してフォレストの準備が正常に完了したことを確認し、ログを閉じて、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-117">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="6c5b5-p103">Active Directory のレプリケーションが完了するまで待機するか、フォレストのルート ドメイン コントローラーの [**Active Directory サイトとサービス**] スナップインに一覧表示されているすべてのドメイン コントローラーへのレプリケーションを強制的に実行してから、ドメインの準備を実行します。サイト内でレプリケーションが数分以内に開始されるよう、すべての Active Directory サイト内のドメイン コントローラー間でレプリケーションを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-p103">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation. Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="6c5b5-120">コマンドレットを使用してフォレストを準備するには</span><span class="sxs-lookup"><span data-stu-id="6c5b5-120">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="6c5b5-121">ドメインに参加しているコンピューターに、フォレストのルート ドメインの Domain Admins グループ メンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-121">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="6c5b5-122">Lync Server コアコンポーネントを次のようにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-122">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="6c5b5-123">Lync Server 2013 インストールフォルダーまたはメディアから、Setup.exe を実行して Lync Server 展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-123">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="6c5b5-124">Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-124">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="6c5b5-125">[Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-125">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="6c5b5-126">既定の場所を選択するか、または好みの場所を **[参照]** で選択し、**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-126">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="6c5b5-127">[使用許諾契約書] ページで **[使用許諾契約書に同意します]** チェック ボックスをオンにし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-127">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="6c5b5-128">インストーラーによって Lync Server 2013 のコアコンポーネントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-128">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="6c5b5-129">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="6c5b5-130">実行</span><span class="sxs-lookup"><span data-stu-id="6c5b5-130">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="6c5b5-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-131">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="6c5b5-p106">GroupDomain パラメーターを指定しない場合、既定値はローカル ドメインになります。 以前に既定のドメインではないドメインでユニバーサル グループを作成した場合は、GroupDomain パラメーターを明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-p106">If you do not specify the GroupDomain parameter, the default value is the local domain. If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="6c5b5-134">Active Directory のレプリケーションが完了するまで待機するか、フォレストのルート ドメイン コントローラーの [**Active Directory サイトとサービス**] スナップインに一覧表示されているすべてのドメイン コントローラーへのレプリケーションを強制的に実行してから、ドメインの準備を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-134">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="6c5b5-p107">フォレストの準備が成功したことを確認します。次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-p107">Verify that forest preparation was successful. Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="6c5b5-137">フォレストの準備が正常に完了した場合、このコマンドレットは \*\*LC \_ FORESTSETTINGS \_ 状態 \_ \*\* の値を返します。</span><span class="sxs-lookup"><span data-stu-id="6c5b5-137">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c5b5-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c5b5-138">See Also</span></span>


[<span data-ttu-id="6c5b5-139">コマンドレットを使用して Lync Server 2013 のフォレストの準備を元に戻す</span><span class="sxs-lookup"><span data-stu-id="6c5b5-139">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="6c5b5-140">Lync Server 2013 のフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="6c5b5-140">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

