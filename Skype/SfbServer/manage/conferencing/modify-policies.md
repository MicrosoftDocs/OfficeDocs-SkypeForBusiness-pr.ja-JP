---
title: Skype for Business Server の会議ポリシーを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '概要: Skype for Business Server の会議ポリシーを変更する方法について説明します。'
ms.openlocfilehash: 9cfb13436a01439a8d5ea152ca1d8ac543bc0e88
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991812"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="0a720-103">Skype for Business Server の会議ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="0a720-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="0a720-104">**概要:** Skype for Business Server の会議ポリシーを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a720-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="0a720-105">会議のポリシーを変更するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="0a720-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0a720-106">Skype for Business Server コントロールパネルを使用して会議のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="0a720-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0a720-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0a720-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="0a720-108">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0a720-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0a720-109">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a720-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="0a720-110">電話会議ポリシーの一覧で、変更するポリシーをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a720-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0a720-111">[**会議ポリシーの編集**] で、変更できないポリシー名以外のポリシー設定のいずれかを変更します。</span><span class="sxs-lookup"><span data-stu-id="0a720-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="0a720-112">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a720-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0a720-113">Skype for Business Server 管理シェルを使用して会議のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="0a720-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0a720-114">会議ポリシーを変更するには、 **set-csconferencingpolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0a720-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0a720-115">次の例では、電話会議ポリシー SalesConferencingPolicy のプロパティ値を変更します。</span><span class="sxs-lookup"><span data-stu-id="0a720-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="0a720-116">このコマンドにより、AllowConferenceRecording プロパティの値が False に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0a720-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="0a720-117">完全な構文とパラメーターの一覧を含む詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a720-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

