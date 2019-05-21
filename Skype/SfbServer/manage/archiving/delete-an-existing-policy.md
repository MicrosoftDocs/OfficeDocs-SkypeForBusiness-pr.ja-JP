---
title: Skype for Business Server で既存のアーカイブポリシーを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: '概要: Skype for Business Server のアーカイブポリシーを削除する方法について説明します。'
ms.openlocfilehash: 04ea9db10a2f95ba5010471f262d58c269c173d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278413"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="c140c-103">Skype for Business Server で既存のアーカイブポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c140c-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="c140c-104">**概要:** Skype for Business Server のアーカイブポリシーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c140c-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="c140c-105">ユーザー ポリシーやサイト ポリシーは削除できますが、グローバル ポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="c140c-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="c140c-106">グローバルポリシーを削除すると、Skype for Business Server によってポリシーが自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="c140c-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="c140c-107">コントロール パネルを使用してポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c140c-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="c140c-108">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c140c-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="c140c-109">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c140c-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c140c-110">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c140c-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="c140c-111">アーカイブ ポリシーのリストで、削除するユーザー ポリシーまたはサイト ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c140c-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="c140c-112">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c140c-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="c140c-113">Windows PowerShell を使用してポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c140c-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="c140c-114">**Remove-CsArchivingPolicy** コマンドレットを使用してアーカイブ ポリシーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c140c-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c140c-p102">たとえば、以下のコマンドを実行すると、site:Redmond という ID を持つポリシーが削除されます。サイト レベルで構成されているポリシーを削除すると、以前にサイト ポリシーによって管理されていたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="c140c-p102">For example, the following command deletes the policy with the Identity site:Redmond. When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="c140c-117">このコマンドでは、ユーザーごとのレベルに適用されているすべてのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c140c-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="c140c-118">このコマンドでは、内部アーカイブが無効になっているすべてのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c140c-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="c140c-119">詳細については、 [CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c140c-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
