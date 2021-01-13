---
title: Skype for Business Server で会議ポリシーを変更する
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '概要: Skype for Business Server で会議ポリシーを変更する方法について説明します。'
ms.openlocfilehash: eafeb56dd9b0c36afffab07830a9efb71bde18fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828007"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="cd98c-103">Skype for Business Server で会議ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="cd98c-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="cd98c-104">**概要:** Skype for Business Server で会議ポリシーを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd98c-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="cd98c-105">会議ポリシーは、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="cd98c-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="cd98c-106">Skype for Business Server コントロール パネルを使用して会議ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="cd98c-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cd98c-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="cd98c-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="cd98c-108">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cd98c-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="cd98c-109">左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cd98c-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="cd98c-110">会議ポリシーの一覧で、変更するポリシーをクリックし、[編集] をクリックして、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cd98c-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="cd98c-111">[ **会議ポリシーの編集**] で、変更できないポリシー名を除くすべてのポリシー設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="cd98c-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="cd98c-112">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd98c-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="cd98c-113">Skype for Business Server 管理シェルを使用して会議ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="cd98c-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="cd98c-114">会議ポリシーを変更するには **、Set-CsConferencingPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="cd98c-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="cd98c-115">次の例では、会議ポリシー SalesConferencingPolicy のプロパティ値を変更します。</span><span class="sxs-lookup"><span data-stu-id="cd98c-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="cd98c-116">このコマンドは、AllowConferenceRecording プロパティの値を False に設定します。</span><span class="sxs-lookup"><span data-stu-id="cd98c-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="cd98c-117">完全な構文やパラメーターの一覧など、詳細については [、「Set-CsConferencingPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="cd98c-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

