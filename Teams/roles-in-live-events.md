---
title: Teams のライブ イベントでのプレゼンターと参加者の機能
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams のライブ イベントでのプレゼンターと参加者の機能について説明します。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 7714442be770420797df1c51a532f769eb0350a4
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565860"
---
<a name="presenter-and-participant-capabilities-in-a-teams-live-event"></a><span data-ttu-id="64360-103">Teams のライブ イベントでのプレゼンターと参加者の機能</span><span class="sxs-lookup"><span data-stu-id="64360-103">Presenter and participant capabilities in a Teams live event</span></span>
======================================================

<span data-ttu-id="64360-104">Microsoft Teams のライブ イベントは、多くの種類の参加者をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="64360-104">Microsoft Teams live events support many participant types.</span></span> <span data-ttu-id="64360-105">参加者は、組織内外の役割に基づいて、さまざまなライブ イベントの機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="64360-105">Participants can access various live event features based on their roles inside or outside of an organization.</span></span>

<span data-ttu-id="64360-106">使用可能な会議の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64360-106">The available meeting features are:</span></span>

- <span data-ttu-id="64360-107">チャット (写真とステッカーを含む)</span><span class="sxs-lookup"><span data-stu-id="64360-107">Chat (includes photos and stickers)</span></span>
- <span data-ttu-id="64360-108">会議のメモ</span><span class="sxs-lookup"><span data-stu-id="64360-108">Meeting Notes</span></span>
- <span data-ttu-id="64360-109">ホワイトボード</span><span class="sxs-lookup"><span data-stu-id="64360-109">Whiteboard</span></span>
- <span data-ttu-id="64360-110">記録</span><span class="sxs-lookup"><span data-stu-id="64360-110">Recording</span></span>
- <span data-ttu-id="64360-111">ファイル</span><span class="sxs-lookup"><span data-stu-id="64360-111">Files</span></span>

<span data-ttu-id="64360-112">この記事では、これらの参加者の機能と、ライブ イベントの機能へのアクセス許可について説明します。</span><span class="sxs-lookup"><span data-stu-id="64360-112">This article describes those participant capabilities and what access they have to live event features.</span></span>

## <a name="presenters-and-organizers"></a><span data-ttu-id="64360-113">プレゼンターと主催者</span><span class="sxs-lookup"><span data-stu-id="64360-113">Presenters and organizers</span></span>

<span data-ttu-id="64360-114">プレゼンターと主催者は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64360-114">Presenters and organizers include the following:</span></span>

- <span data-ttu-id="64360-115">自分の所属組織のプレゼンター</span><span class="sxs-lookup"><span data-stu-id="64360-115">Presenters from my organization</span></span>
- <span data-ttu-id="64360-116">他の組織のプレゼンター</span><span class="sxs-lookup"><span data-stu-id="64360-116">Presenters from other organizations.</span></span> <span data-ttu-id="64360-117">プレゼンターは主催者によって指定され、主催者からの個人的な招待が必要です。</span><span class="sxs-lookup"><span data-stu-id="64360-117">Presenters are designated by the organizer and require a personal invite from the organizer.</span></span>

<span data-ttu-id="64360-118">プレゼンターと主催者は、ライブ イベントのすべての機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="64360-118">Presenters and organizers have access to every feature in a live event.</span></span>

## <a name="participants"></a><span data-ttu-id="64360-119">参加者</span><span class="sxs-lookup"><span data-stu-id="64360-119">Participants</span></span>

<span data-ttu-id="64360-120">ライブ イベントの参加者はいくつかの種類があります。</span><span class="sxs-lookup"><span data-stu-id="64360-120">There are several types of live event participants:</span></span>

- [<span data-ttu-id="64360-121">テナント内の参加者</span><span class="sxs-lookup"><span data-stu-id="64360-121">In-tenant participant</span></span>](#in-tenant-participant)
- [<span data-ttu-id="64360-122">ゲスト参加者</span><span class="sxs-lookup"><span data-stu-id="64360-122">Guest participant</span></span>](#guest-participant)
- [<span data-ttu-id="64360-123">外部 (フェデレーション) 参加者</span><span class="sxs-lookup"><span data-stu-id="64360-123">External (federated) participant</span></span>](#external-federated-participant)
- [<span data-ttu-id="64360-124">匿名参加者</span><span class="sxs-lookup"><span data-stu-id="64360-124">Anonymous participant</span></span>](#anonymous-participant)

### <a name="in-tenant-participant"></a><span data-ttu-id="64360-125">テナント内の参加者</span><span class="sxs-lookup"><span data-stu-id="64360-125">In-tenant participant</span></span>

<span data-ttu-id="64360-126">テナント内の参加者は組織に属しており、テナントの資格情報を持っています。</span><span class="sxs-lookup"><span data-stu-id="64360-126">The in-tenant participant belongs to the organization and has credentials for the tenant.</span></span> <span data-ttu-id="64360-127">この参加者の詳細については、「[セキュリティと Microsoft Teams](teams-security-guide.md#participant-types)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64360-127">Learn more about this participant in [Security and Microsoft Teams](teams-security-guide.md#participant-types).</span></span>

| <span data-ttu-id="64360-128">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="64360-128">Live event</span></span> |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  <span data-ttu-id="64360-129">**機能**</span><span class="sxs-lookup"><span data-stu-id="64360-129">**Feature**</span></span>       | <span data-ttu-id="64360-130">事前会議</span><span class="sxs-lookup"><span data-stu-id="64360-130">Pre-meeting</span></span> | <span data-ttu-id="64360-131">会議中</span><span class="sxs-lookup"><span data-stu-id="64360-131">In-meeting</span></span> | <span data-ttu-id="64360-132">会議後</span><span class="sxs-lookup"><span data-stu-id="64360-132">Post-meeting</span></span> |
| <span data-ttu-id="64360-133">チャット</span><span class="sxs-lookup"><span data-stu-id="64360-133">Chat</span></span> | <span data-ttu-id="64360-134">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-134">N/A</span></span> | <span data-ttu-id="64360-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-135">N/A</span></span> | <span data-ttu-id="64360-136">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-136">N/A</span></span> |
| <span data-ttu-id="64360-137">会議のメモ</span><span class="sxs-lookup"><span data-stu-id="64360-137">Meeting Notes</span></span> | <span data-ttu-id="64360-138">はい</span><span class="sxs-lookup"><span data-stu-id="64360-138">Yes</span></span> | <span data-ttu-id="64360-139">はい</span><span class="sxs-lookup"><span data-stu-id="64360-139">Yes</span></span> |<span data-ttu-id="64360-140">はい</span><span class="sxs-lookup"><span data-stu-id="64360-140">Yes</span></span> |
| <span data-ttu-id="64360-141">ホワイトボード</span><span class="sxs-lookup"><span data-stu-id="64360-141">Whiteboard</span></span> | <span data-ttu-id="64360-142">はい</span><span class="sxs-lookup"><span data-stu-id="64360-142">Yes</span></span> | <span data-ttu-id="64360-143">はい</span><span class="sxs-lookup"><span data-stu-id="64360-143">Yes</span></span> |<span data-ttu-id="64360-144">はい</span><span class="sxs-lookup"><span data-stu-id="64360-144">Yes</span></span> |
| <span data-ttu-id="64360-145">記録</span><span class="sxs-lookup"><span data-stu-id="64360-145">Recording</span></span> | <span data-ttu-id="64360-146">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-146">N/A</span></span> |<span data-ttu-id="64360-147">はい</span><span class="sxs-lookup"><span data-stu-id="64360-147">Yes</span></span> | <span data-ttu-id="64360-148">はい</span><span class="sxs-lookup"><span data-stu-id="64360-148">Yes</span></span> |
| <span data-ttu-id="64360-149">ファイル</span><span class="sxs-lookup"><span data-stu-id="64360-149">Files</span></span> | <span data-ttu-id="64360-150">はい</span><span class="sxs-lookup"><span data-stu-id="64360-150">Yes</span></span> | <span data-ttu-id="64360-151">はい</span><span class="sxs-lookup"><span data-stu-id="64360-151">Yes</span></span> | <span data-ttu-id="64360-152">はい</span><span class="sxs-lookup"><span data-stu-id="64360-152">Yes</span></span> |
|||||||


### <a name="guest-participant"></a><span data-ttu-id="64360-153">ゲスト参加者</span><span class="sxs-lookup"><span data-stu-id="64360-153">Guest participant</span></span>

<span data-ttu-id="64360-154">ゲスト参加者とは、Azure Active Directory B2B プラットフォームに基づいて、組織のテナント内の Teams またはその他のリソースにアクセスするように招待された別の組織からの参加者です。</span><span class="sxs-lookup"><span data-stu-id="64360-154">A guest participant is someone from another organization who has been invited to access Teams or other resources in your organization's tenant, based on the Azure Active Directory B2B platform.</span></span> <span data-ttu-id="64360-155">ゲスト ユーザーは、定例会議やチャネル会議に参加するよう招待できます。</span><span class="sxs-lookup"><span data-stu-id="64360-155">Guest users can be invited to join regular meetings and channel meetings.</span></span> <span data-ttu-id="64360-156">ゲスト参加者の詳細については、「[ゲストのエクスペリエンスについて](guest-experience.md#comparison-of-team-member-and-guest-capabilities)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64360-156">Read more about a guest participant in [What the guest experience is like](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span></span>

| <span data-ttu-id="64360-157">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="64360-157">Live event</span></span>  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="64360-158">**機能**</span><span class="sxs-lookup"><span data-stu-id="64360-158">**Feature**</span></span>        | <span data-ttu-id="64360-159">事前会議</span><span class="sxs-lookup"><span data-stu-id="64360-159">Pre-meeting</span></span> | <span data-ttu-id="64360-160">会議中</span><span class="sxs-lookup"><span data-stu-id="64360-160">In-meeting</span></span> | <span data-ttu-id="64360-161">会議後</span><span class="sxs-lookup"><span data-stu-id="64360-161">Post-meeting</span></span> |
| <span data-ttu-id="64360-162">チャット</span><span class="sxs-lookup"><span data-stu-id="64360-162">Chat</span></span> | <span data-ttu-id="64360-163">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-163">N/A</span></span> | <span data-ttu-id="64360-164">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-164">N/A</span></span> | <span data-ttu-id="64360-165">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-165">N/A</span></span> |
| <span data-ttu-id="64360-166">会議のメモ</span><span class="sxs-lookup"><span data-stu-id="64360-166">Meeting Notes</span></span> | <span data-ttu-id="64360-167">はい</span><span class="sxs-lookup"><span data-stu-id="64360-167">Yes</span></span> | <span data-ttu-id="64360-168">はい</span><span class="sxs-lookup"><span data-stu-id="64360-168">Yes</span></span> | <span data-ttu-id="64360-169">はい</span><span class="sxs-lookup"><span data-stu-id="64360-169">Yes</span></span> |
| <span data-ttu-id="64360-170">ホワイトボード</span><span class="sxs-lookup"><span data-stu-id="64360-170">Whiteboard</span></span> | <span data-ttu-id="64360-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-171">No</span></span> | <span data-ttu-id="64360-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-172">No</span></span> | <span data-ttu-id="64360-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-173">No</span></span> |
| <span data-ttu-id="64360-174">記録</span><span class="sxs-lookup"><span data-stu-id="64360-174">Recording</span></span> | <span data-ttu-id="64360-175">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-175">N/A</span></span> | <span data-ttu-id="64360-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-176">No</span></span> | <span data-ttu-id="64360-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-177">No</span></span> |
| <span data-ttu-id="64360-178">ファイル</span><span class="sxs-lookup"><span data-stu-id="64360-178">Files</span></span> | <span data-ttu-id="64360-179">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-179">No</span></span> | <span data-ttu-id="64360-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-180">No</span></span> | <span data-ttu-id="64360-181">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-181">No</span></span> |
|||||||


### <a name="external-federated-participant"></a><span data-ttu-id="64360-182">外部 (フェデレーション) 参加者</span><span class="sxs-lookup"><span data-stu-id="64360-182">External (federated) participant</span></span>

<span data-ttu-id="64360-183">外部参加者とは、別の組織の Teams を使用して、会議への参加を招待されているが、それ以外の場合は組織の他の共有リソースにアクセスできないユーザーです。</span><span class="sxs-lookup"><span data-stu-id="64360-183">An external participant is someone using Teams in another organization who has been invited to join a meeting, but does not otherwise have access to other shared resources from your organization.</span></span> <span data-ttu-id="64360-184">外部ユーザーの参加者は、自分の組織と同じ ID 名で会議名簿に表示されます。</span><span class="sxs-lookup"><span data-stu-id="64360-184">External user participants appear in the meeting roster with the same identity name as they have in their own organization.</span></span> <span data-ttu-id="64360-185">外部参加者の詳細については、「[別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md#external-access)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64360-185">Read more about an external participant in [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md#external-access).</span></span>

| <span data-ttu-id="64360-186">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="64360-186">Live event</span></span> |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  <span data-ttu-id="64360-187">**機能**</span><span class="sxs-lookup"><span data-stu-id="64360-187">**Feature**</span></span>         | <span data-ttu-id="64360-188">事前会議</span><span class="sxs-lookup"><span data-stu-id="64360-188">Pre-meeting</span></span> | <span data-ttu-id="64360-189">会議中</span><span class="sxs-lookup"><span data-stu-id="64360-189">In-meeting</span></span> | <span data-ttu-id="64360-190">会議後</span><span class="sxs-lookup"><span data-stu-id="64360-190">Post-meeting</span></span> |
| <span data-ttu-id="64360-191">チャット</span><span class="sxs-lookup"><span data-stu-id="64360-191">Chat</span></span> | <span data-ttu-id="64360-192">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-192">N/A</span></span>| <span data-ttu-id="64360-193">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-193">N/A</span></span> | <span data-ttu-id="64360-194">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-194">N/A</span></span> |
| <span data-ttu-id="64360-195">会議のメモ</span><span class="sxs-lookup"><span data-stu-id="64360-195">Meeting Notes</span></span> | <span data-ttu-id="64360-196">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-196">No</span></span> | <span data-ttu-id="64360-197">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-197">No</span></span> | <span data-ttu-id="64360-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-198">No</span></span> |
| <span data-ttu-id="64360-199">ホワイトボード</span><span class="sxs-lookup"><span data-stu-id="64360-199">Whiteboard</span></span> | <span data-ttu-id="64360-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-200">No</span></span>| <span data-ttu-id="64360-201">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-201">No</span></span> | <span data-ttu-id="64360-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-202">No</span></span> |
| <span data-ttu-id="64360-203">記録</span><span class="sxs-lookup"><span data-stu-id="64360-203">Recording</span></span> | <span data-ttu-id="64360-204">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-204">N/A</span></span> | <span data-ttu-id="64360-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-205">No</span></span> | <span data-ttu-id="64360-206">いいえ</span><span class="sxs-lookup"><span data-stu-id="64360-206">No</span></span> |
| <span data-ttu-id="64360-207">ファイル</span><span class="sxs-lookup"><span data-stu-id="64360-207">Files</span></span> | <span data-ttu-id="64360-208">はい</span><span class="sxs-lookup"><span data-stu-id="64360-208">Yes</span></span> | <span data-ttu-id="64360-209">はい</span><span class="sxs-lookup"><span data-stu-id="64360-209">Yes</span></span> | <span data-ttu-id="64360-210">はい</span><span class="sxs-lookup"><span data-stu-id="64360-210">Yes</span></span> |
|||||||

### <a name="anonymous-participant"></a><span data-ttu-id="64360-211">匿名参加者</span><span class="sxs-lookup"><span data-stu-id="64360-211">Anonymous participant</span></span>

<span data-ttu-id="64360-212">匿名参加者は外部ユーザーのようですが、自分の ID は会議に表示されません。</span><span class="sxs-lookup"><span data-stu-id="64360-212">The anonymous participant is like an external user, but their identity is not projected into the meeting.</span></span> <span data-ttu-id="64360-213">参加時に、手動でニックネームを入力します。</span><span class="sxs-lookup"><span data-stu-id="64360-213">At join time, they manually enter a nickname.</span></span> <span data-ttu-id="64360-214">匿名参加者の詳細については、「[セキュリティと Microsoft Teams](teams-security-guide.md#participant-types)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64360-214">Learn more about an anonymous participant in [Security and Microsoft Teams](teams-security-guide.md#participant-types).</span></span>

| <span data-ttu-id="64360-215">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="64360-215">Live event</span></span>|  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="64360-216">**機能**</span><span class="sxs-lookup"><span data-stu-id="64360-216">**Feature**</span></span>        | <span data-ttu-id="64360-217">事前会議</span><span class="sxs-lookup"><span data-stu-id="64360-217">Pre-meeting</span></span> | <span data-ttu-id="64360-218">会議中</span><span class="sxs-lookup"><span data-stu-id="64360-218">In-meeting</span></span> | <span data-ttu-id="64360-219">会議後</span><span class="sxs-lookup"><span data-stu-id="64360-219">Post-meeting</span></span> |
| <span data-ttu-id="64360-220">チャット</span><span class="sxs-lookup"><span data-stu-id="64360-220">Chat</span></span> | <span data-ttu-id="64360-221">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-221">N/A</span></span> | <span data-ttu-id="64360-222">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-222">N/A</span></span> | <span data-ttu-id="64360-223">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-223">N/A</span></span> |
| <span data-ttu-id="64360-224">会議のメモ</span><span class="sxs-lookup"><span data-stu-id="64360-224">Meeting Notes</span></span> | <span data-ttu-id="64360-225">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-225">N/A</span></span> | <span data-ttu-id="64360-226">X</span><span class="sxs-lookup"><span data-stu-id="64360-226">No</span></span> | <span data-ttu-id="64360-227">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-227">N/A</span></span> |
| <span data-ttu-id="64360-228">ホワイトボード</span><span class="sxs-lookup"><span data-stu-id="64360-228">Whiteboard</span></span> | <span data-ttu-id="64360-229">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-229">N/A</span></span> | <span data-ttu-id="64360-230">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-230">N/A</span></span> | <span data-ttu-id="64360-231">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-231">N/A</span></span> |
| <span data-ttu-id="64360-232">記録</span><span class="sxs-lookup"><span data-stu-id="64360-232">Recording</span></span> | <span data-ttu-id="64360-233">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-233">N/A</span></span> | <span data-ttu-id="64360-234">X</span><span class="sxs-lookup"><span data-stu-id="64360-234">No</span></span> | <span data-ttu-id="64360-235">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-235">N/A</span></span> |
| <span data-ttu-id="64360-236">ファイル</span><span class="sxs-lookup"><span data-stu-id="64360-236">Files</span></span> | <span data-ttu-id="64360-237">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-237">N/A</span></span> | <span data-ttu-id="64360-238">X</span><span class="sxs-lookup"><span data-stu-id="64360-238">No</span></span> | <span data-ttu-id="64360-239">該当なし</span><span class="sxs-lookup"><span data-stu-id="64360-239">N/A</span></span> |
|||||||


## <a name="related-topics"></a><span data-ttu-id="64360-240">関連項目</span><span class="sxs-lookup"><span data-stu-id="64360-240">Related topics</span></span>

[<span data-ttu-id="64360-241">セキュリティと Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64360-241">Security and Microsoft Teams</span></span>](teams-security-guide.md)

[<span data-ttu-id="64360-242">Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="64360-242">Guest access in Teams</span></span>](guest-access.md)

[<span data-ttu-id="64360-243">Teams でライブ イベントを計画する</span><span class="sxs-lookup"><span data-stu-id="64360-243">Plan for live events in Teams</span></span>](teams-live-events/plan-for-teams-live-events.md)
