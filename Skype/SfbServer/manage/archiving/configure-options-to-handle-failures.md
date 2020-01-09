---
title: Skype for Business Server のエラーを処理するアーカイブオプションを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '概要: Skype for Business Server に障害が発生したときに、アーカイブを防ぐことができる IM と会議セッションをブロックする方法について説明します。'
ms.openlocfilehash: ed8a59a8c19ace9a83b699e1b69515f52c3af010
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992754"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="5636d-103">Skype for Business Server のエラーを処理するアーカイブオプションを構成する</span><span class="sxs-lookup"><span data-stu-id="5636d-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="5636d-104">**概要:** Skype for Business Server に障害が発生したときに、アーカイブを防ぐことができる IM と会議セッションをブロックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5636d-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="5636d-105">組織でアーカイブが必要な場合は、Skype for Business Server に障害が発生したときに、アーカイブを防ぐことができる IM と会議セッションをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="5636d-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="5636d-106">この動作は重要モードと呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="5636d-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="5636d-107">たとえば、ストレージ サービスに問題が発生した場合、通信のアーカイブが有効になっているユーザーを対象に IM がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="5636d-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="5636d-108">障害が解消されれば、IM も会議も自動的に復旧されます。</span><span class="sxs-lookup"><span data-stu-id="5636d-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="5636d-109">コントロール パネルを使用して重要モードを構成する</span><span class="sxs-lookup"><span data-stu-id="5636d-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="5636d-110">アーカイブを阻む障害が発生した場合に通信セッションを許可するかどうかを指定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5636d-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="5636d-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5636d-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="5636d-112">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5636d-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5636d-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5636d-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="5636d-114">アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5636d-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5636d-115">障害が発生したときのアーカイブの動作を設定するには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="5636d-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="5636d-116">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5636d-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="5636d-117">Windows PowerShell を使用して重要モードを構成する</span><span class="sxs-lookup"><span data-stu-id="5636d-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="5636d-118">また、 **BlockonCsArchivingConfiguration**コマンドレットを使用して、アーカイブを禁止するエラーが発生した場合に通信セッションを許可するかどうかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5636d-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="5636d-119">たとえば、次のコマンドを実行すると、アーカイブに失敗した場合の通信が無効になります。</span><span class="sxs-lookup"><span data-stu-id="5636d-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="5636d-120">次のコマンドは、アーカイブに障害が発生した場合でも通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5636d-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="5636d-121">詳細については、 [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5636d-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

