---
title: Skype for Business Server で障害を処理するためのアーカイブ オプションを構成する
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
description: '概要: アーカイブを妨げる Skype for Business Server 障害が発生した場合に IM および会議セッションをブロックする方法について説明します。'
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817677"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="3c22a-103">Skype for Business Server で障害を処理するためのアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="3c22a-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="3c22a-104">**概要:** アーカイブを妨げる Skype for Business Server 障害が発生した場合に IM および会議セッションをブロックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c22a-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="3c22a-105">アーカイブが組織の要件である場合は、Skype for Business Server でアーカイブを妨げる障害が発生した場合に IM および会議セッションをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="3c22a-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="3c22a-106">これは、重要モードとも呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3c22a-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="3c22a-107">たとえば、記憶域サービスに問題がある場合、通信でアーカイブが有効になっているユーザーに対して IM がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3c22a-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="3c22a-108">障害から回復した後、IM および会議は自動的に回復します。</span><span class="sxs-lookup"><span data-stu-id="3c22a-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="3c22a-109">コントロール パネルを使用して重要モードを構成する</span><span class="sxs-lookup"><span data-stu-id="3c22a-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="3c22a-110">アーカイブを妨げる障害が発生した場合に通信セッションを許可するかどうかを指定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c22a-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="3c22a-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3c22a-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="3c22a-112">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3c22a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3c22a-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c22a-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="3c22a-114">アーカイブ構成の一覧で、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[編集] をクリックして、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c22a-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="3c22a-115">障害が発生したときのアーカイブの動作を設定するには、[アーカイブに失敗した場合にインスタント メッセージング **(IM)** または Web 会議セッションをブロックする] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="3c22a-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="3c22a-116">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c22a-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="3c22a-117">ユーザー設定を使用してクリティカル モードをWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c22a-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="3c22a-118">また、BlockOnArchiveFailure パラメーターで **Set-CsArchivingConfiguration** コマンドレットを使用して、アーカイブを妨げる障害が発生した場合に通信セッションを許可するかどうかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c22a-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="3c22a-119">たとえば、次のコマンドを実行すると、アーカイブに障害が発生した場合に通信が無効になります。</span><span class="sxs-lookup"><span data-stu-id="3c22a-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="3c22a-120">次のコマンドは、アーカイブエラーが発生した場合に通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3c22a-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="3c22a-121">詳細については [、Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c22a-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

