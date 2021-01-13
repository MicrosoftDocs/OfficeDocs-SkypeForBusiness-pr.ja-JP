---
title: Skype for Business Server で会議の構成設定を変更する
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '概要: Skype for Business Server で会議の構成設定を変更する方法について説明します。'
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827997"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="08821-103">Skype for Business Server で会議の構成設定を変更する</span><span class="sxs-lookup"><span data-stu-id="08821-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="08821-104">**概要:** Skype for Business Server で会議の構成設定を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08821-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="08821-105">会議の構成設定は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="08821-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="08821-106">Skype for Business Server コントロール パネルを使用して会議の構成設定を変更する</span><span class="sxs-lookup"><span data-stu-id="08821-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="08821-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="08821-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="08821-108">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="08821-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="08821-109">左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="08821-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="08821-110">会議の構成の一覧で、変更する構成をクリックし、[編集]をクリックして、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="08821-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="08821-111">[**会議の構成の編集**] で、構成名以外の設定を変更します (構成名は変更不可です)。</span><span class="sxs-lookup"><span data-stu-id="08821-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="08821-112">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08821-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="08821-113">Skype for Business Server 管理シェルを使用して会議の構成設定を変更する</span><span class="sxs-lookup"><span data-stu-id="08821-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="08821-114">会議の構成設定を変更するには **、Set-CsMeetingConfiguration コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="08821-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="08821-115">次の例に示すコマンドは、Redmond サイト (-Identity site:Redmond) に割り当てられている会議の構成設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="08821-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="08821-116">この場合、DesignateAsPresenter プロパティの値は Everyone に設定されます。</span><span class="sxs-lookup"><span data-stu-id="08821-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="08821-117">パラメーターの完全な一覧を含む詳細については [、「Set-CsMeetingConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="08821-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

