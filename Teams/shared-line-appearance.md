---
title: Microsoft Teams での共有回線の外観
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
description: Microsoft Teams で音声会議情報を記載したメールをユーザーに送信する方法について説明します。
ms.openlocfilehash: b6a9e8dfba0db32eb4f02f1f4d4e9ea5f2c4be3e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117045"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="87ad9-103">Microsoft Teams での共有回線の外観</span><span class="sxs-lookup"><span data-stu-id="87ad9-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="87ad9-104">回線共有機能は、ユーザーが代理で通話に応答または処理する代理人を選択できる委任機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="87ad9-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="87ad9-105">この機能は、ユーザーの通話を定期的に処理する管理アシスタントがいる場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="87ad9-105">This feature is helpful if a user has an administrative assistant who regularly handles the user's calls.</span></span> <span data-ttu-id="87ad9-106">共有回線の外観のコンテキストでは、マネージャーは、代理人が自分に代わって電話をかけたり受けたりすることを許可するユーザーであり、代理人は他の人に代わって電話をかけたり受けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="87ad9-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87ad9-107">この機能を使用できるのは、Teams のみの展開モードだけです。</span><span class="sxs-lookup"><span data-stu-id="87ad9-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="87ad9-108">Teams 展開モードの詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87ad9-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="87ad9-109">必要なライセンス</span><span class="sxs-lookup"><span data-stu-id="87ad9-109">License required</span></span>

<span data-ttu-id="87ad9-110">ユーザーは、委任または委任を設定し、他のユーザーが自分に代わって電話をかけたり受けたりできるようにするには、PSTN 接続 (通話プラン ライセンスまたは Direct Routing OnlineVoiceRoutingPolicy のいずれか) を備えた電話システムを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="87ad9-110">A user must be have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy) to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="87ad9-111">管理者と代理人の両方が、PSTN 接続 (通話プラン ライセンスまたは Direct Routing OnlineVoiceRoutingPolicy のいずれか) を備えた電話システムを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="87ad9-111">Both managers and delegates need to have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy).</span></span> <span data-ttu-id="87ad9-112">共有回線エクスペリエンスは委任の一部であり、電話システムに含まれています。</span><span class="sxs-lookup"><span data-stu-id="87ad9-112">The shared line experience is part of delegation and is included with Phone System.</span></span> <span data-ttu-id="87ad9-113">ライセンス モデルの詳細については、「[Microsoft Teams サービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87ad9-113">For additional details on the licensing model, See [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="87ad9-114">委任と共有回線の外観の構成</span><span class="sxs-lookup"><span data-stu-id="87ad9-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="87ad9-115">委任と共有回線の外観はユーザー主導の機能です。構成する管理者設定はありません。</span><span class="sxs-lookup"><span data-stu-id="87ad9-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="87ad9-116">この機能の使用方法については、「[電話回線を代理人と共有する](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87ad9-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="87ad9-117">テナント管理者は、**TeamsCallingPolicy AllowDelegation** 設定を介して、または Teams Admin Portal を介して委任を有効にして、この機能を機能させることができます。</span><span class="sxs-lookup"><span data-stu-id="87ad9-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="87ad9-118">テナント管理者は、Teams 管理センターでユーザーの委任関係を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="87ad9-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="87ad9-119">さらに、エンド ユーザーはチームで直接委任関係を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="87ad9-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="87ad9-120">テナント管理者またはユーザーは相互に構成をブロックすることはできませんが、Teams 管理センターと Teams クライアントは両方の場所でこの関係を正確に示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="87ad9-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="87ad9-121">テナント管理者がユーザーの委任をオフにした場合 (オンにした後)、Teams 管理センターでそのユーザーの委任関係をクリーンアップして、誤ったコールルーティングを回避する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="87ad9-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="87ad9-122">共有回線の外観機能の可用性</span><span class="sxs-lookup"><span data-stu-id="87ad9-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="87ad9-123">共有回線の外観は現在、次のアプリとデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="87ad9-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="87ad9-124">機能</span><span class="sxs-lookup"><span data-stu-id="87ad9-124">Capability</span></span> | <span data-ttu-id="87ad9-125">Teams デスクトップ</span><span class="sxs-lookup"><span data-stu-id="87ad9-125">Teams Desktop</span></span> | <span data-ttu-id="87ad9-126">Teams Mac アプリ</span><span class="sxs-lookup"><span data-stu-id="87ad9-126">Teams Mac App</span></span> | <span data-ttu-id="87ad9-127">Teams Web アプリ (Edge)</span><span class="sxs-lookup"><span data-stu-id="87ad9-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="87ad9-128">Teams モバイル iOS/Android アプリ</span><span class="sxs-lookup"><span data-stu-id="87ad9-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="87ad9-129">Teams IP 電話</span><span class="sxs-lookup"><span data-stu-id="87ad9-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="87ad9-130">委任を設定する</span><span class="sxs-lookup"><span data-stu-id="87ad9-130">Set up delegation</span></span> | <span data-ttu-id="87ad9-131">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-131">Yes</span></span> | <span data-ttu-id="87ad9-132">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-132">Yes</span></span> | <span data-ttu-id="87ad9-133">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-133">Yes</span></span> | <span data-ttu-id="87ad9-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="87ad9-134">No</span></span> | <span data-ttu-id="87ad9-135">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-135">Yes</span></span> |
| <span data-ttu-id="87ad9-136">別の人に代わって電話を受ける</span><span class="sxs-lookup"><span data-stu-id="87ad9-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="87ad9-137">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-137">Yes</span></span> | <span data-ttu-id="87ad9-138">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-138">Yes</span></span> | <span data-ttu-id="87ad9-139">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-139">Yes</span></span> | <span data-ttu-id="87ad9-140">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-140">Yes</span></span> | <span data-ttu-id="87ad9-141">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-141">Yes</span></span> |
| <span data-ttu-id="87ad9-142">別の人に代わって電話番号に電話する</span><span class="sxs-lookup"><span data-stu-id="87ad9-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="87ad9-143">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-143">Yes</span></span> | <span data-ttu-id="87ad9-144">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-144">Yes</span></span> | <span data-ttu-id="87ad9-145">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-145">Yes</span></span> | <span data-ttu-id="87ad9-146">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-146">Yes</span></span> | <span data-ttu-id="87ad9-147">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-147">Yes</span></span> |
| <span data-ttu-id="87ad9-148">別のユーザーに代わって Teams ユーザーに電話する</span><span class="sxs-lookup"><span data-stu-id="87ad9-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="87ad9-149">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-149">Yes</span></span> | <span data-ttu-id="87ad9-150">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-150">Yes</span></span> | <span data-ttu-id="87ad9-151">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-151">Yes</span></span> | <span data-ttu-id="87ad9-152">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-152">Yes</span></span> | <span data-ttu-id="87ad9-153">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-153">Yes</span></span> |
| <span data-ttu-id="87ad9-154">共有回線の管理ビューを表示する</span><span class="sxs-lookup"><span data-stu-id="87ad9-154">See the admin view of shared lines</span></span> | <span data-ttu-id="87ad9-155">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-155">Yes</span></span> | <span data-ttu-id="87ad9-156">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-156">Yes</span></span> | <span data-ttu-id="87ad9-157">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-157">Yes</span></span> | <span data-ttu-id="87ad9-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="87ad9-158">No</span></span> | <span data-ttu-id="87ad9-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="87ad9-159">No</span></span> |
| <span data-ttu-id="87ad9-160">マネージャーの通話アクティビティの管理ビューを表示する</span><span class="sxs-lookup"><span data-stu-id="87ad9-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="87ad9-161">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-161">Yes</span></span> | <span data-ttu-id="87ad9-162">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-162">Yes</span></span> | <span data-ttu-id="87ad9-163">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-163">Yes</span></span> | <span data-ttu-id="87ad9-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="87ad9-164">No</span></span> | <span data-ttu-id="87ad9-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="87ad9-165">No</span></span> |
| <span data-ttu-id="87ad9-166">委任のマネージャー ビューを参照してください</span><span class="sxs-lookup"><span data-stu-id="87ad9-166">See the manager view of delegates</span></span> | <span data-ttu-id="87ad9-167">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-167">Yes</span></span> | <span data-ttu-id="87ad9-168">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-168">Yes</span></span> | <span data-ttu-id="87ad9-169">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-169">Yes</span></span> | <span data-ttu-id="87ad9-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="87ad9-170">No</span></span> | <span data-ttu-id="87ad9-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="87ad9-171">No</span></span> |
| <span data-ttu-id="87ad9-172">管理者またはマネージャーは保留または再開できます</span><span class="sxs-lookup"><span data-stu-id="87ad9-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="87ad9-173">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-173">Yes</span></span> | <span data-ttu-id="87ad9-174">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-174">Yes</span></span> | <span data-ttu-id="87ad9-175">はい</span><span class="sxs-lookup"><span data-stu-id="87ad9-175">Yes</span></span> | <span data-ttu-id="87ad9-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="87ad9-176">No</span></span> | <span data-ttu-id="87ad9-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="87ad9-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="87ad9-178">制限事項</span><span class="sxs-lookup"><span data-stu-id="87ad9-178">Limitations</span></span>

<span data-ttu-id="87ad9-179">管理者は最大 25 人の代理人を追加でき、代理人は最大 25 人の管理者を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="87ad9-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="87ad9-180">テナントで作成できる委任関係の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="87ad9-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="87ad9-181">委任者と委任者が同じ地理的場所にいない場合、委任された (代理の) 通話のために発信者 ID が異なる地理的場所から表示されるようにするのは PSTN プロバイダーの責任です。</span><span class="sxs-lookup"><span data-stu-id="87ad9-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="87ad9-182">詳細情報</span><span class="sxs-lookup"><span data-stu-id="87ad9-182">More information</span></span>

[<span data-ttu-id="87ad9-183">電話回線を代理人と共有する</span><span class="sxs-lookup"><span data-stu-id="87ad9-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)