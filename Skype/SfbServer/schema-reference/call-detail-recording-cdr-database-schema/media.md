---
title: Media テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 各レコードは、ピアツーピアセッションで使用される1つのメディアの種類を表します。 複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。
ms.openlocfilehash: 181a78a9fc3fabe8c166f4cdc8c452b5a16b016b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296008"
---
# <a name="media-table"></a><span data-ttu-id="af408-104">Media テーブル</span><span class="sxs-lookup"><span data-stu-id="af408-104">Media table</span></span>
 
<span data-ttu-id="af408-105">各レコードは、ピアツーピアセッションで使用される1つのメディアの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="af408-105">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="af408-106">複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。</span><span class="sxs-lookup"><span data-stu-id="af408-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af408-107">メディアテーブルを使って、セッションのメディアの再生時間を計算することはできません。</span><span class="sxs-lookup"><span data-stu-id="af408-107">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="af408-108">この表には、セッションでのメディア交換の信号の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="af408-108">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="af408-109">メディア交換は INVITE 要求によって実行され、StartTime は招待が送信された時間を示します。この招待は、セッションの開始時刻を意味するわけではありません。これは、セッションを開始した後にのみメディアが開始されるためです。</span><span class="sxs-lookup"><span data-stu-id="af408-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="af408-110">通常、EndTime はこのセッションの終了時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="af408-110">The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="af408-111">**列**</span><span class="sxs-lookup"><span data-stu-id="af408-111">**Column**</span></span>|<span data-ttu-id="af408-112">**データ型**</span><span class="sxs-lookup"><span data-stu-id="af408-112">**Data Type**</span></span>|<span data-ttu-id="af408-113">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="af408-113">**Key/Index**</span></span>|<span data-ttu-id="af408-114">**詳細**</span><span class="sxs-lookup"><span data-stu-id="af408-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af408-115">**セッション Id**</span><span class="sxs-lookup"><span data-stu-id="af408-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="af408-116">datetime</span><span class="sxs-lookup"><span data-stu-id="af408-116">datetime</span></span>  <br/> |<span data-ttu-id="af408-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="af408-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="af408-118">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="af408-118">Time of session request.</span></span> <span data-ttu-id="af408-119">セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="af408-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="af408-120">詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af408-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="af408-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="af408-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="af408-122">int</span><span class="sxs-lookup"><span data-stu-id="af408-122">int</span></span>  <br/> |<span data-ttu-id="af408-123">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="af408-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="af408-124">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="af408-124">ID number to identify the session.</span></span> <span data-ttu-id="af408-125">セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="af408-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="af408-126">詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af408-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="af408-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="af408-127">**MediaId**</span></span> <br/> |<span data-ttu-id="af408-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="af408-128">tinyint</span></span>  <br/> |<span data-ttu-id="af408-129">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="af408-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="af408-130">このメディアの種類を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="af408-130">Unique number identifying this media type.</span></span> <span data-ttu-id="af408-131">詳細については、 [Medialist の表](medialist.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af408-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="af408-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="af408-132">**StartTime**</span></span> <br/> |<span data-ttu-id="af408-133">datetime</span><span class="sxs-lookup"><span data-stu-id="af408-133">datetime</span></span>  <br/> |<span data-ttu-id="af408-134">Primary</span><span class="sxs-lookup"><span data-stu-id="af408-134">Primary</span></span>  <br/> |<span data-ttu-id="af408-135">これは、実際のメディアの開始時刻ではなく、メディア要求が送信された時刻です。</span><span class="sxs-lookup"><span data-stu-id="af408-135">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="af408-136">**StartTime**には、セッションのセットアップ時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="af408-136">**StartTime** includes the session setup time.</span></span> <br/> |
|<span data-ttu-id="af408-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="af408-137">**EndTime**</span></span> <br/> |<span data-ttu-id="af408-138">datetime</span><span class="sxs-lookup"><span data-stu-id="af408-138">datetime</span></span>  <br/> ||<span data-ttu-id="af408-139">これはセッションの終了時刻です。</span><span class="sxs-lookup"><span data-stu-id="af408-139">This is the end time of the session.</span></span>  <br/> |
   

