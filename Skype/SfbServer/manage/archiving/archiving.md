---
title: Skype for Business Server でアーカイブを管理する
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '概要: Skype for Business Server のアーカイブを管理する方法について説明します。'
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818999"
---
# <a name="manage-archiving-in-skype-for-business-server"></a><span data-ttu-id="2925a-103">Skype for Business Server でアーカイブを管理する</span><span class="sxs-lookup"><span data-stu-id="2925a-103">Manage archiving in Skype for Business Server</span></span>

<span data-ttu-id="2925a-104">**概要:** Skype for Business Server のアーカイブを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2925a-104">**Summary:** Learn how to manage archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="2925a-105">組織のアーカイブを展開するときは、展開時に初期構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="2925a-105">When you deploy archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="2925a-106">ただし、日常的な管理のためのアーカイブサポートの実装方法を変更したり、組織の新しい要件を満たす必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="2925a-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements for your organization.</span></span> <span data-ttu-id="2925a-107">たとえば、特定のサイト、特定のプール、または組織内の特定のユーザーに対して、アーカイブのサポートを異なる方法でセットアップすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2925a-107">For example, you may need to set up archiving support differently for a specific site, a specific pool, or specific users within your organization.</span></span> <span data-ttu-id="2925a-108">Skype for Business Server を使っているユーザーは、アーカイブ構成オプションとユーザーポリシーを作成してカスタマイズすることで、この操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2925a-108">For users homed on Skype for Business Server, you do this by creating and customizing archiving configuration options and user policies.</span></span> 
  
<span data-ttu-id="2925a-109">このトピックを読む前に、「 [skype For Business server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」の情報と[Skype for business server のアーカイブの展開](../../deploy/deploy-archiving/deploy-archiving.md)について理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2925a-109">Before you read this topic, be sure you are familiar with the information in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2925a-110">展開で Microsoft Exchange 統合が有効の場合、インプレース保持上にメールボックスがある Exchange 所属のユーザーに対してアーカイブを有効にするかどうかは、Exchange のポリシーで管理されます。</span><span class="sxs-lookup"><span data-stu-id="2925a-110">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="2925a-111">詳細については、「 [skype For Business server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」および「 [Skype for business Server 用の Exchange storage との統合を構成する](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2925a-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="archiving-configuration-options"></a><span data-ttu-id="2925a-112">構成オプションをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="2925a-112">Archiving configuration options</span></span>

<span data-ttu-id="2925a-113">アーカイブ構成オプションでは次の事項を指定します。</span><span class="sxs-lookup"><span data-stu-id="2925a-113">Archiving configuration options specify whether to:</span></span>
  
- <span data-ttu-id="2925a-114">アーカイブの有効または無効</span><span class="sxs-lookup"><span data-stu-id="2925a-114">Enable or disable archiving</span></span>
    
- <span data-ttu-id="2925a-115">IM セッションのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="2925a-115">Archive IM sessions</span></span>
    
- <span data-ttu-id="2925a-116">Web 会議セッションのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="2925a-116">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="2925a-117">アーカイブを使用できない場合のアクティビティのブロック</span><span class="sxs-lookup"><span data-stu-id="2925a-117">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="2925a-118">Exchange 統合の使用</span><span class="sxs-lookup"><span data-stu-id="2925a-118">Use Exchange integration</span></span>
    
- <span data-ttu-id="2925a-119">データの削除とエクスポートのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2925a-119">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="2925a-120">これらのオプションは、グローバル レベル、サイト レベル、プール レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="2925a-120">These options can be set at the global, site, or pool level.</span></span> <span data-ttu-id="2925a-121">詳細については、「 [Skype For Business Server のアーカイブオプションを管理](options.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2925a-121">For more information, see [Manage archiving options in Skype for Business Server](options.md).</span></span>
  
## <a name="archiving-policies"></a><span data-ttu-id="2925a-122">アーカイブのポリシー</span><span class="sxs-lookup"><span data-stu-id="2925a-122">Archiving policies</span></span>

<span data-ttu-id="2925a-123">アーカイブポリシーは、次のアイテムをアーカイブするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2925a-123">Archiving policies determine whether to archive the following:</span></span>
  
- <span data-ttu-id="2925a-124">内部通信</span><span class="sxs-lookup"><span data-stu-id="2925a-124">Internal communications</span></span>
    
- <span data-ttu-id="2925a-125">外部通信</span><span class="sxs-lookup"><span data-stu-id="2925a-125">External communications</span></span>
    
<span data-ttu-id="2925a-126">これらのポリシーは、グローバル レベル、サイト レベル、ユーザー レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="2925a-126">These policies can be set at the global, site, or user level.</span></span> <span data-ttu-id="2925a-127">詳細については、「 [Skype For Business Server でアーカイブポリシーを管理](policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2925a-127">For more information, see [Manage archiving policies in Skype for Business Server](policies.md).</span></span>
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a><span data-ttu-id="2925a-128">コントロール パネルまたは Windows PowerShell コマンドレットを使用してアーカイブを管理する</span><span class="sxs-lookup"><span data-stu-id="2925a-128">Manage archiving by using the Control Panel or by using Windows PowerShell</span></span>

<span data-ttu-id="2925a-129">アーカイブは、コントロール パネルまたは Windows PowerShell コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="2925a-129">You can manage archiving by using the Control Panel or by using Windows PowerShell.</span></span> <span data-ttu-id="2925a-130">次の表に、アーカイブの管理に役立つ使用可能なコマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="2925a-130">The following table summarizes the cmdlets available to help you manage archiving.</span></span> <span data-ttu-id="2925a-131">使用可能なすべてのパラメーターを含む構文の詳細については、「 [Skype For Business Server 管理シェル](../management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2925a-131">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span> 


|<span data-ttu-id="2925a-132">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="2925a-132">**Cmdlet**</span></span>|<span data-ttu-id="2925a-133">**説明**</span><span class="sxs-lookup"><span data-stu-id="2925a-133">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2925a-134">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="2925a-134">Export-CsArchivingData</span></span>  <br/> |<span data-ttu-id="2925a-135">Skype for Business Server アーカイブデータベースに保存されているレコードをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2925a-135">Exports records that have been stored in the Skype for Business Server Archiving database.</span></span>  <br/> |
|<span data-ttu-id="2925a-136">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2925a-136">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2925a-137">組織のアーカイブ構成設定に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="2925a-137">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="2925a-138">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="2925a-138">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="2925a-139">内部および外部通信に関する組織のアーカイブ ポリシーの情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="2925a-139">Returns information about your organization's archiving policies for internal and external communications.</span></span>  <br/> |
|<span data-ttu-id="2925a-140">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="2925a-140">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="2925a-141">インスタント メッセージング (IM) セッションのアーカイブ ポリシーをユーザーまたはユーザー セットに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2925a-141">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="2925a-142">これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりできます。</span><span class="sxs-lookup"><span data-stu-id="2925a-142">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="2925a-143">Invoke-CsArchivingDatabasePurge</span><span class="sxs-lookup"><span data-stu-id="2925a-143">Invoke-CsArchivingDatabasePurge</span></span>  <br/> |<span data-ttu-id="2925a-144">アーカイブ データベースからレコードを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="2925a-144">Manually purges records from the Archiving database.</span></span>  <br/> |
|<span data-ttu-id="2925a-145">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2925a-145">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2925a-146">インスタント メッセージング (IM) 設定のセットを新たに作成します。これらの設定を使用すると、IM セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをブロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="2925a-146">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="2925a-147">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="2925a-147">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="2925a-148">新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2925a-148">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="2925a-149">これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="2925a-149">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="2925a-150">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2925a-150">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2925a-151">アーカイブ設定の指定のコレクションを削除します。アーカイブ設定は、インスタント メッセージング (IM) セッションの自動保存を有効または無効にしたり、アーカイブできないインスタント メッセージをすべてブロックしたり (オプション) するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2925a-151">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="2925a-152">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="2925a-152">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="2925a-153">内部ユーザーとフェデレーションパートナー間のすべての im セッションが、Skype for Business Server によって自動的に保存されるかどうかを決定する、指定したインスタントメッセージング (IM) アーカイブポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2925a-153">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="2925a-154">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2925a-154">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="2925a-155">インスタント メッセージング (IM) アーカイブ構成オプションの既存のコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="2925a-155">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
|<span data-ttu-id="2925a-156">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="2925a-156">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="2925a-157">既存のインスタントメッセージング (IM) アーカイブポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="2925a-157">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="2925a-158">アーカイブポリシーを使用すると、内部ユーザー間で行われるすべての IM セッションと会議をアーカイブすることができます。内部ユーザーとフェデレーションパートナーの間で行われるセッションをアーカイブすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2925a-158">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="2925a-159">Set-CsArchivingServer</span><span class="sxs-lookup"><span data-stu-id="2925a-159">Set-CsArchivingServer</span></span>  <br/> |<span data-ttu-id="2925a-160">1 つ以上のアーカイブ サーバーの新しいデータベースの場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2925a-160">Enables you to specify a new database location for one or more Archiving Servers.</span></span>  <br/> |
   

