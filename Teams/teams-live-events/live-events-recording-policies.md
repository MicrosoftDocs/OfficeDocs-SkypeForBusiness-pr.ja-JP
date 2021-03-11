---
title: ライブ イベント記録ポリシー
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: ライブ イベント記録ポリシーについて説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9fd67ce67d31effdba0d152a3d5920bb17f23b25
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615176"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="ad709-103">Microsoft Teams のライブ イベント記録ポリシー</span><span class="sxs-lookup"><span data-stu-id="ad709-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="ad709-104">Microsoft Teams ライブ イベントを記録するためのオプションは複数あります。</span><span class="sxs-lookup"><span data-stu-id="ad709-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="ad709-105">記録オプションは、記録ポリシーを使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="ad709-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="ad709-106">この記事では、さまざまな設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad709-106">This article describes the various settings.</span></span>

<span data-ttu-id="ad709-107">記録オプションは、PowerShell コマンド [Set-CsTeamsMeetingBroadcastPolicy を使用して設定されます。](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ad709-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="ad709-108">スケジュールとオプションの動作</span><span class="sxs-lookup"><span data-stu-id="ad709-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="ad709-109">ライブ イベントの記録をスケジュールする場合、開催者のオプションは 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="ad709-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="ad709-110">プロデューサーと発表者が利用できるレコーディング</span><span class="sxs-lookup"><span data-stu-id="ad709-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="ad709-111">レコーディング ファイル: プロデューサーと発表者がイベントの終了後にダウンロードできるレコーディング ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="ad709-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="ad709-112">出席者が利用できるレコーディング</span><span class="sxs-lookup"><span data-stu-id="ad709-112">Recording available for attendees</span></span>

  - <span data-ttu-id="ad709-113">DVR: デジタル ビデオレコーダー (DVR) を使用すると、出席者はイベント中に巻き戻しや一時停止を行える</span><span class="sxs-lookup"><span data-stu-id="ad709-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="ad709-114">VOD: ビデオ オンデマンド (VOD) を使用すると、イベントが終わった後に出席者が視聴できます。</span><span class="sxs-lookup"><span data-stu-id="ad709-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="ad709-115">ブロードキャスト録画ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="ad709-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="ad709-116">ブロードキャスト ポリシーの一部として、ライブ イベントのレコーディングをオンまたはオフに切り替える設定があります。</span><span class="sxs-lookup"><span data-stu-id="ad709-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="ad709-117">プロデューサーと発表者が利用できるレコーディング</span><span class="sxs-lookup"><span data-stu-id="ad709-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="ad709-118">出席者が利用できるレコーディング</span><span class="sxs-lookup"><span data-stu-id="ad709-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="ad709-119">常に記録する</span><span class="sxs-lookup"><span data-stu-id="ad709-119">Always record</span></span>               | <span data-ttu-id="ad709-120">無効と選択</span><span class="sxs-lookup"><span data-stu-id="ad709-120">Disabled and selected</span></span>                                | <span data-ttu-id="ad709-121">無効と選択</span><span class="sxs-lookup"><span data-stu-id="ad709-121">Disabled and selected</span></span>         |
| <span data-ttu-id="ad709-122">開催者は記録可能または記録しない</span><span class="sxs-lookup"><span data-stu-id="ad709-122">Organizer can record or not</span></span> | <span data-ttu-id="ad709-123">既定で有効で選択されていない</span><span class="sxs-lookup"><span data-stu-id="ad709-123">Enabled and not selected by default</span></span>                  | <span data-ttu-id="ad709-124">既定で有効で選択されていない</span><span class="sxs-lookup"><span data-stu-id="ad709-124">Enabled and not selected by default</span></span>   |
| <span data-ttu-id="ad709-125">記録しない</span><span class="sxs-lookup"><span data-stu-id="ad709-125">Never record</span></span>               | <span data-ttu-id="ad709-126">無効で選択されていない</span><span class="sxs-lookup"><span data-stu-id="ad709-126">Disabled and not selected</span></span>                            | <span data-ttu-id="ad709-127">無効で選択されていない</span><span class="sxs-lookup"><span data-stu-id="ad709-127">Disabled and not selected</span></span>      |

<span data-ttu-id="ad709-128">ポリシーが [常に記録] **に設定されている場合**、ポリシー ページには次のオプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="ad709-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="ad709-129">![ライブ イベント ポリシーの設定](../media/live-event-recording-policy.png "Microsoft Teams 管理センターのライブ イベント ポリシーの設定を示すスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="ad709-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="ad709-130">記憶域と永続性の動作</span><span class="sxs-lookup"><span data-stu-id="ad709-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="ad709-131">オプション</span><span class="sxs-lookup"><span data-stu-id="ad709-131">Option</span></span>                                       | <span data-ttu-id="ad709-132">都道府県</span><span class="sxs-lookup"><span data-stu-id="ad709-132">State</span></span>   | <span data-ttu-id="ad709-133">DVR</span><span class="sxs-lookup"><span data-stu-id="ad709-133">DVR</span></span>                                                   | <span data-ttu-id="ad709-134">VOD</span><span class="sxs-lookup"><span data-stu-id="ad709-134">VOD</span></span>                                                     | <span data-ttu-id="ad709-135">記録</span><span class="sxs-lookup"><span data-stu-id="ad709-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="ad709-136">プロデューサーと発表者が利用できるレコーディング</span><span class="sxs-lookup"><span data-stu-id="ad709-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="ad709-137">選択済み</span><span class="sxs-lookup"><span data-stu-id="ad709-137">Selected</span></span>     | <span data-ttu-id="ad709-138">DVR が利用可能で、Azure Media Services (AMS) アセットが 180 日間保存される</span><span class="sxs-lookup"><span data-stu-id="ad709-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="ad709-139">出席者はイベントにアクセスして見る</span><span class="sxs-lookup"><span data-stu-id="ad709-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="ad709-140">選択されていない</span><span class="sxs-lookup"><span data-stu-id="ad709-140">Not Selected</span></span> | <span data-ttu-id="ad709-141">DVR が利用可能で、AMS アセットが 180 日間保存される</span><span class="sxs-lookup"><span data-stu-id="ad709-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="ad709-142">イベントが終わった後、出席者はイベントにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="ad709-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="ad709-143">無効 (選択されていない)</span><span class="sxs-lookup"><span data-stu-id="ad709-143">Disabled (Not selected)</span></span>|<span data-ttu-id="ad709-144">DVR が使用可能で、イベントの後に AMS アセットが削除される</span><span class="sxs-lookup"><span data-stu-id="ad709-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="ad709-145">イベントが終わった後、出席者はイベントにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="ad709-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="ad709-146">プロデューサーと発表者が利用できるレコーディング</span><span class="sxs-lookup"><span data-stu-id="ad709-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="ad709-147">選択済み</span><span class="sxs-lookup"><span data-stu-id="ad709-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="ad709-148">MP4 が作成および保存される</span><span class="sxs-lookup"><span data-stu-id="ad709-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="ad709-149">選択されていない</span><span class="sxs-lookup"><span data-stu-id="ad709-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="ad709-150">ファイルが作成されません</span><span class="sxs-lookup"><span data-stu-id="ad709-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="ad709-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad709-151">Related topics</span></span>

- [<span data-ttu-id="ad709-152">Teams ライブ イベントとは</span><span class="sxs-lookup"><span data-stu-id="ad709-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="ad709-153">Teams のライブ イベントの計画</span><span class="sxs-lookup"><span data-stu-id="ad709-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="ad709-154">Teams でライブ イベント設定を構成する</span><span class="sxs-lookup"><span data-stu-id="ad709-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="ad709-155">Teams クラウド会議の記録</span><span class="sxs-lookup"><span data-stu-id="ad709-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)
