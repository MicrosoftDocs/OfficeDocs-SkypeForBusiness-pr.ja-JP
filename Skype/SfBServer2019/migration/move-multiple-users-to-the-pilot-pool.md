---
title: 複数のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 Management Shell を使用して、従来のプールから Skype for Business Server 2019 パイロットプールに複数のユーザーを移動することができます。
ms.openlocfilehash: abaffea04ff190b2ae99639484f63b564fd7784a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988952"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="c1faf-103">複数のユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="c1faf-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="c1faf-104">Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 Management Shell を使用して、従来のプールから Skype for Business Server 2019 パイロットプールに複数のユーザーを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="c1faf-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="c1faf-105">**この記事の内容**</span><span class="sxs-lookup"><span data-stu-id="c1faf-105">**In this article**</span></span>
  
[<span data-ttu-id="c1faf-106">Skype for Business Server 2019 コントロールパネルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="c1faf-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="c1faf-107">Skype for Business Server 2019 管理シェルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="c1faf-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="c1faf-108">Skype for Business Server 2019 管理シェルを使用してすべてのユーザーを同時に移動するには</span><span class="sxs-lookup"><span data-stu-id="c1faf-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="c1faf-109">Skype for Business Server 2019 コントロールパネルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="c1faf-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="c1faf-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="c1faf-110"></span></span>

1. <span data-ttu-id="c1faf-111">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1faf-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="c1faf-112">[**ユーザー**] をクリックし、[**検索**] をクリックして、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1faf-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="c1faf-113">Skype for Business Server 2019 プールに移動する2人のユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="c1faf-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="c1faf-114">この例では、Chen Yang sold と Claus というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![ユーザーを特定のレジスタプールに移動する](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="c1faf-116">[**アクション**] メニューで、[**選択したユーザーをプールに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="c1faf-117">ドロップダウンリストから、Skype for Business Server 2019 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="c1faf-118">[**操作**] をクリックし、[**選択したユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1faf-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="c1faf-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1faf-119">Click **OK**.</span></span>
    
     ![[ユーザーの移動]、[宛先レジストラー pool] ダイアログボックス](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="c1faf-121">ユーザーの**レジストラー pool**列に Skype For business Server 2019 プールが含まれていることを確認します。これは、ユーザーが正常に移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="c1faf-122">Skype for Business Server 2019 管理シェルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="c1faf-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="c1faf-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="c1faf-123"></span></span>

1. <span data-ttu-id="c1faf-124">Skype for Business Server 2019 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1faf-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="c1faf-125">コマンドラインで、次のように入力して、移動する特定のユーザー名で**User1**と**User2**を置き換え、 **pool_FQDN**を移行先プールの名前で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c1faf-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="c1faf-126">この例では、ユーザーの Hao Chen と Katie ヨルダンを移動します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-CsUser コマンドレットの例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="c1faf-128">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="c1faf-129">これで、**レジストラープール**id が、前の手順で**pool_FQDN**として指定したプールをポイントするようになります。</span><span class="sxs-lookup"><span data-stu-id="c1faf-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="c1faf-130">この id の存在は、ユーザーが正常に移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="c1faf-131">手順を繰り返して、 **User2**が移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![PowerShell Get-UsUser Identity コマンドレットの出力](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="c1faf-133">Skype for Business Server 2019 管理シェルを使用してすべてのユーザーを同時に移動するには</span><span class="sxs-lookup"><span data-stu-id="c1faf-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="c1faf-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="c1faf-134"></span></span>

<span data-ttu-id="c1faf-135">この例では、すべてのユーザーが従来のプール (pool01.contoso.net) に戻されています。</span><span class="sxs-lookup"><span data-stu-id="c1faf-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="c1faf-136">Skype for Business Server 2019 管理シェルを使用して、すべてのユーザーを Skype for Business Server 2019 プール (pool02.contoso.net) に同時に移行します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="c1faf-137">Skype for Business Server 2019 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1faf-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="c1faf-138">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell コマンドレットと結果の管理シェル](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="c1faf-140">パイロットユーザーのいずれかに対して **、ユーザーの購入ユーザー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="c1faf-141">各ユーザーの**レジストラープール**id は、前の手順で**pool_FQDN**として指定したプールを指すようになりました。</span><span class="sxs-lookup"><span data-stu-id="c1faf-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="c1faf-142">この id の存在は、ユーザーが正常に移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="c1faf-143">さらに、Skype for Business Server 2019 コントロールパネルでユーザーの一覧を表示し、[レジストラー Pool] の値が Skype for Business Server 2019 プールを指すようになったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1faf-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype for Business Server 2019 コントロールパネルのユーザーリスト](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

