---
title: 電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理者は、オーディオ会議、エンド ・ ユーザー PSTN の呼び出しのユーザーが可能なタイプを制御できます。
ms.openlocfilehash: ed61dc5c131dd38d59820f3ccda9682dcf7fd886
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882014"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="c55d3-103">電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="c55d3-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="c55d3-104">管理者は、オーディオ会議、エンド ・ ユーザー PSTN の呼び出し、組織内のユーザーが作成できるの種類を制限するのには、発信呼び出しコントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="c55d3-105">発信通話コントロールは、ユーザーごとに適用することができ、発信呼び出しの種類を個別に制限するのには次の 2 つのコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="c55d3-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="c55d3-106">既定では、両方のコントロールは、国際および国内の送信呼び出しを許可に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="c55d3-107">コントロール</span><span class="sxs-lookup"><span data-stu-id="c55d3-107">Control</span></span>|<span data-ttu-id="c55d3-108">説明</span><span class="sxs-lookup"><span data-stu-id="c55d3-108">Description</span></span>|<span data-ttu-id="c55d3-109">コントロール オプション</span><span class="sxs-lookup"><span data-stu-id="c55d3-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c55d3-110">オーディオ会議の PSTN の呼び出し</span><span class="sxs-lookup"><span data-stu-id="c55d3-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="c55d3-111">送信の種類を制限します。</span><span class="sxs-lookup"><span data-stu-id="c55d3-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="c55d3-112">内で許可されている呼び出し</span><span class="sxs-lookup"><span data-stu-id="c55d3-112">calls that are allowed from within</span></span> </br><span data-ttu-id="c55d3-113">ユーザーが開催するミーティングです。</span><span class="sxs-lookup"><span data-stu-id="c55d3-113">meetings organized by a user.</span></span>|<span data-ttu-id="c55d3-114">国際および国内 (既定値)</span><span class="sxs-lookup"><span data-stu-id="c55d3-114">International and Domestic (default)</span></span></br><span data-ttu-id="c55d3-115">国内</span><span class="sxs-lookup"><span data-stu-id="c55d3-115">Domestic</span></span></br><span data-ttu-id="c55d3-116">なし</span><span class="sxs-lookup"><span data-stu-id="c55d3-116">None</span></span>|
|<span data-ttu-id="c55d3-117">エンド ・ ユーザーの PSTN の呼び出し</span><span class="sxs-lookup"><span data-stu-id="c55d3-117">End user PSTN calls</span></span>|<span data-ttu-id="c55d3-118">呼び出しの種類を制限します。</span><span class="sxs-lookup"><span data-stu-id="c55d3-118">Restricts the type of calls</span></span> </br><span data-ttu-id="c55d3-119">ユーザーが可能です。</span><span class="sxs-lookup"><span data-stu-id="c55d3-119">that can be made by a user.</span></span>|<span data-ttu-id="c55d3-120">国際および国内 (既定値)</span><span class="sxs-lookup"><span data-stu-id="c55d3-120">International and Domestic (default)</span></span></br><span data-ttu-id="c55d3-121">国内</span><span class="sxs-lookup"><span data-stu-id="c55d3-121">Domestic</span></span></br><span data-ttu-id="c55d3-122">なし</span><span class="sxs-lookup"><span data-stu-id="c55d3-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="c55d3-123">呼び出しは、国内の場合は、開催者の会議 (オーディオ会議) の場合、またはエンド ・ ユーザー (エンド ・ ユーザーの PSTN 通話) の場合に Office 365 に設定されている国の国と同じでは、呼び出し先の電話番号が決定されます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="c55d3-124">オーディオ会議の発信を制限します。</span><span class="sxs-lookup"><span data-stu-id="c55d3-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="c55d3-125">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="c55d3-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c55d3-126">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c55d3-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c55d3-127">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c55d3-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="c55d3-128">**オーディオ会議**の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c55d3-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="c55d3-129">**会議からの発信アクセス許可**を [ダイヤルアウトの制限オプションを選択を選択します。</span><span class="sxs-lookup"><span data-stu-id="c55d3-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="c55d3-130">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c55d3-130">Click **Save**.</span></span> 

<span data-ttu-id="c55d3-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="c55d3-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="c55d3-132">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **のユーザー**、および利用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c55d3-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="c55d3-133">In the Skype for Business admin center, in the left navigation go to Dial-in conferencing > Provider name drop-down, and then select the dial-in conferencing provider for the user.</span><span class="sxs-lookup"><span data-stu-id="c55d3-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="c55d3-134">[**ダイヤル アウトこのユーザーの会議からへの制限**、ダイアル アウトの制限オプションを選択を選択します。</span><span class="sxs-lookup"><span data-stu-id="c55d3-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![ダイアル アウトのオプションを制限](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="c55d3-136">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c55d3-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="c55d3-137">**PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="c55d3-137">**Using PowerShell**</span></span>

<span data-ttu-id="c55d3-138">発信制限は、それぞれの制限属性を持っている OnlineDialOutPolicy と呼ばれる 1 つのポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="c55d3-139">ポリシーをカスタマイズすることはできませんではなく、設定の各組み合わせに対して事前に定義されたポリシーのインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="c55d3-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="c55d3-140">Get CSOnlineDialOutPolicy コマンドレットを使用すると発信の呼び出し元のポリシーを表示し、補助金 CSDialOutPolicy コマンドレットを使用してユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="c55d3-141">(注意: Grant コマンドレット含まれていないこと、単語「オンライン」Get コマンドレットのよう。)</span><span class="sxs-lookup"><span data-stu-id="c55d3-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="c55d3-142">次の表は、各ポリシーの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c55d3-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c55d3-143">Id =' タグ: DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="c55d3-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="c55d3-144">会議内で、ユーザーが国際と国内の番号にダイアル アウトができるし、このユーザーは、国際および国内の番号に発信呼び出しを行うもできます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="c55d3-145">Id =' タグ: DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="c55d3-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="c55d3-146">会議内のユーザー、国内の番号にダイヤルアウトのみ、このユーザーは、国際および国内の番号に発信呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="c55d3-147">Id =' タグ: DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="c55d3-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="c55d3-148">会議内のユーザー任意のダイヤルを作成できません。このユーザーには、国際および国内の番号に発信呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="c55d3-149">Id =' タグ: DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="c55d3-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="c55d3-150">会議内で、ユーザーが国際と国内の番号にダイアル アウトができるし、このユーザーは、国内の PSTN 番号に発信呼び出しを行うだけことができます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="c55d3-151">Id =' タグ: DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="c55d3-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="c55d3-152">会議内で、ユーザーが国際と国内の番号にダイアル アウトができるし、このユーザーは、緊急時の番号だけでなく、PSTN 番号に送信通話をすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c55d3-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="c55d3-153">Id =' タグ: DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="c55d3-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="c55d3-154">会議内のユーザー、国内の番号にダイヤルアウトのみ、このユーザーは国内の PSTN 番号に発信呼び出しのみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="c55d3-155">Id =' タグ: DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="c55d3-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="c55d3-156">会議内のユーザー、国内の番号にダイヤルアウトのみ、このユーザーは、緊急時の番号だけでなく、PSTN 番号に送信通話をすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c55d3-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="c55d3-157">Id =' タグ: DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="c55d3-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="c55d3-158">会議内のユーザーは、任意のダイヤルを行うことはできませんし、このユーザーは国内の PSTN 番号に発信呼び出しのみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c55d3-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="c55d3-159">Id =' タグ: DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="c55d3-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="c55d3-160">会議内のユーザーは、任意のダイヤルを行うことはできませんし、このユーザーは、緊急時の番号だけでなく、PSTN 番号に送信通話をすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c55d3-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
