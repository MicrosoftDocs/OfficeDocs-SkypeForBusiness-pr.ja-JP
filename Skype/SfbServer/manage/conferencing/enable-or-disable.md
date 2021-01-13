---
title: Skype for Business Server でダイヤルイン会議を有効または無効にする
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '概要: コントロール パネルまたは管理シェルを使用して、Skype for Business Server でダイヤルイン会議を有効または無効にする方法について説明します。'
ms.openlocfilehash: 99691540306ba0cccf9c63af2e2188e839367bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828127"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="6db89-103">Skype for Business Server でダイヤルイン会議を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6db89-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="6db89-104">**概要:** コントロール パネルまたは管理シェルを使用して、Skype for Business Server でダイヤルイン会議を有効または無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6db89-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="6db89-105">ダイヤルイン会議は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して有効にできます。</span><span class="sxs-lookup"><span data-stu-id="6db89-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6db89-106">Skype for Business Server コントロール パネルを使用してダイヤルイン会議を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6db89-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6db89-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6db89-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="6db89-108">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6db89-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6db89-109">左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6db89-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="6db89-110">電話会議ポリシーの一覧で、ダイヤルイン会議を有効にするポリシーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db89-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="6db89-p101">ユーザーがダイヤルインで会議に参加できるようにするには、[**PSTN ダイヤルイン会議を有効にする**] チェック ボックスをオンにします。既定では、ユーザーは公衆交換電話網 (PSTN) を使用して、会議にダイヤルインできます。</span><span class="sxs-lookup"><span data-stu-id="6db89-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="6db89-113">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db89-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6db89-114">Skype for Business Server 管理シェルを使用してダイヤルイン会議を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6db89-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6db89-115">ダイヤルイン会議を有効または無効にするには、次のように **Set-CsConferencingPolicy** コマンドレットを EnableDialInConferencing パラメーターと一緒に使用します。</span><span class="sxs-lookup"><span data-stu-id="6db89-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="6db89-116">詳細については [、「Set-CsConferencingPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6db89-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

