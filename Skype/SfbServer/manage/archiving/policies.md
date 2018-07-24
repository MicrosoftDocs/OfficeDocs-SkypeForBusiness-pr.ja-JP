---
title: ビジネス サーバーの Skype でのアーカイブ ・ ポリシーを管理します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: '概要: は、Skype のビジネス サーバーのアーカイブのユーザー ポリシーを管理する方法を説明します。'
ms.openlocfilehash: d29d30c99320631279114d3ebdfa8ee7db00b677
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21013322"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="d75b8-103">ビジネス サーバーの Skype でのアーカイブ ・ ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="d75b8-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="d75b8-104">**の概要:** Skype ビジネス サーバーのアーカイブのユーザー ポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d75b8-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="d75b8-105">最初に、アーカイブを展開するが、変更、追加、および展開後の構成を削除すると、アーカイブ ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="d75b8-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="d75b8-106">アーカイブ ・ ポリシーは、アーカイブするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d75b8-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="d75b8-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="d75b8-107">Internal communications</span></span>
    
- <span data-ttu-id="d75b8-108">外部通信</span><span class="sxs-lookup"><span data-stu-id="d75b8-108">External communications</span></span>
    
<span data-ttu-id="d75b8-109">グローバル設定、サイト、またはユーザー レベル、アーカイブ ポリシーにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d75b8-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d75b8-110">場合は有効にする Microsoft Exchange の統合、展開、Exchange ポリシーの管理に Exchange のホーム サーバーはユーザーのアーカイブが有効になっているし、インプレース保持に自分のメールボックスを配置するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d75b8-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="d75b8-111">詳細については、 [Skype のビジネス サーバーでアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)と[構成との統合 Skype ビジネス サーバー用の Exchange の記憶域](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d75b8-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="d75b8-112">コントロール パネルを使用してアーカイブ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d75b8-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="d75b8-113">次のようにコントロール パネルを使用すると、アーカイブ ポリシーを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="d75b8-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="d75b8-114">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d75b8-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="d75b8-115">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d75b8-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d75b8-116">左側のナビゲーション バーで [**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d75b8-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="d75b8-117">Windows PowerShell を使用してアーカイブ ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d75b8-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="d75b8-118">次の表に示す Windows PowerShell コマンドレットを使用してアーカイブ ポリシーを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d75b8-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="d75b8-119">含むすべての利用可能なパラメーターの構文の詳細については、[ビジネス サーバー管理シェルの Skype](../management-shell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d75b8-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="d75b8-120">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="d75b8-120">**Cmdlet**</span></span>|<span data-ttu-id="d75b8-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="d75b8-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d75b8-122">Get CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d75b8-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d75b8-123">組織のインスタント メッセージング (IM) セッションのアーカイブ ポリシーに関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="d75b8-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="d75b8-124">許可 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d75b8-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d75b8-125">インスタント メッセージング (IM) セッションのアーカイブ ポリシーをユーザーまたはユーザー セットに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d75b8-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="d75b8-126">これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d75b8-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="d75b8-127">新しい-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d75b8-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d75b8-128">新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d75b8-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="d75b8-129">これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="d75b8-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="d75b8-130">削除 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d75b8-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d75b8-131">指定したインスタント メッセージング (IM) アーカイブ ビジネス サーバーの Skype の内部ユーザー、および内部ユーザーとフェデレーション パートナーとの間のすべての IM セッションの間で行われるすべての IM セッションが自動的に保存するかどうかを決定するポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d75b8-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="d75b8-132">セット CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d75b8-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d75b8-133">既存インスタント メッセージング (IM) アーカイブ ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="d75b8-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="d75b8-134">アーカイブ ポリシーは、すべての IM セッションおよび内部ユーザー間で行われる会議をアーカイブする機能を提供します。内部ユーザーとフェデレーション パートナーの間で行われるセッションをアーカイブすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d75b8-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

