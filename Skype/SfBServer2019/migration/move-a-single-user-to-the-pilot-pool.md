---
title: 1人のユーザーをパイロットプールに移動する
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
description: Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 管理シェルを使用して、ユーザーを従来のプールから Skype for Business Server 2019 パイロットプールに移動することができます。 次の例では、レジストラー pool 列で、pool01.contoso.net はレガシプールで、これらのユーザーの6人すべてがこのプールに接続されています。 Skype for business Server 2019 コントロールパネルと Skype for Business Server 管理シェルを使用してユーザーを Skype for business Server 2019 プールに移動するには、次の手順を使用します。
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752509"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="52fb7-105">1人のユーザーをパイロットプールに移動する</span><span class="sxs-lookup"><span data-stu-id="52fb7-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="52fb7-106">Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 管理シェルを使用して、ユーザーを従来のプールから Skype for Business Server 2019 パイロットプールに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="52fb7-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="52fb7-107">次の例では、**レジストラー pool**列で、 **pool01.contoso.net**はレガシプールで、これらのユーザーの6人すべてがこのプールに接続されています。</span><span class="sxs-lookup"><span data-stu-id="52fb7-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="52fb7-108">Skype for business Server 2019 コントロールパネルと Skype for Business Server 管理シェルを使用してユーザーを Skype for business Server 2019 プールに移動するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="52fb7-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="52fb7-109">Skype for Business Server 2019 コントロールパネルを使用してユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="52fb7-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="52fb7-110">RTCUniversalServerAdmins グループのメンバーであるか、CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="52fb7-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="52fb7-111">**Skype For Business Server コントロールパネル**を開きます。</span><span class="sxs-lookup"><span data-stu-id="52fb7-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="52fb7-112">[**ユーザー**]、[**検索**]、[**ユーザー検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="52fb7-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="52fb7-113">Skype for Business Server 2019 プールに移動するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="52fb7-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="52fb7-114">この例では、Sara Davis というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="52fb7-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="52fb7-115">[**アクション**]メニューの [**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52fb7-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="52fb7-116">ドロップダウンリストから、[Skype for Business Server 2019] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="52fb7-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="52fb7-117">[**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52fb7-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="52fb7-118">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52fb7-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="52fb7-119">ユーザーの [**レジストラー pool** ] 列に Skype For business Server 2019 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="52fb7-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="52fb7-120">Skype for Business Server 2019 管理シェルを使用してユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="52fb7-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="52fb7-121">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="52fb7-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="52fb7-122">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="52fb7-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="52fb7-123">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="52fb7-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="52fb7-124">**RegistrarPool** identity は、Skype For business Server 2019 プールをポイントするようになりました。</span><span class="sxs-lookup"><span data-stu-id="52fb7-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="52fb7-125">この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="52fb7-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="52fb7-126">**Get-help user**コマンドレットの詳細については、次を実行してください。取得-**ヘルプ-Csuser-詳細**</span><span class="sxs-lookup"><span data-stu-id="52fb7-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

