---
title: Skype for Business Server でアーカイブポリシーを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: '概要: Skype for Business Server のアーカイブのユーザーポリシーを管理する方法について説明します。'
ms.openlocfilehash: f2dca47dd7fd3095b2865ff72516b6be84144352
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818889"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="ccae2-103">Skype for Business Server でアーカイブポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="ccae2-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="ccae2-104">**概要:** Skype for Business Server のアーカイブのユーザーポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="ccae2-105">アーカイブの展開時にアーカイブポリシーを最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="ccae2-106">アーカイブポリシーは、アーカイブするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="ccae2-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="ccae2-107">Internal communications</span></span>
    
- <span data-ttu-id="ccae2-108">外部通信</span><span class="sxs-lookup"><span data-stu-id="ccae2-108">External communications</span></span>
    
<span data-ttu-id="ccae2-109">アーカイブポリシーは、グローバル、サイト、またはユーザーのレベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ccae2-110">展開に対して Microsoft Exchange の統合を有効にしている場合、exchange のポリシーでは、Exchange を使用しているユーザーに対してアーカイブが有効になっているかどうかが制御されます。また、メールボックスはインプレースホールドに配置されています。</span><span class="sxs-lookup"><span data-stu-id="ccae2-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="ccae2-111">詳細については、「 [skype For Business server でのアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」および「 [Skype for business Server 用の Exchange storage との統合を構成する](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccae2-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="ccae2-112">コントロール パネルを使用してアーカイブ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="ccae2-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="ccae2-113">次のようにコントロール パネルを使用すると、アーカイブ ポリシーを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="ccae2-114">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ccae2-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="ccae2-115">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ccae2-116">左側のナビゲーション バーで [**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccae2-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="ccae2-117">Windows PowerShell を使用してアーカイブ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="ccae2-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="ccae2-118">次の表に示す Windows PowerShell コマンドレットを使用してアーカイブ ポリシーを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="ccae2-119">使用可能なすべてのパラメーターを含む構文の詳細については、「 [Skype For Business Server 管理シェル](../management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccae2-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="ccae2-120">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="ccae2-120">**Cmdlet**</span></span>|<span data-ttu-id="ccae2-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="ccae2-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ccae2-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="ccae2-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="ccae2-123">組織のインスタント メッセージング (IM) セッションのアーカイブ ポリシーに関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="ccae2-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="ccae2-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="ccae2-125">インスタント メッセージング (IM) セッションのアーカイブ ポリシーをユーザーまたはユーザー セットに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="ccae2-126">これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="ccae2-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="ccae2-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="ccae2-128">新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="ccae2-129">これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="ccae2-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="ccae2-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="ccae2-131">内部ユーザーとフェデレーションパートナー間のすべての im セッションが、Skype for Business Server によって自動的に保存されるかどうかを決定する、指定したインスタントメッセージング (IM) アーカイブポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="ccae2-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="ccae2-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="ccae2-133">既存のインスタントメッセージング (IM) アーカイブポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="ccae2-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="ccae2-134">アーカイブポリシーを使用すると、内部ユーザー間で行われるすべての IM セッションと会議をアーカイブすることができます。内部ユーザーとフェデレーションパートナーの間で行われるセッションをアーカイブすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ccae2-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

