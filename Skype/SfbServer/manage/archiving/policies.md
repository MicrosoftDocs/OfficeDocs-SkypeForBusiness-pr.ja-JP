---
title: Skype for Business Server でアーカイブ ポリシーを管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: '概要: Skype for Business Server のアーカイブ用のユーザー ポリシーを管理する方法について説明します。'
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828552"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="8e9e6-103">Skype for Business Server でアーカイブ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="8e9e6-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="8e9e6-104">**概要:** Skype for Business Server のアーカイブのユーザー ポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="8e9e6-105">アーカイブ ポリシーは、最初はアーカイブを展開するときに設定しますが、展開後に構成を変更、追加、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="8e9e6-106">アーカイブ ポリシーは、次の情報をアーカイブするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="8e9e6-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="8e9e6-107">Internal communications</span></span>
    
- <span data-ttu-id="8e9e6-108">外部通信</span><span class="sxs-lookup"><span data-stu-id="8e9e6-108">External communications</span></span>
    
<span data-ttu-id="8e9e6-109">アーカイブ ポリシーは、グローバル レベル、サイト レベル、またはユーザー レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e9e6-110">展開で Microsoft Exchange 統合を有効にした場合、Exchange ポリシーは、Exchange にホームを置き、メールボックスが In-Place Hold に設定されているユーザーに対してアーカイブを有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="8e9e6-111">詳細については [、「Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business Server 」を [参照してください](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="8e9e6-112">コントロール パネルを使用してアーカイブ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="8e9e6-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="8e9e6-113">次のように、コントロール パネルを使用してアーカイブ ポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="8e9e6-114">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="8e9e6-115">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8e9e6-116">左側のナビゲーション バーで、[アーカイブ ポリシー **] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="8e9e6-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="8e9e6-117">アーカイブ ポリシーを使用してアーカイブ ポリシーをWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e9e6-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="8e9e6-118">アーカイブ ポリシーは、次の表にWindows PowerShellコマンドレットを使用して構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="8e9e6-119">使用可能なすべてのパラメーターを含む構文の詳細については [、「Skype for Business Server Management Shell」を参照してください](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="8e9e6-120">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="8e9e6-120">**Cmdlet**</span></span>|<span data-ttu-id="8e9e6-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="8e9e6-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8e9e6-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8e9e6-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8e9e6-123">組織のインスタント メッセージング (IM) セッションのアーカイブ ポリシーに関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="8e9e6-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8e9e6-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8e9e6-125">インスタント メッセージング (IM) セッション アーカイブ ポリシーをユーザーまたはユーザーのセットに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="8e9e6-126">これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="8e9e6-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8e9e6-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8e9e6-128">新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="8e9e6-129">これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="8e9e6-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8e9e6-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8e9e6-131">指定したインスタント メッセージング (IM) アーカイブ ポリシーを削除します。このアーカイブ ポリシーは、Skype for Business Server が内部ユーザー間で行うすべての IM セッション、および内部ユーザーとフェデレーション パートナーとの間で行うすべての IM セッションを自動的に保存するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="8e9e6-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8e9e6-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8e9e6-133">既存のインスタント メッセージング (IM) アーカイブ ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="8e9e6-134">アーカイブ ポリシーを使用すると、内部ユーザー間で行うすべての IM セッションと会議をアーカイブできます。内部ユーザーとフェデレーション パートナーの間で行うセッションをアーカイブすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8e9e6-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

