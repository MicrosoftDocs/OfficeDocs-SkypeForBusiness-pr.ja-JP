---
title: Skype for Business Server の既存のアーカイブ ポリシーを削除する
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: '概要: Skype for Business Server のアーカイブ ポリシーを削除する方法について学習します。'
ms.openlocfilehash: 2baad7d862b1b6739019a4459492bfb3b67e04cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095391"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="c59ae-103">Skype for Business Server の既存のアーカイブ ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c59ae-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="c59ae-104">**概要:** Skype for Business Server のアーカイブ ポリシーを削除する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="c59ae-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="c59ae-105">ユーザー ポリシーまたはサイト ポリシーは削除できますが、グローバル ポリシーは削除できます。</span><span class="sxs-lookup"><span data-stu-id="c59ae-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="c59ae-106">グローバル ポリシーを削除すると、Skype for Business Server はポリシーを既定値に自動的にリセットします。</span><span class="sxs-lookup"><span data-stu-id="c59ae-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="c59ae-107">コントロール パネルを使用してポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c59ae-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="c59ae-108">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c59ae-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="c59ae-109">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c59ae-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c59ae-110">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c59ae-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="c59ae-111">アーカイブ ポリシーのリストで、削除するユーザー ポリシーまたはサイト ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c59ae-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="c59ae-112">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c59ae-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="c59ae-113">ポリシーを使用してポリシーを削除Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c59ae-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="c59ae-114">**Remove-CsArchivingPolicy** コマンドレットを使用してアーカイブ ポリシーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c59ae-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c59ae-115">たとえば、次のコマンドは、Identity サイト:Redmond を使用してポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c59ae-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="c59ae-116">サイト レベルで構成されたポリシーが削除された場合、サイト ポリシーによって以前に管理されたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="c59ae-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="c59ae-117">このコマンドは、ユーザー単位レベルに適用されるアーカイブ ポリシーをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="c59ae-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="c59ae-118">このコマンドでは、内部アーカイブが無効になっているすべてのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c59ae-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="c59ae-119">詳細については [、Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c59ae-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>