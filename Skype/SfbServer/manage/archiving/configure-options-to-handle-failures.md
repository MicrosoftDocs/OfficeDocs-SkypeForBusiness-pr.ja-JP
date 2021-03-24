---
title: Skype for Business Server の障害を処理するアーカイブ オプションを構成する
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '概要: アーカイブを妨げる Skype for Business Server 障害が発生した場合に IM セッションと会議セッションをブロックする方法について説明します。'
ms.openlocfilehash: 8bfe4d3f8e02fa0d7d7d3f1f6b55f224aaa1451a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095451"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="24a36-103">Skype for Business Server の障害を処理するアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="24a36-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="24a36-104">**概要:** アーカイブを妨げる Skype for Business Server 障害が発生した場合に IM セッションと会議セッションをブロックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="24a36-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="24a36-105">アーカイブが組織の要件である場合は、アーカイブを妨げる Skype for Business Server 障害が発生した場合に IM セッションと会議セッションをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="24a36-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="24a36-106">これは、クリティカル モードと呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="24a36-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="24a36-107">たとえば、ストレージ サービスに問題がある場合、アーカイブ用に通信が有効になっているユーザーに対して IM がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="24a36-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="24a36-108">障害から回復した後、IM および会議は自動的に回復します。</span><span class="sxs-lookup"><span data-stu-id="24a36-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="24a36-109">コントロール パネルを使用してクリティカル モードを構成する</span><span class="sxs-lookup"><span data-stu-id="24a36-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="24a36-110">アーカイブを妨げる障害が発生した場合に通信セッションを許可するかどうかを指定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="24a36-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="24a36-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="24a36-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="24a36-112">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="24a36-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="24a36-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24a36-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="24a36-114">アーカイブ構成の一覧で、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[編集] をクリックし、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="24a36-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="24a36-115">障害が発生した場合のアーカイブの動作を設定するには、[アーカイブが失敗した場合にインスタント メッセージング **(IM)** セッションまたは Web 会議セッションをブロックする] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="24a36-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="24a36-116">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24a36-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="24a36-117">アプリケーションを使用してクリティカル モードをWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="24a36-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="24a36-118">**また、BlockOnArchiveFailure パラメーターで Set-CsArchivingConfiguration** コマンドレットを使用して、アーカイブを妨げる障害が発生した場合に通信セッションを許可するかどうかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="24a36-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="24a36-119">たとえば、次のコマンドは、アーカイブに失敗した場合の通信を無効にします。</span><span class="sxs-lookup"><span data-stu-id="24a36-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="24a36-120">次のコマンドは、アーカイブに失敗した場合の通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="24a36-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="24a36-121">詳細については [、Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24a36-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
