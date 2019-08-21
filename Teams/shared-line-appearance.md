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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
ms.custom:
- Phone System
description: '[共有の線の外観] を使うと、ユーザーは代理として応答するか、通話を処理するデリゲートを選ぶことができます。'
ms.openlocfilehash: 67708c05105b83cca80702292a1766a2224681bc
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483703"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="7da17-103">Microsoft Teams での回線共有機能</span><span class="sxs-lookup"><span data-stu-id="7da17-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="7da17-104">共有された線の外観は、委任機能の一部であり、ユーザーは代理として応答したり、通話を処理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="7da17-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="7da17-105">この機能は、ユーザーの通話を定期的に処理する管理アシスタントがある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="7da17-105">This feature is helpful if a user has an administrative assistant who regularly handles the user’s calls.</span></span> <span data-ttu-id="7da17-106">共有線の外観のコンテキストでは、マネージャーは代理人を代理として発信または受信するために代理人を承認し、代理人が他のユーザーの代わりに通話を発信および受信することができます。</span><span class="sxs-lookup"><span data-stu-id="7da17-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7da17-107">この機能は、Teams のみの展開モードでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="7da17-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="7da17-108">Teams の展開モードの詳細については、「 [Microsoft teams と Skype For business の共存と相互運用性につい](teams-and-skypeforbusiness-coexistence-and-interoperability.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7da17-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="7da17-109">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="7da17-109">License required</span></span>

<span data-ttu-id="7da17-110">ユーザーは、代理人として、または委任を設定して、他のユーザーに代わって通話を発信または受信できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7da17-110">A user must be an enterprise voice user to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="7da17-111">マネージャーと代理人の両方がエンタープライズ voip を有効にしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7da17-111">Both managers and delegates need to be enterprise voice enabled.</span></span> <span data-ttu-id="7da17-112">共有ラインエクスペリエンスは委任の一部であり、追加のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7da17-112">The shared line experience is part of delegation and requires no additional license.</span></span> <span data-ttu-id="7da17-113">ライセンスモデルの詳細については、「 [Microsoft Teams の Office 365 ライセンス](office-365-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7da17-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="7da17-114">委任および共有の線の外観を設定する</span><span class="sxs-lookup"><span data-stu-id="7da17-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="7da17-115">委任および共有の線の外観は、ユーザーによる機能です。構成する管理設定はありません。</span><span class="sxs-lookup"><span data-stu-id="7da17-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="7da17-116">この機能を使用する方法については、「[代理人と電話回線を共有](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7da17-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="7da17-117">この機能を使用するには、テナント管理者が Teamadministration の**ポリシー AllowDelegation**設定または Teams 管理ポータルを使って委任を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7da17-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="7da17-118">テナント管理者は、Teams 管理センターでユーザーの委任関係を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7da17-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="7da17-119">さらに、エンドユーザーは、チームに直接委任関係を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7da17-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="7da17-120">テナント管理者またはユーザーは、構成を相互にブロックすることはできませんが、Teams 管理センターとチームクライアントは、両方の場所でこの関係を正確に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7da17-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7da17-121">テナント管理者が、(有効になった後に) ユーザーの委任をオフにすると、誤った通話ルーティングが行われないように、Teams 管理センターでそのユーザーの委任関係をクリーンアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7da17-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="7da17-122">共有線の外観機能の可用性</span><span class="sxs-lookup"><span data-stu-id="7da17-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="7da17-123">共有線の外観は、現在、次のアプリとデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7da17-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="7da17-124">機能</span><span class="sxs-lookup"><span data-stu-id="7da17-124">Capability</span></span> | <span data-ttu-id="7da17-125">Teams のデスクトップ</span><span class="sxs-lookup"><span data-stu-id="7da17-125">Teams Desktop</span></span> | <span data-ttu-id="7da17-126">Teams Mac アプリ</span><span class="sxs-lookup"><span data-stu-id="7da17-126">Teams Mac App</span></span> | <span data-ttu-id="7da17-127">Teams Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="7da17-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="7da17-128">Teams mobile iOS/Android アプリ</span><span class="sxs-lookup"><span data-stu-id="7da17-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="7da17-129">Teams の IP 電話</span><span class="sxs-lookup"><span data-stu-id="7da17-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="7da17-130">代理人を設定する</span><span class="sxs-lookup"><span data-stu-id="7da17-130">Set up delegation</span></span> | <span data-ttu-id="7da17-131">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-131">Yes</span></span> | <span data-ttu-id="7da17-132">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-132">Yes</span></span> | <span data-ttu-id="7da17-133">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-133">Yes</span></span> | <span data-ttu-id="7da17-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="7da17-134">No</span></span> | <span data-ttu-id="7da17-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="7da17-135">No</span></span> |
| <span data-ttu-id="7da17-136">他の人の代理で通話を受信する</span><span class="sxs-lookup"><span data-stu-id="7da17-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="7da17-137">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-137">Yes</span></span> | <span data-ttu-id="7da17-138">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-138">Yes</span></span> | <span data-ttu-id="7da17-139">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-139">Yes</span></span> | <span data-ttu-id="7da17-140">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-140">Yes</span></span> | <span data-ttu-id="7da17-141">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-141">Yes</span></span> |
| <span data-ttu-id="7da17-142">別の電話番号に代わって電話番号に通話を発信する</span><span class="sxs-lookup"><span data-stu-id="7da17-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="7da17-143">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-143">Yes</span></span> | <span data-ttu-id="7da17-144">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-144">Yes</span></span> | <span data-ttu-id="7da17-145">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-145">Yes</span></span> | <span data-ttu-id="7da17-146">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-146">Yes</span></span> | <span data-ttu-id="7da17-147">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-147">Yes</span></span> |
| <span data-ttu-id="7da17-148">他のユーザーの代理として Teams ユーザーに電話をかける</span><span class="sxs-lookup"><span data-stu-id="7da17-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="7da17-149">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-149">Yes</span></span> | <span data-ttu-id="7da17-150">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-150">Yes</span></span> | <span data-ttu-id="7da17-151">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-151">Yes</span></span> | <span data-ttu-id="7da17-152">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-152">Yes</span></span> | <span data-ttu-id="7da17-153">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-153">Yes</span></span> |
| <span data-ttu-id="7da17-154">共有行の管理ビューを表示する</span><span class="sxs-lookup"><span data-stu-id="7da17-154">See the admin view of shared lines</span></span> | <span data-ttu-id="7da17-155">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-155">Yes</span></span> | <span data-ttu-id="7da17-156">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-156">Yes</span></span> | <span data-ttu-id="7da17-157">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-157">Yes</span></span> | <span data-ttu-id="7da17-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="7da17-158">No</span></span> | <span data-ttu-id="7da17-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="7da17-159">No</span></span> |
| <span data-ttu-id="7da17-160">マネージャーの通話活動の管理ビューを表示する</span><span class="sxs-lookup"><span data-stu-id="7da17-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="7da17-161">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-161">Yes</span></span> | <span data-ttu-id="7da17-162">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-162">Yes</span></span> | <span data-ttu-id="7da17-163">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-163">Yes</span></span> | <span data-ttu-id="7da17-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="7da17-164">No</span></span> | <span data-ttu-id="7da17-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="7da17-165">No</span></span> |
| <span data-ttu-id="7da17-166">代理人のマネージャービューを表示する</span><span class="sxs-lookup"><span data-stu-id="7da17-166">See the manager view of delegates</span></span> | <span data-ttu-id="7da17-167">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-167">Yes</span></span> | <span data-ttu-id="7da17-168">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-168">Yes</span></span> | <span data-ttu-id="7da17-169">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-169">Yes</span></span> | <span data-ttu-id="7da17-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="7da17-170">No</span></span> | <span data-ttu-id="7da17-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="7da17-171">No</span></span> |
| <span data-ttu-id="7da17-172">管理者またはマネージャーが保留または再開できる</span><span class="sxs-lookup"><span data-stu-id="7da17-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="7da17-173">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-173">Yes</span></span> | <span data-ttu-id="7da17-174">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-174">Yes</span></span> | <span data-ttu-id="7da17-175">はい</span><span class="sxs-lookup"><span data-stu-id="7da17-175">Yes</span></span> | <span data-ttu-id="7da17-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="7da17-176">No</span></span> | <span data-ttu-id="7da17-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="7da17-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="7da17-178">伴う</span><span class="sxs-lookup"><span data-stu-id="7da17-178">Limitations</span></span>

<span data-ttu-id="7da17-179">マネージャーは最高25人まで追加できます。代理人は最大25人までのマネージャーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="7da17-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="7da17-180">テナントで作成できる委任関係の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="7da17-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="7da17-181">委任者と代理人が同じ地理的な場所にない場合は、PSTN プロバイダーが、委任されている (代理として) 呼び出しについて別の地理的な場所から表示することを許可します。</span><span class="sxs-lookup"><span data-stu-id="7da17-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="7da17-182">詳細情報</span><span class="sxs-lookup"><span data-stu-id="7da17-182">More information</span></span>

[<span data-ttu-id="7da17-183">代理人と電話回線を共有する</span><span class="sxs-lookup"><span data-stu-id="7da17-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
