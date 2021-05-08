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
ms.openlocfilehash: 9c808e4ae4e27e48c14c45711ef80ffd1c812125
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383971"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="47777-103">ライブ イベント記録ポリシー (Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47777-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="47777-104">ライブ イベントを記録するためのオプションMicrosoft Teamsがあります。</span><span class="sxs-lookup"><span data-stu-id="47777-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="47777-105">記録オプションは、記録ポリシーを使用して設定されます。</span><span class="sxs-lookup"><span data-stu-id="47777-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="47777-106">この記事では、さまざまな設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="47777-106">This article describes the various settings.</span></span>

<span data-ttu-id="47777-107">記録オプションは、PowerShell コマンド [Set-CsTeamsMeetingBroadcastPolicy を使用して設定されます](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="47777-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="47777-108">スケジュールとオプションの動作</span><span class="sxs-lookup"><span data-stu-id="47777-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="47777-109">ライブ イベントの記録をスケジュールする場合、開催者のオプションは 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="47777-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="47777-110">プロデューサーと発表者が使用できるレコーディング</span><span class="sxs-lookup"><span data-stu-id="47777-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="47777-111">レコーディング ファイル: プロデューサーと発表者がイベントの終了後にダウンロードできる録音ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="47777-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="47777-112">出席者が利用できる記録</span><span class="sxs-lookup"><span data-stu-id="47777-112">Recording available for attendees</span></span>

  - <span data-ttu-id="47777-113">DVR: デジタル ビデオ レコーダー (DVR) を使用すると、出席者はイベント中に巻き戻して一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="47777-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="47777-114">VOD: ビデオ オン デマンド (VOD) を使用すると、イベントが終わった後に出席者が視聴できます。</span><span class="sxs-lookup"><span data-stu-id="47777-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="47777-115">ブロードキャスト録画ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="47777-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="47777-116">ブロードキャスト ポリシーの一部として、ライブ イベントの記録をオンまたはオフに切り替える設定があります。</span><span class="sxs-lookup"><span data-stu-id="47777-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="47777-117">プロデューサーと発表者が使用できるレコーディング</span><span class="sxs-lookup"><span data-stu-id="47777-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="47777-118">出席者が利用できる記録</span><span class="sxs-lookup"><span data-stu-id="47777-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="47777-119">常に記録する</span><span class="sxs-lookup"><span data-stu-id="47777-119">Always record</span></span>               | <span data-ttu-id="47777-120">無効で選択されている</span><span class="sxs-lookup"><span data-stu-id="47777-120">Disabled and selected</span></span>                                | <span data-ttu-id="47777-121">有効で選択されている</span><span class="sxs-lookup"><span data-stu-id="47777-121">Enabled and selected</span></span>         |
| <span data-ttu-id="47777-122">オーガナイザーは記録可能か記録しないか</span><span class="sxs-lookup"><span data-stu-id="47777-122">Organizer can record or not</span></span> | <span data-ttu-id="47777-123">既定で有効および選択されている</span><span class="sxs-lookup"><span data-stu-id="47777-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="47777-124">既定で有効および選択されている</span><span class="sxs-lookup"><span data-stu-id="47777-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="47777-125">記録しない</span><span class="sxs-lookup"><span data-stu-id="47777-125">Never record</span></span>               | <span data-ttu-id="47777-126">無効で選択されていない</span><span class="sxs-lookup"><span data-stu-id="47777-126">Disabled and not selected</span></span>                            | <span data-ttu-id="47777-127">有効で、選択されていない</span><span class="sxs-lookup"><span data-stu-id="47777-127">Enabled and not selected</span></span>      |

<span data-ttu-id="47777-128">ポリシーが Always record に **設定されている場合**、ポリシー ページには次のオプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="47777-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="47777-129">![ライブ イベント ポリシーの設定](../media/live-event-recording-policy.png "Microsoft Teams 管理センターのライブ イベント ポリシーの設定を示すスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="47777-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="47777-130">Storageと永続化の動作</span><span class="sxs-lookup"><span data-stu-id="47777-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="47777-131">オプション</span><span class="sxs-lookup"><span data-stu-id="47777-131">Option</span></span>                                       | <span data-ttu-id="47777-132">都道府県</span><span class="sxs-lookup"><span data-stu-id="47777-132">State</span></span>   | <span data-ttu-id="47777-133">DVR</span><span class="sxs-lookup"><span data-stu-id="47777-133">DVR</span></span>                                                   | <span data-ttu-id="47777-134">VOD</span><span class="sxs-lookup"><span data-stu-id="47777-134">VOD</span></span>                                                     | <span data-ttu-id="47777-135">記録</span><span class="sxs-lookup"><span data-stu-id="47777-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="47777-136">プロデューサーと発表者が使用できるレコーディング</span><span class="sxs-lookup"><span data-stu-id="47777-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="47777-137">選択済み</span><span class="sxs-lookup"><span data-stu-id="47777-137">Selected</span></span>     | <span data-ttu-id="47777-138">DVR が使用可能で、Azure Media Services (AMS) 資産は 180 日間保存されます。</span><span class="sxs-lookup"><span data-stu-id="47777-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="47777-139">出席者はイベントにアクセスして視聴できます。</span><span class="sxs-lookup"><span data-stu-id="47777-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="47777-140">選択されていない</span><span class="sxs-lookup"><span data-stu-id="47777-140">Not Selected</span></span> | <span data-ttu-id="47777-141">DVR が使用可能で、AMS 資産が 180 日間保存される</span><span class="sxs-lookup"><span data-stu-id="47777-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="47777-142">イベントが終わった後、出席者はイベントにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="47777-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="47777-143">無効 (選択されていない)</span><span class="sxs-lookup"><span data-stu-id="47777-143">Disabled (Not selected)</span></span>|<span data-ttu-id="47777-144">DVR が使用可能で、イベントの後に AMS 資産が削除される</span><span class="sxs-lookup"><span data-stu-id="47777-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="47777-145">イベントが終わった後、出席者はイベントにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="47777-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="47777-146">プロデューサーと発表者が使用できるレコーディング</span><span class="sxs-lookup"><span data-stu-id="47777-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="47777-147">選択済み</span><span class="sxs-lookup"><span data-stu-id="47777-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="47777-148">MP4 が作成され、保存される</span><span class="sxs-lookup"><span data-stu-id="47777-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="47777-149">選択されていない</span><span class="sxs-lookup"><span data-stu-id="47777-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="47777-150">ファイルが作成されません</span><span class="sxs-lookup"><span data-stu-id="47777-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="47777-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="47777-151">Related topics</span></span>

- [<span data-ttu-id="47777-152">Teams のライブ イベントについて</span><span class="sxs-lookup"><span data-stu-id="47777-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="47777-153">Teams のライブ イベントの計画</span><span class="sxs-lookup"><span data-stu-id="47777-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="47777-154">Teams でライブ イベント設定を構成する</span><span class="sxs-lookup"><span data-stu-id="47777-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="47777-155">Teamsクラウド会議の記録</span><span class="sxs-lookup"><span data-stu-id="47777-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)