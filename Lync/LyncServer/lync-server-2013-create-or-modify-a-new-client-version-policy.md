---
title: 'Lync Server 2013: 新しいクライアントバージョンポリシーの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb78150097fe7bde3b72338b3d1c9c37dc2a9b6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506114"
---
# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="e534a-102">Lync Server 2013 で新しいクライアントバージョンポリシーを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="e534a-102">Create or modify a new client version policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e534a-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e534a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e534a-104">クライアントバージョンポリシーを使用して、環境でサポートされているクライアントのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e534a-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="e534a-105">クライアントのバージョン管理を使用すると、複数のクライアントバージョンをサポートするためのコストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="e534a-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="e534a-106">また、クライアントの以前のバージョンとそれ以降のバージョンでは、使用可能な機能が以前のバージョンのクライアントによって制限される可能性があるため、ユーザーの全体的な操作が向上します。</span><span class="sxs-lookup"><span data-stu-id="e534a-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="e534a-107">Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルからクライアントバージョンポリシーを作成または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e534a-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="e534a-108">Lync Server コントロールパネルを使用してクライアントバージョンポリシーを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="e534a-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e534a-109">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e534a-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e534a-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e534a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e534a-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e534a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e534a-112">左側のナビゲーションバーで [ **クライアント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e534a-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e534a-113">既定では、[ <STRONG>クライアントバージョンポリシー</STRONG> ] タブが選択されています。</span><span class="sxs-lookup"><span data-stu-id="e534a-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="e534a-114">[ **クライアントバージョンポリシー** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e534a-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e534a-115">クライアントバージョンポリシーを作成するには、[ **新規**] をクリックし、[ **サイトポリシー**]、[ **プールポリシー**]、または [ **ユーザーポリシー**] をクリックして、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e534a-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="e534a-116">グローバルポリシーまたは既存のクライアントバージョンポリシーを変更するには、ポリシーを選択し、[ **編集**] をクリックしてから、[ **詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e534a-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e534a-117">[ **クライアントバージョンポリシーの編集** ] ページで、「 [Lync Server 2013 の新しいクライアントバージョンポリシールールを作成または変更する](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)」の説明に従ってルールを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="e534a-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e534a-118">Windows PowerShell コマンドレットを使用してクライアントバージョンポリシーを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="e534a-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e534a-119">**新しい-csclientversionpolicy**コマンドレットを使用してクライアントバージョンポリシーを作成し、それを変更するには、 **Set-csclientversionpolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e534a-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="e534a-120">これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e534a-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e534a-121">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="e534a-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="e534a-122">サイトスコープの新しいクライアントバージョンポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e534a-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="e534a-123">次のコマンドは、Redmond サイトに適用される新しいクライアントバージョンポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e534a-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="e534a-124">追加のパラメーターは指定されていないため、新しいポリシーでは既定のクライアントバージョン設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e534a-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="e534a-125">新しいユーザーごとのクライアントバージョンポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e534a-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="e534a-126">ユーザーごとのポリシーを作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e534a-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="e534a-127">詳細については、「 [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) コマンドレット」および「 [Set-csclientversionpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e534a-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

