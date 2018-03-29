---
title: Skype for Business Server 2015 のアーカイブの管理
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '概要: は、Skype のビジネス サーバー 2015 のアーカイブを管理する方法を説明します。'
ms.openlocfilehash: fb8359d47b1933e2575685bc532d69e6b9bb6c45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="c34f5-103">Skype for Business Server 2015 のアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="c34f5-103">Manage archiving in Skype for Business Server 2015</span></span>

<span data-ttu-id="c34f5-104">**の概要:**Skype ビジネス サーバー 2015 のアーカイブを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-104">**Summary:** Learn how to manage archiving for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c34f5-105">組織のアーカイブを展開するときは、初期展開時に構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-105">When you deploy archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="c34f5-106">ただし、日常的な管理のためのアーカイブのサポートを実装する方法を変更するか、組織の新しい要件を満たすために、必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c34f5-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements for your organization.</span></span> <span data-ttu-id="c34f5-107">たとえば、アーカイブとは異なる、特定のサイト、特定のプール、または組織内の特定のユーザーのサポートを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c34f5-107">For example, you may need to set up archiving support differently for a specific site, a specific pool, or specific users within your organization.</span></span> <span data-ttu-id="c34f5-108">ユーザーは、Skype のビジネス サーバーのホームのこれを行うを作成し、アーカイブの構成オプションとユーザーのポリシーをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="c34f5-108">For users homed on Skype for Business Server, you do this by creating and customizing archiving configuration options and user policies.</span></span> 
  
<span data-ttu-id="c34f5-109">このトピックを参照する前に、[ビジネス サーバー 2015 の Skype でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)し、[展開のビジネス サーバー 2015 の Skype のアーカイブ](../../deploy/deploy-archiving/deploy-archiving.md)内の情報に精通していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-109">Before you read this topic, be sure you are familiar with the information in [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c34f5-110">展開で Microsoft Exchange 統合が有効の場合、インプレース保持上にメールボックスがある Exchange 所属のユーザーに対してアーカイブを有効にするかどうかは、Exchange のポリシーで管理されます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-110">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="c34f5-111">詳細については、[ビジネス サーバー 2015 の Skype でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)と[構成との統合ビジネス サーバー 2015 の Skype の Exchange の記憶域](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c34f5-111">For details, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="archiving-configuration-options"></a><span data-ttu-id="c34f5-112">構成オプションをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="c34f5-112">Archiving configuration options</span></span>

<span data-ttu-id="c34f5-113">アーカイブ構成オプションでは次の事項を指定します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-113">Archiving configuration options specify whether to:</span></span>
  
- <span data-ttu-id="c34f5-114">アーカイブの有効または無効</span><span class="sxs-lookup"><span data-stu-id="c34f5-114">Enable or disable archiving</span></span>
    
- <span data-ttu-id="c34f5-115">IM セッションのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="c34f5-115">Archive IM sessions</span></span>
    
- <span data-ttu-id="c34f5-116">Web 会議セッションのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="c34f5-116">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="c34f5-117">アーカイブを使用できない場合のアクティビティのブロック</span><span class="sxs-lookup"><span data-stu-id="c34f5-117">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="c34f5-118">Exchange 統合の使用</span><span class="sxs-lookup"><span data-stu-id="c34f5-118">Use Exchange integration</span></span>
    
- <span data-ttu-id="c34f5-119">データの削除とエクスポートのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c34f5-119">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="c34f5-120">これらのオプションは、グローバル レベル、サイト レベル、プール レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-120">These options can be set at the global, site, or pool level.</span></span> <span data-ttu-id="c34f5-121">詳細については、[ビジネス サーバー 2015 の Skype での管理アーカイブ ・ オプション](options.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c34f5-121">For more information, see [Manage archiving options in Skype for Business Server 2015](options.md).</span></span>
  
## <a name="archiving-policies"></a><span data-ttu-id="c34f5-122">アーカイブのポリシー</span><span class="sxs-lookup"><span data-stu-id="c34f5-122">Archiving policies</span></span>

<span data-ttu-id="c34f5-123">アーカイブ ・ ポリシーは、次にアーカイブするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-123">Archiving policies determine whether to archive the following:</span></span>
  
- <span data-ttu-id="c34f5-124">内部通信</span><span class="sxs-lookup"><span data-stu-id="c34f5-124">Internal communications</span></span>
    
- <span data-ttu-id="c34f5-125">外部通信</span><span class="sxs-lookup"><span data-stu-id="c34f5-125">External communications</span></span>
    
<span data-ttu-id="c34f5-126">これらのポリシーは、グローバル レベル、サイト レベル、ユーザー レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-126">These policies can be set at the global, site, or user level.</span></span> <span data-ttu-id="c34f5-127">詳細については、 [Skype のビジネス サーバー 2015 のアーカイブ ・ ポリシーの管理](policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c34f5-127">For more information, see [Manage archiving policies in Skype for Business Server 2015](policies.md).</span></span>
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a><span data-ttu-id="c34f5-128">コントロール パネルまたは Windows PowerShell コマンドレットを使用してアーカイブを管理する</span><span class="sxs-lookup"><span data-stu-id="c34f5-128">Manage archiving by using the Control Panel or by using Windows PowerShell</span></span>

<span data-ttu-id="c34f5-129">アーカイブは、コントロール パネルまたは Windows PowerShell コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-129">You can manage archiving by using the Control Panel or by using Windows PowerShell.</span></span> <span data-ttu-id="c34f5-130">次の表に、アーカイブの管理に役立つ使用可能なコマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-130">The following table summarizes the cmdlets available to help you manage archiving.</span></span> <span data-ttu-id="c34f5-131">などのすべての利用可能なパラメーターの構文の詳細については、 [Skype ビジネス サーバー 2015 管理シェルに](../management-shell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c34f5-131">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span> 


|<span data-ttu-id="c34f5-132">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="c34f5-132">**Cmdlet**</span></span>|<span data-ttu-id="c34f5-133">**説明**</span><span class="sxs-lookup"><span data-stu-id="c34f5-133">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c34f5-134">.Eml という</span><span class="sxs-lookup"><span data-stu-id="c34f5-134">Export-CsArchivingData</span></span>  <br/> |<span data-ttu-id="c34f5-135">Skype のビジネス ・ サーバのアーカイブ データベースに格納されているレコードをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c34f5-135">Exports records that have been stored in the Skype for Business Server Archiving database.</span></span>  <br/> |
|<span data-ttu-id="c34f5-136">Get CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c34f5-136">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c34f5-137">組織のアーカイブ構成設定に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-137">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="c34f5-138">Get CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c34f5-138">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c34f5-139">内部および外部通信に関する組織のアーカイブ ポリシーの情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-139">Returns information about your organization's archiving policies for internal and external communications.</span></span>  <br/> |
|<span data-ttu-id="c34f5-140">許可 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c34f5-140">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c34f5-141">インスタント メッセージング (IM) セッションのアーカイブ ポリシーをユーザーまたはユーザー セットに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-141">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="c34f5-142">これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりできます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-142">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="c34f5-143">呼び出す CsArchivingDatabasePurge</span><span class="sxs-lookup"><span data-stu-id="c34f5-143">Invoke-CsArchivingDatabasePurge</span></span>  <br/> |<span data-ttu-id="c34f5-144">アーカイブ データベースからレコードを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-144">Manually purges records from the Archiving database.</span></span>  <br/> |
|<span data-ttu-id="c34f5-145">CsArchivingConfiguration で新しい</span><span class="sxs-lookup"><span data-stu-id="c34f5-145">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c34f5-146">インスタント メッセージング (IM) 設定のセットを新たに作成します。これらの設定を使用すると、IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-146">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="c34f5-147">新しい-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c34f5-147">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c34f5-148">新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-148">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="c34f5-149">これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-149">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="c34f5-150">削除 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c34f5-150">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c34f5-151">アーカイブ設定の指定のコレクションを削除します。アーカイブ設定は、インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをすべてブロックしたり (オプション) するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-151">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="c34f5-152">削除 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c34f5-152">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c34f5-153">指定したインスタント メッセージング (IM) アーカイブ ビジネス サーバーの Skype の内部ユーザー、および内部ユーザーとフェデレーション パートナーとの間のすべての IM セッションの間で行われるすべての IM セッションが自動的に保存するかどうかを決定するポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-153">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="c34f5-154">セット CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c34f5-154">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c34f5-155">インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-155">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
|<span data-ttu-id="c34f5-156">セット CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c34f5-156">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c34f5-157">既存インスタント メッセージング (IM) アーカイブ ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c34f5-157">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="c34f5-158">アーカイブ ポリシーは、すべての IM セッションおよび内部ユーザー間で行われる会議をアーカイブする機能を提供します。内部ユーザーとフェデレーション パートナーの間で行われるセッションをアーカイブすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-158">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="c34f5-159">セット CsArchivingServer</span><span class="sxs-lookup"><span data-stu-id="c34f5-159">Set-CsArchivingServer</span></span>  <br/> |<span data-ttu-id="c34f5-160">1 つ以上のアーカイブ サーバーの新しいデータベースの場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c34f5-160">Enables you to specify a new database location for one or more Archiving Servers.</span></span>  <br/> |
   

