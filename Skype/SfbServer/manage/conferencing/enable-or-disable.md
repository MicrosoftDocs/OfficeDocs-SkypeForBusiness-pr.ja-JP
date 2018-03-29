---
title: Skype for Business Server 2015 でのダイヤルイン会議の有効化または無効化
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '概要: は、コントロール パネルまたは管理シェルを使用して、有効またはビジネス サーバー 2015 の Skype では、ダイヤルイン会議を無効にする方法を説明します。'
ms.openlocfilehash: 6441e548ce944cdd8786178ed7b80b0af7d625f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server-2015"></a><span data-ttu-id="a84d5-103">Skype for Business Server 2015 でのダイヤルイン会議の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="a84d5-103">Enable or disable dial-in conferencing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a84d5-104">**の概要:**ビジネス サーバー 2015 の Skype では、ダイヤルイン会議を無効にするを有効または、コントロール パネルまたは管理シェルを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a84d5-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a84d5-105">ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、ダイヤルイン会議を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="a84d5-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a84d5-106">ビジネス サーバーのコントロール パネルの Skype を使用して、ダイヤルイン会議を無効にするを有効または</span><span class="sxs-lookup"><span data-stu-id="a84d5-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a84d5-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a84d5-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="a84d5-108">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a84d5-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a84d5-109">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a84d5-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="a84d5-110">電話会議ポリシーの一覧で、ダイヤルイン会議を有効にするポリシーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a84d5-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="a84d5-p101">ユーザーがダイヤルインで会議に参加できるようにするには、[**PSTN ダイヤルイン会議を有効にする**] チェック ボックスをオンにします。既定では、ユーザーは公衆交換電話網 (PSTN) を使用して、会議にダイヤルインできます。</span><span class="sxs-lookup"><span data-stu-id="a84d5-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="a84d5-113">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a84d5-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a84d5-114">有効にするか、Skype ビジネス サーバー管理シェルを使用してダイヤルイン会議を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a84d5-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a84d5-115">ダイヤルイン会議を有効または無効にするには、次のように **Set-CsConferencingPolicy** コマンドレットを使用し、EnableDialInConferencing パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="a84d5-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="a84d5-116">詳細については、[セット CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a84d5-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

