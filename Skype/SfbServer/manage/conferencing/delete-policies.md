---
title: Skype for Business Server の会議ポリシーを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '概要: Skype for Business Server の会議ポリシーを削除する方法について説明します。'
ms.openlocfilehash: 7cf195e53ec159a8999561c0ddb8461ee1bf0ba6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991872"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="13c7f-103">Skype for Business Server の会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="13c7f-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="13c7f-104">**概要:** Skype for Business Server の会議ポリシーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="13c7f-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="13c7f-105">会議ポリシーを削除するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="13c7f-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="13c7f-106">Skype for Business Server コントロールパネルを使用して会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="13c7f-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="13c7f-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13c7f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="13c7f-108">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="13c7f-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="13c7f-109">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13c7f-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="13c7f-110">電話会議ポリシーのリストで、削除するサイト ポリシーまたはユーザー ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13c7f-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="13c7f-111">Skype for Business Server 管理シェルを使用して会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="13c7f-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="13c7f-112">電話会議ポリシーを削除するには、**Remove-CsConferencingPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="13c7f-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="13c7f-113">次のコマンドは、Identity が RedmondConferencingPolicy の電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="13c7f-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="13c7f-114">次のコマンドは、外部ユーザーに電話会議の記録を許可するすべての電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="13c7f-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="13c7f-115">完全な構文とパラメーターの一覧を含む詳細については、「 [Remove-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13c7f-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

