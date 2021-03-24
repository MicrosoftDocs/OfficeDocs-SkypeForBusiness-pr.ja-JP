---
title: Skype for Business Server のアーカイブ構成を削除する
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: '概要: Skype for Business Server でアーカイブ構成を削除する方法について説明します。'
ms.openlocfilehash: 43913485ce18660b6c7fa7ce747ceeaaebd49923
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095411"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="4dcfc-103">Skype for Business Server のアーカイブ構成を削除する</span><span class="sxs-lookup"><span data-stu-id="4dcfc-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="4dcfc-104">**概要:** Skype for Business Server でアーカイブ構成を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="4dcfc-105">サイト構成またはプール構成を削除できますが、グローバル構成を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="4dcfc-106">グローバル構成を削除すると、自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="4dcfc-107">コントロール パネルを使用してアーカイブ構成を削除する</span><span class="sxs-lookup"><span data-stu-id="4dcfc-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="4dcfc-108">コントロール パネルを使用してアーカイブ構成を削除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="4dcfc-109">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="4dcfc-110">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4dcfc-111">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="4dcfc-112">アーカイブ構成のリストで、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4dcfc-113">グローバル構成をクリックすることもできますが、グローバル構成を既定値にリセットする場合にのみ、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="4dcfc-114">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="4dcfc-115">サーバーを使用してアーカイブ構成を削除Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dcfc-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="4dcfc-116">**Remove-CsArchivingConfiguration** コマンドレットを使用してアーカイブ構成を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="4dcfc-117">たとえば、次のコマンドは、Redmond サイトに適用されるアーカイブ構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="4dcfc-118">サイト スコープで構成されたポリシーが削除された場合、サイト ポリシーによって以前に管理されたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="4dcfc-119">次のコマンドは、サービス スコープに適用されるアーカイブ構成設定をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="4dcfc-120">次のコマンドは、Exchange アーカイブが無効になっているすべてのアーカイブ構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="4dcfc-121">**Remove-CsArchivingConfiguration** コマンドレットを使用して、グローバル設定を既定値にリセットすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="4dcfc-122">たとえば、グローバル レベルで IM セッションアーカイブを有効にしたとします。次のコマンドは、値を既定値の None にリセットし、グローバル レベルでのアーカイブを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="4dcfc-123">詳細については [、Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dcfc-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>