---
title: 複数のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efbce33c2f6ba8abdccfb42909bddfac107b6573
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="f8038-102">複数のユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="f8038-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8038-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f8038-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f8038-104">Lync server 2013 コントロールパネルまたは Lync Server 2013 管理シェルを使用して、lync server 2010 プールから Lync Server 2013 パイロットプールに複数のユーザーを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="f8038-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="f8038-105">Lync Server 2013 コントロールパネルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="f8038-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="f8038-106">[**Lync Server コントロール パネル**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="f8038-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="f8038-107">[**ユーザー**]、[検索]、[**ユーザー検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8038-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="f8038-108">Lync Server 2013 プールに移動する2人のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8038-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="f8038-109">この例では、Chen Yang および Claus Hansen というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="f8038-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="f8038-110">![ユーザーを特定の登録プールに移動する](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "ユーザーを特定の登録プールに移動する")</span><span class="sxs-lookup"><span data-stu-id="f8038-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="f8038-111">[**アクション**] メニューで、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8038-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="f8038-112">ドロップダウンリストから、[Lync Server 2013] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8038-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="f8038-113">[**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8038-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="f8038-114">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8038-114">Click OK.</span></span>
    
    <span data-ttu-id="f8038-115">![[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="f8038-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="f8038-116">ユーザーの [**レジストラープール**] 列に Lync Server 2013 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="f8038-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="f8038-117">Lync Server 2013 管理シェルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="f8038-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="f8038-118">Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f8038-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="f8038-119">コマンドラインで、次のように入力し、 **User1**と**User2**を特定のユーザー名に置き換えて、**プール\_の FQDN**を移行先のプールの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f8038-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="f8038-120">この例では、ユーザーが Hao Chen と Katie ヨルダンを移動します。</span><span class="sxs-lookup"><span data-stu-id="f8038-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="f8038-121">![PowerShell の Get-CsUser コマンドレットの例](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell の Get-CsUser コマンドレットの例")</span><span class="sxs-lookup"><span data-stu-id="f8038-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="f8038-122">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f8038-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="f8038-123">**レジストラープール**id は、前の手順で**プール\_の FQDN**として指定したプールを指すようになります。</span><span class="sxs-lookup"><span data-stu-id="f8038-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="f8038-124">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f8038-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="f8038-125">手順を繰り返して、 **User2**が移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8038-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="f8038-126">![PowerShell の Get-UsUser-Identity コマンドレットの出力](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell の Get-UsUser-Identity コマンドレットの出力")</span><span class="sxs-lookup"><span data-stu-id="f8038-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="f8038-127">Lync Server 2013 管理シェルを使用してすべてのユーザーを同時に移動するには</span><span class="sxs-lookup"><span data-stu-id="f8038-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="f8038-128">この例では、すべてのユーザーが Lync Server 2010 プール (pool01.contoso.net) に返されています。</span><span class="sxs-lookup"><span data-stu-id="f8038-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="f8038-129">Lync Server 2013 管理シェルを使用して、すべてのユーザーを同時に Lync Server 2013 プール (pool02.contoso.net) に移動します。</span><span class="sxs-lookup"><span data-stu-id="f8038-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="f8038-130">**Lync Server 2013 管理シェル**を開きます。</span><span class="sxs-lookup"><span data-stu-id="f8038-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="f8038-131">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f8038-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="f8038-132">![PowerShell コマンドレットと管理シェルの結果](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell コマンドレットと管理シェルの結果")</span><span class="sxs-lookup"><span data-stu-id="f8038-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="f8038-133">次に、いずれかのパイロット ユーザーに対して **Get-CsUser** を実行します。</span><span class="sxs-lookup"><span data-stu-id="f8038-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="f8038-134">各ユーザーの**レジストラープール**id は、前の手順で "プール\_FQDN" として指定したプールを指すようになりました。</span><span class="sxs-lookup"><span data-stu-id="f8038-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="f8038-135">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f8038-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="f8038-136">さらに、Lync Server 2013 コントロールパネルでユーザーの一覧を表示し、レジストラープールの値が Lync Server 2013 プールを指すようになっていることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f8038-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="f8038-137">![Lync Server 2013 コントロールパネルのユーザーリスト](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 コントロールパネルのユーザーリスト")</span><span class="sxs-lookup"><span data-stu-id="f8038-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

