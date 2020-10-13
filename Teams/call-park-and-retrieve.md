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
description: Microsoft Teams で通話パークを使用して通話を保留にする方法について説明します。
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424595"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="70131-103">Microsoft Teams でのコール パークおよび保留解除</span><span class="sxs-lookup"><span data-stu-id="70131-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="70131-104">コールパークと取得は、ユーザーが通話を保留にできる機能です。</span><span class="sxs-lookup"><span data-stu-id="70131-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="70131-105">通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="70131-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="70131-106">通話を保留にしたユーザーは、サポートされているアプリまたはデバイスでそのコードを使って通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="70131-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="70131-107">(詳細について [は、「Teams で通話をパークする](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="70131-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="70131-108">コール パークを使用する一般的なシナリオには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="70131-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="70131-109">受付が、工場で働く人宛にかかってきた通話を保留にします。</span><span class="sxs-lookup"><span data-stu-id="70131-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="70131-110">次に、受付は場内アナウンス設備で着信とコード番号をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="70131-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="70131-111">通話を受けたユーザーは、工場のフロアで Teams 電話を取り、コードを入力して通話を保留解除できます。</span><span class="sxs-lookup"><span data-stu-id="70131-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="70131-112">バッテリーの充電が切れかけているため、ユーザーが携帯電話で通話を保留にします。</span><span class="sxs-lookup"><span data-stu-id="70131-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="70131-113">その後、そのユーザーは Teams の卓上電話でコードを入力して通話を保留解除できます。</span><span class="sxs-lookup"><span data-stu-id="70131-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="70131-114">サポート担当者が顧客からの電話を保留して、顧客への通話サポートを行うエキスパートへ Teams チャネルでアナウンスを送信します。</span><span class="sxs-lookup"><span data-stu-id="70131-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="70131-115">エキスパートが Teams クライアントにコードを入力し、通話を保留解除します。</span><span class="sxs-lookup"><span data-stu-id="70131-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="70131-116">通話をパークして取得するには、ユーザーがエンタープライズボイスユーザーであり、コールパークポリシーに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70131-116">To park and retrieve calls, a user must be an Enterprise Voice user and and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="70131-117">コールパークと取得は [Teams のみの展開モード](teams-and-skypeforbusiness-coexistence-and-interoperability.md) でのみ使用でき、Skype for BUSINESS の IP 電話ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="70131-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="70131-118">コールパークの構成と取得</span><span class="sxs-lookup"><span data-stu-id="70131-118">Configure call park and retrieve</span></span>

<span data-ttu-id="70131-119">コールパークを構成して取得するには、Teams の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="70131-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="70131-120">既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="70131-120">It is disabled by default.</span></span> <span data-ttu-id="70131-121">コール パーク ポリシーを使用して、ユーザーに対して有効にしたり、ユーザー グループを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="70131-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="70131-122">一連のユーザーに同じポリシーを適用すると、そのユーザーの間で通話を保留したり、保留を解除したりできます。</span><span class="sxs-lookup"><span data-stu-id="70131-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="70131-123">コールパークポリシーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="70131-123">To enable a call park policy</span></span>

1. <span data-ttu-id="70131-124">Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  **通話パークポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="70131-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="70131-125">[ **ポリシーの管理** ] タブの [ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70131-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="70131-126">ポリシーに名前を付け、[ **call パークを有効**にする] に切り替え**ます。**</span><span class="sxs-lookup"><span data-stu-id="70131-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![コールパークポリシー設定のスクリーンショット](media/call-park-add-policy.png)

4. <span data-ttu-id="70131-128">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70131-128">Select **Save**.</span></span>

<span data-ttu-id="70131-129">リストでポリシーを選択して [ **編集**] をクリックすると、ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="70131-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="70131-130">ポリシーが機能するためには、そのポリシーがユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70131-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="70131-131">[ポリシーは、ユーザーに個別に割り当てる](assign-policies.md)か、グループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="70131-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="70131-132">グループに通話パーツポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="70131-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="70131-133">[ **コールパークポリシー** ] ページの [ **グループポリシーの割り当て** ] タブで、[グループの **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70131-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="70131-134">使用するグループを検索し、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70131-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="70131-135">他のグループ割り当てと比較して、ランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="70131-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="70131-136">[ **ポリシーの選択**] で、このグループに割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="70131-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="70131-137">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70131-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="70131-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="70131-138">Related topics</span></span>

[<span data-ttu-id="70131-139">Teams で通話をパークする</span><span class="sxs-lookup"><span data-stu-id="70131-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="70131-140">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="70131-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="70131-141">新規-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="70131-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="70131-142">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="70131-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="70131-143">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="70131-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)