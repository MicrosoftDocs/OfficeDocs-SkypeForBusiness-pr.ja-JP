---
title: Skype for Business Server の会議構成設定を削除する
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '概要: Skype for Business Server で会議構成設定を削除する方法について説明します。'
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119496"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="51b57-103">Skype for Business Server の会議構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="51b57-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="51b57-104">**概要:** Skype for Business Server で会議構成設定を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="51b57-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="51b57-105">会議の構成設定は、Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="51b57-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="51b57-106">サイトまたはユーザー構成を削除できますが、グローバル構成を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="51b57-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="51b57-107">グローバル構成を削除しようとすると、自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="51b57-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="51b57-108">Skype for Business Server コントロール パネルを使用して会議の構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="51b57-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="51b57-109">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="51b57-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="51b57-110">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="51b57-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="51b57-111">左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="51b57-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="51b57-112">会議構成の一覧で、削除するサイトまたはプールの構成をクリックし、[編集]をクリックし、[削除] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="51b57-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="51b57-113">Skype for Business Server 管理シェルを使用して会議の構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="51b57-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="51b57-114">会議の設定を削除するには **、Remove-CsMeetingConfiguration コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="51b57-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="51b57-115">次のコマンドは、Redmond サイトに適用される会議構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="51b57-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="51b57-116">次のコマンドは、サイト スコープに適用されている会議構成設定をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="51b57-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="51b57-117">パラメーターの完全な一覧を含む詳細については [、「Remove-CsMeetingConfiguration」を参照してください](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="51b57-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
