---
title: 表示限定の会議エクスペリエンス
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 管理者、発表者、出席者の Teams 表示限定の会議エクスペリエンスについて説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09fe424dc576b6b167eec49e7cd8edf2f61d6cce
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697802"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="44455-103">Teams の表示限定の会議エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="44455-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="44455-104">表示限定のブロードキャストは、Microsoft 365 E3/E5 および Microsoft 365 A3/A5 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="44455-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="44455-105">この機能は2021 年 3 月 1 日に有効になりますが、既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="44455-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="44455-106">Microsoft 365 Government Community Cloud (GCC) の機能は、2021 年 3 月末にロールアウトが開始される予定です。</span><span class="sxs-lookup"><span data-stu-id="44455-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="44455-107">Government Community Cloud High (GCCH) と Department of Defense (DoD) は後日ロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="44455-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="44455-108">この機能を既定でオンにしたい場合は、その日付以降に既定のポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44455-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="44455-109">PowerShell を使用して、ポリシー`Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`を有効にする。</span><span class="sxs-lookup"><span data-stu-id="44455-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="44455-110">会議やウェビナーが容量を超えた場合、Teams は 10,000 人に対応できる表示限定のブロードキャスト エクスペリエンスにシームレスに拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="44455-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="44455-111">さらに、リモート 作業が増加したこの期間中は、今年の終わりまでさらに大規模な 20,000 人のブロードキャストを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="44455-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="44455-112">Microsoft Teams では、最大 10,000 人の参加者がTeams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="44455-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="44455-113">メイン会議のキャパシティに達すると (300 人のユーザーが会議に参加すると)、追加の出席者がビュー専用のエクスペリエンスで参加します。</span><span class="sxs-lookup"><span data-stu-id="44455-113">After the capacity of the main meeting has been reached (which is when 300 users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="44455-114">メイン会議のキャパシティまで、最初に会議に参加する出席者には、完全な Teams 会議エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="44455-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="44455-115">音声とビデオの共有、共有ビデオの表示、会議チャットへの参加ができます。</span><span class="sxs-lookup"><span data-stu-id="44455-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="44455-116">主要な会議の容量に達した後に参加する出席者には、表示限定のエクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="44455-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="44455-117">出席者は、デスクトップ、Web、Teams モバイル (Android および iOS) を通じて表示専用のエクスペリエンスに参加できます。</span><span class="sxs-lookup"><span data-stu-id="44455-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="44455-118">"メイン会議" (つまり、完全に対話可能なユーザーの数) の現在の制限容量は、WW では 300 人、GCC、GCC High、DoD では 250 人です。</span><span class="sxs-lookup"><span data-stu-id="44455-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="44455-119">Teams の表示専用エクスペリエンス コントロール</span><span class="sxs-lookup"><span data-stu-id="44455-119">Teams view-only experience controls</span></span>

<span data-ttu-id="44455-120">PowerShell を使用して表示専用のエクスペリエンスを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="44455-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="44455-121">表示専用のエクスペリエンスを無効にするには、PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="44455-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="44455-122">今後は、Teams 管理センターで表示専用のエクスペリエンスを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="44455-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="44455-123">ユーザーへの影響</span><span class="sxs-lookup"><span data-stu-id="44455-123">Impact to users</span></span>

<span data-ttu-id="44455-124">ユーザーのエクスペリエンスは、いくつかの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="44455-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="44455-125">メイン会議の容量に達すると、次の場合、出席者は会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="44455-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="44455-126">管理者が、開催者またはテナント全体に対して Teams ビュー専用のエクスペリエンスを無効にしました。</span><span class="sxs-lookup"><span data-stu-id="44455-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="44455-127">ビュー専用の出席者はロビーをバイパスできない。</span><span class="sxs-lookup"><span data-stu-id="44455-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="44455-128">たとえば、会議の開催者が、組織内のユーザーだけがロビーをバイパスし、組織外の出席者がビュー専用の出席者として参加しようとする場合、参加者は参加できます。</span><span class="sxs-lookup"><span data-stu-id="44455-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they won't be able to join.</span></span>

<span data-ttu-id="44455-129">メイン会議のキャパシティに達すると、会議の開催者と発表者には、新しい出席者が表示専用の出席者として参加するという通知のバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44455-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![主催者と発表者用の Teams クライアントとバナー メッセージ](media/chat-and-banner-message.png)

<span data-ttu-id="44455-131">メイン会議の容量に達すると、会議の出席者は参加前の画面で、表示限定モードで参加しているという通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44455-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams の参加前の画面と参加者に表示限定モードで参加することを伝えるメッセージ](media/view-only-pre-join-screen.png)

<span data-ttu-id="44455-133">スペースがある場合は、ユーザーは常にメイン会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="44455-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="44455-134">メイン会議が容量に達してから、1 人または複数の出席者がメイン会議を離れると、メイン会議には利用可能な容量ができます。</span><span class="sxs-lookup"><span data-stu-id="44455-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="44455-135">会議に参加 (または再参加) した出席者は、再び容量に達するまでメイン会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="44455-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="44455-136">表示専用の操作に参加している出席者は、自動的にメイン会議に昇格されるので、メイン会議に手動で昇格することはできません。</span><span class="sxs-lookup"><span data-stu-id="44455-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't be manually promoted to the main meeting.</span></span>

<span data-ttu-id="44455-137">発表者と出席者の役割が設定され、発表者がメイン会議のキャパシティに達した後に会議に参加しようとすると、発表者は表示専用の出席者として参加し、他の表示専用出席者と同じ制限を持つ。</span><span class="sxs-lookup"><span data-stu-id="44455-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="44455-138">すべての発表者がメイン会議に参加するためのサポートは、後日ロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="44455-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="44455-139">開催者は、常にメイン会議の空き領域が保証されます。</span><span class="sxs-lookup"><span data-stu-id="44455-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters-and-organizers"></a><span data-ttu-id="44455-140">会議の発表者と開催者への影響</span><span class="sxs-lookup"><span data-stu-id="44455-140">Impact to meeting presenters and organizers</span></span>

<span data-ttu-id="44455-141">会議の発表者と開催者の制限事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44455-141">Limitations for meeting presenters and organizers include:</span></span>

- <span data-ttu-id="44455-142">表示限定の出席者に関する情報はありません。</span><span class="sxs-lookup"><span data-stu-id="44455-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="44455-143">E-Discovery は、表示限定の出席者に対してサポートしません。</span><span class="sxs-lookup"><span data-stu-id="44455-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="44455-144">メイン会議のユーザーには、表示専用の出席者が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44455-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="44455-145">会議から表示限定の出席者を削除できません。</span><span class="sxs-lookup"><span data-stu-id="44455-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="44455-146">出席者数には、メイン会議の参加者だけが反映され、表示専用ルームのユーザーは反映されません。</span><span class="sxs-lookup"><span data-stu-id="44455-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="44455-147">そのため、発表者は、表示限定エクスペリエンスのユーザー数を正確にカウントすることができません。</span><span class="sxs-lookup"><span data-stu-id="44455-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="44455-148">表示限定出席者のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="44455-148">Experience for view-only attendees</span></span>

<span data-ttu-id="44455-149">Teams の表示限定エクスペリエンスでは、参加者は次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="44455-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="44455-150">Teams のメイン会議の参加者の話を聞きます。</span><span class="sxs-lookup"><span data-stu-id="44455-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="44455-151">アクティブなスピーカーのビデオ フィードを見ます (アクティブなスピーカーがビデオを共有している場合)。</span><span class="sxs-lookup"><span data-stu-id="44455-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="44455-152">デスクトップまたは画面の共有機能を使用して、共有されているコンテンツを確認します。</span><span class="sxs-lookup"><span data-stu-id="44455-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="44455-153">表示限定出席者は、会議で次のオプションを利用できません。</span><span class="sxs-lookup"><span data-stu-id="44455-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="44455-154">設定したロビー ポリシーまたはオプションに基づく、ロビーをバイパスするアクセス許可を持っていてない場合は、会議に参加すること。</span><span class="sxs-lookup"><span data-stu-id="44455-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="44455-155">オーディオ会議を使用して、表示限定の部屋に参加すること。</span><span class="sxs-lookup"><span data-stu-id="44455-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="44455-156">Microsoft Teams Rooms システムを使用するか、クラウド ビデオ相互運用 (CVI) サービスを使用して、ビュー専用ルームに参加します。</span><span class="sxs-lookup"><span data-stu-id="44455-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="44455-157">オーディオまたはビデオを共有すること。</span><span class="sxs-lookup"><span data-stu-id="44455-157">Share their audio or video.</span></span>
- <span data-ttu-id="44455-158">会議チャットを参照または参加すること。</span><span class="sxs-lookup"><span data-stu-id="44455-158">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="44455-159">参加者がアクティブな発表者でない場合は、会議参加者のビデオ フィードを参照すること。</span><span class="sxs-lookup"><span data-stu-id="44455-159">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="44455-160">PowerPoint Live 機能または個々のアプリケーション共有 (デスクトップまたは画面共有以外) を使用して共有されている PowerPoint ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44455-160">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="44455-161">会議で手を上げる。</span><span class="sxs-lookup"><span data-stu-id="44455-161">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="44455-162">リアクションを送信または表示します。</span><span class="sxs-lookup"><span data-stu-id="44455-162">Send or see reactions.</span></span>
- <span data-ttu-id="44455-163">投票を含む、Teams 会議に統合されている 3P アプリと対話します。</span><span class="sxs-lookup"><span data-stu-id="44455-163">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="44455-164">表示限定機能の制限</span><span class="sxs-lookup"><span data-stu-id="44455-164">View-only feature limitations</span></span>

- <span data-ttu-id="44455-165">表示専用の出席者は、デスクトップと Web でのみライブ キャプションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="44455-165">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="44455-166">現時点でサポートされているのは英語のキャプションのみです。</span><span class="sxs-lookup"><span data-stu-id="44455-166">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="44455-167">表示限定の出席者はストリーミング テクノロジでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="44455-167">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="44455-168">参加レポートには、表示限定の出席者は含まれません。</span><span class="sxs-lookup"><span data-stu-id="44455-168">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="44455-169">表示限定の出席者は、1 つのビデオ機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="44455-169">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="44455-170">アクティブな発表者を見ること、または共有されているコンテンツの閲覧はできますが、両方はできません。</span><span class="sxs-lookup"><span data-stu-id="44455-170">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="44455-171">現在、**ギャラリー**、 **大きなギャラリー**、または表示限定の出席者用の **Together モード** レイアウトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="44455-171">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="44455-172">表示限定の出席者は、通常の出席者と同じ待機時間ではありません。</span><span class="sxs-lookup"><span data-stu-id="44455-172">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="44455-173"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="44455-173"><sup>1</sup></span></span>

  <span data-ttu-id="44455-174"><sup>1</sup> 表示限定の出席者は、会議で 30 秒のビデオと音声の遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="44455-174"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
