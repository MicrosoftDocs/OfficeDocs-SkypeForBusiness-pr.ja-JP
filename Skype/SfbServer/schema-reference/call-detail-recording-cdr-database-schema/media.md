---
title: Media テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 各レコードは、ピア ツー ピア セッションで使用される 1 つのメディアの種類を表します。 セッションは 1 つで表されます、テーブル内の複数のレコード 1 つ以上のメディア タイプを使用する場合。
ms.openlocfilehash: f0525b279fbef5cc7d4a1bc2ce0fce9212636a96
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893027"
---
# <a name="media-table"></a><span data-ttu-id="0460a-104">Media テーブル</span><span class="sxs-lookup"><span data-stu-id="0460a-104">Media table</span></span>
 
<span data-ttu-id="0460a-105">各レコードは、ピア ツー ピア セッションで使用される 1 つのメディアの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="0460a-105">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="0460a-106">セッションは 1 つで表されます、テーブル内の複数のレコード 1 つ以上のメディア タイプを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="0460a-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0460a-107">Media テーブルは、セッションのメディアの長さを計算するのにはない使用してください。</span><span class="sxs-lookup"><span data-stu-id="0460a-107">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="0460a-108">このテーブルには、セッションでのメディアの交換のシグナルの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0460a-108">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="0460a-109">INVITE 要求、メディアの交換を行うし、開始時刻は、招待状が送信された時刻を示します。招待時間は必ずしもメディアの開始時刻、メディアは、sessionee がセッションを受け入れた後にのみ開始されるためです。</span><span class="sxs-lookup"><span data-stu-id="0460a-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="0460a-110">終了時刻は、通常、このセッションの終了時刻を意味します。</span><span class="sxs-lookup"><span data-stu-id="0460a-110">The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="0460a-111">**列**</span><span class="sxs-lookup"><span data-stu-id="0460a-111">**Column**</span></span>|<span data-ttu-id="0460a-112">**データ型**</span><span class="sxs-lookup"><span data-stu-id="0460a-112">**Data Type**</span></span>|<span data-ttu-id="0460a-113">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="0460a-113">**Key/Index**</span></span>|<span data-ttu-id="0460a-114">**詳細**</span><span class="sxs-lookup"><span data-stu-id="0460a-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0460a-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="0460a-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="0460a-116">datetime</span><span class="sxs-lookup"><span data-stu-id="0460a-116">datetime</span></span>  <br/> |<span data-ttu-id="0460a-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="0460a-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0460a-118">セッションの要求の時間です。</span><span class="sxs-lookup"><span data-stu-id="0460a-118">Time of session request.</span></span> <span data-ttu-id="0460a-119">セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="0460a-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="0460a-120">[Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0460a-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0460a-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="0460a-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="0460a-122">int</span><span class="sxs-lookup"><span data-stu-id="0460a-122">int</span></span>  <br/> |<span data-ttu-id="0460a-123">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="0460a-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0460a-124">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="0460a-124">ID number to identify the session.</span></span> <span data-ttu-id="0460a-125">セッションを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="0460a-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="0460a-126">[Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0460a-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0460a-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="0460a-127">**MediaId**</span></span> <br/> |<span data-ttu-id="0460a-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="0460a-128">tinyint</span></span>  <br/> |<span data-ttu-id="0460a-129">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="0460a-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0460a-130">このメディアの種類を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="0460a-130">Unique number identifying this media type.</span></span> <span data-ttu-id="0460a-131">詳細については[メディアの表](medialist.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0460a-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0460a-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="0460a-132">**StartTime**</span></span> <br/> |<span data-ttu-id="0460a-133">datetime</span><span class="sxs-lookup"><span data-stu-id="0460a-133">datetime</span></span>  <br/> |<span data-ttu-id="0460a-134">Primary</span><span class="sxs-lookup"><span data-stu-id="0460a-134">Primary</span></span>  <br/> |<span data-ttu-id="0460a-135">メディアの要求が送信された時刻は、実際のメディアではなく開始時間。</span><span class="sxs-lookup"><span data-stu-id="0460a-135">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="0460a-136">**開始時刻**には、セッションのセットアップ時間が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0460a-136">**StartTime** includes the session setup time.</span></span> <br/> |
|<span data-ttu-id="0460a-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="0460a-137">**EndTime**</span></span> <br/> |<span data-ttu-id="0460a-138">datetime</span><span class="sxs-lookup"><span data-stu-id="0460a-138">datetime</span></span>  <br/> ||<span data-ttu-id="0460a-139">これは、セッションの終了時刻です。</span><span class="sxs-lookup"><span data-stu-id="0460a-139">This is the end time of the session.</span></span>  <br/> |
   

