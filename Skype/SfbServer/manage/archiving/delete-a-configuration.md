---
title: Skype for Business Server でアーカイブ構成を削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: '概要: Skype for Business Server でアーカイブ構成を削除する方法について説明します。'
ms.openlocfilehash: 82415e2cac7293d991280c3fcee6e64d684f5c26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818939"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="f949e-103">Skype for Business Server でアーカイブ構成を削除する</span><span class="sxs-lookup"><span data-stu-id="f949e-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="f949e-104">**概要:** Skype for Business Server でアーカイブ構成を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f949e-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="f949e-p101">サイト構成やプール構成は削除できますが、グローバル構成は削除できません。グローバル構成を削除すると、グローバル構成は自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="f949e-p101">You can delete a site configuration or pool configuration, but you cannot delete the global configuration. If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="f949e-107">コントロール パネルを使用してアーカイブ構成を削除する</span><span class="sxs-lookup"><span data-stu-id="f949e-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="f949e-108">コントロール パネルを使用してアーカイブ構成を削除するには、次の手順を実行します</span><span class="sxs-lookup"><span data-stu-id="f949e-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="f949e-109">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f949e-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="f949e-110">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f949e-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f949e-111">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f949e-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f949e-112">アーカイブ構成のリストで、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f949e-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f949e-113">グローバル構成をクリックすることもできますが、グローバル構成を既定値にリセットする場合にのみこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f949e-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="f949e-114">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f949e-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="f949e-115">Windows PowerShell を使用してアーカイブ構成を削除する</span><span class="sxs-lookup"><span data-stu-id="f949e-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="f949e-116">**CsArchivingConfiguration**コマンドレットを使用して、アーカイブ構成を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="f949e-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="f949e-p102">たとえば、以下のコマンドを実行すると、Redmond サイトに適用されているアーカイブ構成設定が削除されます。サイト スコープで構成されているポリシーを削除すると、以前にサイト ポリシーによって管理されていたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="f949e-p102">For example, the following command removes the archiving configuration settings applied to the Redmond site. When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="f949e-119">次のコマンドを実行すると、サービス スコープに適用されているすべてのアーカイブ構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="f949e-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="f949e-120">次のコマンドを実行すると、Exchange のアーカイブが無効になっているすべてのアーカイブ構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="f949e-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="f949e-121">また、**Remove-CsArchivingConfiguration** コマンドレットを使用してグローバル設定を既定値にリセットすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f949e-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="f949e-122">たとえば、グローバル レベルで IM セッションのアーカイブを有効にしている場合、次のコマンドを実行すると、値が既定値の "None" にリセットされ、グローバル レベルでのアーカイブが無効になります。</span><span class="sxs-lookup"><span data-stu-id="f949e-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="f949e-123">詳細については、 [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f949e-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
