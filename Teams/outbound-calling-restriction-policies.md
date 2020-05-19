---
title: 発信通話制限-電話会議 & PSTN 通話
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 管理者は、ユーザーが発信できる電話会議とエンドユーザーの PSTN 通話の種類を制御できます。
ms.openlocfilehash: 84acbed4017a709b63e657f12ef0bbe3c1eb620c
ms.sourcegitcommit: 5a88788bd0a0b2ccbc5b977b38dcfe4681cd5d10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2020
ms.locfileid: "44278180"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="712ac-103">電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="712ac-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="712ac-104">管理者は、発信通話の制御を使用して、組織内のユーザーが発信できる電話会議の種類とエンド ユーザーの PSTN 通話を制限できます。</span><span class="sxs-lookup"><span data-stu-id="712ac-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="712ac-105">発信通話コントロールは、ユーザー単位で適用できます。また、次の2つのコントロールを使用して、各送信通話の種類を個別に制限することができます。</span><span class="sxs-lookup"><span data-stu-id="712ac-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="712ac-106">既定では、両方のコントロールが国際通話と国内送信通話を許可するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="712ac-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="712ac-107">リモコン</span><span class="sxs-lookup"><span data-stu-id="712ac-107">Control</span></span>|<span data-ttu-id="712ac-108">説明</span><span class="sxs-lookup"><span data-stu-id="712ac-108">Description</span></span>|<span data-ttu-id="712ac-109">コントロールオプション</span><span class="sxs-lookup"><span data-stu-id="712ac-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="712ac-110">電話会議の PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="712ac-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="712ac-111">送信の種類を制限します</span><span class="sxs-lookup"><span data-stu-id="712ac-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="712ac-112">で許可されている通話</span><span class="sxs-lookup"><span data-stu-id="712ac-112">calls that are allowed from within</span></span> </br><span data-ttu-id="712ac-113">ユーザーによって開催された会議。</span><span class="sxs-lookup"><span data-stu-id="712ac-113">meetings organized by a user.</span></span>|<span data-ttu-id="712ac-114">任意の場所 (既定)</span><span class="sxs-lookup"><span data-stu-id="712ac-114">Any destination (default)</span></span></br><span data-ttu-id="712ac-115">組織の所在国または地域で、</span><span class="sxs-lookup"><span data-stu-id="712ac-115">In the same country or region as the organizor</span></span> </br> </br><span data-ttu-id="712ac-116">国または地域のみをゾーンにする</span><span class="sxs-lookup"><span data-stu-id="712ac-116">Zone A countries or regions only</span></span> </br><span data-ttu-id="712ac-117">許可しない</span><span class="sxs-lookup"><span data-stu-id="712ac-117">Don't allow</span></span>|
|<span data-ttu-id="712ac-118">エンドユーザーによる PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="712ac-118">End user PSTN calls</span></span>|<span data-ttu-id="712ac-119">通話の種類を制限する</span><span class="sxs-lookup"><span data-stu-id="712ac-119">Restricts the type of calls</span></span> </br><span data-ttu-id="712ac-120">これはユーザーが行うことができます。</span><span class="sxs-lookup"><span data-stu-id="712ac-120">that can be made by a user.</span></span>|<span data-ttu-id="712ac-121">国際および国内 (既定)</span><span class="sxs-lookup"><span data-stu-id="712ac-121">International and Domestic (default)</span></span></br><span data-ttu-id="712ac-122">市外</span><span class="sxs-lookup"><span data-stu-id="712ac-122">Domestic</span></span></br><span data-ttu-id="712ac-123">なし</span><span class="sxs-lookup"><span data-stu-id="712ac-123">None</span></span>|

<span data-ttu-id="712ac-124">ゾーン A と見なされる国/地域を確認するには、「[国/地域のゾーンを](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365)指定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="712ac-124">To find out which countries/regions are considered Zone A, see [Zone A countries/regions](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span></span>

   > [!NOTE]
   > <span data-ttu-id="712ac-125">発信先の番号が、会議の開催者 (電話会議の場合) またはエンドユーザー (エンドユーザーの PSTN 通話の場合) で Office 365 が設定されている同じ国/地域にある場合は、国内と見なされます。</span><span class="sxs-lookup"><span data-stu-id="712ac-125">A call is considered domestic if the number dialed is in the same country/region where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="712ac-126">電話会議の発信通話を制限する</span><span class="sxs-lookup"><span data-stu-id="712ac-126">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="712ac-127">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="712ac-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="712ac-128">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="712ac-128">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="712ac-129">ページの上部にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="712ac-129">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="712ac-130">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="712ac-130">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="712ac-131">[**会議からのダイヤルアウトアクセス許可**] で、目的のダイヤルアウト制限オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="712ac-131">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="712ac-132">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="712ac-132">Click **Save**.</span></span> 

<span data-ttu-id="712ac-133">![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="712ac-133">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.    <span data-ttu-id="712ac-134">**Skype for business 管理センター**の左のナビゲーションで、[**電話会議**  >  **ユーザー**] に移動し、利用可能なユーザーのリストからユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="712ac-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.    <span data-ttu-id="712ac-135">操作ウィンドウで、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="712ac-135">In the Action pane, click **Edit**.</span></span>

3.    <span data-ttu-id="712ac-136">[**このユーザーの会議からのダイヤル**アウトの制限] で、目的のダイヤルアウト制限オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="712ac-136">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![ダイヤルアウトオプションの制限](media/restrictions-to-dial-outs.png)

5. <span data-ttu-id="712ac-138">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="712ac-138">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="712ac-139">**PowerShell を使用する場合**</span><span class="sxs-lookup"><span data-stu-id="712ac-139">**Using PowerShell**</span></span>

<span data-ttu-id="712ac-140">発信通話の制限は、それぞれの制限属性を持つ OnlineDialOutPolicy という1つのポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="712ac-140">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="712ac-141">ポリシーをカスタマイズすることはできません。設定の各組み合わせに対して事前に定義されたポリシーインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="712ac-141">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="712ac-142">Get-Csonlinaloutpolicy コマンドレットを使用して、発信通話ポリシーを表示し、アクセス許可を付与してユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="712ac-142">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="712ac-143">(Grant コマンドレットには、Get コマンドレットの場合、"Online" という単語が含まれていないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="712ac-143">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="712ac-144">次の表は、各ポリシーの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="712ac-144">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="712ac-145">Identity = ' tag: DialoutCPCandPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="712ac-145">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="712ac-146">電話会議に参加しているユーザーは、国際電話や国内の番号にダイヤルアウトすることができます。このユーザーは、国際電話と国内の番号に発信することもできます。</span><span class="sxs-lookup"><span data-stu-id="712ac-146">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="712ac-147">Identity = ' tag: DialoutCPCDomesticPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="712ac-147">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="712ac-148">電話会議のユーザーは国内電話番号へのダイヤルアウトのみを行うことができ、このユーザーは国際電話番号と国内電話番号への発信通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="712ac-148">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="712ac-149">Identity = ' tag: DialoutCPCDisabledPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="712ac-149">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="712ac-150">会議に参加しているユーザーは、ダイヤルアウトを行うことができません。このユーザーは、国際電話番号と国内電話番号への発信通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="712ac-150">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="712ac-151">Identity = ' tag: DialoutCPCInternationalPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="712ac-151">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="712ac-152">電話会議に参加しているユーザーは、国際電話番号にダイヤルアウトすることができ、このユーザーは国内の PSTN 番号に対してのみ発信通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="712ac-152">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="712ac-153">Identity = ' tag: DialoutCPCInternationalPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="712ac-153">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="712ac-154">電話会議に参加しているユーザーは、国際電話番号や国内電話にダイヤルアウトすることができます。このユーザーは、緊急電話番号以外の PSTN 番号への発信通話を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="712ac-154">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="712ac-155">Identity = ' tag: DialoutCPCandPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="712ac-155">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="712ac-156">電話会議のユーザーは国内の電話番号にのみダイヤルアウトできます。このユーザーは国内の PSTN 番号に対してのみ発信通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="712ac-156">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="712ac-157">Identity = ' tag: DialoutCPCDomesticPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="712ac-157">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="712ac-158">電話会議に参加しているユーザーは、国内電話番号へのダイヤルアウトのみを行うことができます。このユーザーは、緊急電話番号以外の PSTN 番号への発信通話を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="712ac-158">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="712ac-159">Identity = ' tag: DialoutCPCDisabledPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="712ac-159">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="712ac-160">電話会議のユーザーはダイヤルアウトを行うことができず、このユーザーは国内の PSTN 番号に対してのみ発信通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="712ac-160">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="712ac-161">Identity = ' tag: DialoutCPCandPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="712ac-161">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="712ac-162">電話会議のユーザーはダイヤルアウトを行うことができません。このユーザーは、緊急電話番号以外の PSTN 番号への発信通話を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="712ac-162">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="712ac-163">Identity = ' tag: ' の場合、'</span><span class="sxs-lookup"><span data-stu-id="712ac-163">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="712ac-164">電話会議のユーザーは、国と地域のみを対象としたダイヤルアウトを行うことができます。このユーザーは、国際および国内の電話番号に発信することができます。</span><span class="sxs-lookup"><span data-stu-id="712ac-164">User in the conference can only dial out to Zone A countries and regions, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="712ac-165">Identity = ' tag: ' の場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="712ac-165">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="712ac-166">電話会議のユーザーは、国と地域のみを対象としたダイヤルアウトを行うことができます。このユーザーは、国内の PSTN 番号に対してのみ発信通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="712ac-166">User in the conference can only dial out to Zone A countries and regions, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="712ac-167">Identity = ' tag: ' の場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="712ac-167">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="712ac-168">電話会議のユーザーは、国と地域のみを対象としたダイヤルアウトを行うことができます。このユーザーは、緊急電話番号以外の PSTN 番号への発信通話を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="712ac-168">User in the conference can only dial out to Zone A countries and regions, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
