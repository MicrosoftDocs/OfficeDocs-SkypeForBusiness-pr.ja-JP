---
title: Skype for Business Server 2015 でのアーカイブ オプションの管理
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '概要: ビジネス サーバー 2015 の Skype のアーカイブのオプションを構成する方法を説明します。'
ms.openlocfilehash: 29800fef7054cd0e82f203d2ad6ec1ed53251ca4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-options-in-skype-for-business-server-2015"></a><span data-ttu-id="2c340-103">Skype for Business Server 2015 でのアーカイブ オプションの管理</span><span class="sxs-lookup"><span data-stu-id="2c340-103">Manage archiving options in Skype for Business Server 2015</span></span>

<span data-ttu-id="2c340-104">**の概要:**ビジネス サーバー 2015 の Skype のアーカイブのオプションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c340-104">**Summary:** Learn how to configure archiving options for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2c340-105">アーカイブは展開時に初期構成しますが、展開後に変更、追加、削除ができます。</span><span class="sxs-lookup"><span data-stu-id="2c340-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="2c340-106">アーカイブ オプションでは次の事項を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c340-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="2c340-107">アーカイブの有効または無効</span><span class="sxs-lookup"><span data-stu-id="2c340-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="2c340-108">IM セッションのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="2c340-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="2c340-109">Web 会議セッションのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="2c340-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="2c340-110">アーカイブを使用できない場合のアクティビティのブロック</span><span class="sxs-lookup"><span data-stu-id="2c340-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="2c340-111">Exchange 統合の使用</span><span class="sxs-lookup"><span data-stu-id="2c340-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="2c340-112">データの削除とエクスポートのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2c340-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="2c340-113">構成オプションは次のレベルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="2c340-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="2c340-114">ビジネス サーバーに対して Skype を展開するときに既定で作成されるグローバル レベルの構成</span><span class="sxs-lookup"><span data-stu-id="2c340-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="2c340-115">(オプション) 特定のサイトにアーカイブを実装する方法を指定するサイト レベルの構成</span><span class="sxs-lookup"><span data-stu-id="2c340-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="2c340-116">特定のプールのアーカイブの実装方法を指定するオプションのプールレベルの構成</span><span class="sxs-lookup"><span data-stu-id="2c340-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="2c340-117">サイト構成やプール構成は削除できますが、グローバル構成は削除できません。</span><span class="sxs-lookup"><span data-stu-id="2c340-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="2c340-118">グローバル構成を削除すると、グローバル構成は自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2c340-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="2c340-119">アーカイブ構成の実装方法の詳細について、アーカイブ構成の階層構造では、 [Skype のビジネス サーバー 2015 でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c340-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="2c340-120">コントロール パネルを使用してアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="2c340-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="2c340-121">アーカイブ オプションは、コントロール パネルを使用して次の手順で構成できます。</span><span class="sxs-lookup"><span data-stu-id="2c340-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="2c340-122">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2c340-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="2c340-123">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2c340-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2c340-124">左側のナビゲーション バーで [**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c340-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="2c340-125">Windows PowerShell を使用してアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="2c340-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="2c340-126">次の表に示す Windows PowerShell コマンドレットを使用してアーカイブ オプションを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2c340-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="2c340-127">などのすべての利用可能なパラメーターの構文の詳細については、 [Skype ビジネス サーバー 2015 管理シェルに](../management-shell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c340-127">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="2c340-128">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="2c340-128">**Cmdlet**</span></span>|<span data-ttu-id="2c340-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="2c340-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2c340-130">Get CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2c340-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2c340-131">組織のアーカイブ構成設定に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="2c340-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="2c340-132">CsArchivingConfiguration で新しい</span><span class="sxs-lookup"><span data-stu-id="2c340-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2c340-133">インスタント メッセージング (IM) 設定のセットを新たに作成します。これらの設定を使用すると、IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="2c340-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="2c340-134">削除 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2c340-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2c340-135">アーカイブ設定の指定のコレクションを削除します。アーカイブ設定は、インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをすべてブロックしたり (オプション) するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c340-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="2c340-136">セット CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2c340-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2c340-137">インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="2c340-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |