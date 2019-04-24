---
title: 管理会議の Skype ビジネス サーバーの構成設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '概要: を管理する方法を学習する Skype ビジネス サーバーの構成設定に対応します。'
ms.openlocfilehash: 90d1004101f1dd3b4737c7bfa4414438a65c54a6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197977"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="855a4-103">管理会議の Skype ビジネス サーバーの構成設定</span><span class="sxs-lookup"><span data-stu-id="855a4-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="855a4-104">**の概要:** 管理する方法については Skype ビジネス サーバーの構成設定に対応します。</span><span class="sxs-lookup"><span data-stu-id="855a4-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="855a4-105">このトピックでは、会議の構成設定を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="855a4-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="855a4-106">予定し、会議を展開する方法の詳細については、[ビジネスのサーバー用の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)と[ビジネス サーバーの Skype で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="855a4-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="855a4-107">会議の構成設定では、ユーザーが作成できる会議の種類を指定でき、さらにこの会議への匿名ユーザーやダイヤルイン会議ユーザーの参加方法について (または、参加可能かどうかについても) 制御できます。</span><span class="sxs-lookup"><span data-stu-id="855a4-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="855a4-108">これらの設定のみに影響を与えるスケジュールされたミーティングです。ビジネス用の Skype で即時会議のオプション] をクリックして作成、臨時会議には影響しません。</span><span class="sxs-lookup"><span data-stu-id="855a4-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="855a4-109">会議の構成設定では、次の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="855a4-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="855a4-110">公衆交換電話網 (PSTN) からダイヤルインするユーザーをロビーに移動するかどうか</span><span class="sxs-lookup"><span data-stu-id="855a4-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="855a4-111">発表者の条件</span><span class="sxs-lookup"><span data-stu-id="855a4-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="855a4-112">会議の種類を既定で割り当てるかどうか</span><span class="sxs-lookup"><span data-stu-id="855a4-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="855a4-113">匿名 (認証されていない) ユーザーを既定で許可するかどうか</span><span class="sxs-lookup"><span data-stu-id="855a4-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="855a4-114">ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、会議の特性を定義できます。</span><span class="sxs-lookup"><span data-stu-id="855a4-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="855a4-115">指定できます (デフォルトで作成)、グローバル レベルの設定を達成するには、サイト レベルでは、または、プールのレベル。</span><span class="sxs-lookup"><span data-stu-id="855a4-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="855a4-116">既定では、グローバル設定が会議に関する操作性を定義します。</span><span class="sxs-lookup"><span data-stu-id="855a4-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="855a4-117">プール レベル設定を作成すると、その設定は、そのプールがホストするすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="855a4-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="855a4-118">プール レベル設定を作成しない場合は、サイト レベル設定が存在すればそれが適用されます。</span><span class="sxs-lookup"><span data-stu-id="855a4-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="855a4-119">サイト レベル設定を定義しない場合は、グローバル設定がすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="855a4-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="855a4-120">ビジネス サーバーのコントロール パネルの Skype を使用して、会議の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="855a4-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="855a4-121">ビジネス サーバーのコントロール パネルの Skype を使用して、会議の設定の管理。</span><span class="sxs-lookup"><span data-stu-id="855a4-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="855a4-122">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="855a4-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="855a4-123">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="855a4-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="855a4-124">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="855a4-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="855a4-125">ビジネス サーバー管理シェルの Skype を使用して、会議の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="855a4-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="855a4-126">Skype ビジネス サーバー管理シェルを使用して会議を管理するためには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="855a4-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="855a4-127">**会議の構成設定**</span><span class="sxs-lookup"><span data-stu-id="855a4-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="855a4-128">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="855a4-128">**Cmdlet**</span></span>|<span data-ttu-id="855a4-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="855a4-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="855a4-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="855a4-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="855a4-131">組織で現在使用されている会議の構成設定に関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="855a4-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="855a4-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="855a4-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="855a4-133">サイト スコープまたはサービス スコープで会議の構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="855a4-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="855a4-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="855a4-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="855a4-135">会議の構成設定の既存のコレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="855a4-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="855a4-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="855a4-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="855a4-137">組織で現在使用されている会議の構成設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="855a4-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

