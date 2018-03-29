---
title: Skype for Business Server 2015 での電話会議ポリシーの削除
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Summary: Learn how to delete conferencing policies in Skype for Business Server 2015.'
ms.openlocfilehash: 783e2ef4c1bc0732fd93949427cea21c5ca165ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="delete-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="93e41-103">Skype for Business Server 2015 での電話会議ポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="93e41-103">Delete conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="93e41-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="93e41-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="93e41-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="93e41-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="93e41-106">Delete conferencing policies by using Skype for Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="93e41-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="93e41-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="93e41-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="93e41-108">Open Skype for Business Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="93e41-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="93e41-109">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93e41-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="93e41-110">電話会議ポリシーのリストで、削除するサイト ポリシーまたはユーザー ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93e41-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="93e41-111">Delete conferencing policies by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="93e41-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="93e41-112">電話会議ポリシーを削除するには、**Remove-CsConferencingPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="93e41-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="93e41-113">次のコマンドは、Identity が RedmondConferencingPolicy の電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="93e41-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="93e41-114">次のコマンドは、外部ユーザーに電話会議の記録を許可するすべての電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="93e41-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="93e41-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="93e41-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

