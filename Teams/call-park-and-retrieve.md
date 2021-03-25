---
title: Microsoft Teams でのコール パークおよび保留解除
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Microsoft Teams でコール パークを使用して通話を保留する方法について説明します。
ms.openlocfilehash: 11c0abc5c9cd49a524417ce9706129cea9ccae1e
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197582"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="ff3c2-103">Microsoft Teams でのコール パークおよび保留解除</span><span class="sxs-lookup"><span data-stu-id="ff3c2-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="ff3c2-104">コール パークと取得は、ユーザーが通話を保留にできる機能です。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="ff3c2-105">通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="ff3c2-106">通話をパークしたユーザーまたは他のユーザーは、サポートされているアプリまたはデバイスでそのコードを使用して通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="ff3c2-107">(詳細については [、「Teams で通話をパークする」](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="ff3c2-108">コール パークを使用する一般的なシナリオには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="ff3c2-109">受付が、工場で働く人宛にかかってきた通話を保留にします。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="ff3c2-110">次に、受付は場内アナウンス設備で着信とコード番号をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="ff3c2-111">通話を受けたユーザーは、工場のフロアで Teams 電話を取り、コードを入力して通話を保留解除できます。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="ff3c2-112">バッテリーの充電が切れかけているため、ユーザーが携帯電話で通話を保留にします。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="ff3c2-113">その後、そのユーザーは Teams の卓上電話でコードを入力して通話を保留解除できます。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="ff3c2-114">サポート担当者が顧客からの電話を保留して、顧客への通話サポートを行うエキスパートへ Teams チャネルでアナウンスを送信します。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="ff3c2-115">エキスパートが Teams クライアントにコードを入力し、通話を保留解除します。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="ff3c2-116">通話をパークして取得するには、ユーザーがユーザーのエンタープライズ VoIPであり、コール パーク ポリシーに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="ff3c2-117">コール パークと取得は [、Teams 展開](teams-and-skypeforbusiness-coexistence-and-interoperability.md) モードでのみ使用できます。Skype for Business IP 電話機ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="ff3c2-118">コール パークを構成して取得する</span><span class="sxs-lookup"><span data-stu-id="ff3c2-118">Configure call park and retrieve</span></span>

<span data-ttu-id="ff3c2-119">通話パークを構成して取得するには、Teams 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="ff3c2-120">既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-120">It is disabled by default.</span></span> <span data-ttu-id="ff3c2-121">コール パーク ポリシーを使用して、ユーザーに対して有効にしたり、ユーザー グループを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="ff3c2-122">一連のユーザーに同じポリシーを適用すると、そのユーザーの間で通話を保留したり、保留を解除したりできます。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="ff3c2-123">コール パーク ポリシーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="ff3c2-123">To enable a call park policy</span></span>

1. <span data-ttu-id="ff3c2-124">Microsoft Teams 管理センターの左側のナビゲーションで、**音声** 通話パークの  >  **ポリシーに移動します**。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="ff3c2-125">[ポリシーの **管理] タブの [** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="ff3c2-126">ポリシーに名前を付け、[通話パークの許可] を [オン]**に\*\*\*\*切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![コール パーク ポリシー設定のスクリーンショット](media/call-park-add-policy.png)

4. <span data-ttu-id="ff3c2-128">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-128">Select **Save**.</span></span>

<span data-ttu-id="ff3c2-129">ポリシーを編集するには、一覧でポリシーを選び、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="ff3c2-130">ポリシーを機能するには、ポリシーをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="ff3c2-131">ポリシーを [ユーザーに個別に割り当てるか](assign-policies.md) 、グループに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="ff3c2-132">コール パーク ポリシーをグループに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="ff3c2-132">To assign a call park policy to a group</span></span>

1. <span data-ttu-id="ff3c2-133">[コール **パーク ポリシー] ページの [** グループ ポリシーの割り当 **て** ] タブで、[グループの **追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="ff3c2-134">使用するグループを検索し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="ff3c2-135">他のグループ割り当てと比較してランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="ff3c2-136">[ **ポリシーの選択]** で、このグループを割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![パーク ポリシーの画像](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="ff3c2-138">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff3c2-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ff3c2-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ff3c2-139">Related topics</span></span>

[<span data-ttu-id="ff3c2-140">Teams で通話をパークする</span><span class="sxs-lookup"><span data-stu-id="ff3c2-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="ff3c2-141">Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ff3c2-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="ff3c2-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="ff3c2-142">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="ff3c2-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="ff3c2-143">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="ff3c2-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="ff3c2-144">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)