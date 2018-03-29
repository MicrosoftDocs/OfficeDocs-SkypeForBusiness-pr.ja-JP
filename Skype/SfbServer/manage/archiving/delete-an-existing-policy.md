---
title: Skype for Business Server 2015 での既存のアーカイブ ポリシーの削除
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: '概要: は、Skype のビジネス サーバー 2015 のアーカイブ ポリシーを削除する方法を説明します。'
ms.openlocfilehash: aeb640cc832bffbded4765e5b6cc931a17365215
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="59c52-103">Skype for Business Server 2015 での既存のアーカイブ ポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="59c52-103">Delete an existing archiving policy in Skype for Business Server 2015</span></span>

<span data-ttu-id="59c52-104">**の概要:**ビジネス サーバー 2015 の Skype は、アーカイブ ・ ポリシーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="59c52-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="59c52-105">ユーザー ポリシーやサイト ポリシーは削除できますが、グローバル ポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="59c52-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="59c52-106">グローバル ポリシーを削除する場合 Skype ビジネス サーバーに自動的にポリシーをリセットする既定値にします。</span><span class="sxs-lookup"><span data-stu-id="59c52-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="59c52-107">コントロール パネルを使用してポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="59c52-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="59c52-108">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="59c52-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="59c52-109">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="59c52-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="59c52-110">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59c52-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="59c52-111">アーカイブ ポリシーのリストで、削除するユーザー ポリシーまたはサイト ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59c52-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="59c52-112">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59c52-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="59c52-113">Windows PowerShell を使用してポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="59c52-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="59c52-114">**Remove-CsArchivingPolicy** コマンドレットを使用してアーカイブ ポリシーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="59c52-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="59c52-p102">たとえば、以下のコマンドを実行すると、site:Redmond という ID を持つポリシーが削除されます。サイト レベルで構成されているポリシーを削除すると、以前にサイト ポリシーによって管理されていたユーザーは、代わりにグローバル アーカイブ ポリシーによって自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="59c52-p102">For example, the following command deletes the policy with the Identity site:Redmond. When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="59c52-117">このコマンドでは、ユーザーごとのレベルに適用されているすべてのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="59c52-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="59c52-118">このコマンドでは、内部アーカイブが無効になっているすべてのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="59c52-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="59c52-119">詳細については、[削除 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59c52-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>