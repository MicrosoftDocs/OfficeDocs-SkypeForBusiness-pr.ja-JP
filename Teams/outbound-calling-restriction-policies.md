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
description: 管理者は、ユーザーが行える電話会議とエンドユーザー PSTN 通話の種類を制御できます。
ms.openlocfilehash: 86622b493fbb8d31f98f600acb7158afc82e15e5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526730"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="0b5df-103">電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="0b5df-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="0b5df-104">管理者は、発信通話コントロールを使用して、組織内のユーザーが行える電話会議とエンドユーザーの公衆交換電話網 (PSTN) 通話の種類を制限できます。</span><span class="sxs-lookup"><span data-stu-id="0b5df-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end-user Public Switched Telephone Network (PSTN) calls that can be made by users in your organization.</span></span>

<span data-ttu-id="0b5df-105">発信呼び出しコントロールは、ユーザー単位またはテナント単位で適用できます。次の 2 つのコントロールを提供して、各種類の送信呼び出しを個別に制限します。</span><span class="sxs-lookup"><span data-stu-id="0b5df-105">Outbound call controls can be applied on a per-user basis or on a tenant basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="0b5df-106">既定では、両方のコントロールが、国際および国内の発信呼び出しを許可する設定になっています。</span><span class="sxs-lookup"><span data-stu-id="0b5df-106">By default, both controls are set to allow international and domestic outbound calls.</span></span>

|<span data-ttu-id="0b5df-107">コントロール</span><span class="sxs-lookup"><span data-stu-id="0b5df-107">Control</span></span>|<span data-ttu-id="0b5df-108">説明</span><span class="sxs-lookup"><span data-stu-id="0b5df-108">Description</span></span>|<span data-ttu-id="0b5df-109">コントロール オプション</span><span class="sxs-lookup"><span data-stu-id="0b5df-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0b5df-110">電話会議 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="0b5df-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="0b5df-111">送信の種類を制限します。</span><span class="sxs-lookup"><span data-stu-id="0b5df-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="0b5df-112">内から許可されている呼び出し</span><span class="sxs-lookup"><span data-stu-id="0b5df-112">calls that are allowed from within</span></span> </br><span data-ttu-id="0b5df-113">ユーザーが開催した会議。</span><span class="sxs-lookup"><span data-stu-id="0b5df-113">meetings organized by a user.</span></span>|<span data-ttu-id="0b5df-114">任意の宛先 (既定)</span><span class="sxs-lookup"><span data-stu-id="0b5df-114">Any destination (default)</span></span></br><span data-ttu-id="0b5df-115">開催者と同じ国または地域</span><span class="sxs-lookup"><span data-stu-id="0b5df-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="0b5df-116">[ゾーン A の国または地域のみ](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="0b5df-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="0b5df-117">許可しない</span><span class="sxs-lookup"><span data-stu-id="0b5df-117">Don't allow</span></span>|
|<span data-ttu-id="0b5df-118">エンドユーザーの PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="0b5df-118">End-user PSTN calls</span></span>|<span data-ttu-id="0b5df-119">呼び出しの種類を制限します。</span><span class="sxs-lookup"><span data-stu-id="0b5df-119">Restricts the type of calls</span></span> </br><span data-ttu-id="0b5df-120">ユーザーが作成できます。</span><span class="sxs-lookup"><span data-stu-id="0b5df-120">that can be made by a user.</span></span>|<span data-ttu-id="0b5df-121">国際および国内 (既定)</span><span class="sxs-lookup"><span data-stu-id="0b5df-121">International and Domestic (default)</span></span></br><span data-ttu-id="0b5df-122">国内</span><span class="sxs-lookup"><span data-stu-id="0b5df-122">Domestic</span></span></br><span data-ttu-id="0b5df-123">なし</span><span class="sxs-lookup"><span data-stu-id="0b5df-123">None</span></span>|

<span data-ttu-id="0b5df-124">ゾーン A と見なされる国と地域を確認するには、「電話会議の国と [地域のゾーン」を参照してください](audio-conferencing-zones.md)。</span><span class="sxs-lookup"><span data-stu-id="0b5df-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="0b5df-125">ダイヤルされた番号が会議の開催者 (電話会議の場合) またはエンド ユーザー (エンド ユーザー PSTN 通話の場合) に設定されている Office 365 Microsoft 365国と同じ国にある場合、通話は国内と見なされます。</span><span class="sxs-lookup"><span data-stu-id="0b5df-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="0b5df-126">電話会議の発信通話を制限する</span><span class="sxs-lookup"><span data-stu-id="0b5df-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="0b5df-127">![[Microsoft Teams 管理 ](media/teams-logo-30x30.png) **センターを使用Microsoft Teamsロゴ**</span><span class="sxs-lookup"><span data-stu-id="0b5df-127">![the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0b5df-128">左側のナビゲーションで [ユーザー] **を選択** し、使用可能なユーザーの一覧からユーザーの表示名を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5df-128">In the left navigation, select **Users**, and then select the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="0b5df-129">[電話会議 **] の横にある [** 編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0b5df-129">Next to **Audio Conferencing**, select **Edit**.</span></span>

4. <span data-ttu-id="0b5df-130">[ **会議からのダイヤルアウト] で**、必要なダイヤルアウト制限オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5df-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="0b5df-131">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5df-131">Select **Save**.</span></span>

<span data-ttu-id="0b5df-132">![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="0b5df-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="0b5df-133">[Skype for Business **管理** センター] の左側のナビゲーションで、[電話会議ユーザー ] に移動し、使用可能なユーザーの一覧からユーザー  >  を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5df-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0b5df-134">[操作] ウィンドウで、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0b5df-134">In the Action pane, select **Edit**.</span></span>

3.  <span data-ttu-id="0b5df-135">[ **このユーザーの会議からの** ダイヤルアウトの制限] で、必要なダイヤルアウト制限オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5df-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![[ダイヤルアウトの制限] オプション](media/restrictions-to-dial-outs.png)

4. <span data-ttu-id="0b5df-137">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b5df-137">Select **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="0b5df-138">**PowerShell を使用する場合**</span><span class="sxs-lookup"><span data-stu-id="0b5df-138">**Using PowerShell**</span></span>

<span data-ttu-id="0b5df-139">発信呼び出し制限は、OnlineDialOutPolicy と呼ばれる 1 つのポリシーによって制御されます。このポリシーには、それぞれに制限属性があります。</span><span class="sxs-lookup"><span data-stu-id="0b5df-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy, which has a restriction attribute for each.</span></span> <span data-ttu-id="0b5df-140">ポリシーをカスタマイズすることはできません。設定の組み合わせごとに事前に定義されたポリシー インスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="0b5df-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span>

<span data-ttu-id="0b5df-141">Get-CSOnlineDialOutPolicy コマンドレットを使用して、発信呼び出しポリシーを表示し、セットアップに次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b5df-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and use the following command for the setup.</span></span>

<span data-ttu-id="0b5df-142">**次のコマンドレットを使用して、ユーザーレベルでポリシーを設定します**。</span><span class="sxs-lookup"><span data-stu-id="0b5df-142">**Set the policy on a per-user level with the following cmdlet**.</span></span> <span data-ttu-id="0b5df-143">(Grant コマンドレットには、Get コマンドレットと同様に "Online" という単語が含まれている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="0b5df-143">(The Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span>

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

<span data-ttu-id="0b5df-144">**次のコマンドレットを使用して、テナント レベルでポリシーを設定します**。</span><span class="sxs-lookup"><span data-stu-id="0b5df-144">**Set the policy on the tenant level with the following cmdlet**.</span></span>

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

<span data-ttu-id="0b5df-145">ダイヤルアウト ポリシーが割り当てられていないテナントのすべてのユーザーに、このポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b5df-145">All users of the tenant who don't have any dialout policy assigned will get this policy.</span></span> <span data-ttu-id="0b5df-146">他のユーザーは、現在のポリシーのままです。</span><span class="sxs-lookup"><span data-stu-id="0b5df-146">Other users remain with their current policy.</span></span>

<span data-ttu-id="0b5df-147">次の表は、各ポリシーの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="0b5df-147">The following table provides an overview of each policy.</span></span>

|<span data-ttu-id="0b5df-148">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="0b5df-148">PowerShell cmdlet</span></span>|<span data-ttu-id="0b5df-149">説明</span><span class="sxs-lookup"><span data-stu-id="0b5df-149">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b5df-150">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0b5df-150">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="0b5df-151">会議のユーザーは、国際電話番号と国内番号にダイヤルアウトできます。また、このユーザーは、国際電話番号と国内番号への発信通話を行う場合にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b5df-151">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="0b5df-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0b5df-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="0b5df-153">会議のユーザーは国内番号にのみダイヤルアウトできます。このユーザーは、国際番号と国内番号への発信通話を行います。</span><span class="sxs-lookup"><span data-stu-id="0b5df-153">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="0b5df-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0b5df-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="0b5df-155">会議のユーザーがダイヤルアウトできない。このユーザーは、国際番号と国内番号への発信呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="0b5df-155">User in the conference can't dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="0b5df-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0b5df-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="0b5df-157">会議のユーザーは国際番号と国内番号にダイヤルアウトできます。このユーザーは国内 PSTN 番号への発信通話のみを行います。</span><span class="sxs-lookup"><span data-stu-id="0b5df-157">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="0b5df-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0b5df-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="0b5df-159">会議のユーザーは国際番号と国内番号にダイヤルアウトできます。このユーザーは、緊急電話番号以外に PSTN 番号への発信通話を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b5df-159">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="0b5df-160">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0b5df-160">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="0b5df-161">会議のユーザーは国内番号にのみダイヤルアウトできます。このユーザーは国内 PSTN 番号への発信通話のみを行います。</span><span class="sxs-lookup"><span data-stu-id="0b5df-161">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="0b5df-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0b5df-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="0b5df-163">会議のユーザーは国内番号にのみダイヤルアウトできます。このユーザーは、緊急電話番号以外に PSTN 番号への発信通話を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b5df-163">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="0b5df-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0b5df-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="0b5df-165">会議のユーザーはダイヤルアウトできないので、このユーザーは国内 PSTN 番号への発信通話のみを行います。</span><span class="sxs-lookup"><span data-stu-id="0b5df-165">User in the conference can't dial out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="0b5df-166">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0b5df-166">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="0b5df-167">会議のユーザーはダイヤルアウトできないので、このユーザーは緊急電話番号以外に PSTN 番号への発信通話を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b5df-167">User in the conference can't dial out, and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="0b5df-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0b5df-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="0b5df-169">会議のユーザーはゾーン [A](audio-conferencing-zones.md)の国と地域にのみダイヤルアウトできます。このユーザーは、国際番号と国内番号への発信通話を行います。</span><span class="sxs-lookup"><span data-stu-id="0b5df-169">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="0b5df-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0b5df-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="0b5df-171">会議のユーザーはゾーン [A](audio-conferencing-zones.md)の国と地域にのみダイヤルアウトできます。このユーザーは国内 PSTN 番号への発信通話のみを行います。</span><span class="sxs-lookup"><span data-stu-id="0b5df-171">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="0b5df-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0b5df-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="0b5df-173">会議のユーザーはゾーン [A](audio-conferencing-zones.md)の国と地域にのみダイヤルアウトできます。このユーザーは、緊急電話番号以外に PSTN 番号への発信呼び出しを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b5df-173">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
