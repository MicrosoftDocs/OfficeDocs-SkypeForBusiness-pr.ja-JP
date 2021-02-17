---
title: 表示のみ会議のエクスペリエンス
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
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
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237457"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="280a1-103">Teams の表示のみ会議のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="280a1-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="280a1-104">表示専用の会議エクスペリエンスは、2021 年 3 月初めに利用できます。</span><span class="sxs-lookup"><span data-stu-id="280a1-104">View-only meeting experience will be available in early March 2021.</span></span>

> [!Note]
> <span data-ttu-id="280a1-105">20,000 人の出席者に対する表示専用のエクスペリエンスが一時的に向上しましたが、2021 年 6 月 30 日に 10,000 人の出席者にサポートを戻します。</span><span class="sxs-lookup"><span data-stu-id="280a1-105">We've temporarily increased view-only experience for 20,000 attendees, but we'll revert support to 10,000 attendees on June 30, 2021.</span></span>

<span data-ttu-id="280a1-106">Microsoft Teams では、最大 10,000 人の出席者が Teams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="280a1-106">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="280a1-107">メイン会議のキャパシティに達すると、追加の出席者がビュー専用のエクスペリエンスで参加します。</span><span class="sxs-lookup"><span data-stu-id="280a1-107">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="280a1-108">最初に会議に参加する出席者 (会議のキャパシティまで) は、完全な Teams 会議エクスペリエンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="280a1-108">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="280a1-109">音声とビデオの共有、共有ビデオの表示、会議チャットへの参加を行います。</span><span class="sxs-lookup"><span data-stu-id="280a1-109">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="280a1-110">メインの会議のキャパシティに達した後に参加する出席者には、表示専用のエクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="280a1-110">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="280a1-111">参加者が参加するために Android および iOS モバイルの完全なサポートを受け取っている。</span><span class="sxs-lookup"><span data-stu-id="280a1-111">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="280a1-112">会議にチャットおよびコールインできるユーザーの現在の制限は、WW では 300 人、GCC では 250 人、GCC High、DoD では 250 人です。</span><span class="sxs-lookup"><span data-stu-id="280a1-112">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="280a1-113">表示専用のエクスペリエンスは、E3/E5/A3/A5 SKU を持つすべての開催者に対して既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="280a1-113">The view-only experience is enabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="280a1-114">それ以上の構成やセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="280a1-114">No further configuration or setup is required.</span></span>

### <a name="disable-teams-view-only-experience"></a><span data-ttu-id="280a1-115">Teams の表示専用エクスペリエンスを無効にする</span><span class="sxs-lookup"><span data-stu-id="280a1-115">Disable Teams view-only experience</span></span>

<span data-ttu-id="280a1-116">管理者は、PowerShell を使用して表示専用のエクスペリエンスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="280a1-116">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="280a1-117">今後、管理者は Teams 管理センターで表示専用のエクスペリエンスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="280a1-117">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="280a1-118">ユーザーへの影響</span><span class="sxs-lookup"><span data-stu-id="280a1-118">Impact to users</span></span>

<span data-ttu-id="280a1-119">ユーザーのエクスペリエンスは、いくつかの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="280a1-119">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="280a1-120">メイン会議のキャパシティに達すると、次の条件に該当する場合、出席者は会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="280a1-120">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="280a1-121">管理者が Teams の表示専用エクスペリエンスを無効にしました。</span><span class="sxs-lookup"><span data-stu-id="280a1-121">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="280a1-122">出席者には、ロビーをバイパスするアクセス許可が与えらな。</span><span class="sxs-lookup"><span data-stu-id="280a1-122">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="280a1-123">メイン会議のキャパシティに達すると、会議の開催者と発表者に、会議のキャパシティに達し、新しい出席者がビュー専用の出席者に参加するという通知のバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="280a1-123">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![開催者と発表者のための Teams クライアントとバナーの乱雑な問題](media/chat-and-banner-message.png)

<span data-ttu-id="280a1-125">メイン会議のキャパシティに達すると、会議の出席者は、参加前の画面で、出席者が表示専用モードで参加中である通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="280a1-125">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams の事前参加画面と、参加者に表示専用モードで参加を伝えるメッセージ](media/view-only-pre-join-screen.png)

<span data-ttu-id="280a1-127">空き領域がある場合、ユーザーは常にメイン会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="280a1-127">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="280a1-128">メイン会議がキャパシティに達し、1 人または複数の出席者がメイン会議から退席した場合、メイン会議には利用可能な容量があります。</span><span class="sxs-lookup"><span data-stu-id="280a1-128">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="280a1-129">会議に参加 (または再参加) した出席者は、再び会議のキャパシティに達するまで、メイン会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="280a1-129">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="280a1-130">表示専用の操作に参加している出席者は、メイン会議には自動的に昇格されません。また、現在、メイン会議に手動で昇格することはできません。</span><span class="sxs-lookup"><span data-stu-id="280a1-130">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="280a1-131">発表者/出席者の役割が設定されていない場合、メイン会議のスペースは先着順で入力されます。</span><span class="sxs-lookup"><span data-stu-id="280a1-131">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="280a1-132">会議のキャパシティに達すると、他のすべてのユーザーがビュー専用のエクスペリエンスで参加します。</span><span class="sxs-lookup"><span data-stu-id="280a1-132">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="280a1-133">会議の発表者への影響</span><span class="sxs-lookup"><span data-stu-id="280a1-133">Impact to meeting presenters</span></span>

<span data-ttu-id="280a1-134">通常の会議には、会議オプションで発表者として明示的に指定されたユーザー用の空き領域が予約されます。</span><span class="sxs-lookup"><span data-stu-id="280a1-134">We'll reserve space in the normal meeting for users explicitly indicated as presenters in the meeting options.</span></span> <span data-ttu-id="280a1-135">発表者が離れ、その後会議に再び参加すると、発表者として会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="280a1-135">If a presenter leaves and then later rejoins the meeting, they'll be let into the meeting as a presenter.</span></span>

<span data-ttu-id="280a1-136">会議の発表者には、次のような制限があります。</span><span class="sxs-lookup"><span data-stu-id="280a1-136">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="280a1-137">表示専用の出席者に関する情報はありません。</span><span class="sxs-lookup"><span data-stu-id="280a1-137">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="280a1-138">表示専用の出席者に対する E-discovery はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="280a1-138">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="280a1-139">ユーザーは、表示専用の出席者を表示できない。</span><span class="sxs-lookup"><span data-stu-id="280a1-139">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="280a1-140">会議から表示専用の出席者を削除できない。</span><span class="sxs-lookup"><span data-stu-id="280a1-140">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="280a1-141">出席者数は会議の参加者のみを反映し、オーバーフロールームのユーザーは反映されません。</span><span class="sxs-lookup"><span data-stu-id="280a1-141">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="280a1-142">そのため、発表者は、ビュー専用のエクスペリエンスを持つユーザーの正確なカウントを取得できない。</span><span class="sxs-lookup"><span data-stu-id="280a1-142">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="280a1-143">表示専用の出席者のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="280a1-143">Experience for view-only attendees</span></span>

<span data-ttu-id="280a1-144">Teams の表示専用エクスペリエンスでは、出席者は次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="280a1-144">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="280a1-145">Teams のメイン会議の参加者の話を聞きます。</span><span class="sxs-lookup"><span data-stu-id="280a1-145">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="280a1-146">アクティブなスピーカーのビデオ フィードを表示します (アクティブなスピーカーがビデオを共有している場合)。</span><span class="sxs-lookup"><span data-stu-id="280a1-146">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="280a1-147">共有デスクトップ機能を使用して共有されているコンテンツを確認します。</span><span class="sxs-lookup"><span data-stu-id="280a1-147">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="280a1-148">表示専用の出席者は、会議で次のオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="280a1-148">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="280a1-149">出席者にロビー ポリシーまたはオプションの設定に基づいてロビーをバイパスするアクセス許可がない場合は、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="280a1-149">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="280a1-150">電話会議でオーバーフロー ルームに参加します。</span><span class="sxs-lookup"><span data-stu-id="280a1-150">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="280a1-151">Microsoft Teams Room system または Cloud Video Interop (CVI) サービスを介してオーバーフロー ルームに参加します。</span><span class="sxs-lookup"><span data-stu-id="280a1-151">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="280a1-152">Teams Android モバイル アプリでオーバーフロー ルームに参加します。</span><span class="sxs-lookup"><span data-stu-id="280a1-152">Join the Overflow Room via the Teams Android mobile app.</span></span>
- <span data-ttu-id="280a1-153">音声またはビデオを共有します。</span><span class="sxs-lookup"><span data-stu-id="280a1-153">Share their audio or video.</span></span>
- <span data-ttu-id="280a1-154">会議チャットを表示または参加します。</span><span class="sxs-lookup"><span data-stu-id="280a1-154">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="280a1-155">参加者がアクティブな発表者である場合を含め、会議参加者のビデオ フィードを表示します。</span><span class="sxs-lookup"><span data-stu-id="280a1-155">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="280a1-156">ネイティブの共有 PowerPoint 機能または (デスクトップ共有以外の) 個々のアプリケーション共有を使用して共有されている PowerPoint ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="280a1-156">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="280a1-157">表示専用機能の制限事項</span><span class="sxs-lookup"><span data-stu-id="280a1-157">View-only feature limitations</span></span>

- <span data-ttu-id="280a1-158">表示専用の出席者には、その会議のライブ キャプション設定に関係なく、常にライブ キャプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="280a1-158">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="280a1-159">現時点では、英語のキャプションのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="280a1-159">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="280a1-160">表示専用の出席者はストリーミング テクノロジでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="280a1-160">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="280a1-161">表示専用の出席者は、出席レポートに含まれません。</span><span class="sxs-lookup"><span data-stu-id="280a1-161">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="280a1-162">表示専用の出席者は、1 つのビデオエクスペリエンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="280a1-162">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="280a1-163">アクティブなスピーカーまたは共有されているコンテンツは表示できますが、両方は表示できません。</span><span class="sxs-lookup"><span data-stu-id="280a1-163">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="280a1-164">現在、表示専用出席者の **ギャラリー**、 **大きなギャラリー**、または **一** 緒に使用するモードのレイアウトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="280a1-164">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="280a1-165">表示専用の出席者は、通常の出席者と同じ待機時間を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="280a1-165">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="280a1-166"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="280a1-166"><sup>1</sup></span></span>

  <span data-ttu-id="280a1-167"><sup>1</sup> 表示専用の出席者は、会議で 30 秒のビデオと音声による遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="280a1-167"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="280a1-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="280a1-168">Related topics</span></span>

- [<span data-ttu-id="280a1-169">Teams の高度なコミュニケーション アドオン</span><span class="sxs-lookup"><span data-stu-id="280a1-169">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="280a1-170">Teams の制限と仕様</span><span class="sxs-lookup"><span data-stu-id="280a1-170">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)