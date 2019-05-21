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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '[コールパーク] を使って、クラウドの Teams サービスで通話を保留にします。'
ms.openlocfilehash: fc33ef6c36a9764e39840f384dc70aa1a692579c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283502"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="87864-103">Microsoft Teams でのコール パークおよび保留解除</span><span class="sxs-lookup"><span data-stu-id="87864-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="87864-104">[コールパーク] と [取得] は、ユーザーがクラウドの Teams サービスで通話を保留できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="87864-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="87864-105">通話が保留中の場合、サービスは通話の取得用に一意のコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="87864-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="87864-106">通話または他のユーザーが、そのコードとサポートされているアプリまたはデバイスを使って通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="87864-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="87864-107">コールパークを使用する一般的なシナリオには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="87864-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="87864-108">受付係は、工場で仕事をしている人のために電話をかけます。</span><span class="sxs-lookup"><span data-stu-id="87864-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="87864-109">次に、受付によって、通話とコード番号がパブリックアドレスシステム経由でアナウンスされます。</span><span class="sxs-lookup"><span data-stu-id="87864-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="87864-110">次に、通話を発信しているユーザーは、工場のフロアで Teams 電話を選択して、通話を取得するためのコードを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="87864-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="87864-111">デバイスのバッテリーの電力が不足しているため、ユーザーがモバイルデバイスで通話をパークしています。</span><span class="sxs-lookup"><span data-stu-id="87864-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="87864-112">次に、ユーザーはコードを入力して、Teams 卓上電話から通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="87864-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="87864-113">サポート担当者は、顧客からの通話をパークし、専門家が通話を取得して顧客を支援するためにチームチャネルでお知らせを送信します。</span><span class="sxs-lookup"><span data-stu-id="87864-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="87864-114">エキスパートが Teams クライアントにコードを入力して通話を取得する</span><span class="sxs-lookup"><span data-stu-id="87864-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87864-115">この機能は、Teams のみの展開モードでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="87864-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="87864-116">Teams の展開モードの詳細については、「 [Microsoft Teams と Skype For business の共存と相互運用性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87864-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="87864-117">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="87864-117">License required</span></span>

<span data-ttu-id="87864-118">通話をパークして取得するには、ユーザーはエンタープライズボイスユーザーである必要があります。管理者は、ユーザーにコールパークポリシーを与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="87864-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="87864-119">ライセンスモデルの詳細については、「 [Microsoft Teams の Office 365 ライセンス](office-365-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87864-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="87864-120">通話パークと機能の可用性の取得</span><span class="sxs-lookup"><span data-stu-id="87864-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="87864-121">コールパークと取得は、現在次のクライアントとデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87864-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="87864-122">(チーム専用モードでサポートされています。 PSTN 接続の有無はサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="87864-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="87864-123">機能</span><span class="sxs-lookup"><span data-stu-id="87864-123">Capability</span></span> | <span data-ttu-id="87864-124">Teams のデスクトップ</span><span class="sxs-lookup"><span data-stu-id="87864-124">Teams Desktop</span></span> | <span data-ttu-id="87864-125">Teams Mac アプリ</span><span class="sxs-lookup"><span data-stu-id="87864-125">Teams Mac App</span></span> | <span data-ttu-id="87864-126">Teams Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="87864-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="87864-127">Teams mobile iOS/Android アプリ</span><span class="sxs-lookup"><span data-stu-id="87864-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="87864-128">Teams の IP 電話</span><span class="sxs-lookup"><span data-stu-id="87864-128">Teams IP phone</span></span> | <span data-ttu-id="87864-129">Skype for Business の IP 電話</span><span class="sxs-lookup"><span data-stu-id="87864-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="87864-130">通話をパークする</span><span class="sxs-lookup"><span data-stu-id="87864-130">Park a call</span></span> | <span data-ttu-id="87864-131">はい</span><span class="sxs-lookup"><span data-stu-id="87864-131">Yes</span></span> | <span data-ttu-id="87864-132">はい</span><span class="sxs-lookup"><span data-stu-id="87864-132">Yes</span></span> | <span data-ttu-id="87864-133">はい</span><span class="sxs-lookup"><span data-stu-id="87864-133">Yes</span></span> | <span data-ttu-id="87864-134">はい</span><span class="sxs-lookup"><span data-stu-id="87864-134">Yes</span></span> | <span data-ttu-id="87864-135">もうすぐです</span><span class="sxs-lookup"><span data-stu-id="87864-135">Coming soon</span></span>| <span data-ttu-id="87864-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="87864-136">No</span></span> |
| <span data-ttu-id="87864-137">保留中の通話を取得する</span><span class="sxs-lookup"><span data-stu-id="87864-137">Retrieve a parked call</span></span> | <span data-ttu-id="87864-138">はい</span><span class="sxs-lookup"><span data-stu-id="87864-138">Yes</span></span> | <span data-ttu-id="87864-139">はい</span><span class="sxs-lookup"><span data-stu-id="87864-139">Yes</span></span> | <span data-ttu-id="87864-140">はい</span><span class="sxs-lookup"><span data-stu-id="87864-140">Yes</span></span> | <span data-ttu-id="87864-141">はい</span><span class="sxs-lookup"><span data-stu-id="87864-141">Yes</span></span> | <span data-ttu-id="87864-142">もうすぐです</span><span class="sxs-lookup"><span data-stu-id="87864-142">Coming soon</span></span>| <span data-ttu-id="87864-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="87864-143">No</span></span> |
| <span data-ttu-id="87864-144">着信コールバックの取り消し</span><span class="sxs-lookup"><span data-stu-id="87864-144">Unretrieved call ring back</span></span> | <span data-ttu-id="87864-145">はい</span><span class="sxs-lookup"><span data-stu-id="87864-145">Yes</span></span> | <span data-ttu-id="87864-146">はい</span><span class="sxs-lookup"><span data-stu-id="87864-146">Yes</span></span> | <span data-ttu-id="87864-147">はい</span><span class="sxs-lookup"><span data-stu-id="87864-147">Yes</span></span> | <span data-ttu-id="87864-148">はい</span><span class="sxs-lookup"><span data-stu-id="87864-148">Yes</span></span> | <span data-ttu-id="87864-149">もうすぐです</span><span class="sxs-lookup"><span data-stu-id="87864-149">Coming soon</span></span>| <span data-ttu-id="87864-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="87864-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="87864-151">コールパークと取得の構成</span><span class="sxs-lookup"><span data-stu-id="87864-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="87864-152">コールパークを構成して取得するには、管理者である必要があります。この機能は、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="87864-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="87864-153">ユーザーに対して有効にし、[コールパーク] ポリシーを使用してユーザーグループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="87864-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="87864-154">同じポリシーを一連のユーザーに適用すると、その間で通話をパークして取得することができます。</span><span class="sxs-lookup"><span data-stu-id="87864-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="87864-155">ユーザー用のコールパークを構成し、コールパークのユーザーグループを作成するには、以下の「[コールパークポリシーの割り当て](#assign-a-call-park-policy)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="87864-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="87864-156">コールパークを使用して機能を取得する方法については、「 [Teams で通話をパーク](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87864-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="87864-157">コールパークポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="87864-157">Enable a call park policy</span></span>

<span data-ttu-id="87864-158">次の手順に従って、コールパークポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="87864-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="87864-159">**Microsoft Teams 管理センター** > の**音声** > **通話パークポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="87864-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="87864-160">[**新しいポリシー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="87864-160">Select **New policy**.</span></span>
3. <span data-ttu-id="87864-161">ポリシーに名前を付け、[ **Call パークを有効**にする\*\*\*\*] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="87864-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="87864-162">[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="87864-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="87864-163">コールパークポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="87864-163">Assign a call park policy</span></span>

<span data-ttu-id="87864-164">次の手順に従って、1人以上のユーザーにコールパークポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="87864-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="87864-165">**Microsoft Teams 管理センター** > の**音声** > **通話パークポリシー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="87864-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="87864-166">ポリシー名の左側をクリックして、ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="87864-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="87864-167">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="87864-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="87864-168">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87864-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="87864-169">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="87864-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="87864-170">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87864-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="87864-171">PowerShell を使用したコールパークと取得の構成</span><span class="sxs-lookup"><span data-stu-id="87864-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="87864-172">[新しい-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用して、コールパークポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="87864-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="87864-173">コールパークポリシーを付与するには、 [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="87864-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="87864-174">既定の設定を変更するには、次のように、 [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)を使用します。</span><span class="sxs-lookup"><span data-stu-id="87864-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="87864-175">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="87864-175">Troubleshooting</span></span>

<span data-ttu-id="87864-176">ユーザーが [パーク] または [取得] ボタンを表示できない場合:</span><span class="sxs-lookup"><span data-stu-id="87864-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="87864-177">ユーザーがコールパークポリシーを有効にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="87864-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="87864-178">ユーザーが通話を取得しようとして失敗した場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="87864-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="87864-179">ユーザーがチームクライアントまたはチーム対応デバイス/スマートフォンを使用していることを確認する</span><span class="sxs-lookup"><span data-stu-id="87864-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="87864-180">グループ化–ユーザーは [コールパーク] グループのメンバーになっていますか?</span><span class="sxs-lookup"><span data-stu-id="87864-180">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="87864-181">アイランドモード– Teams アイランドモードでは、コールパークと取得は利用できません。</span><span class="sxs-lookup"><span data-stu-id="87864-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="87864-182">通話は既に取得または終了されています。</span><span class="sxs-lookup"><span data-stu-id="87864-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="87864-183">詳細情報</span><span class="sxs-lookup"><span data-stu-id="87864-183">More information</span></span>

<span data-ttu-id="87864-184">[Teams で通話をパーク](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)します。</span><span class="sxs-lookup"><span data-stu-id="87864-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>