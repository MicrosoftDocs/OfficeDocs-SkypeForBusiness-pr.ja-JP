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
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875057"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="f92a1-103">Teams の表示限定の会議エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="f92a1-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="f92a1-104">表示限定のブロードキャストは、Microsoft 365 E3/E5 および Microsoft 365 A3/A5 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="f92a1-105">この機能は2021 年 3 月 1 日に有効になりますが、既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="f92a1-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="f92a1-106">Microsoft 365 Government Community Cloud (GCC) の機能は、2021 年 3 月末にロールアウトが開始される予定です。</span><span class="sxs-lookup"><span data-stu-id="f92a1-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="f92a1-107">Government Community Cloud High (GCCH) と Department of Defense (DoD) は後日ロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="f92a1-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="f92a1-108">この機能を既定でオンにしたい場合は、その日付以降に既定のポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f92a1-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="f92a1-109">PowerShell を使用して、ポリシー`Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`を有効にする。</span><span class="sxs-lookup"><span data-stu-id="f92a1-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="f92a1-110">会議やウェビナーが容量を超えた場合、Teams は 10,000 人に対応できる表示限定のブロードキャスト エクスペリエンスにシームレスに拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="f92a1-111">さらに、リモート 作業が増加したこの期間中は、今年の終わりまでさらに大規模な 20,000 人のブロードキャストを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="f92a1-112">Microsoft Teams では、最大 10,000 人の参加者がTeams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="f92a1-113">メイン会議の容量に達すると、その他の出席者は表示限定のエクスペリエンスで参加します。</span><span class="sxs-lookup"><span data-stu-id="f92a1-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="f92a1-114">会議に最初に参加する出席者 (会議の容量制限まで) は、Teams の会議エクスペリエンスをフルに活用できます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="f92a1-115">音声とビデオの共有、共有ビデオの表示、会議チャットへの参加ができます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="f92a1-116">主要な会議の容量に達した後に参加する出席者には、表示限定のエクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="f92a1-117">出席者が参加できるように、Android と iOS モバイルの完全なサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="f92a1-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="f92a1-118">現在、会議でチャットや通話ができるユーザー数の制限は、WW では 300、GCC、GCC High、DoD では 250です。</span><span class="sxs-lookup"><span data-stu-id="f92a1-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="f92a1-119">E3/E5/A3/A5 SKU を持つ主催者の場合、規定で表示限定のエクスペリエンスは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f92a1-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="f92a1-120">それ以上の構成やセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="f92a1-121">Teams の表示限定のエクスペリエンスを無効にする</span><span class="sxs-lookup"><span data-stu-id="f92a1-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="f92a1-122">管理者は、PowerShell を使用して表示限定のエクスペリエンスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="f92a1-123">今後、管理者は Teams 管理センターで表示限定のエクスペリエンスを無効にできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f92a1-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="f92a1-124">ユーザーへの影響</span><span class="sxs-lookup"><span data-stu-id="f92a1-124">Impact to users</span></span>

<span data-ttu-id="f92a1-125">ユーザーのエクスペリエンスは、いくつかの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f92a1-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="f92a1-126">メイン会議の容量に達すると、次の場合、出席者は会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="f92a1-127">管理者が Teams の表示限定のエクスペリエンスを無効にしました。</span><span class="sxs-lookup"><span data-stu-id="f92a1-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="f92a1-128">参加者には、ロビーをバイパスするアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="f92a1-129">メイン会議の容量に達すると、会議の開催者と発表者には、会議の出席者の容量に達し、新しい出席者が表示限定の出席者として参加する、という通知のバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![主催者と発表者用の Teams クライアントとバナー メッセージ](media/chat-and-banner-message.png)

<span data-ttu-id="f92a1-131">メイン会議の容量に達すると、会議の出席者は参加前の画面で、表示限定モードで参加しているという通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams の参加前の画面と参加者に表示限定モードで参加することを伝えるメッセージ](media/view-only-pre-join-screen.png)

<span data-ttu-id="f92a1-133">スペースがある場合は、ユーザーは常にメイン会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="f92a1-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="f92a1-134">メイン会議が容量に達してから、1 人または複数の出席者がメイン会議を離れると、メイン会議には利用可能な容量ができます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="f92a1-135">会議に参加 (または再参加) した出席者は、再び容量に達するまでメイン会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="f92a1-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="f92a1-136">表示限定のエクスペリエンスで参加している出席者は、自動的にメイン会議に昇格されることはありません。現在、メイン会議に手動で昇格することはできません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="f92a1-137">発表者/出席者の役割が設定されていない場合は、メイン会議のスペースが先着順で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="f92a1-138">会議の容量に達すると、他のすべてのユーザーは表示限定のエクスペリエンスで参加します。</span><span class="sxs-lookup"><span data-stu-id="f92a1-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="f92a1-139">会議の発表者に与える影響</span><span class="sxs-lookup"><span data-stu-id="f92a1-139">Impact to meeting presenters</span></span>

<span data-ttu-id="f92a1-140">会議の発表者には次のような制限があります。</span><span class="sxs-lookup"><span data-stu-id="f92a1-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="f92a1-141">表示限定の出席者に関する情報はありません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="f92a1-142">E-Discovery は、表示限定の出席者に対してサポートしません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="f92a1-143">ユーザーは、表示限定の出席者を表示できません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="f92a1-144">会議から表示限定の出席者を削除できません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="f92a1-145">出席者数には会議のユーザー数だけが反映され、表示限定会議室のユーザー数は反映されません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="f92a1-146">そのため、発表者は、表示限定エクスペリエンスのユーザー数を正確にカウントすることができません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="f92a1-147">表示限定出席者のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="f92a1-147">Experience for view-only attendees</span></span>

<span data-ttu-id="f92a1-148">Teams の表示限定エクスペリエンスでは、参加者は次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="f92a1-149">Teams のメイン会議の参加者の話を聞きます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="f92a1-150">アクティブなスピーカーのビデオ フィードを見ます (アクティブなスピーカーがビデオを共有している場合)。</span><span class="sxs-lookup"><span data-stu-id="f92a1-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="f92a1-151">デスクトップ共有機能を使用して共有されているコンテンツを閲覧します。</span><span class="sxs-lookup"><span data-stu-id="f92a1-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="f92a1-152">表示限定出席者は、会議で次のオプションを利用できません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="f92a1-153">設定したロビー ポリシーまたはオプションに基づく、ロビーをバイパスするアクセス許可を持っていてない場合は、会議に参加すること。</span><span class="sxs-lookup"><span data-stu-id="f92a1-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="f92a1-154">オーディオ会議を使用して、表示限定の部屋に参加すること。</span><span class="sxs-lookup"><span data-stu-id="f92a1-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="f92a1-155">Microsoft Teams Room System を使用するか、クラウド ビデオ相互運用機能 (CVI) サービスを使用して、表示限定の部屋に参加すること。</span><span class="sxs-lookup"><span data-stu-id="f92a1-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="f92a1-156">オーディオまたはビデオを共有すること。</span><span class="sxs-lookup"><span data-stu-id="f92a1-156">Share their audio or video.</span></span>
- <span data-ttu-id="f92a1-157">会議チャットを参照または参加すること。</span><span class="sxs-lookup"><span data-stu-id="f92a1-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="f92a1-158">参加者がアクティブな発表者でない場合は、会議参加者のビデオ フィードを参照すること。</span><span class="sxs-lookup"><span data-stu-id="f92a1-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="f92a1-159">(デスクトップ共有以外の) ネイティブ共有の PowerPoint 機能または個々のアプリケーション共有を使用して共有されている PowerPoint ファイルを参照すること。</span><span class="sxs-lookup"><span data-stu-id="f92a1-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="f92a1-160">表示限定機能の制限</span><span class="sxs-lookup"><span data-stu-id="f92a1-160">View-only feature limitations</span></span>

- <span data-ttu-id="f92a1-161">表示限定の出席者には、その会議のライブ キャプション設定に関係なく、常にライブ キャプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="f92a1-162">現時点でサポートされているのは英語のキャプションのみです。</span><span class="sxs-lookup"><span data-stu-id="f92a1-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="f92a1-163">表示限定の出席者はストリーミング テクノロジでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="f92a1-164">参加レポートには、表示限定の出席者は含まれません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="f92a1-165">表示限定の出席者は、1 つのビデオ機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="f92a1-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="f92a1-166">アクティブな発表者を見ること、または共有されているコンテンツの閲覧はできますが、両方はできません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="f92a1-167">現在、**ギャラリー**、 **大きなギャラリー**、または表示限定の出席者用の **Together モード** レイアウトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="f92a1-168">表示限定の出席者は、通常の出席者と同じ待機時間ではありません。</span><span class="sxs-lookup"><span data-stu-id="f92a1-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="f92a1-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f92a1-169"><sup>1</sup></span></span>

  <span data-ttu-id="f92a1-170"><sup>1</sup> 表示限定の出席者は、会議で 30 秒のビデオと音声の遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="f92a1-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
