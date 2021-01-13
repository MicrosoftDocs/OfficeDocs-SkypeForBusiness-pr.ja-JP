---
title: Skype for Business Server のユーザーにアーカイブ ポリシーを適用する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '概要: Skype for Business Server でアーカイブ ポリシーをユーザーに割り当てる方法について学習します。'
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817767"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="e4bc4-103">Skype for Business Server のユーザーにアーカイブ ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="e4bc4-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="e4bc4-104">**概要:** Skype for Business Server でアーカイブ ポリシーをユーザーに割り当てる方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="e4bc4-105">Skype for Business Server にホームのユーザーのアーカイブ用に 1 つ以上のユーザー ポリシーを作成した場合は、該当するポリシーをそれらのユーザーまたはユーザー グループに適用することで、特定のユーザーのアーカイブ サポートを実装できます。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="e4bc4-106">たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合、そのポリシーを少なくとも 1 つのユーザーまたはユーザー グループに適用して、ユーザーの Skype for Business Server 通信のアーカイブをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4bc4-107">展開で Microsoft Exchange 統合を有効にした場合、Exchange In-Place 保留ポリシーは、Exchange にホームを置き、メールボックスを In-Place 保留にするユーザーに対してアーカイブを有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e4bc4-108">詳細については [、「Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business Server 」を [参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="e4bc4-109">コントロール パネルを使用してユーザー ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="e4bc4-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="e4bc4-110">コントロール パネルを使用してユーザー ポリシーを適用するには:</span><span class="sxs-lookup"><span data-stu-id="e4bc4-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="e4bc4-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="e4bc4-112">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e4bc4-113">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="e4bc4-114">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e4bc4-115">[Lync **Server ユーザーの** 編集] の **[アーカイブ** ポリシー] で、適用するアーカイブ ユーザー ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e4bc4-116">この **\<Automatic\>** 設定では、既定のサーバー インストール設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="e4bc4-117">これらの設定はサーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="e4bc4-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="e4bc4-119">ユーザー ポリシーを使用してユーザー ポリシーをWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4bc4-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="e4bc4-120">**Grant-CsArchivingPolicy** コマンドレットを使用してWindows PowerShellポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e4bc4-121">次のコマンドは、ユーザー単位のアーカイブ ポリシーである RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="e4bc4-122">このコマンドは、ユーザー単位のアーカイブ ポリシー RedmondArchivingPolicy を、レジストラー プールにホームのアカウントを持つすべてのユーザーに割り当atl-cs-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="e4bc4-123">このコマンドで使用される Filter パラメーターの詳細については [、Get-CsUser コマンドレット](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="e4bc4-124">次のコマンドは、Ken Myer に以前割り当てられたユーザーごとのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="e4bc4-125">ユーザーごとのポリシーを削除すると、Ken Myer は、グローバル ポリシーまたは存在する場合はローカル サイト ポリシーを使用して自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="e4bc4-126">サイト ポリシーの方がグローバル ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="e4bc4-127">詳細については [、Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4bc4-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

