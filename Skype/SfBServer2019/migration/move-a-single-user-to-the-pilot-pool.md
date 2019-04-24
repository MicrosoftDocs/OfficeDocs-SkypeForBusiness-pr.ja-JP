---
title: 1 人のユーザーをパイロット プールに移動します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 パイロット プールのビジネス サーバー 2019 のコントロール パネルまたは Skype の Skype を使用してビジネス サーバー 2019 管理シェルには、Skype を従来のプールからユーザーを移動できます。 レジストラー プール] 列に、次の例で pool01.contoso.net は、従来のプールでは、および 6 のこれらのユーザーがこのプールに接続しています。 ビジネス サーバー 2019 プールのサーバー管理シェルのビジネスのビジネス サーバー 2019 のコントロール パネルと Skype の Skype を使用して、Skype にユーザーを移動するのにには、次の手順を使用します。
ms.openlocfilehash: 94896ce2ea05a3102d5a7643e3f26430e74bfe19
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231596"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="5cd6d-105">1 人のユーザーをパイロット プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="5cd6d-106">ビジネス サーバー 2019 パイロット プールのビジネス サーバー 2019 のコントロール パネルまたは Skype の Skype を使用してビジネス サーバー 2019 管理シェルには、Skype を従来のプールからユーザーを移動できます。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="5cd6d-107">**レジストラー プール**] 列に、次の例で**pool01.contoso.net**は、従来のプールでは、および 6 のこれらのユーザーがこのプールに接続しています。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="5cd6d-108">ビジネス サーバー 2019 プールのサーバー管理シェルのビジネスのビジネス サーバー 2019 のコントロール パネルと Skype の Skype を使用して、Skype にユーザーを移動するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="5cd6d-109">ビジネス サーバー 2019 のコントロール パネルの Skype を使用してユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="5cd6d-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="5cd6d-110">RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="5cd6d-111">**Skype ビジネス サーバーのコントロール パネル**を開きます。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="5cd6d-112">[**ユーザー**] をクリックして、**検索**] をクリックし、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="5cd6d-113">Skype のビジネス サーバー 2019 プールに移動するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="5cd6d-114">この例では、Sara Davis というユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="5cd6d-115">[**アクション**] メニューの [**選択されたユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="5cd6d-116">」ドロップ ダウン リストから、Skype のビジネス サーバー 2019 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="5cd6d-117">[**アクション**] をクリックし、**プールを選択したユーザーの移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="5cd6d-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="5cd6d-119">**レジストラー プール**] 列ユーザーにはに今すぐビジネス サーバー 2019 のプールは、ユーザーが正常に移動されたことを示します、Skype が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="5cd6d-120">ビジネス サーバー 2019 管理シェルには、Skype を使用してユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="5cd6d-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="5cd6d-121">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="5cd6d-122">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="5cd6d-123">次に、コマンド ・ ラインでは、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="5cd6d-124">**RegistrarPool** id は、ビジネス サーバー 2019 プールの Skype を指します。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="5cd6d-125">この id の存在は、ユーザーが正常に移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5cd6d-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5cd6d-126">**Get CsUser**コマンドレットの詳細についてを実行: **Get-csuser からのヘルプを表示-詳細な**</span><span class="sxs-lookup"><span data-stu-id="5cd6d-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

