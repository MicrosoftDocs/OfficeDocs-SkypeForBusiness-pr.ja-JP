---
title: 電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー
ms.reviewer: ''
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
ms.openlocfilehash: 36f116acb62cd16863cb547a11fe5687457a8a4e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881841"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="ce093-103">電話会議およびユーザーの PSTN 通話に対する発信通話の制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="ce093-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="ce093-104">管理者は、発信通話の制御を使用して、組織内のユーザーが発信できる電話会議の種類とエンド ユーザーの PSTN 通話を制限できます。</span><span class="sxs-lookup"><span data-stu-id="ce093-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="ce093-105">発信通話コントロールは、ユーザーごとに適用することができ、発信呼び出しの種類を個別に制限するのには次の 2 つのコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="ce093-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="ce093-106">既定では、両方のコントロールは、国際および国内の送信呼び出しを許可に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ce093-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="ce093-107">コントロール</span><span class="sxs-lookup"><span data-stu-id="ce093-107">Control</span></span>|<span data-ttu-id="ce093-108">説明</span><span class="sxs-lookup"><span data-stu-id="ce093-108">Description</span></span>|<span data-ttu-id="ce093-109">コントロール オプション</span><span class="sxs-lookup"><span data-stu-id="ce093-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ce093-110">オーディオ会議の PSTN の呼び出し</span><span class="sxs-lookup"><span data-stu-id="ce093-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="ce093-111">送信の種類を制限します。</span><span class="sxs-lookup"><span data-stu-id="ce093-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="ce093-112">内で許可されている呼び出し</span><span class="sxs-lookup"><span data-stu-id="ce093-112">calls that are allowed from within</span></span> </br><span data-ttu-id="ce093-113">ユーザーが開催するミーティングです。</span><span class="sxs-lookup"><span data-stu-id="ce093-113">meetings organized by a user.</span></span>|<span data-ttu-id="ce093-114">国際および国内 (既定値)</span><span class="sxs-lookup"><span data-stu-id="ce093-114">International and Domestic (default)</span></span></br><span data-ttu-id="ce093-115">国内</span><span class="sxs-lookup"><span data-stu-id="ce093-115">Domestic</span></span></br><span data-ttu-id="ce093-116">なし</span><span class="sxs-lookup"><span data-stu-id="ce093-116">None</span></span>|
|<span data-ttu-id="ce093-117">エンド ・ ユーザーの PSTN の呼び出し</span><span class="sxs-lookup"><span data-stu-id="ce093-117">End user PSTN calls</span></span>|<span data-ttu-id="ce093-118">呼び出しの種類を制限します。</span><span class="sxs-lookup"><span data-stu-id="ce093-118">Restricts the type of calls</span></span> </br><span data-ttu-id="ce093-119">ユーザーが可能です。</span><span class="sxs-lookup"><span data-stu-id="ce093-119">that can be made by a user.</span></span>|<span data-ttu-id="ce093-120">国際および国内 (既定値)</span><span class="sxs-lookup"><span data-stu-id="ce093-120">International and Domestic (default)</span></span></br><span data-ttu-id="ce093-121">国内</span><span class="sxs-lookup"><span data-stu-id="ce093-121">Domestic</span></span></br><span data-ttu-id="ce093-122">なし</span><span class="sxs-lookup"><span data-stu-id="ce093-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="ce093-123">呼び出しは、国内の場合は、開催者の会議 (オーディオ会議) の場合、またはエンド ・ ユーザー (エンド ・ ユーザーの PSTN 通話) の場合に Office 365 に設定されている国の国と同じでは、呼び出し先の電話番号が決定されます。</span><span class="sxs-lookup"><span data-stu-id="ce093-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="ce093-124">オーディオ会議の発信を制限します。</span><span class="sxs-lookup"><span data-stu-id="ce093-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="ce093-125">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="ce093-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ce093-126">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce093-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ce093-127">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce093-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="ce093-128">**オーディオ会議**の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce093-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="ce093-129">**会議からの発信アクセス許可**を [ダイヤルアウトの制限オプションを選択を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce093-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="ce093-130">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce093-130">Click **Save**.</span></span> 

<span data-ttu-id="ce093-131">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="ce093-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="ce093-132">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **のユーザー**、および利用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce093-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="ce093-133">操作ウィンドウで、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce093-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="ce093-134">[**ダイヤル アウトこのユーザーの会議からへの制限**、ダイアル アウトの制限オプションを選択を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce093-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![ダイアル アウトのオプションを制限](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="ce093-136">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce093-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="ce093-137">**PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="ce093-137">**Using PowerShell**</span></span>

<span data-ttu-id="ce093-138">発信制限は、それぞれの制限属性を持っている OnlineDialOutPolicy と呼ばれる 1 つのポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="ce093-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="ce093-139">ポリシーをカスタマイズすることはできませんではなく、設定の各組み合わせに対して事前に定義されたポリシーのインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="ce093-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="ce093-140">Get CSOnlineDialOutPolicy コマンドレットを使用すると発信の呼び出し元のポリシーを表示し、補助金 CSDialOutPolicy コマンドレットを使用してユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ce093-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="ce093-141">(注意: Grant コマンドレット含まれていないこと、単語「オンライン」Get コマンドレットのよう。)</span><span class="sxs-lookup"><span data-stu-id="ce093-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="ce093-142">次の表は、各ポリシーの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ce093-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ce093-143">Id =' タグ: DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="ce093-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="ce093-144">会議内で、ユーザーが国際と国内の番号にダイアル アウトができるし、このユーザーは、国際および国内の番号に発信呼び出しを行うもできます。</span><span class="sxs-lookup"><span data-stu-id="ce093-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="ce093-145">Id =' タグ: DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="ce093-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="ce093-146">会議内のユーザー、国内の番号にダイヤルアウトのみ、このユーザーは、国際および国内の番号に発信呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ce093-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="ce093-147">Id =' タグ: DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="ce093-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="ce093-148">会議内のユーザー任意のダイヤルを作成できません。このユーザーには、国際および国内の番号に発信呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ce093-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="ce093-149">Id =' タグ: DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="ce093-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="ce093-150">会議内で、ユーザーが国際と国内の番号にダイアル アウトができるし、このユーザーは、国内の PSTN 番号に発信呼び出しを行うだけことができます。</span><span class="sxs-lookup"><span data-stu-id="ce093-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="ce093-151">Id =' タグ: DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="ce093-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="ce093-152">会議内で、ユーザーが国際と国内の番号にダイアル アウトができるし、このユーザーは、緊急時の番号だけでなく、PSTN 番号に送信通話をすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ce093-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="ce093-153">Id =' タグ: DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="ce093-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="ce093-154">会議内のユーザー、国内の番号にダイヤルアウトのみ、このユーザーは国内の PSTN 番号に発信呼び出しのみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce093-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="ce093-155">Id =' タグ: DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="ce093-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="ce093-156">会議内のユーザー、国内の番号にダイヤルアウトのみ、このユーザーは、緊急時の番号だけでなく、PSTN 番号に送信通話をすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ce093-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="ce093-157">Id =' タグ: DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="ce093-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="ce093-158">会議内のユーザーは、任意のダイヤルを行うことはできませんし、このユーザーは国内の PSTN 番号に発信呼び出しのみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce093-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="ce093-159">Id =' タグ: DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="ce093-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="ce093-160">会議内のユーザーは、任意のダイヤルを行うことはできませんし、このユーザーは、緊急時の番号だけでなく、PSTN 番号に送信通話をすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ce093-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
