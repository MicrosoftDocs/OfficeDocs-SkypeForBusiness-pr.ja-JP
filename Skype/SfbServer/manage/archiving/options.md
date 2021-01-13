---
title: Skype for Business Server でアーカイブ オプションを管理する
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '概要: Skype for Business Server のアーカイブ オプションを構成する方法について説明します。'
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817537"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="9d18c-103">Skype for Business Server でアーカイブ オプションを管理する</span><span class="sxs-lookup"><span data-stu-id="9d18c-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="9d18c-104">**概要:** Skype for Business Server のアーカイブ オプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9d18c-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="9d18c-105">最初は展開時にアーカイブを構成しますが、展開後に構成を変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="9d18c-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="9d18c-106">アーカイブ オプションは、次の処理を行うかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9d18c-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="9d18c-107">アーカイブの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="9d18c-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="9d18c-108">IM セッションをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="9d18c-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="9d18c-109">Web 会議セッションをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="9d18c-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="9d18c-110">アーカイブが利用できない場合のアクティビティのブロック</span><span class="sxs-lookup"><span data-stu-id="9d18c-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="9d18c-111">Exchange 統合の使用</span><span class="sxs-lookup"><span data-stu-id="9d18c-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="9d18c-112">データの削除とエクスポートを設定する</span><span class="sxs-lookup"><span data-stu-id="9d18c-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="9d18c-113">構成オプションは、次のレベルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="9d18c-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="9d18c-114">Skype for Business Server を展開するときに既定で作成されるグローバル レベルの構成</span><span class="sxs-lookup"><span data-stu-id="9d18c-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="9d18c-115">特定のサイトに対するアーカイブの実装方法を指定するオプションのサイト レベルの構成</span><span class="sxs-lookup"><span data-stu-id="9d18c-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="9d18c-116">特定のプールに対するアーカイブの実装方法を指定するオプションのプール レベルの構成</span><span class="sxs-lookup"><span data-stu-id="9d18c-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="9d18c-117">サイト構成またはプール構成は削除できますが、グローバル構成を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="9d18c-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="9d18c-118">グローバル構成を削除すると、自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="9d18c-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="9d18c-119">アーカイブ構成の実装方法とアーカイブ構成の階層の詳細については [、「Plan for archiving in Skype for Business Server」](../../plan-your-deployment/archiving/archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d18c-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="9d18c-120">コントロール パネルを使用してアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="9d18c-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="9d18c-121">次のように、コントロール パネルを使用してアーカイブ オプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="9d18c-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="9d18c-122">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9d18c-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9d18c-123">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9d18c-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9d18c-124">左側のナビゲーション バーで、[アーカイブ構成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d18c-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="9d18c-125">アーカイブ オプションを構成するには、次のWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d18c-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="9d18c-126">次の表に示すコマンドレットWindows PowerShell使用して、アーカイブ オプションを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d18c-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="9d18c-127">使用可能なすべてのパラメーターを含む構文の詳細については [、「Skype for Business Server Management Shell」を参照してください](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="9d18c-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="9d18c-128">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="9d18c-128">**Cmdlet**</span></span>|<span data-ttu-id="9d18c-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="9d18c-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9d18c-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9d18c-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="9d18c-131">組織のアーカイブ構成設定に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="9d18c-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="9d18c-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9d18c-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="9d18c-133">インスタント メッセージング (IM) 設定の新しいセットを作成します。IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d18c-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="9d18c-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9d18c-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="9d18c-135">インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをオプションでブロックしたりするために使用されるアーカイブ設定の指定されたコレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="9d18c-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="9d18c-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9d18c-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="9d18c-137">インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="9d18c-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
