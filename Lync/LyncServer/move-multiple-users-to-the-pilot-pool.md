---
title: 複数のユーザーをパイロットプールに移動する
description: 複数のユーザーをパイロットプールに移動します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 121509fbad863b0ce2d6cc9c7e9afaef360e2eb6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571333"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="3f407-103">複数のユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="3f407-103">Move multiple users to the pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f407-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3f407-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3f407-105">Lync server 2013 コントロールパネルまたは Lync Server 2013 管理シェルを使用して、lync server 2010 プールから Lync Server 2013 パイロットプールに複数のユーザーを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="3f407-105">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="3f407-106">Lync Server 2013 コントロールパネルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="3f407-106">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="3f407-107">[**Lync Server コントロール パネル**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="3f407-107">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="3f407-108">[**ユーザー**]、[検索]、[**ユーザー検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f407-108">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="3f407-109">Lync Server 2013 プールに移動する2人のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f407-109">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="3f407-110">この例では、Chen Yang および Claus Hansen というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="3f407-110">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="3f407-111">![ユーザーを特定の登録プールに移動する](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "ユーザーを特定の登録プールに移動する")</span><span class="sxs-lookup"><span data-stu-id="3f407-111">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="3f407-112">[**アクション**] メニューで、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f407-112">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="3f407-113">ドロップダウンリストから、[Lync Server 2013] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f407-113">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="3f407-114">[**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f407-114">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="3f407-115">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f407-115">Click OK.</span></span>
    
    <span data-ttu-id="3f407-116">![[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="3f407-116">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="3f407-117">ユーザーの [ **レジストラープール** ] 列に Lync Server 2013 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="3f407-117">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="3f407-118">Lync Server 2013 管理シェルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="3f407-118">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="3f407-119">Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3f407-119">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="3f407-120">コマンドラインで、次のように入力し、 **User1** と **User2** を特定のユーザー名に置き換えて、 **プールの \_ FQDN** を移行先のプールの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3f407-120">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="3f407-121">この例では、ユーザーが Hao Chen と Katie ヨルダンを移動します。</span><span class="sxs-lookup"><span data-stu-id="3f407-121">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="3f407-122">![PowerShell Get-CsUser コマンドレットの例](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell Get-CsUser コマンドレットの例")</span><span class="sxs-lookup"><span data-stu-id="3f407-122">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="3f407-123">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3f407-123">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="3f407-124">**レジストラープール**id は、前の手順で**プールの \_ FQDN**として指定したプールを指すようになります。</span><span class="sxs-lookup"><span data-stu-id="3f407-124">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="3f407-125">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3f407-125">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="3f407-126">手順を繰り返して、 **User2** が移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f407-126">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="3f407-127">![PowerShell Get-UsUser コマンドレットの出力](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell Get-UsUser コマンドレットの出力")</span><span class="sxs-lookup"><span data-stu-id="3f407-127">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="3f407-128">Lync Server 2013 管理シェルを使用してすべてのユーザーを同時に移動するには</span><span class="sxs-lookup"><span data-stu-id="3f407-128">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="3f407-129">この例では、すべてのユーザーが Lync Server 2010 プール (pool01.contoso.net) に返されています。</span><span class="sxs-lookup"><span data-stu-id="3f407-129">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="3f407-130">Lync Server 2013 管理シェルを使用して、すべてのユーザーを同時に Lync Server 2013 プール (pool02.contoso.net) に移動します。</span><span class="sxs-lookup"><span data-stu-id="3f407-130">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="3f407-131">**Lync Server 2013 管理シェル**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3f407-131">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="3f407-132">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3f407-132">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="3f407-133">![PowerShell コマンドレットと管理シェルの結果](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell コマンドレットと管理シェルの結果")</span><span class="sxs-lookup"><span data-stu-id="3f407-133">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="3f407-134">次に、いずれかのパイロット ユーザーに対して **Get-CsUser** を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f407-134">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="3f407-135">各ユーザーの **レジストラープール** id は、前の手順で "プール FQDN" として指定したプールを指すようになりました \_ 。</span><span class="sxs-lookup"><span data-stu-id="3f407-135">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="3f407-136">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3f407-136">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="3f407-137">さらに、Lync Server 2013 コントロールパネルでユーザーの一覧を表示し、レジストラープールの値が Lync Server 2013 プールを指すようになっていることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3f407-137">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="3f407-138">![Lync Server 2013 コントロールパネルのユーザーリスト](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 コントロールパネルのユーザーリスト")</span><span class="sxs-lookup"><span data-stu-id="3f407-138">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

