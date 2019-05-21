---
title: Skype for Business Server のユーザーにアーカイブポリシーを適用する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '概要: Skype for Business Server のユーザーにアーカイブポリシーを割り当てる方法について説明します。'
ms.openlocfilehash: 895a7fac34fcac0a4a7e39756796f6b7d2fc6377
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282050"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="5cb81-103">Skype for Business Server のユーザーにアーカイブポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="5cb81-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="5cb81-104">**概要:** Skype for Business Server のユーザーにアーカイブポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5cb81-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="5cb81-105">Skype for Business Server を使用しているユーザー用にアーカイブ用のユーザーポリシーを1つ以上作成した場合は、それらのユーザーまたはユーザーグループに適切なポリシーを適用することで、特定のユーザーのアーカイブサポートを実装できます。</span><span class="sxs-lookup"><span data-stu-id="5cb81-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="5cb81-106">たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合、ユーザーの Skype for Business Server の通信のアーカイブをサポートするために、少なくとも1人のユーザーまたはユーザーグループに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="5cb81-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5cb81-107">展開で Microsoft Exchange の統合を有効にしている場合、Exchange のインプレースホールドポリシーは、Exchange を使用しているユーザーに対してアーカイブが有効になっているかどうかを制御します。また、メールボックスはインプレースホールドに配置されています。</span><span class="sxs-lookup"><span data-stu-id="5cb81-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="5cb81-108">詳細については、「 [skype For Business server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」および「 [Skype for business Server 用の Exchange storage との統合を構成する](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cb81-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="5cb81-109">コントロール パネルを使用したユーザー ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="5cb81-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="5cb81-110">コントロール パネルを使用してユーザー ポリシーを適用するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5cb81-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="5cb81-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5cb81-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="5cb81-112">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5cb81-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5cb81-113">左側のナビゲーション バーで [**ユーザー**] をクリックして、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="5cb81-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="5cb81-114">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cb81-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5cb81-115">[**アーカイブポリシー**] の [ **Lync Server ユーザーの編集**] で、適用するアーカイブユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5cb81-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5cb81-116">\*\* \<自動\> \*\*設定では、既定のサーバーインストール設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5cb81-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="5cb81-117">これらの設定はサーバーにより自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5cb81-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="5cb81-118">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5cb81-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="5cb81-119">Windows PowerShell を使用してユーザーポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="5cb81-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="5cb81-120">また、Windows PowerShell **Grant-CsArchivingPolicy**コマンドレットを使用して、ユーザーポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5cb81-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5cb81-121">次のコマンドは、ユーザー単位のアーカイブ ポリシー RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5cb81-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="5cb81-122">次のコマンドは、ユーザーごとのアーカイブ ポリシーである RedmondArchivingPolicy を、レジストラー プール atl-cs-001.contoso.com に所属するアカウントを持つすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5cb81-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="5cb81-123">このコマンドで使用される Filter パラメーターの詳細については、「 [CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cb81-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="5cb81-p105">次のコマンドは、Ken Myer に割り当てられたユーザー単位のアーカイブ ポリシーを削除します。ユーザー単位のポリシーが削除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5cb81-p105">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="5cb81-127">詳細については、「 [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cb81-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

