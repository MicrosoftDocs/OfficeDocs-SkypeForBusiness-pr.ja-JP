---
title: Skype for Business Server の会議構成の設定を変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '概要: Skype for Business Server で会議構成の設定を変更する方法について説明します。'
ms.openlocfilehash: 2e9d8a737a2bfc48cdcbe39540a22e4c236003b3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992854"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="6f807-103">Skype for Business Server の会議構成の設定を変更する</span><span class="sxs-lookup"><span data-stu-id="6f807-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="6f807-104">**概要:** Skype for Business Server で会議の設定を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f807-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="6f807-105">会議の設定を変更するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f807-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6f807-106">Skype for Business Server コントロールパネルを使用して会議の設定を変更する</span><span class="sxs-lookup"><span data-stu-id="6f807-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6f807-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6f807-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="6f807-108">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f807-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6f807-109">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f807-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="6f807-110">会議構成の一覧で、変更する構成をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f807-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="6f807-111">[**会議の構成の編集**] で、構成名以外の構成設定を変更します (構成名は変更不可です)。</span><span class="sxs-lookup"><span data-stu-id="6f807-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="6f807-112">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f807-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6f807-113">Skype for Business Server 管理シェルを使用して会議の設定を変更する</span><span class="sxs-lookup"><span data-stu-id="6f807-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6f807-114">会議の構成設定を変更するには、**Set-CsMeetingConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f807-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="6f807-p101">次の例に示すコマンドは、Redmond サイト (-Identity site:Redmond) に割り当てられている会議構成設定を変更します。この場合、DesignateAsPresenter プロパティの値が "Everyone" に設定されています。</span><span class="sxs-lookup"><span data-stu-id="6f807-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="6f807-117">パラメーターの完全な一覧など、詳細については、「 [Cs会議構成](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f807-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

