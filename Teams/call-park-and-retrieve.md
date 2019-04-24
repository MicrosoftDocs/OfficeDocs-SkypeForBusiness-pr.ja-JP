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
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: チームのクラウド サービスに保留中の通話をパークおよび取得を使用します。
ms.openlocfilehash: 798e53ef9a0638be659da8567419b7bd3d3c3555
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211839"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="1f2e5-103">Microsoft Teams でのコール パークおよび保留解除</span><span class="sxs-lookup"><span data-stu-id="1f2e5-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="1f2e5-104">パークおよび取得は、チームのクラウド サービスに保留中の呼び出しを行うユーザーをできるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="1f2e5-105">呼び出しが駐機している場合、サービスは、呼び出しを取得するための一意のコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="1f2e5-106">呼び出しまたは他のユーザーを保持しているユーザーは、呼び出しを取得するのにコード、およびサポートされているアプリケーションまたはデバイスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="1f2e5-107">コール パークを使用するための一般的なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="1f2e5-108">工場で作業しているユーザのための呼び出し必要事項を受付係。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="1f2e5-109">受付係では、パブリック アドレス システムを呼び出し、コード番号を発表します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="1f2e5-110">ユーザー呼び出しの工場チームの電話を選択し、呼び出しを取得するコードを入力してください。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="1f2e5-111">デバイスのバッテリの電源が不足しているために、ユーザーの事項をモバイル デバイス上の呼び出し。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="1f2e5-112">ユーザーは、チームの机上電話からの呼び出しを取得するコードを入力できます。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="1f2e5-113">サポートの代表的な公園顧客は、呼び出しし、呼び出しを取得し、お客様を支援する専門家のチームのチャンネルでお知らせを送信します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="1f2e5-114">専門家の呼び出しを取得するためにチームのクライアントのコードが入力されます。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f2e5-115">この機能は、配置モードのチームのみで利用可能なだけです。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="1f2e5-116">チームの展開方法の詳細については、[マイクロソフト チームの理解と Skype ビジネスの共存と相互運用性を](teams-and-skypeforbusiness-coexistence-and-interoperability.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="1f2e5-117">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="1f2e5-117">License required</span></span>

<span data-ttu-id="1f2e5-118">駐機し、呼び出しを取得、ユーザーが、エンタープライズ VoIP のユーザーをする必要があり、管理者が、コール パークのポリシーにはユーザーの与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="1f2e5-119">ライセンス ・ モデルの詳細については、 [Office 365 は、マイクロソフトのチームのライセンス](office-365-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="1f2e5-120">公園を呼び出すし、使用可能な機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="1f2e5-121">パークおよび取得は、現在、次のクライアントとデバイスです。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="1f2e5-122">(チームのみのモードで、PSTN への接続の有無にかかわらずサポート)。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="1f2e5-123">機能</span><span class="sxs-lookup"><span data-stu-id="1f2e5-123">Capability</span></span> | <span data-ttu-id="1f2e5-124">チームのデスクトップ</span><span class="sxs-lookup"><span data-stu-id="1f2e5-124">Teams Desktop</span></span> | <span data-ttu-id="1f2e5-125">チームの Mac アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1f2e5-125">Teams Mac App</span></span> | <span data-ttu-id="1f2e5-126">チームの Web アプリケーション (エッジ)</span><span class="sxs-lookup"><span data-stu-id="1f2e5-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="1f2e5-127">チーム モバイル iOS と Android アプリ</span><span class="sxs-lookup"><span data-stu-id="1f2e5-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="1f2e5-128">チームの IP 電話</span><span class="sxs-lookup"><span data-stu-id="1f2e5-128">Teams IP phone</span></span> | <span data-ttu-id="1f2e5-129">ビジネス IP 電話の Skype</span><span class="sxs-lookup"><span data-stu-id="1f2e5-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="1f2e5-130">公園の呼び出し</span><span class="sxs-lookup"><span data-stu-id="1f2e5-130">Park a call</span></span> | <span data-ttu-id="1f2e5-131">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-131">Yes</span></span> | <span data-ttu-id="1f2e5-132">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-132">Yes</span></span> | <span data-ttu-id="1f2e5-133">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-133">Yes</span></span> | <span data-ttu-id="1f2e5-134">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-134">Yes</span></span> | <span data-ttu-id="1f2e5-135">もうすぐです</span><span class="sxs-lookup"><span data-stu-id="1f2e5-135">Coming soon</span></span>| <span data-ttu-id="1f2e5-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="1f2e5-136">No</span></span> |
| <span data-ttu-id="1f2e5-137">停止の呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-137">Retrieve a parked call</span></span> | <span data-ttu-id="1f2e5-138">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-138">Yes</span></span> | <span data-ttu-id="1f2e5-139">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-139">Yes</span></span> | <span data-ttu-id="1f2e5-140">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-140">Yes</span></span> | <span data-ttu-id="1f2e5-141">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-141">Yes</span></span> | <span data-ttu-id="1f2e5-142">もうすぐです</span><span class="sxs-lookup"><span data-stu-id="1f2e5-142">Coming soon</span></span>| <span data-ttu-id="1f2e5-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="1f2e5-143">No</span></span> |
| <span data-ttu-id="1f2e5-144">Unretrieved の通話の呼び出しに戻る</span><span class="sxs-lookup"><span data-stu-id="1f2e5-144">Unretrieved call ring back</span></span> | <span data-ttu-id="1f2e5-145">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-145">Yes</span></span> | <span data-ttu-id="1f2e5-146">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-146">Yes</span></span> | <span data-ttu-id="1f2e5-147">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-147">Yes</span></span> | <span data-ttu-id="1f2e5-148">はい</span><span class="sxs-lookup"><span data-stu-id="1f2e5-148">Yes</span></span> | <span data-ttu-id="1f2e5-149">もうすぐです</span><span class="sxs-lookup"><span data-stu-id="1f2e5-149">Coming soon</span></span>| <span data-ttu-id="1f2e5-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="1f2e5-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="1f2e5-151">パークおよび取得を構成します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="1f2e5-152">コール パークと取得を構成する管理者をする必要があり、機能が既定で無効にします。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="1f2e5-153">ユーザーに対して有効にし、コール パークのポリシーを使用してユーザー グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="1f2e5-154">一連のユーザーに同じポリシーを適用するとき、駐車し、自体の間での呼び出しを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="1f2e5-155">ユーザーのコール パークを構成し、コール パークのユーザー ・ グループを作成、以下の[コール パークのポリシーを割り当てる](#assign-a-call-park-policy)手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="1f2e5-156">コール パークを使用し、機能を取得する方法の詳細については、[公園のチームでの呼び出し](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="1f2e5-157">コール パークのポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-157">Enable a call park policy</span></span>

<span data-ttu-id="1f2e5-158">コール パークのポリシーを有効にするのには次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="1f2e5-159">**マイクロソフトのチーム管理センター**を参照して > **音声** > **公園のポリシーを呼び出します**。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="1f2e5-160">**新しいポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-160">Select **New policy**.</span></span>
3. <span data-ttu-id="1f2e5-161">ポリシーの名前を入力し、**公園の呼び出しを許可するの**に切り替える**に**します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="1f2e5-162">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="1f2e5-163">コール パークのポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1f2e5-163">Assign a call park policy</span></span>

<span data-ttu-id="1f2e5-164">コール パークのポリシーを 1 つまたは複数のユーザーに割り当てるには次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="1f2e5-165">**マイクロソフトのチーム管理センター**を参照して > **音声** > **公園のポリシーを呼び出します**。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="1f2e5-166">ポリシーを選択するには、ポリシー名の左側にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="1f2e5-167">**ユーザーの管理**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="1f2e5-168">**ユーザーの管理**ウィンドウで、表示名、ユーザー名、ユーザーの検索、名を選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="1f2e5-169">追加するユーザーごとにこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="1f2e5-170">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="1f2e5-171">コール パークを構成して、PowerShell を使用して取得</span><span class="sxs-lookup"><span data-stu-id="1f2e5-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="1f2e5-172">[新規 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)の PowerShell コマンドレットを使用すると、コール パークのポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="1f2e5-173">コール パークのポリシーを付与するのに[Grant CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="1f2e5-174">[セット CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)を使用して次のように、既定の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="1f2e5-175">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1f2e5-175">Troubleshooting</span></span>

<span data-ttu-id="1f2e5-176">ユーザーは、公園を参照してくださいか、ボタンを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="1f2e5-177">パーク ポリシーの有効化をユーザーが持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="1f2e5-178">ユーザーの呼び出しを取得しようとしてくださいが成功しない場合は、以下を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="1f2e5-179">ユーザーがチームのクライアントやチームが有効なデバイスと電話を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="1f2e5-180">グループ – は、ユーザーのコール パークのグループのメンバーですか。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-180">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="1f2e5-181">島モード – パークおよび取得は、チーム島モードで使用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="1f2e5-182">呼び出しは既に取得または終了します。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="1f2e5-183">詳細情報</span><span class="sxs-lookup"><span data-stu-id="1f2e5-183">More information</span></span>

<span data-ttu-id="1f2e5-184">[公園チームでの呼び出し](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="1f2e5-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>