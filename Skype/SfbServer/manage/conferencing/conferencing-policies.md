---
title: Skype での会議のポリシーを管理するビジネス サーバー
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: '概要: ビジネス サーバーの Skype での会議ポリシーを管理する方法を説明します。'
ms.openlocfilehash: 96b2f5e27aa65931f5cd76499e1a3f66b817baa5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898145"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="31b9f-103">Skype での会議のポリシーを管理するビジネス サーバー</span><span class="sxs-lookup"><span data-stu-id="31b9f-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="31b9f-104">**の概要:** ビジネス サーバーの Skype での会議ポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31b9f-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="31b9f-105">このトピックでは、電話会議ポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31b9f-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="31b9f-106">予定し、会議を展開する方法の詳細については、[ビジネスのサーバー用の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)と[ビジネス サーバーの Skype で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b9f-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="31b9f-p102">電話会議ポリシーにより、会議に IP オーディオと IP ビデオを組み込むことができるかどうかから、出席可能な最大参加者数に至るまでの、さまざまなスケジューリングおよび参加オプションを定義できます。電話会議ポリシーを使用すると、セキュリティ、帯域幅、および会議の法的側面を管理できます。</span><span class="sxs-lookup"><span data-stu-id="31b9f-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="31b9f-109">電話会議ポリシーは、グローバル スコープ、サイト スコープ、およびユーザー スコープの 3 つのレベルで定義できます。</span><span class="sxs-lookup"><span data-stu-id="31b9f-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="31b9f-110">設定の対象になるのは、最も狭いスコープから最も広いスコープまでのどのスコープでも、特定のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="31b9f-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="31b9f-111">ポリシーをユーザーに割り当てると、それらの設定は優先権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="31b9f-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="31b9f-112">ユーザー ポリシーを割り当てていない場合は、サイト設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="31b9f-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="31b9f-113">ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル ポリシーが既定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="31b9f-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="31b9f-114">グローバル ポリシーは既定として存在するため、新しいグローバル ポリシーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="31b9f-114">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="31b9f-115">また、既存のグローバル ポリシーを削除することはできませんが、既存のグローバル ポリシーを変更して既定の設定をカスタマイズすることはできます。</span><span class="sxs-lookup"><span data-stu-id="31b9f-115">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="31b9f-116">ビジネス サーバーのコントロール パネルの Skype を使用して、会議のポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="31b9f-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="31b9f-117">会議ポリシーを管理するには、Skype を使用してビジネス サーバーのコントロール パネルの。</span><span class="sxs-lookup"><span data-stu-id="31b9f-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="31b9f-118">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="31b9f-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="31b9f-119">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="31b9f-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="31b9f-120">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31b9f-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="31b9f-121">Skype ビジネス サーバー管理シェルを使用して会議のポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="31b9f-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="31b9f-122">Skype ビジネス サーバー管理シェルを使用して会議を管理するためには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="31b9f-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="31b9f-123">**電話会議ポリシーの設定**</span><span class="sxs-lookup"><span data-stu-id="31b9f-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="31b9f-124">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="31b9f-124">**Cmdlet**</span></span>|<span data-ttu-id="31b9f-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="31b9f-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="31b9f-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="31b9f-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="31b9f-127">組織で使用するために構成されている電話会議ポリシーに関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="31b9f-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="31b9f-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="31b9f-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="31b9f-129">電話会議ポリシーをユーザーごとのスコープで割り当てます。</span><span class="sxs-lookup"><span data-stu-id="31b9f-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="31b9f-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="31b9f-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="31b9f-131">組織で使用するために新しい電話会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="31b9f-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="31b9f-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="31b9f-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="31b9f-133">指定の電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="31b9f-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="31b9f-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="31b9f-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="31b9f-135">既存の電話会議ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="31b9f-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

