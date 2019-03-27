---
title: ビジネス サーバーの Skype での障害を処理するためにアーカイブのオプションを構成します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '概要: アーカイブを妨げるビジネス サーバー障害の IM と会議のセッションの場合は、Skype をブロックする方法を説明します。'
ms.openlocfilehash: 4fe63319f2b480557c73e238f2b19692df06440f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883019"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="f5e59-103">ビジネス サーバーの Skype での障害を処理するためにアーカイブのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="f5e59-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="f5e59-104">**の概要:** アーカイブを妨げるビジネス サーバー障害の IM と会議のセッションの場合は、Skype をブロックする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f5e59-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="f5e59-105">アーカイブは、組織の必要な場合、Skype のアーカイブを妨げるビジネス サーバー障害の発生時に IM および会議セッションをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="f5e59-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="f5e59-106">この動作は重要モードと呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="f5e59-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="f5e59-107">たとえば、ストレージ サービスに問題が発生した場合、通信のアーカイブが有効になっているユーザーを対象に IM がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f5e59-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="f5e59-108">障害が解消されれば、IM も会議も自動的に復旧されます。</span><span class="sxs-lookup"><span data-stu-id="f5e59-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="f5e59-109">コントロール パネルを使用して重要モードを構成する</span><span class="sxs-lookup"><span data-stu-id="f5e59-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="f5e59-110">アーカイブを阻む障害が発生した場合に通信セッションを許可するかどうかを指定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f5e59-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="f5e59-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f5e59-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="f5e59-112">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f5e59-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f5e59-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5e59-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f5e59-114">アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5e59-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f5e59-115">障害が発生したときのアーカイブの動作を設定するには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="f5e59-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="f5e59-116">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5e59-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="f5e59-117">Windows PowerShell を使用して重要モードを構成する</span><span class="sxs-lookup"><span data-stu-id="f5e59-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="f5e59-118">BlockOnArchiveFailure パラメーターを使用して**セット CsArchivingConfiguration**コマンドレットを使用してアーカイブを妨げる障害が発生した場合の通信セッションを許可するかどうかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5e59-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="f5e59-119">たとえば、次のコマンドは、アーカイブが失敗した場合の通信を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f5e59-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="f5e59-120">次のコマンドは、アーカイブに障害が発生した場合でも通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f5e59-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="f5e59-121">詳細については、[セット CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5e59-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

