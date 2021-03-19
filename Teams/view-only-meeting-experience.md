---
title: 表示のみ会議のエクスペリエンス
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 管理者、発表者、出席者向け Teams の表示専用の会議エクスペリエンスについて説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875057"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="c78c5-103">Teams の表示のみ会議のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="c78c5-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="c78c5-104">表示専用ブロードキャストは、Microsoft 365 E3/E5 および Microsoft 365 A3/A5 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="c78c5-105">この機能は、既定ではオフとして 2021 年 3 月 1 日に有効になります。</span><span class="sxs-lookup"><span data-stu-id="c78c5-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="c78c5-106">Microsoft 365 Government Community Cloud (GCC) の機能は、2021 年 3 月末に展開が開始されます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="c78c5-107">Government Community Cloud High (GCCH) と国防総省 (DoD) は、後日ロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="c78c5-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="c78c5-108">この機能を既定でオンにしたい場合は、その日付以降に既定のポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c78c5-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="c78c5-109">PowerShell を使用してポリシーを有効にする `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="c78c5-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="c78c5-110">会議またはウェビナーが容量を超える場合、Teams は 10,000 人のビュー専用ブロードキャストエクスペリエンスに対応するようにシームレスにスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="c78c5-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="c78c5-111">さらに、リモート作業の増加に当たっては、今年の終わりまで、さらに大規模な 20,000 人のブロードキャストを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="c78c5-112">Microsoft Teams では、最大 10,000 人の出席者が Teams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="c78c5-113">メイン会議のキャパシティに達すると、追加の出席者が表示専用のエクスペリエンスで参加します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="c78c5-114">最初に会議に参加する出席者 (会議のキャパシティまで) は、完全な Teams 会議エクスペリエンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="c78c5-115">音声とビデオの共有、共有ビデオの表示、会議チャットへの参加を行います。</span><span class="sxs-lookup"><span data-stu-id="c78c5-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="c78c5-116">メインの会議のキャパシティに達した後に参加する出席者には、表示専用のエクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="c78c5-117">出席者が参加するには、Android と iOS モバイルの完全なサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="c78c5-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="c78c5-118">会議にチャットおよびコールインできるユーザーの現在の制限は、WW では 300 人、GCC では 250 人、GCC High、DoD では 250 人です。</span><span class="sxs-lookup"><span data-stu-id="c78c5-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="c78c5-119">表示専用のエクスペリエンスは、E3/E5/A3/A5 SKU を持つすべての開催者に対して既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c78c5-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="c78c5-120">それ以上の構成やセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c78c5-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="c78c5-121">Teams の表示専用エクスペリエンスを無効にする</span><span class="sxs-lookup"><span data-stu-id="c78c5-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="c78c5-122">管理者は、PowerShell を使用して表示専用のエクスペリエンスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="c78c5-123">今後、管理者は Teams 管理センターで表示専用のエクスペリエンスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="c78c5-124">ユーザーへの影響</span><span class="sxs-lookup"><span data-stu-id="c78c5-124">Impact to users</span></span>

<span data-ttu-id="c78c5-125">ユーザーのエクスペリエンスは、いくつかの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c78c5-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="c78c5-126">メイン会議のキャパシティに達すると、次の条件に該当する場合、出席者は会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="c78c5-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="c78c5-127">管理者が Teams の表示専用エクスペリエンスを無効にしました。</span><span class="sxs-lookup"><span data-stu-id="c78c5-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="c78c5-128">出席者はロビーをバイパスするアクセス許可を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="c78c5-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="c78c5-129">メイン会議のキャパシティに達すると、会議の開催者と発表者に、会議のキャパシティに達し、新しい出席者がビュー専用の出席者に参加するという通知のバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![開催者と発表者向け Teams クライアントとバナー メッセージ](media/chat-and-banner-message.png)

<span data-ttu-id="c78c5-131">メイン会議のキャパシティに達すると、会議の出席者は、参加前の画面で、出席者が表示専用モードで参加中である通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c78c5-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams の事前参加画面と、参加者が表示専用モードで参加すると伝えるメッセージ](media/view-only-pre-join-screen.png)

<span data-ttu-id="c78c5-133">空き領域がある場合、ユーザーは常にメイン会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="c78c5-134">メイン会議がキャパシティに達し、1 人または複数の出席者がメイン会議から退席する場合、メイン会議には利用可能な容量があります。</span><span class="sxs-lookup"><span data-stu-id="c78c5-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="c78c5-135">会議に参加 (または再参加) した出席者は、再び会議のキャパシティに達するまで、メイン会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="c78c5-136">表示専用の操作を行っている出席者は、メイン会議には自動的に昇格されません。また、現在、メイン会議に手動で昇格することはできません。</span><span class="sxs-lookup"><span data-stu-id="c78c5-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="c78c5-137">発表者/出席者の役割が設定されていない場合、メイン会議のスペースは先着順で入力されます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="c78c5-138">会議のキャパシティに達すると、他のすべてのユーザーがビュー専用のエクスペリエンスで参加します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="c78c5-139">会議の発表者への影響</span><span class="sxs-lookup"><span data-stu-id="c78c5-139">Impact to meeting presenters</span></span>

<span data-ttu-id="c78c5-140">会議の発表者には、次のような制限があります。</span><span class="sxs-lookup"><span data-stu-id="c78c5-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="c78c5-141">表示専用の出席者に関する情報はありません。</span><span class="sxs-lookup"><span data-stu-id="c78c5-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="c78c5-142">表示専用の出席者に対する E-discovery はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c78c5-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="c78c5-143">ユーザーは、表示専用の出席者を表示できない。</span><span class="sxs-lookup"><span data-stu-id="c78c5-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="c78c5-144">会議から表示専用の出席者を削除できない。</span><span class="sxs-lookup"><span data-stu-id="c78c5-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="c78c5-145">出席者数には会議の参加者だけが反映され、表示専用ルームのユーザーは反映されません。</span><span class="sxs-lookup"><span data-stu-id="c78c5-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="c78c5-146">そのため、発表者は、ビュー専用のエクスペリエンスを持つユーザーの正確なカウントを取得できないのです。</span><span class="sxs-lookup"><span data-stu-id="c78c5-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="c78c5-147">表示専用の出席者のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="c78c5-147">Experience for view-only attendees</span></span>

<span data-ttu-id="c78c5-148">Teams の表示専用エクスペリエンスでは、出席者は次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="c78c5-149">Teams のメイン会議の参加者の話を聞きます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="c78c5-150">アクティブなスピーカーのビデオ フィードを表示します (アクティブなスピーカーがビデオを共有している場合)。</span><span class="sxs-lookup"><span data-stu-id="c78c5-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="c78c5-151">共有デスクトップ機能を使用して共有されているコンテンツを確認します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="c78c5-152">表示専用の出席者は、会議で次のオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="c78c5-153">出席者にロビー ポリシーまたはオプションの設定に基づいてロビーをバイパスするアクセス許可がない場合は、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="c78c5-154">電話会議を使用して、ビュー専用のルームに参加します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="c78c5-155">Microsoft Teams Room system または Cloud Video Interop (CVI) サービスを使用して、ビュー専用ルームに参加します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="c78c5-156">音声またはビデオを共有します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-156">Share their audio or video.</span></span>
- <span data-ttu-id="c78c5-157">会議チャットを表示または参加します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="c78c5-158">参加者がアクティブなスピーカーである場合を限り、会議参加者のビデオ フィードを表示します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="c78c5-159">ネイティブの共有 PowerPoint 機能または個々のアプリケーション共有 (デスクトップ共有以外) を使用して共有されている PowerPoint ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c78c5-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="c78c5-160">表示専用機能の制限事項</span><span class="sxs-lookup"><span data-stu-id="c78c5-160">View-only feature limitations</span></span>

- <span data-ttu-id="c78c5-161">表示専用の出席者には、その会議のライブ キャプション設定に関係なく、常にライブ キャプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="c78c5-162">現時点では、英語のキャプションのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c78c5-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="c78c5-163">表示専用の出席者はストリーミング テクノロジでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="c78c5-164">表示専用の出席者は、出席レポートに含まれません。</span><span class="sxs-lookup"><span data-stu-id="c78c5-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="c78c5-165">表示専用の出席者は、1 つのビデオエクスペリエンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c78c5-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="c78c5-166">アクティブなスピーカーまたは共有されているコンテンツは表示できますが、両方は表示できません。</span><span class="sxs-lookup"><span data-stu-id="c78c5-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="c78c5-167">現在、表示専用出席者の **ギャラリー**、 **大きなギャラリー**、または **一** 緒に使用するモードのレイアウトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c78c5-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="c78c5-168">表示専用の出席者は、通常の出席者と同じ待機時間を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="c78c5-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="c78c5-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c78c5-169"><sup>1</sup></span></span>

  <span data-ttu-id="c78c5-170"><sup>1</sup> 表示専用の出席者は、会議で 30 秒のビデオと音声による遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="c78c5-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
