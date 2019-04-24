---
title: Microsoft Teams での回線共有機能
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
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
description: 共有行の外観は、回答や、ユーザーに代わって呼び出しを処理する代理人を選択するユーザーをことができます。
ms.openlocfilehash: d16fe4b3241e814609999d8068ee47743bfca516
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204492"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="adcd5-103">Microsoft Teams での回線共有機能</span><span class="sxs-lookup"><span data-stu-id="adcd5-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="adcd5-104">共有行の外観は、回答や、ユーザーに代わって呼び出しを処理する代理人を選択するユーザーをできるようにする委任の機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="adcd5-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="adcd5-105">この機能は、ユーザーが定期的にユーザーの呼び出しを処理している管理アシスタントを持っている場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="adcd5-105">This feature is helpful if a user has an administrative assistant who regularly handles the user’s calls.</span></span> <span data-ttu-id="adcd5-106">外観の回線を共有するのでは、マネージャーは、他のユーザーを承認するか、ユーザーに代わって呼び出しを受信するデリゲートと、デリゲートが作成および他のユーザーに代わって呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="adcd5-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adcd5-107">この機能は、配置モードのチームのみで利用可能なだけです。</span><span class="sxs-lookup"><span data-stu-id="adcd5-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="adcd5-108">チームの展開方法の詳細については、[マイクロソフト チームの理解と Skype ビジネスの共存と相互運用性を](teams-and-skypeforbusiness-coexistence-and-interoperability.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="adcd5-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="adcd5-109">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="adcd5-109">License required</span></span>

<span data-ttu-id="adcd5-110">ユーザーは、代理人または委任を設定または、ユーザーに代わって呼び出しを受信する他のユーザーを有効にすると、エンタープライズ ボイスのユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="adcd5-110">A user must be an enterprise voice user to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="adcd5-111">管理者と代理人の両方は、エンタープライズ ボイスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="adcd5-111">Both managers and delegates need to be enterprise voice enabled.</span></span> <span data-ttu-id="adcd5-112">回線を共有する経験は、委任の一部であるし、追加ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="adcd5-112">The shared line experience is part of delegation, and requires no additional license.</span></span> <span data-ttu-id="adcd5-113">ライセンス ・ モデルの詳細については、 [Office 365 は、マイクロソフトのチームのライセンス](office-365-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adcd5-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="adcd5-114">委任、および共有の線の外観を構成します。</span><span class="sxs-lookup"><span data-stu-id="adcd5-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="adcd5-115">委任と回線を共有する外観は、ユーザーによる機能: 構成するのには管理者の設定はありません。</span><span class="sxs-lookup"><span data-stu-id="adcd5-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="adcd5-116">機能を使用する方法の詳細については、[代理人に電話回線の共有](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adcd5-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="adcd5-117">テナント管理は、作業には、この機能の**TeamsCallingPolicy の AllowDelegation**設定を使用して委任を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="adcd5-117">The tenant admin should enable delegation via the **TeamsCallingPolicy AllowDelegation** setting for this feature to work.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="adcd5-118">行の外観の機能の可用性を共有</span><span class="sxs-lookup"><span data-stu-id="adcd5-118">Shared line appearance feature availability</span></span>

<span data-ttu-id="adcd5-119">共有行の外観は、現在、次のアプリケーションとデバイスです。</span><span class="sxs-lookup"><span data-stu-id="adcd5-119">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="adcd5-120">機能</span><span class="sxs-lookup"><span data-stu-id="adcd5-120">Capability</span></span> | <span data-ttu-id="adcd5-121">チームのデスクトップ</span><span class="sxs-lookup"><span data-stu-id="adcd5-121">Teams Desktop</span></span> | <span data-ttu-id="adcd5-122">チームの Mac アプリケーション</span><span class="sxs-lookup"><span data-stu-id="adcd5-122">Teams Mac App</span></span> | <span data-ttu-id="adcd5-123">チームの Web アプリケーション (エッジ)</span><span class="sxs-lookup"><span data-stu-id="adcd5-123">Teams Web App (Edge)</span></span> |<span data-ttu-id="adcd5-124">チーム モバイル iOS と Android アプリ</span><span class="sxs-lookup"><span data-stu-id="adcd5-124">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="adcd5-125">チームの IP 電話</span><span class="sxs-lookup"><span data-stu-id="adcd5-125">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="adcd5-126">委任を設定します</span><span class="sxs-lookup"><span data-stu-id="adcd5-126">Set up delegation</span></span> | <span data-ttu-id="adcd5-127">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-127">Yes</span></span> | <span data-ttu-id="adcd5-128">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-128">Yes</span></span> | <span data-ttu-id="adcd5-129">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-129">Yes</span></span> | <span data-ttu-id="adcd5-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="adcd5-130">No</span></span> | <span data-ttu-id="adcd5-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="adcd5-131">No</span></span> |
| <span data-ttu-id="adcd5-132">代理人の呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="adcd5-132">Receive calls on behalf of another</span></span> | <span data-ttu-id="adcd5-133">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-133">Yes</span></span> | <span data-ttu-id="adcd5-134">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-134">Yes</span></span> | <span data-ttu-id="adcd5-135">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-135">Yes</span></span> | <span data-ttu-id="adcd5-136">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-136">Yes</span></span> | <span data-ttu-id="adcd5-137">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-137">Yes</span></span> |
| <span data-ttu-id="adcd5-138">代理人の電話番号を呼び出す</span><span class="sxs-lookup"><span data-stu-id="adcd5-138">Call a phone number on behalf of another</span></span> | <span data-ttu-id="adcd5-139">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-139">Yes</span></span> | <span data-ttu-id="adcd5-140">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-140">Yes</span></span> | <span data-ttu-id="adcd5-141">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-141">Yes</span></span> | <span data-ttu-id="adcd5-142">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-142">Yes</span></span> | <span data-ttu-id="adcd5-143">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-143">Yes</span></span> |
| <span data-ttu-id="adcd5-144">代理人のチームのユーザーを呼び出し</span><span class="sxs-lookup"><span data-stu-id="adcd5-144">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="adcd5-145">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-145">Yes</span></span> | <span data-ttu-id="adcd5-146">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-146">Yes</span></span> | <span data-ttu-id="adcd5-147">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-147">Yes</span></span> | <span data-ttu-id="adcd5-148">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-148">Yes</span></span> | <span data-ttu-id="adcd5-149">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-149">Yes</span></span> |
| <span data-ttu-id="adcd5-150">共有回線の管理ビューを参照してください。</span><span class="sxs-lookup"><span data-stu-id="adcd5-150">See the admin view of shared lines</span></span> | <span data-ttu-id="adcd5-151">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-151">Yes</span></span> | <span data-ttu-id="adcd5-152">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-152">Yes</span></span> | <span data-ttu-id="adcd5-153">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-153">Yes</span></span> | <span data-ttu-id="adcd5-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="adcd5-154">No</span></span> | <span data-ttu-id="adcd5-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="adcd5-155">No</span></span> |
| <span data-ttu-id="adcd5-156">マネージャーの待機活動の管理ビューを参照してください。</span><span class="sxs-lookup"><span data-stu-id="adcd5-156">See the admin view of manager's call activities</span></span> | <span data-ttu-id="adcd5-157">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-157">Yes</span></span> | <span data-ttu-id="adcd5-158">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-158">Yes</span></span> | <span data-ttu-id="adcd5-159">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-159">Yes</span></span> | <span data-ttu-id="adcd5-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="adcd5-160">No</span></span> | <span data-ttu-id="adcd5-161">いいえ</span><span class="sxs-lookup"><span data-stu-id="adcd5-161">No</span></span> |
| <span data-ttu-id="adcd5-162">代理人のマネージャーのビューを参照してください。</span><span class="sxs-lookup"><span data-stu-id="adcd5-162">See the manager view of delegates</span></span> | <span data-ttu-id="adcd5-163">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-163">Yes</span></span> | <span data-ttu-id="adcd5-164">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-164">Yes</span></span> | <span data-ttu-id="adcd5-165">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-165">Yes</span></span> | <span data-ttu-id="adcd5-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="adcd5-166">No</span></span> | <span data-ttu-id="adcd5-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="adcd5-167">No</span></span> |
| <span data-ttu-id="adcd5-168">管理者またはマネージャーを保持したり、再開</span><span class="sxs-lookup"><span data-stu-id="adcd5-168">Admin or manager can hold or resume</span></span> | <span data-ttu-id="adcd5-169">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-169">Yes</span></span> | <span data-ttu-id="adcd5-170">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-170">Yes</span></span> | <span data-ttu-id="adcd5-171">はい</span><span class="sxs-lookup"><span data-stu-id="adcd5-171">Yes</span></span> | <span data-ttu-id="adcd5-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="adcd5-172">No</span></span> | <span data-ttu-id="adcd5-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="adcd5-173">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="adcd5-174">制限</span><span class="sxs-lookup"><span data-stu-id="adcd5-174">Limitations</span></span>

<span data-ttu-id="adcd5-175">マネージャーは、25 の代理人まで追加でき、代理人は、最大 25 個のマネージャーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="adcd5-175">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="adcd5-176">テナントが作成されることができます委任関係の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="adcd5-176">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="adcd5-177">委任者と代理人が同じ地理的な場所にない場合は、(上の人の代理) に委任された呼び出しを別の地理的な場所から表示するのには発信者番号通知を許可するのには、PSTN のプロバイダーの役目です。</span><span class="sxs-lookup"><span data-stu-id="adcd5-177">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="adcd5-178">詳細情報</span><span class="sxs-lookup"><span data-stu-id="adcd5-178">More information</span></span>

[<span data-ttu-id="adcd5-179">代理人と電話回線を共有します。</span><span class="sxs-lookup"><span data-stu-id="adcd5-179">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
