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
ms.openlocfilehash: 6c6f61287cfc75b7500317d62de4ea846af1abd3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244573"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="f7c32-103">複数のユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="f7c32-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="f7c32-104">Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 Management Shell を使用して、従来のプールから Skype for Business Server 2019 パイロットプールに複数のユーザーを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="f7c32-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="f7c32-105">**この記事の内容**</span><span class="sxs-lookup"><span data-stu-id="f7c32-105">**In this article**</span></span>
  
[<span data-ttu-id="f7c32-106">Skype for Business Server 2019 コントロールパネルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="f7c32-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="f7c32-107">Skype for Business Server 2019 管理シェルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="f7c32-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="f7c32-108">Skype for Business Server 2019 管理シェルを使用してすべてのユーザーを同時に移動するには</span><span class="sxs-lookup"><span data-stu-id="f7c32-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="f7c32-109">Skype for Business Server 2019 コントロールパネルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="f7c32-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="f7c32-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="f7c32-110"></span></span>

1. <span data-ttu-id="f7c32-111">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7c32-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="f7c32-112">[**ユーザー**] をクリックし、[**検索**] をクリックして、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7c32-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="f7c32-113">Skype for Business Server 2019 プールに移動する2人のユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="f7c32-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f7c32-114">この例では、Chen Yang sold と Claus というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![ユーザーを特定のレジスタプールに移動する](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="f7c32-116">[**アクション**] メニューで、[**選択したユーザーをプールに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="f7c32-117">ドロップダウンリストから、Skype for Business Server 2019 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="f7c32-118">[**操作**] をクリックし、[**選択したユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7c32-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="f7c32-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7c32-119">Click **OK**.</span></span>
    
     ![[ユーザーの移動]、[宛先レジストラー pool] ダイアログボックス](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="f7c32-121">ユーザーの**レジストラー pool**列に Skype For business Server 2019 プールが含まれていることを確認します。これは、ユーザーが正常に移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="f7c32-122">Skype for Business Server 2019 管理シェルを使用して複数のユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="f7c32-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="f7c32-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="f7c32-123"></span></span>

1. <span data-ttu-id="f7c32-124">Skype for Business Server 2019 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7c32-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="f7c32-125">コマンドラインで、次のように入力し、移動する特定のユーザー名で**User1**と**User2**を置き換えて、 **pool_FQDN**を目的のプールの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f7c32-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="f7c32-126">この例では、ユーザーの Hao Chen と Katie ヨルダンを移動します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-CsUser コマンドレットの例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="f7c32-128">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-128">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="f7c32-129">**レジストラープール**id は、前の手順で**pool_FQDN**として指定したプールを指すようになります。</span><span class="sxs-lookup"><span data-stu-id="f7c32-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="f7c32-130">この id の存在は、ユーザーが正常に移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="f7c32-131">手順を繰り返して、 **User2**が移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![PowerShell Get-UsUser Identity コマンドレットの出力](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="f7c32-133">Skype for Business Server 2019 管理シェルを使用してすべてのユーザーを同時に移動するには</span><span class="sxs-lookup"><span data-stu-id="f7c32-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="f7c32-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="f7c32-134"></span></span>

<span data-ttu-id="f7c32-135">この例では、すべてのユーザーが従来のプール (pool01.contoso.net) に戻されています。</span><span class="sxs-lookup"><span data-stu-id="f7c32-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="f7c32-136">Skype for Business Server 2019 管理シェルを使用して、すべてのユーザーを Skype for Business Server 2019 プール (pool02.contoso.net) に同時に移行します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="f7c32-137">Skype for Business Server 2019 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7c32-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="f7c32-138">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-138">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell コマンドレットと結果の管理シェル](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="f7c32-140">パイロットユーザーのいずれかに対して **、ユーザーの購入ユーザー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="f7c32-141">各ユーザーの**レジストラープール**id は、前の手順で**pool_FQDN**として指定したプールを指すようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7c32-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="f7c32-142">この id の存在は、ユーザーが正常に移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="f7c32-143">さらに、Skype for Business Server 2019 コントロールパネルでユーザーの一覧を表示し、[レジストラー Pool] の値が Skype for Business Server 2019 プールを指すようになったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7c32-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype for Business Server 2019 コントロールパネルのユーザーリスト](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

