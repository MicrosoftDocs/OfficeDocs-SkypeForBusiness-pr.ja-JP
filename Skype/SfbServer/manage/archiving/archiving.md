---
title: Skype for Business Server でのアーカイブの管理
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '概要: Skype for Business Server のアーカイブを管理する方法について学習します。'
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817737"
---
# <a name="manage-archiving-in-skype-for-business-server"></a><span data-ttu-id="c23d0-103">Skype for Business Server でのアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="c23d0-103">Manage archiving in Skype for Business Server</span></span>

<span data-ttu-id="c23d0-104">**概要:** Skype for Business Server のアーカイブを管理する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-104">**Summary:** Learn how to manage archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="c23d0-105">組織のアーカイブを展開する場合は、展開時に初期構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-105">When you deploy archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="c23d0-106">ただし、日次管理のアーカイブ サポートの実装方法を変更したり、組織の新しい要件を満たしたりしたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="c23d0-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements for your organization.</span></span> <span data-ttu-id="c23d0-107">たとえば、組織内の特定のサイト、特定のプール、または特定のユーザーに対して、アーカイブ サポートを異なる方法で設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c23d0-107">For example, you may need to set up archiving support differently for a specific site, a specific pool, or specific users within your organization.</span></span> <span data-ttu-id="c23d0-108">Skype for Business Server にホームのユーザーの場合は、アーカイブ構成オプションとユーザー ポリシーを作成およびカスタマイズすることで、これを行います。</span><span class="sxs-lookup"><span data-stu-id="c23d0-108">For users homed on Skype for Business Server, you do this by creating and customizing archiving configuration options and user policies.</span></span> 
  
<span data-ttu-id="c23d0-109">このトピックを読む前に [、「Plan for archiving in Skype for Business Server」および「Deploy](../../plan-your-deployment/archiving/archiving.md) [archiving for Skype for Business Server」](../../deploy/deploy-archiving/deploy-archiving.md)の情報を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c23d0-109">Before you read this topic, be sure you are familiar with the information in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c23d0-110">展開で Microsoft Exchange 統合を有効にした場合、Exchange ポリシーは、Exchange にホームを置き、メールボックスが In-Place Hold に設定されているユーザーに対してアーカイブを有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-110">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="c23d0-111">詳細については [、「Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business Server 」を [参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="c23d0-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="archiving-configuration-options"></a><span data-ttu-id="c23d0-112">アーカイブ構成オプション</span><span class="sxs-lookup"><span data-stu-id="c23d0-112">Archiving configuration options</span></span>

<span data-ttu-id="c23d0-113">アーカイブ構成オプションでは、次の処理を行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-113">Archiving configuration options specify whether to:</span></span>
  
- <span data-ttu-id="c23d0-114">アーカイブの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="c23d0-114">Enable or disable archiving</span></span>
    
- <span data-ttu-id="c23d0-115">IM セッションをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="c23d0-115">Archive IM sessions</span></span>
    
- <span data-ttu-id="c23d0-116">Web 会議セッションをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="c23d0-116">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="c23d0-117">アーカイブが利用できない場合のアクティビティのブロック</span><span class="sxs-lookup"><span data-stu-id="c23d0-117">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="c23d0-118">Exchange 統合の使用</span><span class="sxs-lookup"><span data-stu-id="c23d0-118">Use Exchange integration</span></span>
    
- <span data-ttu-id="c23d0-119">データの削除とエクスポートを設定する</span><span class="sxs-lookup"><span data-stu-id="c23d0-119">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="c23d0-120">これらのオプションは、グローバル レベル、サイト レベル、またはプール レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="c23d0-120">These options can be set at the global, site, or pool level.</span></span> <span data-ttu-id="c23d0-121">詳細については、「Skype for Business Server でのアーカイブ オプションの [管理」を参照してください](options.md)。</span><span class="sxs-lookup"><span data-stu-id="c23d0-121">For more information, see [Manage archiving options in Skype for Business Server](options.md).</span></span>
  
## <a name="archiving-policies"></a><span data-ttu-id="c23d0-122">アーカイブ ポリシー</span><span class="sxs-lookup"><span data-stu-id="c23d0-122">Archiving policies</span></span>

<span data-ttu-id="c23d0-123">アーカイブ ポリシーは、以下をアーカイブするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-123">Archiving policies determine whether to archive the following:</span></span>
  
- <span data-ttu-id="c23d0-124">内部通信</span><span class="sxs-lookup"><span data-stu-id="c23d0-124">Internal communications</span></span>
    
- <span data-ttu-id="c23d0-125">外部通信</span><span class="sxs-lookup"><span data-stu-id="c23d0-125">External communications</span></span>
    
<span data-ttu-id="c23d0-126">これらのポリシーは、グローバル レベル、サイト レベル、またはユーザー レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="c23d0-126">These policies can be set at the global, site, or user level.</span></span> <span data-ttu-id="c23d0-127">詳細については [、「Skype for Business Server でのアーカイブ ポリシーの管理」を参照してください](policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c23d0-127">For more information, see [Manage archiving policies in Skype for Business Server](policies.md).</span></span>
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a><span data-ttu-id="c23d0-128">コントロール パネルまたはコントロール パネルを使用してアーカイブをWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c23d0-128">Manage archiving by using the Control Panel or by using Windows PowerShell</span></span>

<span data-ttu-id="c23d0-129">コントロール パネルまたはコントロール パネルを使用して、アーカイブをWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c23d0-129">You can manage archiving by using the Control Panel or by using Windows PowerShell.</span></span> <span data-ttu-id="c23d0-130">次の表に、アーカイブの管理に役立つコマンドレットの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-130">The following table summarizes the cmdlets available to help you manage archiving.</span></span> <span data-ttu-id="c23d0-131">使用可能なすべてのパラメーターを含む構文の詳細については [、「Skype for Business Server Management Shell」を参照してください](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="c23d0-131">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span> 


|<span data-ttu-id="c23d0-132">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="c23d0-132">**Cmdlet**</span></span>|<span data-ttu-id="c23d0-133">**説明**</span><span class="sxs-lookup"><span data-stu-id="c23d0-133">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c23d0-134">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="c23d0-134">Export-CsArchivingData</span></span>  <br/> |<span data-ttu-id="c23d0-135">Skype for Business Server Archiving データベースに格納されているレコードをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c23d0-135">Exports records that have been stored in the Skype for Business Server Archiving database.</span></span>  <br/> |
|<span data-ttu-id="c23d0-136">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c23d0-136">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c23d0-137">組織のアーカイブ構成設定に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-137">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="c23d0-138">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c23d0-138">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c23d0-139">内部通信と外部通信に関する組織のアーカイブ ポリシーに関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-139">Returns information about your organization's archiving policies for internal and external communications.</span></span>  <br/> |
|<span data-ttu-id="c23d0-140">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c23d0-140">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c23d0-141">インスタント メッセージング (IM) セッション アーカイブ ポリシーをユーザーまたはユーザーのセットに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c23d0-141">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="c23d0-142">これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c23d0-142">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="c23d0-143">Invoke-CsArchivingDatabasePurge</span><span class="sxs-lookup"><span data-stu-id="c23d0-143">Invoke-CsArchivingDatabasePurge</span></span>  <br/> |<span data-ttu-id="c23d0-144">アーカイブ データベースからレコードを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-144">Manually purges records from the Archiving database.</span></span>  <br/> |
|<span data-ttu-id="c23d0-145">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c23d0-145">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c23d0-146">インスタント メッセージング (IM) 設定の新しいセットを作成します。IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c23d0-146">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="c23d0-147">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c23d0-147">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c23d0-148">新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-148">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="c23d0-149">これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="c23d0-149">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="c23d0-150">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c23d0-150">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c23d0-151">インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをオプションでブロックしたりするために使用されるアーカイブ設定の指定されたコレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-151">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="c23d0-152">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c23d0-152">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c23d0-153">指定したインスタント メッセージング (IM) アーカイブ ポリシーを削除します。このポリシーは、Skype for Business Server が内部ユーザー間で行うすべての IM セッション、および内部ユーザーとフェデレーション パートナー間のすべての IM セッションを自動的に保存するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-153">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="c23d0-154">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c23d0-154">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c23d0-155">インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-155">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
|<span data-ttu-id="c23d0-156">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c23d0-156">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c23d0-157">既存のインスタント メッセージング (IM) アーカイブ ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c23d0-157">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="c23d0-158">アーカイブ ポリシーを使用すると、内部ユーザー間で行うすべての IM セッションと会議をアーカイブできます。内部ユーザーとフェデレーション パートナーの間で行うセッションをアーカイブすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c23d0-158">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="c23d0-159">Set-CsArchivingServer</span><span class="sxs-lookup"><span data-stu-id="c23d0-159">Set-CsArchivingServer</span></span>  <br/> |<span data-ttu-id="c23d0-160">1 つ以上のアーカイブ サーバーの新しいデータベースの場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c23d0-160">Enables you to specify a new database location for one or more Archiving Servers.</span></span>  <br/> |
   

