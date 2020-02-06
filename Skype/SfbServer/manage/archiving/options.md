---
title: Skype for Business Server でアーカイブオプションを管理する
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '概要: Skype for Business Server のアーカイブオプションを構成する方法について説明します。'
ms.openlocfilehash: af5c8f90cd49f556e1e787e5f550b54da1976c45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818899"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="ffe71-103">Skype for Business Server でアーカイブオプションを管理する</span><span class="sxs-lookup"><span data-stu-id="ffe71-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="ffe71-104">**概要:** Skype for Business Server のアーカイブオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffe71-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="ffe71-105">アーカイブは展開時に初期構成しますが、展開後に変更、追加、削除ができます。</span><span class="sxs-lookup"><span data-stu-id="ffe71-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="ffe71-106">アーカイブ オプションでは次の事項を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffe71-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="ffe71-107">アーカイブの有効または無効</span><span class="sxs-lookup"><span data-stu-id="ffe71-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="ffe71-108">IM セッションのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="ffe71-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="ffe71-109">Web 会議セッションのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="ffe71-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="ffe71-110">アーカイブを使用できない場合のアクティビティのブロック</span><span class="sxs-lookup"><span data-stu-id="ffe71-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="ffe71-111">Exchange 統合の使用</span><span class="sxs-lookup"><span data-stu-id="ffe71-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="ffe71-112">データの削除とエクスポートのセットアップ</span><span class="sxs-lookup"><span data-stu-id="ffe71-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="ffe71-113">構成オプションは次のレベルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="ffe71-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="ffe71-114">Skype for Business Server を展開するときに既定で作成されるグローバルレベルの構成</span><span class="sxs-lookup"><span data-stu-id="ffe71-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="ffe71-115">(オプション) 特定のサイトにアーカイブを実装する方法を指定するサイト レベルの構成</span><span class="sxs-lookup"><span data-stu-id="ffe71-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="ffe71-116">特定のプールに対するアーカイブの実装方法を指定するオプションのプールレベル構成</span><span class="sxs-lookup"><span data-stu-id="ffe71-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="ffe71-117">サイト構成やプール構成は削除できますが、グローバル構成は削除できません。</span><span class="sxs-lookup"><span data-stu-id="ffe71-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="ffe71-118">グローバル構成を削除すると、グローバル構成は自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="ffe71-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="ffe71-119">アーカイブ構成の実装方法とアーカイブ構成の階層について詳しくは、「 [Skype For Business Server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ffe71-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="ffe71-120">コントロール パネルを使用してアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="ffe71-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="ffe71-121">アーカイブ オプションは、コントロール パネルを使用して次の手順で構成できます。</span><span class="sxs-lookup"><span data-stu-id="ffe71-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="ffe71-122">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ffe71-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="ffe71-123">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ffe71-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ffe71-124">左側のナビゲーション バーで [**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffe71-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="ffe71-125">Windows PowerShell を使用してアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="ffe71-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="ffe71-126">次の表に示す Windows PowerShell コマンドレットを使用してアーカイブ オプションを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ffe71-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="ffe71-127">使用可能なすべてのパラメーターを含む構文の詳細については、「 [Skype For Business Server 管理シェル](../management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe71-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="ffe71-128">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="ffe71-128">**Cmdlet**</span></span>|<span data-ttu-id="ffe71-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="ffe71-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ffe71-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ffe71-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="ffe71-131">組織のアーカイブ構成設定に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="ffe71-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="ffe71-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ffe71-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="ffe71-133">インスタント メッセージング (IM) 設定のセットを新たに作成します。これらの設定を使用すると、IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="ffe71-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="ffe71-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ffe71-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="ffe71-135">アーカイブ設定の指定のコレクションを削除します。アーカイブ設定は、インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをすべてブロックしたり (オプション) するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ffe71-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="ffe71-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ffe71-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="ffe71-137">インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="ffe71-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
