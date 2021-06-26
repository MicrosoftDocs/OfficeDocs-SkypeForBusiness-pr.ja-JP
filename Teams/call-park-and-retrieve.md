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
description: コール パークを使用して通話を取得し、通話を保留する方法についてMicrosoft Teams。
ms.openlocfilehash: fb60e09148f2b96ce9b4d059d7d112c817239822
ms.sourcegitcommit: 355c7858b98518f6a922110390c51eb7e2cd6690
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "53147185"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="71b83-103">Microsoft Teams でのコール パークおよび保留解除</span><span class="sxs-lookup"><span data-stu-id="71b83-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="71b83-104">コール パークと取得は、ユーザーが通話を保留にできる機能です。</span><span class="sxs-lookup"><span data-stu-id="71b83-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="71b83-105">通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="71b83-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="71b83-106">通話を登録したユーザーまたは他のユーザーは、サポートされているアプリまたはデバイスでそのコードを使用して、呼び出しを取得できます。</span><span class="sxs-lookup"><span data-stu-id="71b83-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="71b83-107">(詳細については、「通話[を他のユーザーにTeams」](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="71b83-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="71b83-108">コール パークを使用する一般的なシナリオには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="71b83-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="71b83-109">受付が、工場で働く人宛にかかってきた通話を保留にします。</span><span class="sxs-lookup"><span data-stu-id="71b83-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="71b83-110">次に、受付は場内アナウンス設備で着信とコード番号をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="71b83-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="71b83-111">通話を受けたユーザーは、工場のフロアで Teams 電話を取り、コードを入力して通話を保留解除できます。</span><span class="sxs-lookup"><span data-stu-id="71b83-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="71b83-112">バッテリーの充電が切れかけているため、ユーザーが携帯電話で通話を保留にします。</span><span class="sxs-lookup"><span data-stu-id="71b83-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="71b83-113">その後、そのユーザーは Teams の卓上電話でコードを入力して通話を保留解除できます。</span><span class="sxs-lookup"><span data-stu-id="71b83-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="71b83-114">サポート担当者が顧客からの電話を保留して、顧客への通話サポートを行うエキスパートへ Teams チャネルでアナウンスを送信します。</span><span class="sxs-lookup"><span data-stu-id="71b83-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="71b83-115">エキスパートが Teams クライアントにコードを入力し、通話を保留解除します。</span><span class="sxs-lookup"><span data-stu-id="71b83-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="71b83-116">呼び出しをパークして取得するには、ユーザーはユーザーエンタープライズ VoIP、コール パーク ポリシーに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="71b83-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="71b83-117">コール パークと取得は、Teams[展開](teams-and-skypeforbusiness-coexistence-and-interoperability.md)モードでのみ使用できます。また、IP 電話Skype for Businessサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="71b83-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="71b83-118">コール パークの構成と取得</span><span class="sxs-lookup"><span data-stu-id="71b83-118">Configure call park and retrieve</span></span>

<span data-ttu-id="71b83-119">コール パークを構成して取得Teams管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="71b83-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="71b83-120">既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="71b83-120">It is disabled by default.</span></span> <span data-ttu-id="71b83-121">コール パーク ポリシーを使用して、ユーザーに対して有効にしたり、ユーザー グループを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="71b83-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="71b83-122">一連のユーザーに同じポリシーを適用すると、そのユーザーの間で通話を保留したり、保留を解除したりできます。</span><span class="sxs-lookup"><span data-stu-id="71b83-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="71b83-123">呼び出しの集荷番号の範囲は、10 ~ 99 の範囲に事前に定義され、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="71b83-123">The range of call pickup numbers is predefined to be from 10-99 and cannot be modified.</span></span> <span data-ttu-id="71b83-124">最初にパークされた呼び出しは 10 の集荷コードをレンダリングし、次にパークされた呼び出しは 11 などの集荷コードをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="71b83-124">The first parked call will be rendered a pickup code of 10, the next parked call will be rendered a pickup code of 11, etc.</span></span> <span data-ttu-id="71b83-125">99 までが集荷コードとしてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="71b83-125">until 99 is rendered as a pickup code.</span></span> <span data-ttu-id="71b83-126">その後、レンダリングされた集荷コードは 10 から再度開始されます。</span><span class="sxs-lookup"><span data-stu-id="71b83-126">After which, the rendered pickup codes start over from 10 once again.</span></span>  <span data-ttu-id="71b83-127">89 を超えるアクティブなパークされた呼び出しがある場合、レンダリングされた集荷コードは 99 を超えて増加し続け、90 番目のアクティブなパークされた呼び出しは集荷コードに対して 100 回レンダリングされ、91 番目のアクティブなパークされた呼び出しは 101 の集荷コードをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="71b83-127">If there are more than 89 active parked calls, the rendered pickup codes will keep incrementing beyond 99 such that the 90th active parked call would be rendered 100 for a pickup code, the 91st active parked call would be rendered a pickup code of 101.</span></span>

<span data-ttu-id="71b83-128">コール パーク ポリシーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="71b83-128">To enable a call park policy</span></span>

1. <span data-ttu-id="71b83-129">管理センターの左側のナビゲーションMicrosoft Teams、音声 **通話パークポリシー**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="71b83-129">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="71b83-130">[ポリシーの **管理] タブで、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="71b83-130">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="71b83-131">ポリシーに名前を付け、[呼び出しパークを **許可する] を [オン** ] に **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="71b83-131">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![コール パーク ポリシー設定のスクリーンショット](media/call-park-add-policy.png)

4. <span data-ttu-id="71b83-133">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="71b83-133">Select **Save**.</span></span>

<span data-ttu-id="71b83-134">ポリシーを編集するには、一覧でポリシーを選択し、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="71b83-134">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="71b83-135">ポリシーを機能するには、ポリシーをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="71b83-135">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="71b83-136">ポリシーを [ユーザーに個別に割り当てるか](assign-policies.md) 、グループに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="71b83-136">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="71b83-137">グループにコール パーク ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="71b83-137">To assign a call park policy to a group</span></span>

1. <span data-ttu-id="71b83-138">[コール **パーク ポリシー] ページの** [グループ ポリシーの割り当て] タブ **で** 、[グループの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="71b83-138">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="71b83-139">使用するグループを検索し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="71b83-139">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="71b83-140">他のグループ割り当てと比較してランクを選択します。</span><span class="sxs-lookup"><span data-stu-id="71b83-140">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="71b83-141">[ **ポリシーの選択] で**、このグループを割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="71b83-141">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![park policies image](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="71b83-143">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="71b83-143">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="71b83-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="71b83-144">Related topics</span></span>

[<span data-ttu-id="71b83-145">通話を一時Teams</span><span class="sxs-lookup"><span data-stu-id="71b83-145">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="71b83-146"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="71b83-146">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="71b83-147">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="71b83-147">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="71b83-148">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="71b83-148">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="71b83-149">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="71b83-149">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
