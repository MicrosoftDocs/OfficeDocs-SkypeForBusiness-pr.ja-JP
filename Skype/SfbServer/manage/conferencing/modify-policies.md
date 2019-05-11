---
title: ビジネス サーバーの Skype での会議ポリシーを変更します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '概要: ビジネス サーバーの Skype での会議ポリシーを変更する方法を説明します。'
ms.openlocfilehash: 0ca232398c9133c3340cbae909ac43d44ba641dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911988"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="8df7f-103">ビジネス サーバーの Skype での会議ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8df7f-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="8df7f-104">**の概要:** ビジネス サーバーの Skype での会議ポリシーを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8df7f-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="8df7f-105">ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、会議ポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8df7f-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8df7f-106">ビジネス サーバーのコントロール パネルの Skype を使用して、会議ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8df7f-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8df7f-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8df7f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="8df7f-108">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8df7f-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8df7f-109">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8df7f-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="8df7f-110">電話会議ポリシーの一覧で、変更するポリシーをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8df7f-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8df7f-111">[**会議ポリシーの編集**] で、変更できないポリシー名以外のポリシー設定のいずれかを変更します。</span><span class="sxs-lookup"><span data-stu-id="8df7f-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="8df7f-112">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8df7f-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8df7f-113">Skype ビジネス サーバー管理シェルを使用して会議ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8df7f-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="8df7f-114">会議ポリシーを変更するには、**セット CsConferencingPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8df7f-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="8df7f-115">次の例では、電話会議ポリシー SalesConferencingPolicy のプロパティ値を変更します。</span><span class="sxs-lookup"><span data-stu-id="8df7f-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="8df7f-116">このコマンドにより、AllowConferenceRecording プロパティの値が False に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8df7f-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="8df7f-117">詳細については、完全な構文とパラメーターのリストを含む[セット CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8df7f-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

