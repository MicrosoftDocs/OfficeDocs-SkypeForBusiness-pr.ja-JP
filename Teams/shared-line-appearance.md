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
f1keywords: None
ms.custom:
- Phone System
description: '[共有の線の外観] を使うと、ユーザーは代理として応答するか、通話を処理するデリゲートを選ぶことができます。'
ms.openlocfilehash: 619e011e1af5a765bc86ca6bd68134dc5ab1e9fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298656"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="94899-103">Microsoft Teams での回線共有機能</span><span class="sxs-lookup"><span data-stu-id="94899-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="94899-104">共有された線の外観は、委任機能の一部であり、ユーザーは代理として応答したり、通話を処理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="94899-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="94899-105">この機能は、ユーザーの通話を定期的に処理する管理アシスタントがある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="94899-105">This feature is helpful if a user has an administrative assistant who regularly handles the user’s calls.</span></span> <span data-ttu-id="94899-106">共有線の外観のコンテキストでは、マネージャーは代理人を代理として発信または受信するために代理人を承認し、代理人が他のユーザーの代わりに通話を発信および受信することができます。</span><span class="sxs-lookup"><span data-stu-id="94899-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94899-107">この機能は、Teams のみの展開モードでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="94899-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="94899-108">Teams の展開モードの詳細については、「 [Microsoft teams と Skype For business の共存と相互運用性につい](teams-and-skypeforbusiness-coexistence-and-interoperability.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94899-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="94899-109">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="94899-109">License required</span></span>

<span data-ttu-id="94899-110">ユーザーは、代理人として、または委任を設定して、他のユーザーに代わって通話を発信または受信できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94899-110">A user must be an enterprise voice user to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="94899-111">マネージャーと代理人の両方がエンタープライズ voip を有効にしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="94899-111">Both managers and delegates need to be enterprise voice enabled.</span></span> <span data-ttu-id="94899-112">共有回線のエクスペリエンスは委任の一部であり、追加のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="94899-112">The shared line experience is part of delegation, and requires no additional license.</span></span> <span data-ttu-id="94899-113">ライセンスモデルの詳細については、「 [Microsoft Teams の Office 365 ライセンス](office-365-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94899-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="94899-114">委任および共有の線の外観を設定する</span><span class="sxs-lookup"><span data-stu-id="94899-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="94899-115">委任および共有の線の外観は、ユーザーによる機能です。構成する管理設定はありません。</span><span class="sxs-lookup"><span data-stu-id="94899-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="94899-116">この機能を使用する方法については、「[代理人と電話回線を共有](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94899-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="94899-117">この機能を使用するには、テナント管理者が Teamadministration の**ポリシー AllowDelegation**設定を使って委任を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94899-117">The tenant admin should enable delegation via the **TeamsCallingPolicy AllowDelegation** setting for this feature to work.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="94899-118">共有線の外観機能の可用性</span><span class="sxs-lookup"><span data-stu-id="94899-118">Shared line appearance feature availability</span></span>

<span data-ttu-id="94899-119">共有線の外観は、現在、次のアプリとデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="94899-119">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="94899-120">機能</span><span class="sxs-lookup"><span data-stu-id="94899-120">Capability</span></span> | <span data-ttu-id="94899-121">Teams のデスクトップ</span><span class="sxs-lookup"><span data-stu-id="94899-121">Teams Desktop</span></span> | <span data-ttu-id="94899-122">Teams Mac アプリ</span><span class="sxs-lookup"><span data-stu-id="94899-122">Teams Mac App</span></span> | <span data-ttu-id="94899-123">Teams Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="94899-123">Teams Web App (Edge)</span></span> |<span data-ttu-id="94899-124">Teams mobile iOS/Android アプリ</span><span class="sxs-lookup"><span data-stu-id="94899-124">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="94899-125">Teams の IP 電話</span><span class="sxs-lookup"><span data-stu-id="94899-125">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="94899-126">代理人を設定する</span><span class="sxs-lookup"><span data-stu-id="94899-126">Set up delegation</span></span> | <span data-ttu-id="94899-127">はい</span><span class="sxs-lookup"><span data-stu-id="94899-127">Yes</span></span> | <span data-ttu-id="94899-128">はい</span><span class="sxs-lookup"><span data-stu-id="94899-128">Yes</span></span> | <span data-ttu-id="94899-129">はい</span><span class="sxs-lookup"><span data-stu-id="94899-129">Yes</span></span> | <span data-ttu-id="94899-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="94899-130">No</span></span> | <span data-ttu-id="94899-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="94899-131">No</span></span> |
| <span data-ttu-id="94899-132">他の人の代理で通話を受信する</span><span class="sxs-lookup"><span data-stu-id="94899-132">Receive calls on behalf of another</span></span> | <span data-ttu-id="94899-133">はい</span><span class="sxs-lookup"><span data-stu-id="94899-133">Yes</span></span> | <span data-ttu-id="94899-134">はい</span><span class="sxs-lookup"><span data-stu-id="94899-134">Yes</span></span> | <span data-ttu-id="94899-135">はい</span><span class="sxs-lookup"><span data-stu-id="94899-135">Yes</span></span> | <span data-ttu-id="94899-136">はい</span><span class="sxs-lookup"><span data-stu-id="94899-136">Yes</span></span> | <span data-ttu-id="94899-137">はい</span><span class="sxs-lookup"><span data-stu-id="94899-137">Yes</span></span> |
| <span data-ttu-id="94899-138">別の電話番号に代わって電話番号に通話を発信する</span><span class="sxs-lookup"><span data-stu-id="94899-138">Call a phone number on behalf of another</span></span> | <span data-ttu-id="94899-139">はい</span><span class="sxs-lookup"><span data-stu-id="94899-139">Yes</span></span> | <span data-ttu-id="94899-140">はい</span><span class="sxs-lookup"><span data-stu-id="94899-140">Yes</span></span> | <span data-ttu-id="94899-141">はい</span><span class="sxs-lookup"><span data-stu-id="94899-141">Yes</span></span> | <span data-ttu-id="94899-142">はい</span><span class="sxs-lookup"><span data-stu-id="94899-142">Yes</span></span> | <span data-ttu-id="94899-143">はい</span><span class="sxs-lookup"><span data-stu-id="94899-143">Yes</span></span> |
| <span data-ttu-id="94899-144">他のユーザーの代理として Teams ユーザーに電話をかける</span><span class="sxs-lookup"><span data-stu-id="94899-144">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="94899-145">はい</span><span class="sxs-lookup"><span data-stu-id="94899-145">Yes</span></span> | <span data-ttu-id="94899-146">はい</span><span class="sxs-lookup"><span data-stu-id="94899-146">Yes</span></span> | <span data-ttu-id="94899-147">はい</span><span class="sxs-lookup"><span data-stu-id="94899-147">Yes</span></span> | <span data-ttu-id="94899-148">はい</span><span class="sxs-lookup"><span data-stu-id="94899-148">Yes</span></span> | <span data-ttu-id="94899-149">はい</span><span class="sxs-lookup"><span data-stu-id="94899-149">Yes</span></span> |
| <span data-ttu-id="94899-150">共有行の管理ビューを表示する</span><span class="sxs-lookup"><span data-stu-id="94899-150">See the admin view of shared lines</span></span> | <span data-ttu-id="94899-151">はい</span><span class="sxs-lookup"><span data-stu-id="94899-151">Yes</span></span> | <span data-ttu-id="94899-152">はい</span><span class="sxs-lookup"><span data-stu-id="94899-152">Yes</span></span> | <span data-ttu-id="94899-153">はい</span><span class="sxs-lookup"><span data-stu-id="94899-153">Yes</span></span> | <span data-ttu-id="94899-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="94899-154">No</span></span> | <span data-ttu-id="94899-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="94899-155">No</span></span> |
| <span data-ttu-id="94899-156">マネージャーの通話活動の管理ビューを表示する</span><span class="sxs-lookup"><span data-stu-id="94899-156">See the admin view of manager's call activities</span></span> | <span data-ttu-id="94899-157">はい</span><span class="sxs-lookup"><span data-stu-id="94899-157">Yes</span></span> | <span data-ttu-id="94899-158">はい</span><span class="sxs-lookup"><span data-stu-id="94899-158">Yes</span></span> | <span data-ttu-id="94899-159">はい</span><span class="sxs-lookup"><span data-stu-id="94899-159">Yes</span></span> | <span data-ttu-id="94899-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="94899-160">No</span></span> | <span data-ttu-id="94899-161">いいえ</span><span class="sxs-lookup"><span data-stu-id="94899-161">No</span></span> |
| <span data-ttu-id="94899-162">代理人のマネージャービューを表示する</span><span class="sxs-lookup"><span data-stu-id="94899-162">See the manager view of delegates</span></span> | <span data-ttu-id="94899-163">はい</span><span class="sxs-lookup"><span data-stu-id="94899-163">Yes</span></span> | <span data-ttu-id="94899-164">はい</span><span class="sxs-lookup"><span data-stu-id="94899-164">Yes</span></span> | <span data-ttu-id="94899-165">はい</span><span class="sxs-lookup"><span data-stu-id="94899-165">Yes</span></span> | <span data-ttu-id="94899-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="94899-166">No</span></span> | <span data-ttu-id="94899-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="94899-167">No</span></span> |
| <span data-ttu-id="94899-168">管理者またはマネージャーが保留または再開できる</span><span class="sxs-lookup"><span data-stu-id="94899-168">Admin or manager can hold or resume</span></span> | <span data-ttu-id="94899-169">はい</span><span class="sxs-lookup"><span data-stu-id="94899-169">Yes</span></span> | <span data-ttu-id="94899-170">はい</span><span class="sxs-lookup"><span data-stu-id="94899-170">Yes</span></span> | <span data-ttu-id="94899-171">はい</span><span class="sxs-lookup"><span data-stu-id="94899-171">Yes</span></span> | <span data-ttu-id="94899-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="94899-172">No</span></span> | <span data-ttu-id="94899-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="94899-173">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="94899-174">伴う</span><span class="sxs-lookup"><span data-stu-id="94899-174">Limitations</span></span>

<span data-ttu-id="94899-175">マネージャーは最高25人まで追加できます。代理人は最大25人までのマネージャーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="94899-175">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="94899-176">テナントで作成できる委任関係の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="94899-176">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="94899-177">委任者と代理人が同じ地理的な場所にない場合は、PSTN プロバイダーが、委任されている (代理として) 呼び出しについて別の地理的な場所から表示することを許可します。</span><span class="sxs-lookup"><span data-stu-id="94899-177">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="94899-178">詳細情報</span><span class="sxs-lookup"><span data-stu-id="94899-178">More information</span></span>

[<span data-ttu-id="94899-179">代理人と電話回線を共有する</span><span class="sxs-lookup"><span data-stu-id="94899-179">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
