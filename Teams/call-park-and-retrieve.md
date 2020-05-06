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
ms.openlocfilehash: e36690c4059ceae67c8615b1e910051439ca8e78
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042964"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="de676-103">Microsoft Teams でのコール パークおよび保留解除</span><span class="sxs-lookup"><span data-stu-id="de676-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="de676-104">コール パークおよび保留解除は、ユーザーがクラウド内の Teams サービスで通話を保留にする機能です。</span><span class="sxs-lookup"><span data-stu-id="de676-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="de676-105">通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="de676-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="de676-106">通話を保留したユーザーまたは他のユーザーは、そのコードとサポートされているアプリやデバイスを使用して、通話を再開できます。</span><span class="sxs-lookup"><span data-stu-id="de676-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="de676-107">コール パークを使用する一般的なシナリオには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="de676-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="de676-108">受付が、工場で働く人宛にかかってきた通話を保留にします。</span><span class="sxs-lookup"><span data-stu-id="de676-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="de676-109">次に、受付は場内アナウンス設備で着信とコード番号をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="de676-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="de676-110">通話を受けたユーザーは、工場のフロアで Teams 電話を取り、コードを入力して通話を保留解除できます。</span><span class="sxs-lookup"><span data-stu-id="de676-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="de676-111">バッテリーの充電が切れかけているため、ユーザーが携帯電話で通話を保留にします。</span><span class="sxs-lookup"><span data-stu-id="de676-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="de676-112">その後、そのユーザーは Teams の卓上電話でコードを入力して通話を保留解除できます。</span><span class="sxs-lookup"><span data-stu-id="de676-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="de676-113">サポート担当者が顧客からの電話を保留して、顧客への通話サポートを行うエキスパートへ Teams チャネルでアナウンスを送信します。</span><span class="sxs-lookup"><span data-stu-id="de676-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="de676-114">エキスパートが Teams クライアントにコードを入力し、通話を保留解除します。</span><span class="sxs-lookup"><span data-stu-id="de676-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de676-115">この機能を使用できるのは、Teams のみの展開モードだけです。</span><span class="sxs-lookup"><span data-stu-id="de676-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="de676-116">Teams 展開モードの詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de676-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="de676-117">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="de676-117">License required</span></span>

<span data-ttu-id="de676-118">通話を保留および解除するには、ユーザーがエンタープライズ VoIP ユーザーであり、管理者がユーザーにコール パーク ポリシーを付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de676-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="de676-119">ライセンスモデルの詳細については、「 [Microsoft Teams サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de676-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="de676-120">コール パークおよび保留解除機能の可用性</span><span class="sxs-lookup"><span data-stu-id="de676-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="de676-121">コール パークおよび保留解除は現在、次のクライアントとデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de676-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="de676-122">(PSTN 接続の有無にかかわらず、Teams のみのモードでサポートされています。)</span><span class="sxs-lookup"><span data-stu-id="de676-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="de676-123">機能</span><span class="sxs-lookup"><span data-stu-id="de676-123">Capability</span></span> | <span data-ttu-id="de676-124">Teams デスクトップ</span><span class="sxs-lookup"><span data-stu-id="de676-124">Teams Desktop</span></span> | <span data-ttu-id="de676-125">Teams Mac アプリ</span><span class="sxs-lookup"><span data-stu-id="de676-125">Teams Mac App</span></span> | <span data-ttu-id="de676-126">Teams Web アプリ (Edge)</span><span class="sxs-lookup"><span data-stu-id="de676-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="de676-127">Teams モバイル iOS/Android アプリ</span><span class="sxs-lookup"><span data-stu-id="de676-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="de676-128">Teams IP 電話</span><span class="sxs-lookup"><span data-stu-id="de676-128">Teams IP phone</span></span> | <span data-ttu-id="de676-129">Skype for Business IP 電話</span><span class="sxs-lookup"><span data-stu-id="de676-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="de676-130">通話を保留する</span><span class="sxs-lookup"><span data-stu-id="de676-130">Park a call</span></span> | <span data-ttu-id="de676-131">はい</span><span class="sxs-lookup"><span data-stu-id="de676-131">Yes</span></span> | <span data-ttu-id="de676-132">はい</span><span class="sxs-lookup"><span data-stu-id="de676-132">Yes</span></span> | <span data-ttu-id="de676-133">はい</span><span class="sxs-lookup"><span data-stu-id="de676-133">Yes</span></span> | <span data-ttu-id="de676-134">はい</span><span class="sxs-lookup"><span data-stu-id="de676-134">Yes</span></span> | <span data-ttu-id="de676-135">近日対応予定</span><span class="sxs-lookup"><span data-stu-id="de676-135">Coming soon</span></span>| <span data-ttu-id="de676-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="de676-136">No</span></span> |
| <span data-ttu-id="de676-137">通話の保留を解除する</span><span class="sxs-lookup"><span data-stu-id="de676-137">Retrieve a parked call</span></span> | <span data-ttu-id="de676-138">はい</span><span class="sxs-lookup"><span data-stu-id="de676-138">Yes</span></span> | <span data-ttu-id="de676-139">はい</span><span class="sxs-lookup"><span data-stu-id="de676-139">Yes</span></span> | <span data-ttu-id="de676-140">はい</span><span class="sxs-lookup"><span data-stu-id="de676-140">Yes</span></span> | <span data-ttu-id="de676-141">はい</span><span class="sxs-lookup"><span data-stu-id="de676-141">Yes</span></span> | <span data-ttu-id="de676-142">近日対応予定</span><span class="sxs-lookup"><span data-stu-id="de676-142">Coming soon</span></span>| <span data-ttu-id="de676-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="de676-143">No</span></span> |
| <span data-ttu-id="de676-144">未解除通話のかけ直し</span><span class="sxs-lookup"><span data-stu-id="de676-144">Unretrieved call ring back</span></span> | <span data-ttu-id="de676-145">はい</span><span class="sxs-lookup"><span data-stu-id="de676-145">Yes</span></span> | <span data-ttu-id="de676-146">はい</span><span class="sxs-lookup"><span data-stu-id="de676-146">Yes</span></span> | <span data-ttu-id="de676-147">はい</span><span class="sxs-lookup"><span data-stu-id="de676-147">Yes</span></span> | <span data-ttu-id="de676-148">はい</span><span class="sxs-lookup"><span data-stu-id="de676-148">Yes</span></span> | <span data-ttu-id="de676-149">近日対応予定</span><span class="sxs-lookup"><span data-stu-id="de676-149">Coming soon</span></span>| <span data-ttu-id="de676-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="de676-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="de676-151">コール パークおよび保留解除を構成する</span><span class="sxs-lookup"><span data-stu-id="de676-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="de676-152">コール パークおよび保留解除を構成するには管理者である必要があり、この機能は既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="de676-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="de676-153">コール パーク ポリシーを使用して、ユーザーに対して有効にしたり、ユーザー グループを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="de676-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="de676-154">一連のユーザーに同じポリシーを適用すると、そのユーザーの間で通話を保留したり、保留を解除したりできます。</span><span class="sxs-lookup"><span data-stu-id="de676-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="de676-155">ユーザーのコール パークを構成したり、コール パーク ユーザー グループを作成したりするには、この下の「[コール パーク ポリシーを割り当てる](#assign-a-call-park-policy)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="de676-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="de676-156">コール パークおよび保留解除機能の使用方法の詳細については、「[Teams で通話を保留する](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de676-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="de676-157">コール パーク ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="de676-157">Enable a call park policy</span></span>

<span data-ttu-id="de676-158">コール パーク ポリシーを有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de676-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="de676-159">**[Microsoft Teams 管理センター]** > **[音声]** > **[コール パーク ポリシー]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="de676-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="de676-160">**[新しいポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de676-160">Select **New policy**.</span></span>
3. <span data-ttu-id="de676-161">ポリシーに名前を付け、次に **[コール パークを許可]** を **[オン]** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="de676-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="de676-162">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de676-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="de676-163">コール パーク ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="de676-163">Assign a call park policy</span></span>

<span data-ttu-id="de676-164">1 人以上のユーザーにコール パーク ポリシーを割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de676-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="de676-165">**[Microsoft Teams 管理センター]** > **[音声]** > **[コール パーク ポリシー]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="de676-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="de676-166">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="de676-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="de676-167">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de676-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="de676-168">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de676-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="de676-169">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="de676-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="de676-170">ユーザーの追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de676-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="de676-171">PowerShell を使用してコール パークおよび保留解除を構成する</span><span class="sxs-lookup"><span data-stu-id="de676-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="de676-172">[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用して、コール パーク ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="de676-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="de676-173">[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用して、コール パーク ポリシーを付与します。</span><span class="sxs-lookup"><span data-stu-id="de676-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="de676-174">[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) を使用して既定の設定を変更するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="de676-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="de676-175">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="de676-175">Troubleshooting</span></span>

<span data-ttu-id="de676-176">ユーザーが [パーク] または [取得] ボタンを表示できない場合:</span><span class="sxs-lookup"><span data-stu-id="de676-176">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="de676-177">ユーザーがコール パーク ポリシーを有効にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de676-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="de676-178">ユーザーが通話の保留を解除しようとしても失敗した場合は、次の点を確認します:</span><span class="sxs-lookup"><span data-stu-id="de676-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="de676-179">ユーザーが Teams クライアントまたは Teams が有効なデバイス/スマートフォンを使用していることを確認します</span><span class="sxs-lookup"><span data-stu-id="de676-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="de676-180">グループ – ユーザーが、同じ Teams コール パーク ポリシーが割り当てられている、コール パーク グループのメンバーであるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="de676-180">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="de676-181">アイランド モード – コール パークおよび保留解除は、Teams アイランド モードでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="de676-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="de676-182">通話は既に保留解除または終了しています。</span><span class="sxs-lookup"><span data-stu-id="de676-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="de676-183">詳細情報</span><span class="sxs-lookup"><span data-stu-id="de676-183">More information</span></span>

<span data-ttu-id="de676-184">[Teams で通話を保留する](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="de676-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>
