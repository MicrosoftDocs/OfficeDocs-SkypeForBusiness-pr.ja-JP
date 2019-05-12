---
title: ビジネス サーバーの Skype での会議ポリシーを削除します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '概要: ビジネス サーバーの Skype での会議ポリシーを削除する方法を説明します。'
ms.openlocfilehash: 534dc52e730051b82c7f5edcb1bd2564be7dde2f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919438"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="28921-103">ビジネス サーバーの Skype での会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="28921-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="28921-104">**の概要:** ビジネス サーバーの Skype での会議ポリシーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="28921-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="28921-105">ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、会議ポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="28921-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="28921-106">ビジネス サーバーのコントロール パネルの Skype を使用して、会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="28921-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="28921-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="28921-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="28921-108">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="28921-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="28921-109">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28921-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="28921-110">電話会議ポリシーのリストで、削除するサイト ポリシーまたはユーザー ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28921-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="28921-111">Skype ビジネス サーバー管理シェルを使用して会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="28921-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="28921-112">電話会議ポリシーを削除するには、**Remove-CsConferencingPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="28921-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="28921-113">次のコマンドは、Identity が RedmondConferencingPolicy の電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="28921-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="28921-114">次のコマンドは、外部ユーザーに電話会議の記録を許可するすべての電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="28921-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="28921-115">詳細については、完全な構文とパラメーターのリストを含む[削除 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28921-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

