---
title: 複数のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 管理シェルを使用して、従来のプールから Skype for business Server 2019 パイロットプールに複数のユーザーを移動することができます。
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753429"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="62716-103">複数のユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="62716-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="62716-104">Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 管理シェルを使用して、従来のプールから Skype for business Server 2019 パイロットプールに複数のユーザーを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="62716-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="62716-105">**この記事の内容**</span><span class="sxs-lookup"><span data-stu-id="62716-105">**In this article**</span></span>
  
[<span data-ttu-id="62716-106">Skype for Business Server 2019 コントロールパネルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="62716-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="62716-107">Skype for Business Server 2019 管理シェルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="62716-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="62716-108">Skype for Business Server 2019 管理シェルを使用してすべてのユーザーを同時に移動するには</span><span class="sxs-lookup"><span data-stu-id="62716-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="62716-109">Skype for Business Server 2019 コントロールパネルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="62716-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="62716-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="62716-110"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="62716-111">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="62716-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="62716-112">[**ユーザー**]、[**検索**]、[**ユーザー検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="62716-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="62716-113">Skype for Business Server 2019 プールに移動する2人のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="62716-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="62716-114">この例では、Chen Yang および Claus Hansen というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="62716-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![ユーザーを特定の登録プールに移動する](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="62716-116">[**アクション**] メニューで、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62716-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="62716-117">ドロップダウンリストから、[Skype for Business Server 2019] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="62716-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="62716-118">[**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62716-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="62716-119">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62716-119">Click **OK**.</span></span>
    
     ![[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="62716-121">ユーザーの [**レジストラープール**] 列に Skype For business Server 2019 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="62716-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="62716-122">Skype for Business Server 2019 管理シェルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="62716-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="62716-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="62716-123"><a name="sectionSection1"> </a></span></span>

1. <span data-ttu-id="62716-124">Skype for Business Server 2019 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="62716-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="62716-125">コマンドラインで、次のように入力し、 **User1**と**User2**を移動する特定のユーザー名に置き換えて、 **pool_FQDN**を移行先プールの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="62716-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="62716-126">この例では、ユーザーが Hao Chen と Katie ヨルダンを移動します。</span><span class="sxs-lookup"><span data-stu-id="62716-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell の Get-CsUser コマンドレットの例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="62716-128">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="62716-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="62716-129">**レジストラープール**id は、前の手順で**pool_FQDN**として指定したプールを指すようになります。</span><span class="sxs-lookup"><span data-stu-id="62716-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="62716-130">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="62716-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="62716-131">手順を繰り返して、 **User2**が移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="62716-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![PowerShell の Get-UsUser-Identity コマンドレットの出力](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="62716-133">Skype for Business Server 2019 管理シェルを使用してすべてのユーザーを同時に移動するには</span><span class="sxs-lookup"><span data-stu-id="62716-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="62716-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="62716-134"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="62716-135">この例では、すべてのユーザーが従来のプール (pool01.contoso.net) に返されています。</span><span class="sxs-lookup"><span data-stu-id="62716-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="62716-136">Skype for Business Server 2019 管理シェルを使用して、すべてのユーザーを同時に Skype for Business Server 2019 プール (pool02.contoso.net) に移動します。</span><span class="sxs-lookup"><span data-stu-id="62716-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="62716-137">Skype for Business Server 2019 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="62716-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="62716-138">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="62716-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell コマンドレットと管理シェルの結果](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="62716-140">パイロットユーザーの1人に対して、 **Get-CsUser**を実行します。</span><span class="sxs-lookup"><span data-stu-id="62716-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="62716-141">各ユーザーの**レジストラープール**id は、前の手順で**pool_FQDN**として指定したプールを指すようになります。</span><span class="sxs-lookup"><span data-stu-id="62716-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="62716-142">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="62716-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="62716-143">さらに、Skype for Business Server 2019 コントロールパネルでユーザーの一覧を表示し、レジストラープールの値が Skype for Business Server 2019 プールを指すようになっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="62716-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype for Business Server 2019 コントロールパネルのユーザーリスト](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

