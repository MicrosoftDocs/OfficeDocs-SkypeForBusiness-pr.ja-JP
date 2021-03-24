---
title: Skype for Business Server で場所ポリシーを作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Skype for Business Server エンタープライズ VoIP で拡張緊急サービス (E9-1-1) の場所ポリシーを構成する方法については、このトピックを参照エンタープライズ VoIP。
ms.openlocfilehash: cee02204a9c5b3708a83e9433f6a88c70230fd64
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093145"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="9876d-103">Skype for Business Server で場所ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="9876d-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="9876d-104">Skype for Business Server エンタープライズ VoIP で拡張緊急サービス (E9-1-1) の場所ポリシーを構成する方法については、このトピックを参照エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="9876d-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="9876d-105">Skype for Business Server は、場所ポリシーを使用して、クライアント登録中に Skype for Business クライアントを E9-1-1 で有効にします。</span><span class="sxs-lookup"><span data-stu-id="9876d-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="9876d-106">場所のポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9876d-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="9876d-107">詳細については [、「Plan location policis for Skype for Business Server」を参照してください](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9876d-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="9876d-108">場所ポリシーは、Skype for Business コントロール パネルを使用するか [、New-CsLocationPolicy コマンドレットを使用して定義](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) します。</span><span class="sxs-lookup"><span data-stu-id="9876d-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="9876d-109">Skype for Business Server では、クライアントの複数の緊急電話番号の構成がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9876d-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="9876d-110">複数の緊急電話番号を構成する場合は [、「Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) で複数の緊急電話番号を計画する」および「Skype for Business で複数の緊急電話番号を構成する」の情報に従う [必要があります](configure-multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="9876d-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="9876d-p103">グローバルの場所のポリシーを編集して、マークされた新しい場所のポリシーを作成できます。場所のポリシーが関連付けられたサブネット内部に配置されていない場合や、場所のポリシーが直接割り当てられていない場合に、クライアントはグローバル ポリシーを取得します。マークされたポリシーは、サブネットまたはユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9876d-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="9876d-114">場所のポリシーを作成するには、作成するユーザーが RTCUniversalServerAdmins グループまたは CsVoiceAdministrator 管理者役割のメンバーか、あるいは同等の管理者権限とアクセス許可を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="9876d-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="9876d-115">詳細については [、「Plan location policis for Skype for Business Server」を参照してください](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9876d-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="9876d-116">この手順のコマンドレットでは、次の値を使用して定義された場所ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9876d-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="9876d-117">コマンドレットのパラメーターと値の詳細については [、「New-CsLocationPolicy」を参照してください](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9876d-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="9876d-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="9876d-118">**Element**</span></span>                               | <span data-ttu-id="9876d-119">**値**</span><span class="sxs-lookup"><span data-stu-id="9876d-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9876d-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="9876d-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="9876d-121">**True**</span><span class="sxs-lookup"><span data-stu-id="9876d-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="9876d-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="9876d-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="9876d-123">**免責事項**</span><span class="sxs-lookup"><span data-stu-id="9876d-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="9876d-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="9876d-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="9876d-p105">会社のポリシーで場所の設定が要求されています。場所を設定しない場合、緊急サービスが緊急時に発見できません。場所を設定してください。</span><span class="sxs-lookup"><span data-stu-id="9876d-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
| <span data-ttu-id="9876d-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="9876d-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="9876d-129">**False**</span><span class="sxs-lookup"><span data-stu-id="9876d-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="9876d-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="9876d-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="9876d-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="9876d-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="9876d-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="9876d-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="9876d-133">**911**</span><span class="sxs-lookup"><span data-stu-id="9876d-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="9876d-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="9876d-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="9876d-135">**112**</span><span class="sxs-lookup"><span data-stu-id="9876d-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="9876d-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="9876d-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="9876d-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="9876d-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="9876d-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="9876d-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="9876d-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="9876d-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="9876d-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="9876d-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="9876d-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="9876d-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="9876d-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="9876d-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="9876d-143">**2**</span><span class="sxs-lookup"><span data-stu-id="9876d-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="9876d-144">場所のポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="9876d-144">To create location policies</span></span>

1. <span data-ttu-id="9876d-145">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9876d-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9876d-146">**PstnUsage** の設定がグローバルの PstnUsages 一覧にあらかじめ存在していない場合、CsLocationPolicy は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9876d-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="9876d-147">オプションで、次のコマンドレットを実行して、グローバルの場所のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="9876d-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="9876d-148">次のコマンドレットを実行してマークされた場所のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9876d-148">Run the following to create a tagged Location Policy.</span></span>

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="9876d-149">次のコマンドレットを実行して、ステップ 3 で作成したマークされた場所のポリシーをユーザー ポリシーに適用します。</span><span class="sxs-lookup"><span data-stu-id="9876d-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```