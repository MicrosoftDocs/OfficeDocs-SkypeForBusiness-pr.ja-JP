---
title: Skype for Business Server 2015 での電話会議ポリシーの管理
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: '概要: ビジネス サーバー 2015 の Skype での会議ポリシーを管理する方法を説明します。'
ms.openlocfilehash: 48ae623a9571b848ccb70b377416343eccca0c1c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="14f33-103">Skype for Business Server 2015 での電話会議ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="14f33-103">Manage conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="14f33-104">**の概要:**ビジネス サーバー 2015 の Skype での会議ポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14f33-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="14f33-105">このトピックでは、電話会議ポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14f33-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="14f33-106">予定し、会議を展開する方法の詳細については、[ビジネス サーバー 2015 の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)および[ビジネス サーバー 2015 の Skype での展開の会議](../../deploy/deploy-conferencing/deploy-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14f33-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="14f33-p102">電話会議ポリシーにより、会議に IP オーディオと IP ビデオを組み込むことができるかどうかから、出席可能な最大参加者数に至るまでの、さまざまなスケジューリングおよび参加オプションを定義できます。電話会議ポリシーを使用すると、セキュリティ、帯域幅、および会議の法的側面を管理できます。</span><span class="sxs-lookup"><span data-stu-id="14f33-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="14f33-109">電話会議ポリシーは、グローバル スコープ、サイト スコープ、およびユーザー スコープの 3 つのレベルで定義できます。</span><span class="sxs-lookup"><span data-stu-id="14f33-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="14f33-110">設定の対象になるのは、最も狭いスコープから最も広いスコープまでのどのスコープでも、特定のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="14f33-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="14f33-111">ポリシーをユーザーに割り当てると、それらの設定は優先権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="14f33-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="14f33-112">ユーザー ポリシーを割り当てていない場合は、サイト設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="14f33-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="14f33-113">ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル ポリシーが既定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="14f33-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="14f33-114">グローバル ポリシーは既定として存在するため、新しいグローバル ポリシーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="14f33-114">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="14f33-115">また、既存のグローバル ポリシーを削除することはできませんが、既存のグローバル ポリシーを変更して既定の設定をカスタマイズすることはできます。</span><span class="sxs-lookup"><span data-stu-id="14f33-115">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="14f33-116">ビジネス サーバーのコントロール パネルの Skype を使用して、会議のポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="14f33-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="14f33-117">会議ポリシーを管理するには、Skype を使用してビジネス サーバーのコントロール パネルの。</span><span class="sxs-lookup"><span data-stu-id="14f33-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="14f33-118">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="14f33-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="14f33-119">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="14f33-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="14f33-120">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14f33-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="14f33-121">Skype ビジネス サーバー管理シェルを使用して会議のポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="14f33-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="14f33-122">Skype ビジネス サーバー管理シェルを使用して会議を管理するためには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="14f33-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="14f33-123">**会議ポリシーの設定**</span><span class="sxs-lookup"><span data-stu-id="14f33-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="14f33-124">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="14f33-124">**Cmdlet**</span></span>|<span data-ttu-id="14f33-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="14f33-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="14f33-126">Get CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="14f33-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="14f33-127">組織で使用するために構成されている電話会議ポリシーに関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="14f33-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="14f33-128">許可 CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="14f33-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="14f33-129">電話会議ポリシーをユーザーごとのスコープで割り当てます。</span><span class="sxs-lookup"><span data-stu-id="14f33-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="14f33-130">CsConferencingPolicy で新しい</span><span class="sxs-lookup"><span data-stu-id="14f33-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="14f33-131">組織で使用するために新しい電話会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="14f33-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="14f33-132">削除 CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="14f33-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="14f33-133">指定の電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="14f33-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="14f33-134">セット CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="14f33-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="14f33-135">既存の電話会議ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="14f33-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

