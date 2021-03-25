---
title: Microsoft Teams での回線共有機能
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
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
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Microsoft Teams の電話会議情報を含むメールをユーザーに送信する方法について説明します。
ms.openlocfilehash: b6a9e8dfba0db32eb4f02f1f4d4e9ea5f2c4be3e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117045"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="fdccd-103">Microsoft Teams での回線共有機能</span><span class="sxs-lookup"><span data-stu-id="fdccd-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="fdccd-104">共有行の外観は委任機能の一部で、ユーザーが代理人を選択して、自分の代わりに通話に応答したり処理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fdccd-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="fdccd-105">この機能は、ユーザーが管理アシスタントを持ち、ユーザーの呼び出しを定期的に処理する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fdccd-105">This feature is helpful if a user has an administrative assistant who regularly handles the user's calls.</span></span> <span data-ttu-id="fdccd-106">共有された回線の外観の場合、マネージャーは代理人に代わって通話の送受信を許可するユーザーであり、代理人は他のユーザーの代わりに通話を行い、受信することができます。</span><span class="sxs-lookup"><span data-stu-id="fdccd-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fdccd-107">この機能を使用できるのは、Teams のみの展開モードだけです。</span><span class="sxs-lookup"><span data-stu-id="fdccd-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="fdccd-108">Teams 展開モードの詳細については、「Microsoft Teams と Skype for Business の共存と相互運用性について[」を参照してください](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="fdccd-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="fdccd-109">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="fdccd-109">License required</span></span>

<span data-ttu-id="fdccd-110">ユーザーが代理または委任を設定し、他のユーザーが自分の代わりに通話を発信または受信するには、PSTN 接続を持つ電話システム (通話プラン ライセンスまたは直接ルーティング OnlineVoiceRoutingPolicy) が必要です。</span><span class="sxs-lookup"><span data-stu-id="fdccd-110">A user must be have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy) to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="fdccd-111">マネージャーと代理人の両方が PSTN 接続の電話システム (通話プラン ライセンスまたは直接ルーティング OnlineVoiceRoutingPolicy) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdccd-111">Both managers and delegates need to have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy).</span></span> <span data-ttu-id="fdccd-112">共有回線エクスペリエンスは委任の一部であり、電話システムに含まれます。</span><span class="sxs-lookup"><span data-stu-id="fdccd-112">The shared line experience is part of delegation and is included with Phone System.</span></span> <span data-ttu-id="fdccd-113">ライセンス モデルの詳細については、Microsoft Teams サービスの説明 [を参照してください](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="fdccd-113">For additional details on the licensing model, See [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="fdccd-114">委任と共有行の外観を構成する</span><span class="sxs-lookup"><span data-stu-id="fdccd-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="fdccd-115">委任と共有の行の外観は、ユーザー駆動型の機能です。構成する管理者設定はありません。</span><span class="sxs-lookup"><span data-stu-id="fdccd-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="fdccd-116">この機能の使い方の詳細については、「代理人と電話回線を共有する」 [を参照してください。](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="fdccd-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="fdccd-117">この機能を動作するには、テナント管理者は **TeamsCallingPolicy AllowDelegation** 設定または Teams 管理ポータルを介して委任を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="fdccd-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="fdccd-118">テナント管理者は、Teams 管理センターでユーザーの委任リレーションシップを構成できます。</span><span class="sxs-lookup"><span data-stu-id="fdccd-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="fdccd-119">さらに、エンド ユーザーは Teams で委任関係を直接構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fdccd-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="fdccd-120">テナント管理者またはユーザーが互いに構成をブロックすることはできませんが、Teams 管理センターと Teams クライアントは両方の場所でこの関係を正確に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdccd-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="fdccd-121">テナント管理者がユーザーの委任を無効にした場合 (有効にした後)、誤った通話ルーティングを回避するには、Teams 管理センターでユーザーの委任関係をクリーンアップする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="fdccd-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="fdccd-122">共有線の外観機能の可用性</span><span class="sxs-lookup"><span data-stu-id="fdccd-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="fdccd-123">現在、共有線の外観は、次のアプリとデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fdccd-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="fdccd-124">機能</span><span class="sxs-lookup"><span data-stu-id="fdccd-124">Capability</span></span> | <span data-ttu-id="fdccd-125">Teams デスクトップ</span><span class="sxs-lookup"><span data-stu-id="fdccd-125">Teams Desktop</span></span> | <span data-ttu-id="fdccd-126">Teams Mac アプリ</span><span class="sxs-lookup"><span data-stu-id="fdccd-126">Teams Mac App</span></span> | <span data-ttu-id="fdccd-127">Teams Web アプリ (Edge)</span><span class="sxs-lookup"><span data-stu-id="fdccd-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="fdccd-128">Teams モバイル iOS/Android アプリ</span><span class="sxs-lookup"><span data-stu-id="fdccd-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="fdccd-129">Teams IP 電話</span><span class="sxs-lookup"><span data-stu-id="fdccd-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="fdccd-130">委任を設定する</span><span class="sxs-lookup"><span data-stu-id="fdccd-130">Set up delegation</span></span> | <span data-ttu-id="fdccd-131">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-131">Yes</span></span> | <span data-ttu-id="fdccd-132">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-132">Yes</span></span> | <span data-ttu-id="fdccd-133">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-133">Yes</span></span> | <span data-ttu-id="fdccd-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="fdccd-134">No</span></span> | <span data-ttu-id="fdccd-135">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-135">Yes</span></span> |
| <span data-ttu-id="fdccd-136">別のユーザーに代わって通話を受信する</span><span class="sxs-lookup"><span data-stu-id="fdccd-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="fdccd-137">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-137">Yes</span></span> | <span data-ttu-id="fdccd-138">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-138">Yes</span></span> | <span data-ttu-id="fdccd-139">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-139">Yes</span></span> | <span data-ttu-id="fdccd-140">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-140">Yes</span></span> | <span data-ttu-id="fdccd-141">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-141">Yes</span></span> |
| <span data-ttu-id="fdccd-142">別の電話番号に代わって電話番号に電話する</span><span class="sxs-lookup"><span data-stu-id="fdccd-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="fdccd-143">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-143">Yes</span></span> | <span data-ttu-id="fdccd-144">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-144">Yes</span></span> | <span data-ttu-id="fdccd-145">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-145">Yes</span></span> | <span data-ttu-id="fdccd-146">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-146">Yes</span></span> | <span data-ttu-id="fdccd-147">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-147">Yes</span></span> |
| <span data-ttu-id="fdccd-148">別のユーザーに代わって Teams ユーザーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="fdccd-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="fdccd-149">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-149">Yes</span></span> | <span data-ttu-id="fdccd-150">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-150">Yes</span></span> | <span data-ttu-id="fdccd-151">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-151">Yes</span></span> | <span data-ttu-id="fdccd-152">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-152">Yes</span></span> | <span data-ttu-id="fdccd-153">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-153">Yes</span></span> |
| <span data-ttu-id="fdccd-154">共有行の管理ビューを表示する</span><span class="sxs-lookup"><span data-stu-id="fdccd-154">See the admin view of shared lines</span></span> | <span data-ttu-id="fdccd-155">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-155">Yes</span></span> | <span data-ttu-id="fdccd-156">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-156">Yes</span></span> | <span data-ttu-id="fdccd-157">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-157">Yes</span></span> | <span data-ttu-id="fdccd-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="fdccd-158">No</span></span> | <span data-ttu-id="fdccd-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="fdccd-159">No</span></span> |
| <span data-ttu-id="fdccd-160">マネージャーの通話アクティビティの管理ビューを表示する</span><span class="sxs-lookup"><span data-stu-id="fdccd-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="fdccd-161">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-161">Yes</span></span> | <span data-ttu-id="fdccd-162">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-162">Yes</span></span> | <span data-ttu-id="fdccd-163">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-163">Yes</span></span> | <span data-ttu-id="fdccd-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="fdccd-164">No</span></span> | <span data-ttu-id="fdccd-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="fdccd-165">No</span></span> |
| <span data-ttu-id="fdccd-166">代理人のマネージャー ビューを表示する</span><span class="sxs-lookup"><span data-stu-id="fdccd-166">See the manager view of delegates</span></span> | <span data-ttu-id="fdccd-167">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-167">Yes</span></span> | <span data-ttu-id="fdccd-168">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-168">Yes</span></span> | <span data-ttu-id="fdccd-169">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-169">Yes</span></span> | <span data-ttu-id="fdccd-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="fdccd-170">No</span></span> | <span data-ttu-id="fdccd-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="fdccd-171">No</span></span> |
| <span data-ttu-id="fdccd-172">管理者またはマネージャーが保留または再開できる</span><span class="sxs-lookup"><span data-stu-id="fdccd-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="fdccd-173">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-173">Yes</span></span> | <span data-ttu-id="fdccd-174">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-174">Yes</span></span> | <span data-ttu-id="fdccd-175">はい</span><span class="sxs-lookup"><span data-stu-id="fdccd-175">Yes</span></span> | <span data-ttu-id="fdccd-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="fdccd-176">No</span></span> | <span data-ttu-id="fdccd-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="fdccd-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="fdccd-178">制限事項</span><span class="sxs-lookup"><span data-stu-id="fdccd-178">Limitations</span></span>

<span data-ttu-id="fdccd-179">マネージャーは最大 25 人の代理人を追加し、代理人には最大 25 人のマネージャーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="fdccd-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="fdccd-180">テナントで作成できる委任リレーションシップの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="fdccd-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="fdccd-181">委任者と代理人が同じ地理的な場所にいない場合、委任された (代理で) 通話の別の地理的な場所から発信者番号を表示できるのは PSTN プロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="fdccd-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="fdccd-182">詳細情報</span><span class="sxs-lookup"><span data-stu-id="fdccd-182">More information</span></span>

[<span data-ttu-id="fdccd-183">代理人と電話回線を共有する</span><span class="sxs-lookup"><span data-stu-id="fdccd-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)