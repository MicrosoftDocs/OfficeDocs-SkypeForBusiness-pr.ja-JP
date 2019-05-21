---
title: Skype for Business Server で会議の構成設定を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '概要: Skype for Business Server で会議の構成設定を管理する方法について説明します。'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283740"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="68373-103">Skype for Business Server で会議の構成設定を管理する</span><span class="sxs-lookup"><span data-stu-id="68373-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="68373-104">**概要:** Skype for Business Server で会議の構成設定を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68373-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="68373-105">このトピックでは、会議の構成設定を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68373-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="68373-106">会議の計画と展開の詳細については、「Skype for business [server で会議の計画を立てる](../../plan-your-deployment/conferencing/conferencing.md)」および「 [Skype for business server で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68373-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="68373-107">会議の構成設定では、ユーザーが作成できる会議の種類を指定でき、さらにこの会議への匿名ユーザーやダイヤルイン会議ユーザーの参加方法について (または、参加可能かどうかについても) 制御できます。</span><span class="sxs-lookup"><span data-stu-id="68373-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="68373-108">これらの設定は、スケジュールされた会議にのみ影響します。Skype for Business の [今すぐ会議] オプションをクリックして作成されたアドホック会議には影響ありません。</span><span class="sxs-lookup"><span data-stu-id="68373-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="68373-109">会議の構成設定では、次の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="68373-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="68373-110">公衆交換電話網 (PSTN) からダイヤルインするユーザーをロビーに移動するかどうか</span><span class="sxs-lookup"><span data-stu-id="68373-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="68373-111">発表者の条件</span><span class="sxs-lookup"><span data-stu-id="68373-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="68373-112">会議の種類を既定で割り当てるかどうか</span><span class="sxs-lookup"><span data-stu-id="68373-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="68373-113">匿名 (認証されていない) ユーザーを既定で許可するかどうか</span><span class="sxs-lookup"><span data-stu-id="68373-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="68373-114">会議の特性は、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して定義できます。</span><span class="sxs-lookup"><span data-stu-id="68373-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="68373-115">会議の設定は、グローバルレベル (既定で作成)、サイトレベル、またはプールレベルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="68373-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="68373-116">既定では、グローバル設定が会議に関する操作性を定義します。</span><span class="sxs-lookup"><span data-stu-id="68373-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="68373-117">プール レベル設定を作成すると、その設定は、そのプールがホストするすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="68373-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="68373-118">プール レベル設定を作成しない場合は、サイト レベル設定が存在すればそれが適用されます。</span><span class="sxs-lookup"><span data-stu-id="68373-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="68373-119">サイト レベル設定を定義しない場合は、グローバル設定がすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="68373-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="68373-120">Skype for Business Server コントロールパネルを使用して会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="68373-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="68373-121">Skype for Business Server コントロールパネルを使用して会議の設定を管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="68373-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="68373-122">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="68373-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="68373-123">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="68373-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="68373-124">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68373-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="68373-125">Skype for Business Server 管理シェルを使用して会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="68373-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="68373-126">Skype for Business Server 管理シェルを使用して会議を管理するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="68373-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="68373-127">**会議の構成設定**</span><span class="sxs-lookup"><span data-stu-id="68373-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="68373-128">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="68373-128">**Cmdlet**</span></span>|<span data-ttu-id="68373-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="68373-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="68373-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="68373-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="68373-131">組織で現在使用されている会議の構成設定に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="68373-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="68373-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="68373-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="68373-133">サイト スコープまたはサービス スコープで会議の構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="68373-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="68373-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="68373-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="68373-135">会議の構成設定の既存のコレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="68373-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="68373-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="68373-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="68373-137">組織で現在使用されている会議の構成設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="68373-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

