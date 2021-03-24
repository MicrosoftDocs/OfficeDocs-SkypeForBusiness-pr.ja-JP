---
title: Skype for Business Server で会議ポリシーを管理する
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: '概要: Skype for Business Server で会議ポリシーを管理する方法について説明します。'
ms.openlocfilehash: 39855aac09b88852d0931c9b8fbdb8e2e9187c71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099103"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="a078e-103">Skype for Business Server で会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="a078e-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="a078e-104">**概要:** Skype for Business Server で会議ポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a078e-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="a078e-105">このトピックでは、会議ポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a078e-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="a078e-106">会議を計画および展開する方法の詳細については [、「Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) での会議の計画」および「Skype for Business Server での会議の展開 [」を参照してください](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="a078e-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="a078e-107">会議ポリシーを使用すると、会議に IP オーディオとビデオを含めるかどうかから、出席できる最大人数まで、さまざまなスケジュールと参加オプションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a078e-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="a078e-108">会議ポリシーを使用して、会議のセキュリティ、帯域幅、法的側面を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a078e-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="a078e-109">会議ポリシーは、グローバル スコープ、サイト スコープ、およびユーザー スコープの 3 つのレベルで定義できます。</span><span class="sxs-lookup"><span data-stu-id="a078e-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="a078e-110">設定の対象になるのは、最も狭いスコープから最も広いスコープまでのどのスコープでも、特定のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a078e-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="a078e-111">ユーザーにポリシーを割り当てる場合、これらの設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="a078e-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="a078e-112">ユーザー ポリシーを割り当てていない場合は、サイト設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a078e-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="a078e-113">ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル ポリシーが既定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="a078e-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="a078e-p104">グローバル ポリシーは既定として存在するため、新しいグローバル ポリシーを作成することはできません。 また、既存のグローバル ポリシーを削除することはできませんが、既存のグローバル ポリシーを変更して既定の設定をカスタマイズすることはできます。</span><span class="sxs-lookup"><span data-stu-id="a078e-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a078e-116">Skype for Business Server コントロール パネルを使用して会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="a078e-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="a078e-117">Skype for Business Server コントロール パネルを使用して会議ポリシーを管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a078e-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="a078e-118">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a078e-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="a078e-119">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a078e-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a078e-120">左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a078e-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a078e-121">Skype for Business Server 管理シェルを使用して会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="a078e-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a078e-122">Skype for Business Server 管理シェルを使用して会議を管理するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a078e-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="a078e-123">**会議ポリシーの設定**</span><span class="sxs-lookup"><span data-stu-id="a078e-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="a078e-124">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="a078e-124">**Cmdlet**</span></span>|<span data-ttu-id="a078e-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="a078e-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a078e-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="a078e-126">Get-CsConferencingPolicy</span></span>](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="a078e-127">組織で使用するように構成されている会議ポリシーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="a078e-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="a078e-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="a078e-128">Grant-CsConferencingPolicy</span></span>](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="a078e-129">ユーザーごとのスコープで会議ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a078e-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="a078e-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="a078e-130">New-CsConferencingPolicy</span></span>](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="a078e-131">組織で使用する新しい会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a078e-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="a078e-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="a078e-132">Remove-CsConferencingPolicy</span></span>](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="a078e-133">指定した会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a078e-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="a078e-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="a078e-134">Set-CsConferencingPolicy</span></span>](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="a078e-135">既存の会議ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="a078e-135">Modifies an existing conferencing policy.</span></span>  <br/> |
