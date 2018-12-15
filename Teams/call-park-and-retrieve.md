---
title: 公園を呼び出すし、マイクロソフトのチームで取得
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/13/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: チームのクラウド サービスに保留中の通話をパークおよび取得を使用します。
ms.openlocfilehash: 02ec2b3af52cac65f82f5f0f0fc2b4b54ae61369
ms.sourcegitcommit: 5f7e078125f810a9e9a89052854ef63916afe7d3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "27283160"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="caea5-103">公園を呼び出すし、マイクロソフトのチームで取得</span><span class="sxs-lookup"><span data-stu-id="caea5-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="caea5-104">パークおよび取得は、チームのクラウド サービスに保留中の呼び出しを行うユーザーをできるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="caea5-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="caea5-105">呼び出しが駐機している場合、サービスは、呼び出しを取得するための一意のコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="caea5-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="caea5-106">呼び出しまたは他のユーザーを保持しているユーザーは、呼び出しを取得するのにコード、およびサポートされているアプリケーションまたはデバイスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="caea5-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="caea5-107">コール パークを使用するための一般的なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="caea5-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="caea5-108">工場で作業しているユーザのための呼び出し必要事項を受付係。</span><span class="sxs-lookup"><span data-stu-id="caea5-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="caea5-109">受付係では、パブリック アドレス システムを呼び出し、コード番号を発表します。</span><span class="sxs-lookup"><span data-stu-id="caea5-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="caea5-110">ユーザー呼び出しの工場チームの電話を選択し、呼び出しを取得するコードを入力してください。</span><span class="sxs-lookup"><span data-stu-id="caea5-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="caea5-111">デバイスのバッテリの電源が不足しているために、ユーザーの事項をモバイル デバイス上の呼び出し。</span><span class="sxs-lookup"><span data-stu-id="caea5-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="caea5-112">ユーザーことができますしを入力し、チームの机上電話からの呼び出しを取得するコードです。</span><span class="sxs-lookup"><span data-stu-id="caea5-112">The user can then enter then code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="caea5-113">サポートの代表的な公園顧客は、呼び出しし、呼び出しを取得し、お客様を支援する専門家のチームのチャンネルでお知らせを送信します。</span><span class="sxs-lookup"><span data-stu-id="caea5-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="caea5-114">専門家の呼び出しを取得するためにチームのクライアントのコードが入力されます。</span><span class="sxs-lookup"><span data-stu-id="caea5-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="caea5-115">この機能は、配置モードのチームのみで利用可能なだけです。</span><span class="sxs-lookup"><span data-stu-id="caea5-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="caea5-116">チームの展開方法の詳細については、[マイクロソフト チームの理解と Skype ビジネスの共存と相互運用性を](teams-and-skypeforbusiness-coexistence-and-interoperability.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="caea5-116">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="caea5-117">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="caea5-117">License required</span></span>

<span data-ttu-id="caea5-118">駐機し、呼び出しを取得、ユーザーが、エンタープライズ VoIP のユーザーをする必要があり、管理者が、コール パークのポリシーにはユーザーの与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="caea5-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="caea5-119">ライセンス ・ モデルの詳細については、 [Office 365 は、マイクロソフトのチームのライセンス](office-365-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caea5-119">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="caea5-120">公園を呼び出すし、使用可能な機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="caea5-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="caea5-121">パークおよび取得は、現在、次のクライアントとデバイスです。</span><span class="sxs-lookup"><span data-stu-id="caea5-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="caea5-122">(チームのみのモードで、PSTN への接続の有無にかかわらずサポート)。</span><span class="sxs-lookup"><span data-stu-id="caea5-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="caea5-123">機能</span><span class="sxs-lookup"><span data-stu-id="caea5-123">Capability</span></span> | <span data-ttu-id="caea5-124">チームのデスクトップ</span><span class="sxs-lookup"><span data-stu-id="caea5-124">Teams Desktop</span></span> | <span data-ttu-id="caea5-125">チームの Mac アプリケーション</span><span class="sxs-lookup"><span data-stu-id="caea5-125">Teams Mac App</span></span> | <span data-ttu-id="caea5-126">チームの Web アプリケーション (エッジ)</span><span class="sxs-lookup"><span data-stu-id="caea5-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="caea5-127">チーム モバイル iOS と Android アプリ</span><span class="sxs-lookup"><span data-stu-id="caea5-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="caea5-128">チームの IP 電話</span><span class="sxs-lookup"><span data-stu-id="caea5-128">Teams IP phone</span></span> | <span data-ttu-id="caea5-129">ビジネス IP 電話の Skype</span><span class="sxs-lookup"><span data-stu-id="caea5-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="caea5-130">公園の呼び出し</span><span class="sxs-lookup"><span data-stu-id="caea5-130">Park a call</span></span> | <span data-ttu-id="caea5-131">あり</span><span class="sxs-lookup"><span data-stu-id="caea5-131">Yes</span></span> | <span data-ttu-id="caea5-132">あり</span><span class="sxs-lookup"><span data-stu-id="caea5-132">Yes</span></span> | <span data-ttu-id="caea5-133">あり</span><span class="sxs-lookup"><span data-stu-id="caea5-133">Yes</span></span> | <span data-ttu-id="caea5-134">準備中</span><span class="sxs-lookup"><span data-stu-id="caea5-134">Coming soon</span></span> | <span data-ttu-id="caea5-135">準備中</span><span class="sxs-lookup"><span data-stu-id="caea5-135">Coming soon</span></span>| <span data-ttu-id="caea5-136">なし</span><span class="sxs-lookup"><span data-stu-id="caea5-136">No</span></span> |
| <span data-ttu-id="caea5-137">停止の呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="caea5-137">Retrieve a parked call</span></span> | <span data-ttu-id="caea5-138">あり</span><span class="sxs-lookup"><span data-stu-id="caea5-138">Yes</span></span> | <span data-ttu-id="caea5-139">あり</span><span class="sxs-lookup"><span data-stu-id="caea5-139">Yes</span></span> | <span data-ttu-id="caea5-140">あり</span><span class="sxs-lookup"><span data-stu-id="caea5-140">Yes</span></span> | <span data-ttu-id="caea5-141">準備中</span><span class="sxs-lookup"><span data-stu-id="caea5-141">Coming soon</span></span> | <span data-ttu-id="caea5-142">準備中</span><span class="sxs-lookup"><span data-stu-id="caea5-142">Coming soon</span></span>| <span data-ttu-id="caea5-143">なし</span><span class="sxs-lookup"><span data-stu-id="caea5-143">No</span></span> |
| <span data-ttu-id="caea5-144">取得されていない通話の呼び出しに戻る</span><span class="sxs-lookup"><span data-stu-id="caea5-144">Un-retrieved call ring back</span></span> | <span data-ttu-id="caea5-145">あり</span><span class="sxs-lookup"><span data-stu-id="caea5-145">Yes</span></span> | <span data-ttu-id="caea5-146">あり</span><span class="sxs-lookup"><span data-stu-id="caea5-146">Yes</span></span> | <span data-ttu-id="caea5-147">あり</span><span class="sxs-lookup"><span data-stu-id="caea5-147">Yes</span></span> | <span data-ttu-id="caea5-148">準備中</span><span class="sxs-lookup"><span data-stu-id="caea5-148">Coming soon</span></span> | <span data-ttu-id="caea5-149">準備中</span><span class="sxs-lookup"><span data-stu-id="caea5-149">Coming soon</span></span>| <span data-ttu-id="caea5-150">なし</span><span class="sxs-lookup"><span data-stu-id="caea5-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="caea5-151">パークおよび取得を構成します。</span><span class="sxs-lookup"><span data-stu-id="caea5-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="caea5-152">コール パークと取得を構成する管理者をする必要があり、機能が既定で無効にします。</span><span class="sxs-lookup"><span data-stu-id="caea5-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="caea5-153">ユーザーに対して有効にし、コール パークのポリシーを使用してユーザー グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="caea5-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="caea5-154">一連のユーザーに同じポリシーを適用すると、駐機し、自体の間での呼び出しを取得することがようになります。</span><span class="sxs-lookup"><span data-stu-id="caea5-154">When you apply the same policy to a set of users, they will be able to park and retrieve calls among themselves.</span></span> <span data-ttu-id="caea5-155">ユーザーのコール パークを構成し、コール パークのユーザー グループを作成、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="caea5-155">To configure call park for users and create call park user groups, follow the procedure below.</span></span>

<span data-ttu-id="caea5-156">コール パークを使用し、機能を取得する方法の詳細については、[公園のチームでの呼び出し](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caea5-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="caea5-157">コール パークを構成して、PowerShell を使用して取得</span><span class="sxs-lookup"><span data-stu-id="caea5-157">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="caea5-158">[新規 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)の PowerShell コマンドレットを使用すると、コール パークのポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="caea5-158">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="caea5-159">コール パークのポリシーを付与するのに[Grant CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="caea5-159">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="caea5-160">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="caea5-160">Troubleshooting</span></span>

<span data-ttu-id="caea5-161">ユーザーは、公園を参照してくださいか、ボタンを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="caea5-161">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="caea5-162">パーク ポリシーの有効化をユーザーが持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="caea5-162">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="caea5-163">ユーザーの呼び出しを取得しようとしてくださいが成功しない場合は、以下を確認します。</span><span class="sxs-lookup"><span data-stu-id="caea5-163">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="caea5-164">ユーザーがチームのクライアントやチームが有効なデバイスと電話を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="caea5-164">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="caea5-165">グループ – は、ユーザーのコール パークのグループのメンバーですか。</span><span class="sxs-lookup"><span data-stu-id="caea5-165">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="caea5-166">島モード – パークおよび取得は、チーム島モードで使用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="caea5-166">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="caea5-167">呼び出しは既に取得または終了します。</span><span class="sxs-lookup"><span data-stu-id="caea5-167">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="caea5-168">詳細情報</span><span class="sxs-lookup"><span data-stu-id="caea5-168">More information</span></span>

<span data-ttu-id="caea5-169">[公園チームでの呼び出し](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="caea5-169">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>