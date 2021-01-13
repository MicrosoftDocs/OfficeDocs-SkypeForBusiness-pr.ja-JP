---
title: Skype for Business Server で場所のポリシーを作成する
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
description: このトピックでは、Skype for Business Server エンタープライズ VoIP で拡張緊急サービス (E9-1-1) の場所ポリシーを構成する方法について説明します。
ms.openlocfilehash: 4230d6ac1a820cb9612d58b21a2e5b6ae36d8f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822547"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="3dd17-103">Skype for Business Server で場所のポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3dd17-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="3dd17-104">このトピックでは、Skype for Business Server エンタープライズ VoIP で拡張緊急サービス (E9-1-1) の場所ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3dd17-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="3dd17-105">Skype for Business Server は、場所ポリシーを使用して、クライアント登録時に E9-1-1 の Skype for Business クライアントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3dd17-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="3dd17-106">場所のポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3dd17-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="3dd17-107">詳細については [、「Skype for Business Server の場所ポリシーを計画する」を参照してください](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd17-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="3dd17-108">場所ポリシーは、Skype for Business コントロール パネルまたは [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) コマンドレットを使用して定義します。</span><span class="sxs-lookup"><span data-stu-id="3dd17-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="3dd17-109">Skype for Business Server では、クライアントの複数の緊急電話番号の構成がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3dd17-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="3dd17-110">複数の緊急電話番号を構成する場合は [、「Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) で複数の緊急電話番号を計画する」および「Skype for Business で複数の緊急電話番号を構成する」の情報に従う [必要があります](configure-multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd17-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="3dd17-p103">グローバルの場所のポリシーを編集して、マークされた新しい場所のポリシーを作成できます。場所のポリシーが関連付けられたサブネット内部に配置されていない場合や、場所のポリシーが直接割り当てられていない場合に、クライアントはグローバル ポリシーを取得します。マークされたポリシーは、サブネットまたはユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3dd17-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="3dd17-114">場所のポリシーを作成するには、作成するユーザーが RTCUniversalServerAdmins グループまたは CsVoiceAdministrator 管理者役割のメンバーか、あるいは同等の管理者権限とアクセス許可を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dd17-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="3dd17-115">詳細については [、「Skype for Business Server の場所ポリシーを計画する」を参照してください](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd17-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="3dd17-116">この手順のコマンドレットでは、次の値を使用して定義された場所ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dd17-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="3dd17-117">コマンドレットのパラメーターと値の詳細については [、「New-CsLocationPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3dd17-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="3dd17-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="3dd17-118">**Element**</span></span>                               | <span data-ttu-id="3dd17-119">**値**</span><span class="sxs-lookup"><span data-stu-id="3dd17-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3dd17-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="3dd17-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="3dd17-121">**True**</span><span class="sxs-lookup"><span data-stu-id="3dd17-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="3dd17-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="3dd17-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="3dd17-123">**免責事項**</span><span class="sxs-lookup"><span data-stu-id="3dd17-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="3dd17-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="3dd17-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="3dd17-p105">会社のポリシーで場所の設定が要求されています。場所を設定しない場合、緊急サービスが緊急時に発見できません。場所を設定してください。</span><span class="sxs-lookup"><span data-stu-id="3dd17-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
| <span data-ttu-id="3dd17-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="3dd17-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="3dd17-129">**False**</span><span class="sxs-lookup"><span data-stu-id="3dd17-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="3dd17-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="3dd17-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="3dd17-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="3dd17-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="3dd17-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="3dd17-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="3dd17-133">**911**</span><span class="sxs-lookup"><span data-stu-id="3dd17-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="3dd17-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="3dd17-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="3dd17-135">**112**</span><span class="sxs-lookup"><span data-stu-id="3dd17-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="3dd17-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="3dd17-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="3dd17-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="3dd17-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="3dd17-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="3dd17-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="3dd17-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="3dd17-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="3dd17-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="3dd17-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="3dd17-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="3dd17-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="3dd17-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="3dd17-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="3dd17-143">**2**</span><span class="sxs-lookup"><span data-stu-id="3dd17-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="3dd17-144">場所のポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="3dd17-144">To create location policies</span></span>

1. <span data-ttu-id="3dd17-145">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3dd17-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3dd17-146">**PstnUsage** の設定がグローバルの PstnUsages 一覧にあらかじめ存在していない場合、CsLocationPolicy は失敗します。</span><span class="sxs-lookup"><span data-stu-id="3dd17-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="3dd17-147">オプションで、次のコマンドレットを実行して、グローバルの場所のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="3dd17-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="3dd17-148">次のコマンドレットを実行してマークされた場所のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3dd17-148">Run the following to create a tagged Location Policy.</span></span>

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="3dd17-149">次のコマンドレットを実行して、ステップ 3 で作成したマークされた場所のポリシーをユーザー ポリシーに適用します。</span><span class="sxs-lookup"><span data-stu-id="3dd17-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
