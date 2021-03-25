---
title: Skype for Business Server での会議ポリシーの削除
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '概要: Skype for Business Server で会議ポリシーを削除する方法について説明します。'
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119506"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="59951-103">Skype for Business Server での会議ポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="59951-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="59951-104">**概要:** Skype for Business Server で会議ポリシーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="59951-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="59951-105">会議ポリシーは、Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="59951-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="59951-106">Skype for Business Server コントロール パネルを使用して会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="59951-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="59951-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="59951-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="59951-108">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="59951-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="59951-109">左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="59951-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="59951-110">会議ポリシーの一覧で、削除するサイトまたはユーザー ポリシーをクリックし、[編集] をクリックし、[削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="59951-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="59951-111">Skype for Business Server 管理シェルを使用して会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="59951-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="59951-112">会議ポリシーを削除するには **、Remove-CsConferencingPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="59951-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="59951-113">次のコマンドは、ID RedmondConferencingPolicy を持つ電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="59951-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="59951-114">次のコマンドは、外部ユーザーが会議を記録できる会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="59951-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="59951-115">完全な構文とパラメーターの一覧を含む詳細については [、「Remove-CsConferencingPolicy」を参照してください](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="59951-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
