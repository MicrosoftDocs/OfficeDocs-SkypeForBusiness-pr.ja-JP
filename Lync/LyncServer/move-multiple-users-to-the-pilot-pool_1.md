---
title: 複数のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf1f33a47a9a311a9e4b09c7c50190c2c864452
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="2d87d-102">複数のユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="2d87d-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d87d-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2d87d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2d87d-104">Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルを使用して、Office Communications Server 2007 R2 プールから Lync Server 2013 パイロットプールに複数のユーザーを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="2d87d-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="2d87d-105">Lync Server 2013 コントロールパネルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="2d87d-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="2d87d-106">[**Lync Server コントロール パネル**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="2d87d-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="2d87d-107">[**ユーザー検索**] タブの [**検索**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d87d-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="2d87d-108">次に、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d87d-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="2d87d-109">[**Office Communications Server ユーザー**] が [**True**] のフィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="2d87d-110">[**検索**] をクリックして、従来の Office Communications Server 2007 R2 ユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="2d87d-111">Lync Server 2013 プールに移動する2人のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="2d87d-112">この例では、Chen Yang および Claus Hansen というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="2d87d-113">![OCS ユーザーを検索したときに表示されるユーザーリスト](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "OCS ユーザーを検索したときに表示されるユーザーリスト")</span><span class="sxs-lookup"><span data-stu-id="2d87d-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="2d87d-114">[**アクション**] メニューで、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d87d-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="2d87d-115">ドロップダウンリストから、[Lync Server 2013] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="2d87d-116">[**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d87d-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="2d87d-117">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d87d-117">Click OK.</span></span>
    
    <span data-ttu-id="2d87d-118">![[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="2d87d-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="2d87d-119">ユーザーの [**レジストラープール**] 列に Lync Server 2013 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="2d87d-120">Lync Server 2013 管理シェルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="2d87d-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="2d87d-121">Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d87d-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="2d87d-122">コマンドラインで、次のように入力し、 **User1**と**User2**を特定のユーザー名に置き換えて、**プール\_の FQDN**を移行先のプールの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2d87d-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="2d87d-123">この例では、ユーザーが Hao Chen と Katie ヨルダンを移動します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="2d87d-124">![レガシユーザーを移動するコマンドレットの例](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "レガシユーザーを移動するコマンドレットの例")</span><span class="sxs-lookup"><span data-stu-id="2d87d-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="2d87d-125">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="2d87d-126">**レジストラープール**id は、前の手順で**プール\_の FQDN**として指定したプールを指すようになります。</span><span class="sxs-lookup"><span data-stu-id="2d87d-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="2d87d-127">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2d87d-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="2d87d-128">手順を繰り返して、 **User2**が移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="2d87d-129">![PowerShell の Get-UsUser-Identity コマンドレットの出力](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell の Get-UsUser-Identity コマンドレットの出力")</span><span class="sxs-lookup"><span data-stu-id="2d87d-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="2d87d-130">Lync Server 2013 管理シェルを使用してすべてのユーザーを同時に移動するには</span><span class="sxs-lookup"><span data-stu-id="2d87d-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="2d87d-131">この例では、すべてのユーザーが Office Communications Server 2007 R2 プール (pool01.contoso.net) に返されています。</span><span class="sxs-lookup"><span data-stu-id="2d87d-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="2d87d-132">Lync Server 2013 管理シェルを使用して、すべてのユーザーを同時に Lync Server 2013 プール (pool02.contoso.net) に移動します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="2d87d-133">**Lync Server 2013 管理シェル**を開きます。</span><span class="sxs-lookup"><span data-stu-id="2d87d-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="2d87d-134">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="2d87d-135">![プール内のすべてのレガシユーザーを移動するコマンドレットの例](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "プール内のすべてのレガシユーザーを移動するコマンドレットの例")</span><span class="sxs-lookup"><span data-stu-id="2d87d-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="2d87d-136">次に、いずれかのパイロット ユーザーに対して **Get-CsUser** を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d87d-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="2d87d-137">各ユーザーの**レジストラープール**id は、前の手順で "プール\_FQDN" として指定したプールを指すようになりました。</span><span class="sxs-lookup"><span data-stu-id="2d87d-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="2d87d-138">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2d87d-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="2d87d-139">さらに、Lync Server 2013 コントロールパネルでユーザーの一覧を表示し、レジストラープールの値が Lync Server 2013 プールを指すようになっていることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="2d87d-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="2d87d-140">![Lync Server 2013 コントロールパネルのユーザーリスト](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 コントロールパネルのユーザーリスト")</span><span class="sxs-lookup"><span data-stu-id="2d87d-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

