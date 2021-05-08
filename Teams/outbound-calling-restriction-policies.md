---
title: 発信通話の制限 - PSTN 通話&電話会議
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
description: 管理者は、ユーザーが行える電話会議とエンド ユーザーの PSTN 通話の種類を制御できます。
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908656"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="9ffa2-103">電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="9ffa2-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="9ffa2-104">管理者は、発信通話の制御を使用して、組織内のユーザーが発信できる電話会議の種類とエンド ユーザーの PSTN 通話を制限できます。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="9ffa2-105">発信呼び出しコントロールは、ユーザーごとに適用できます。次の 2 つのコントロールを提供して、送信呼び出しの各種類を個別に制限します。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="9ffa2-106">既定では、両方のコントロールが、国際および国内の発信呼び出しを許可する設定になっています。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="9ffa2-107">コントロール</span><span class="sxs-lookup"><span data-stu-id="9ffa2-107">Control</span></span>|<span data-ttu-id="9ffa2-108">説明</span><span class="sxs-lookup"><span data-stu-id="9ffa2-108">Description</span></span>|<span data-ttu-id="9ffa2-109">コントロール オプション</span><span class="sxs-lookup"><span data-stu-id="9ffa2-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9ffa2-110">電話会議 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="9ffa2-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="9ffa2-111">送信の種類を制限します。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="9ffa2-112">内から許可されている呼び出し</span><span class="sxs-lookup"><span data-stu-id="9ffa2-112">calls that are allowed from within</span></span> </br><span data-ttu-id="9ffa2-113">ユーザーが開催した会議。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-113">meetings organized by a user.</span></span>|<span data-ttu-id="9ffa2-114">任意の宛先 (既定)</span><span class="sxs-lookup"><span data-stu-id="9ffa2-114">Any destination (default)</span></span></br><span data-ttu-id="9ffa2-115">開催者と同じ国または地域</span><span class="sxs-lookup"><span data-stu-id="9ffa2-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="9ffa2-116">[ゾーン A の国または地域のみ](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="9ffa2-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="9ffa2-117">許可しない</span><span class="sxs-lookup"><span data-stu-id="9ffa2-117">Don't allow</span></span>|
|<span data-ttu-id="9ffa2-118">エンド ユーザーの PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="9ffa2-118">End user PSTN calls</span></span>|<span data-ttu-id="9ffa2-119">呼び出しの種類を制限します。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-119">Restricts the type of calls</span></span> </br><span data-ttu-id="9ffa2-120">ユーザーが作成できます。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-120">that can be made by a user.</span></span>|<span data-ttu-id="9ffa2-121">国際および国内 (既定)</span><span class="sxs-lookup"><span data-stu-id="9ffa2-121">International and Domestic (default)</span></span></br><span data-ttu-id="9ffa2-122">国内</span><span class="sxs-lookup"><span data-stu-id="9ffa2-122">Domestic</span></span></br><span data-ttu-id="9ffa2-123">なし</span><span class="sxs-lookup"><span data-stu-id="9ffa2-123">None</span></span>|

<span data-ttu-id="9ffa2-124">ゾーン A と見なされる国と地域を確認するには、「電話会議の国と [地域のゾーン」を参照してください](audio-conferencing-zones.md)。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="9ffa2-125">ダイヤルされた番号が会議の開催者 (電話会議の場合) またはエンド ユーザー (エンド ユーザー PSTN 通話の場合) に設定されている Office 365 Microsoft 365国と同じ国にある場合、通話は国内と見なされます。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="9ffa2-126">電話会議の発信通話を制限する</span><span class="sxs-lookup"><span data-stu-id="9ffa2-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="9ffa2-127">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="9ffa2-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9ffa2-128">左側のナビゲーションで、[ユーザー] **をクリック** し、使用可能なユーザーの一覧からユーザーの表示名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-128">In the left navigation, click **Users**, and then click the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="9ffa2-129">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-129">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="9ffa2-130">[ **会議からのダイヤルアウト] で**、必要なダイヤルアウト制限オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="9ffa2-131">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-131">Click **Save**.</span></span> 

<span data-ttu-id="9ffa2-132">![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="9ffa2-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="9ffa2-133">[Skype for Business **管理** センター] の左側のナビゲーションで、[電話会議ユーザー ] に移動し、使用可能なユーザーの一覧からユーザー  >  を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9ffa2-134">操作ウィンドウで、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-134">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="9ffa2-135">[ **このユーザーの会議からの** ダイヤルアウトの制限] で、必要なダイヤルアウト制限オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![[ダイヤルアウトの制限] オプション](media/restrictions-to-dial-outs.png)
      

4. <span data-ttu-id="9ffa2-137">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-137">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="9ffa2-138">**PowerShell を使用する場合**</span><span class="sxs-lookup"><span data-stu-id="9ffa2-138">**Using PowerShell**</span></span>

<span data-ttu-id="9ffa2-139">発信呼び出し制限は、OnlineDialOutPolicy と呼ばれる 1 つのポリシーによって制御され、それぞれに制限属性があります。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="9ffa2-140">ポリシーをカスタマイズすることはできません。設定の組み合わせごとに事前に定義されたポリシー インスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="9ffa2-141">Get-CSOnlineDialOutPolicy コマンドレットを使用して、送信呼び出しポリシーを表示し、Grant-CSDialOutPolicy を使用してユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="9ffa2-142">(Get コマンドレットと同様に、Grant コマンドレットには "Online" という単語が含まれているので注意してください)。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-142">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="9ffa2-143">次の表は、各ポリシーの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-143">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9ffa2-144">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-144">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="9ffa2-145">会議のユーザーは、国際電話番号と国内番号にダイヤルアウトできます。また、このユーザーは、国際電話番号と国内番号への発信通話を行う場合にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-145">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="9ffa2-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="9ffa2-147">会議のユーザーは国内番号にのみダイヤルアウトできます。このユーザーは、国際番号と国内番号への発信通話を行います。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-147">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="9ffa2-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="9ffa2-149">会議のユーザーがダイヤルアウトすることはできません。このユーザーは、国際番号と国内番号への発信呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-149">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="9ffa2-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="9ffa2-151">会議のユーザーは国際番号と国内番号にダイヤルアウトできます。このユーザーは国内 PSTN 番号への発信通話のみを行います。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-151">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="9ffa2-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="9ffa2-153">会議のユーザーは国際番号と国内番号にダイヤルアウトできます。このユーザーは、緊急電話番号以外に PSTN 番号への発信通話を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-153">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="9ffa2-154">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-154">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="9ffa2-155">会議のユーザーは国内番号にのみダイヤルアウトできます。このユーザーは国内 PSTN 番号への発信通話のみを行います。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-155">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="9ffa2-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="9ffa2-157">会議のユーザーは国内番号にのみダイヤルアウトできます。このユーザーは、緊急電話番号以外に PSTN 番号への発信通話を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-157">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="9ffa2-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="9ffa2-159">会議のユーザーはダイヤルアウトできません。このユーザーは国内 PSTN 番号への発信通話のみを行います。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-159">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="9ffa2-160">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-160">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="9ffa2-161">会議のユーザーはダイヤルアウトできません。また、このユーザーは、緊急電話番号以外に PSTN 番号への発信通話を発信することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-161">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="9ffa2-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="9ffa2-163">会議のユーザーはゾーン [A](audio-conferencing-zones.md)の国と地域にのみダイヤルアウトできます。このユーザーは、国際番号と国内番号への発信通話を行います。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-163">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="9ffa2-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="9ffa2-165">会議のユーザーはゾーン [A](audio-conferencing-zones.md)の国と地域にのみダイヤルアウトできます。このユーザーは国内 PSTN 番号への発信通話のみを行います。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-165">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="9ffa2-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="9ffa2-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="9ffa2-167">会議のユーザーはゾーン [A](audio-conferencing-zones.md)の国と地域にのみダイヤルアウトできます。このユーザーは、緊急電話番号以外に PSTN 番号への発信通話を発信することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ffa2-167">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
