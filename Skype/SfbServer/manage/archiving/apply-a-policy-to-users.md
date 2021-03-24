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
description: '概要: Skype for Business Server のユーザーにアーカイブ ポリシーを割り当てる方法について学習します。'
ms.openlocfilehash: 1fce0dbd0cc7b0595dcf3cd91baeba9ed364e28a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095491"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="7b81a-103">Skype for Business Server のユーザーにアーカイブ ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="7b81a-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="7b81a-104">**概要:** Skype for Business Server のユーザーにアーカイブ ポリシーを割り当てる方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="7b81a-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="7b81a-105">Skype for Business Server に保存されているユーザーのアーカイブ用に 1 つ以上のユーザー ポリシーを作成した場合は、該当するポリシーをそれらのユーザーまたはユーザー グループに適用することで、特定のユーザーのアーカイブ サポートを実装できます。</span><span class="sxs-lookup"><span data-stu-id="7b81a-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="7b81a-106">たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合、それを少なくとも 1 つのユーザーまたはユーザー グループに適用して、ユーザーの Skype for Business Server 通信のアーカイブをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="7b81a-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b81a-107">展開に対して Microsoft Exchange 統合を有効にした場合、Exchange In-Place Hold ポリシーは、Exchange にホームを持ち、メールボックスを In-Place ホールドに置くユーザーに対してアーカイブを有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="7b81a-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7b81a-108">詳細については [、「Plan for archiving in Skype for Business Server」および「Configure](../../plan-your-deployment/archiving/archiving.md) integration with Exchange storage [for Skype for Business Server」を参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="7b81a-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="7b81a-109">コントロール パネルを使用してユーザー ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="7b81a-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="7b81a-110">コントロール パネルを使用してユーザー ポリシーを適用するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7b81a-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="7b81a-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7b81a-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="7b81a-112">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7b81a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="7b81a-113">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="7b81a-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="7b81a-114">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b81a-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="7b81a-115">[**アーカイブ ポリシー] の [Lync Server ユーザー** の編集] で、適用するアーカイブ ユーザー ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b81a-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7b81a-116">この **\<Automatic\>** 設定は、既定のサーバー インストール設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="7b81a-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="7b81a-117">これらの設定はサーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7b81a-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="7b81a-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b81a-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="7b81a-119">ユーザー ポリシーを使用してユーザー ポリシーを適用Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b81a-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="7b81a-120">**Grant-CsArchivingPolicy** コマンドレットを使用してWindows PowerShellポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b81a-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="7b81a-121">次のコマンドは、ユーザー単位のアーカイブ ポリシーである RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7b81a-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="7b81a-122">このコマンドは、ユーザーごとのアーカイブ ポリシー RedmondArchivingPolicy をレジストラー プール にアカウントを持つすべてのユーザーに割り当 atl-cs-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7b81a-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="7b81a-123">このコマンドで使用される Filter パラメーターの詳細については [、Get-CsUser コマンドレットのドキュメントを](/powershell/module/skype/get-csuser?view=skype-ps) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b81a-123">For details about the Filter parameter used in this command, see the [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="7b81a-124">次のコマンドは、Ken Myer に以前割り当てられたユーザーごとのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b81a-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="7b81a-125">ユーザーごとのポリシーが削除されると、Ken Myer はグローバル ポリシーを使用するか、存在する場合はローカル サイト ポリシーを使用して自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="7b81a-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="7b81a-126">サイト ポリシーの方がグローバル ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="7b81a-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="7b81a-127">詳細については [、Grant-CsArchivingPolicy コマンドレットのドキュメントを](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b81a-127">For details, see the [Grant-CsArchivingPolicy](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
