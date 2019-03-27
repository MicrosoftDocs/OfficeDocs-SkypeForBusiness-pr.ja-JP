---
title: Skype でビジネスのサーバーの場所のポリシーを作成します。
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 構成する方法の詳細については、このトピックでは、Skype で緊急サービス (~ 9-1-1) の場所のポリシーを強化ビジネス サーバーのエンタープライズ VoIP を参照してください。
ms.openlocfilehash: 2e3c25586c09e8cb517f781ec9e9dc33c58d81da
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897985"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="a6fa3-103">Skype でビジネスのサーバーの場所のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="a6fa3-104">構成する方法の詳細については、このトピックでは、Skype で緊急サービス (~ 9-1-1) の場所のポリシーを強化ビジネス サーバーのエンタープライズ VoIP を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="a6fa3-105">ビジネス サーバーの Skype では、~ 9-1-1 のビジネスのクライアントのクライアントの登録中に Skype を有効にするのに場所のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="a6fa3-106">場所ポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="a6fa3-107">詳細については、 [Skype のビジネス サーバーの場所のポリシーの計画](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="a6fa3-108">ビジネス コントロール パネルの Skype を使用して、または[新規 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)コマンドレットを使用して、場所のポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a6fa3-109">Skype ビジネス サーバーがクライアントの複数の緊急番号の構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="a6fa3-110">複数の緊急番号を構成する場合は、 [Skype ビジネス サーバーの複数の緊急番号に計画](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)し、[ビジネスの Skype で複数の緊急番号の構成](configure-multiple-emergency-numbers.md)内の情報に従ってください。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="a6fa3-p103">グローバルの場所のポリシーを編集して、マークされた新しい場所のポリシーを作成できます。場所のポリシーが関連付けられたサブネット内部に配置されていない場合や、場所のポリシーが直接割り当てられていない場合に、クライアントはグローバル ポリシーを取得します。マークされたポリシーは、サブネットまたはユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="a6fa3-114">場所のポリシーを作成するには、作成するユーザーが RTCUniversalServerAdmins グループまたは CsVoiceAdministrator 管理者役割のメンバーか、あるいは同等の管理者権限とアクセス許可を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="a6fa3-115">詳細については、 [Skype のビジネス サーバーの場所のポリシーの計画](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="a6fa3-116">この手順での cmdlet は、次の値を使用して定義される場所のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="a6fa3-117">コマンドレットのパラメーターと値の詳細については、[新規 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="a6fa3-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="a6fa3-118">**Element**</span></span>                               | <span data-ttu-id="a6fa3-119">**値**</span><span class="sxs-lookup"><span data-stu-id="a6fa3-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a6fa3-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="a6fa3-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="a6fa3-121">**True**</span><span class="sxs-lookup"><span data-stu-id="a6fa3-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="a6fa3-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="a6fa3-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="a6fa3-123">**Disclaimer**</span><span class="sxs-lookup"><span data-stu-id="a6fa3-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="a6fa3-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="a6fa3-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="a6fa3-p105">会社のポリシーで場所の設定が要求されています。場所を設定しない場合、緊急サービスが緊急時に発見できません。場所を設定してください。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
| <span data-ttu-id="a6fa3-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="a6fa3-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="a6fa3-129">**False**</span><span class="sxs-lookup"><span data-stu-id="a6fa3-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="a6fa3-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="a6fa3-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="a6fa3-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="a6fa3-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="a6fa3-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="a6fa3-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="a6fa3-133">**911**</span><span class="sxs-lookup"><span data-stu-id="a6fa3-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="a6fa3-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="a6fa3-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="a6fa3-135">**112**</span><span class="sxs-lookup"><span data-stu-id="a6fa3-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="a6fa3-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="a6fa3-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="a6fa3-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="a6fa3-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="a6fa3-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="a6fa3-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="a6fa3-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="a6fa3-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="a6fa3-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="a6fa3-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="a6fa3-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="a6fa3-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="a6fa3-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="a6fa3-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="a6fa3-143">**2**</span><span class="sxs-lookup"><span data-stu-id="a6fa3-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="a6fa3-144">場所のポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="a6fa3-144">To create location policies</span></span>

1. <span data-ttu-id="a6fa3-145">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6fa3-146">**PstnUsage** の設定がグローバルの PstnUsages 一覧にあらかじめ存在していない場合、CsLocationPolicy は失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="a6fa3-147">オプションで、次のコマンドレットを実行して、グローバルの場所のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="a6fa3-148">次のコマンドレットを実行してマークされた場所のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-148">Run the following to create a tagged Location Policy.</span></span>

   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="a6fa3-149">次のコマンドレットを実行して、ステップ 3 で作成したマークされた場所のポリシーをユーザー ポリシーに適用します。</span><span class="sxs-lookup"><span data-stu-id="a6fa3-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
