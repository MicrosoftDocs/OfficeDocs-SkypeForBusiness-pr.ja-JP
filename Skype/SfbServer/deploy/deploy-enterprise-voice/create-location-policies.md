---
title: Skype for Business Server で場所のポリシーを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: このトピックでは、Skype for Business Server Enterprise Voice で拡張緊急対応サービス (E9) の場所のポリシーを構成する方法について説明します。
ms.openlocfilehash: e3e98394b660174eeb58b259de0121196934ad3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286377"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="d3156-103">Skype for Business Server で場所のポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d3156-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="d3156-104">このトピックでは、Skype for Business Server Enterprise Voice で拡張緊急対応サービス (E9) の場所のポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3156-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="d3156-105">Skype for Business Server は、位置情報ポリシーを使って、クライアントの登録中に E9-1 の Skype for Business クライアントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d3156-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="d3156-106">場所ポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3156-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="d3156-107">詳細については、「 [Skype For Business Server の場所のポリシーを計画](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3156-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="d3156-108">場所のポリシーを定義するには、Skype for Business コントロールパネルを使用するか、または[新しい-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3156-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d3156-109">Skype for Business Server で、クライアントの複数の緊急電話番号の構成がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d3156-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="d3156-110">複数の緊急電話番号を構成する場合は、Skype for business [Server の複数の緊急電話番号に](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)ついて、計画の情報に従って、 [skype for business で複数の緊急電話番号を設定](configure-multiple-emergency-numbers.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3156-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="d3156-p103">グローバルの場所のポリシーを編集して、マークされた新しい場所のポリシーを作成できます。場所のポリシーが関連付けられたサブネット内部に配置されていない場合や、場所のポリシーが直接割り当てられていない場合に、クライアントはグローバル ポリシーを取得します。マークされたポリシーは、サブネットまたはユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d3156-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="d3156-114">場所のポリシーを作成するには、作成するユーザーが RTCUniversalServerAdmins グループまたは CsVoiceAdministrator 管理者役割のメンバーか、あるいは同等の管理者権限とアクセス許可を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3156-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="d3156-115">詳細については、「 [Skype For Business Server の場所のポリシーを計画](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3156-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="d3156-116">この手順での cmdlet は、次の値を使用して定義される場所のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3156-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="d3156-117">コマンドレットのパラメーターと値の詳細については、「[新しい-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3156-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="d3156-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="d3156-118">**Element**</span></span>                               | <span data-ttu-id="d3156-119">**値**</span><span class="sxs-lookup"><span data-stu-id="d3156-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d3156-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="d3156-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="d3156-121">**True**</span><span class="sxs-lookup"><span data-stu-id="d3156-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="d3156-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="d3156-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="d3156-123">**Disclaimer**</span><span class="sxs-lookup"><span data-stu-id="d3156-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="d3156-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="d3156-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="d3156-p105">会社のポリシーで場所の設定が要求されています。場所を設定しない場合、緊急サービスが緊急時に発見できません。場所を設定してください。</span><span class="sxs-lookup"><span data-stu-id="d3156-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
| <span data-ttu-id="d3156-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="d3156-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="d3156-129">**False**</span><span class="sxs-lookup"><span data-stu-id="d3156-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="d3156-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="d3156-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="d3156-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="d3156-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="d3156-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="d3156-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="d3156-133">**911**</span><span class="sxs-lookup"><span data-stu-id="d3156-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="d3156-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="d3156-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="d3156-135">**112**</span><span class="sxs-lookup"><span data-stu-id="d3156-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="d3156-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="d3156-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="d3156-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="d3156-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="d3156-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="d3156-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="d3156-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="d3156-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="d3156-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="d3156-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="d3156-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="d3156-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="d3156-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="d3156-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="d3156-143">**2**</span><span class="sxs-lookup"><span data-stu-id="d3156-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="d3156-144">場所のポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="d3156-144">To create location policies</span></span>

1. <span data-ttu-id="d3156-145">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3156-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d3156-146">**PstnUsage** の設定がグローバルの PstnUsages 一覧にあらかじめ存在していない場合、CsLocationPolicy は失敗します。</span><span class="sxs-lookup"><span data-stu-id="d3156-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="d3156-147">オプションで、次のコマンドレットを実行して、グローバルの場所のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="d3156-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="d3156-148">次のコマンドレットを実行してマークされた場所のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3156-148">Run the following to create a tagged Location Policy.</span></span>

   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="d3156-149">次のコマンドレットを実行して、ステップ 3 で作成したマークされた場所のポリシーをユーザー ポリシーに適用します。</span><span class="sxs-lookup"><span data-stu-id="d3156-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
