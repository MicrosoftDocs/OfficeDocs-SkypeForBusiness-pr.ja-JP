---
title: Microsoft Teams でのコール パークおよび保留解除
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
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
description: 電話会議を使って、クラウドの Teams サービスで通話を保留にする方法について説明します。
ms.openlocfilehash: a9518705cd5edff3834be21732f78dd47352cd63
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938536"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="02370-103">Microsoft Teams でのコール パークおよび保留解除</span><span class="sxs-lookup"><span data-stu-id="02370-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="02370-104">コール パークおよび保留解除は、ユーザーがクラウド内の Teams サービスで通話を保留にする機能です。</span><span class="sxs-lookup"><span data-stu-id="02370-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="02370-105">通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="02370-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="02370-106">通話を保留したユーザーまたは他のユーザーは、そのコードとサポートされているアプリやデバイスを使用して、通話を再開できます。</span><span class="sxs-lookup"><span data-stu-id="02370-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="02370-107">コール パークを使用する一般的なシナリオには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="02370-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="02370-108">受付が、工場で働く人宛にかかってきた通話を保留にします。</span><span class="sxs-lookup"><span data-stu-id="02370-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="02370-109">次に、受付は場内アナウンス設備で着信とコード番号をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="02370-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="02370-110">通話を受けたユーザーは、工場のフロアで Teams 電話を取り、コードを入力して通話を保留解除できます。</span><span class="sxs-lookup"><span data-stu-id="02370-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="02370-111">バッテリーの充電が切れかけているため、ユーザーが携帯電話で通話を保留にします。</span><span class="sxs-lookup"><span data-stu-id="02370-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="02370-112">その後、そのユーザーは Teams の卓上電話でコードを入力して通話を保留解除できます。</span><span class="sxs-lookup"><span data-stu-id="02370-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="02370-113">サポート担当者が顧客からの電話を保留して、顧客への通話サポートを行うエキスパートへ Teams チャネルでアナウンスを送信します。</span><span class="sxs-lookup"><span data-stu-id="02370-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="02370-114">エキスパートが Teams クライアントにコードを入力し、通話を保留解除します。</span><span class="sxs-lookup"><span data-stu-id="02370-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02370-115">この機能を使用できるのは、Teams のみの展開モードだけです。</span><span class="sxs-lookup"><span data-stu-id="02370-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="02370-116">Teams 展開モードの詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02370-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="02370-117">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="02370-117">License required</span></span>

<span data-ttu-id="02370-118">通話を保留および解除するには、ユーザーがエンタープライズ VoIP ユーザーであり、管理者がユーザーにコール パーク ポリシーを付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02370-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="02370-119">ライセンスモデルの詳細については、「 [Microsoft Teams サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02370-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="02370-120">コール パークおよび保留解除機能の可用性</span><span class="sxs-lookup"><span data-stu-id="02370-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="02370-121">コール パークおよび保留解除は現在、次のクライアントとデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="02370-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="02370-122">(PSTN 接続の有無にかかわらず、Teams のみのモードでサポートされています。)</span><span class="sxs-lookup"><span data-stu-id="02370-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="02370-123">機能</span><span class="sxs-lookup"><span data-stu-id="02370-123">Capability</span></span> | <span data-ttu-id="02370-124">Teams デスクトップ</span><span class="sxs-lookup"><span data-stu-id="02370-124">Teams Desktop</span></span> | <span data-ttu-id="02370-125">Teams Mac アプリ</span><span class="sxs-lookup"><span data-stu-id="02370-125">Teams Mac App</span></span> | <span data-ttu-id="02370-126">Teams Web アプリ (Edge)</span><span class="sxs-lookup"><span data-stu-id="02370-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="02370-127">Teams モバイル iOS/Android アプリ</span><span class="sxs-lookup"><span data-stu-id="02370-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="02370-128">Teams IP 電話</span><span class="sxs-lookup"><span data-stu-id="02370-128">Teams IP phone</span></span> | <span data-ttu-id="02370-129">Skype for Business IP 電話</span><span class="sxs-lookup"><span data-stu-id="02370-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="02370-130">通話を保留する</span><span class="sxs-lookup"><span data-stu-id="02370-130">Park a call</span></span> | <span data-ttu-id="02370-131">はい</span><span class="sxs-lookup"><span data-stu-id="02370-131">Yes</span></span> | <span data-ttu-id="02370-132">はい</span><span class="sxs-lookup"><span data-stu-id="02370-132">Yes</span></span> | <span data-ttu-id="02370-133">はい</span><span class="sxs-lookup"><span data-stu-id="02370-133">Yes</span></span> | <span data-ttu-id="02370-134">はい</span><span class="sxs-lookup"><span data-stu-id="02370-134">Yes</span></span> | <span data-ttu-id="02370-135">はい</span><span class="sxs-lookup"><span data-stu-id="02370-135">Yes</span></span> | <span data-ttu-id="02370-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="02370-136">No</span></span> |
| <span data-ttu-id="02370-137">通話の保留を解除する</span><span class="sxs-lookup"><span data-stu-id="02370-137">Retrieve a parked call</span></span> | <span data-ttu-id="02370-138">はい</span><span class="sxs-lookup"><span data-stu-id="02370-138">Yes</span></span> | <span data-ttu-id="02370-139">はい</span><span class="sxs-lookup"><span data-stu-id="02370-139">Yes</span></span> | <span data-ttu-id="02370-140">はい</span><span class="sxs-lookup"><span data-stu-id="02370-140">Yes</span></span> | <span data-ttu-id="02370-141">はい</span><span class="sxs-lookup"><span data-stu-id="02370-141">Yes</span></span> | <span data-ttu-id="02370-142">はい</span><span class="sxs-lookup"><span data-stu-id="02370-142">Yes</span></span> | <span data-ttu-id="02370-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="02370-143">No</span></span> |
| <span data-ttu-id="02370-144">未解除通話のかけ直し</span><span class="sxs-lookup"><span data-stu-id="02370-144">Unretrieved call ring back</span></span> | <span data-ttu-id="02370-145">はい</span><span class="sxs-lookup"><span data-stu-id="02370-145">Yes</span></span> | <span data-ttu-id="02370-146">はい</span><span class="sxs-lookup"><span data-stu-id="02370-146">Yes</span></span> | <span data-ttu-id="02370-147">はい</span><span class="sxs-lookup"><span data-stu-id="02370-147">Yes</span></span> | <span data-ttu-id="02370-148">はい</span><span class="sxs-lookup"><span data-stu-id="02370-148">Yes</span></span> | <span data-ttu-id="02370-149">はい</span><span class="sxs-lookup"><span data-stu-id="02370-149">Yes</span></span> | <span data-ttu-id="02370-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="02370-150">No</span></span> |

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="02370-151">コールパークの構成と取得</span><span class="sxs-lookup"><span data-stu-id="02370-151">Configure call park and retrieve</span></span>

<span data-ttu-id="02370-152">コールパークを構成して取得するには、管理者である必要があります。この機能は、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="02370-152">You must be an admin to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="02370-153">コール パーク ポリシーを使用して、ユーザーに対して有効にしたり、ユーザー グループを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="02370-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="02370-154">一連のユーザーに同じポリシーを適用すると、そのユーザーの間で通話を保留したり、保留を解除したりできます。</span><span class="sxs-lookup"><span data-stu-id="02370-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="02370-155">ユーザーのコール パークを構成したり、コール パーク ユーザー グループを作成したりするには、この下の「[コール パーク ポリシーを割り当てる](#assign-a-call-park-policy)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="02370-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="02370-156">コール パークおよび保留解除機能の使用方法の詳細については、「[Teams で通話を保留する](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02370-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="02370-157">コール パーク ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="02370-157">Enable a call park policy</span></span>

1. <span data-ttu-id="02370-158">Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  **通話パークポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02370-158">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="02370-159">[**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02370-159">Select **Add**.</span></span>
3. <span data-ttu-id="02370-160">ポリシーに名前を付け、[ **call パークを有効**にする] に切り替え**ます。**</span><span class="sxs-lookup"><span data-stu-id="02370-160">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>
4. <span data-ttu-id="02370-161">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="02370-161">Select **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="02370-162">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="02370-162">Using PowerShell</span></span>

<span data-ttu-id="02370-163">「[新規-CsTeamsCallParkPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)参照してください。</span><span class="sxs-lookup"><span data-stu-id="02370-163">See [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span></span>

### <a name="edit-a-call-park-policy"></a><span data-ttu-id="02370-164">コールパークポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="02370-164">Edit a call park policy</span></span>

1. <span data-ttu-id="02370-165">Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  **通話パークポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02370-165">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="02370-166">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02370-166">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="02370-167">[**通話パークを許可**する] を [**オフ**] または **[オン**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="02370-167">Switch **Allow call park** to **Off** or **On**.</span></span>
4. <span data-ttu-id="02370-168">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02370-168">Click **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="02370-169">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="02370-169">Using PowerShell</span></span>

<span data-ttu-id="02370-170">「 [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02370-170">See [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span></span> <span data-ttu-id="02370-171">たとえば、既定の設定を変更するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="02370-171">For example, to change the default setting, run the following:</span></span>

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="02370-172">コール パーク ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="02370-172">Assign a call park policy</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
<span data-ttu-id="02370-173">「[許可-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02370-173">See also [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="02370-174">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="02370-174">Troubleshooting</span></span>

<span data-ttu-id="02370-175">ユーザーが [パーク] または [取得] ボタンを表示できない場合:</span><span class="sxs-lookup"><span data-stu-id="02370-175">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="02370-176">ユーザーがコール パーク ポリシーを有効にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="02370-176">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="02370-177">ユーザーが通話の保留を解除しようとしても失敗した場合は、次の点を確認します:</span><span class="sxs-lookup"><span data-stu-id="02370-177">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="02370-178">ユーザーが Teams クライアントまたは Teams が有効なデバイス/スマートフォンを使用していることを確認します</span><span class="sxs-lookup"><span data-stu-id="02370-178">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="02370-179">グループ – ユーザーが、同じ Teams コール パーク ポリシーが割り当てられている、コール パーク グループのメンバーであるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="02370-179">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="02370-180">アイランド モード – コール パークおよび保留解除は、Teams アイランド モードでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="02370-180">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="02370-181">通話は既に保留解除または終了しています。</span><span class="sxs-lookup"><span data-stu-id="02370-181">The call has already been retrieved or terminated.</span></span>

## <a name="related-topics"></a><span data-ttu-id="02370-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="02370-182">Related topics</span></span>

[<span data-ttu-id="02370-183">Teams で通話をパークする</span><span class="sxs-lookup"><span data-stu-id="02370-183">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="02370-184">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="02370-184">Assign policies to your users in Teams</span></span>](assign-policies.md)
