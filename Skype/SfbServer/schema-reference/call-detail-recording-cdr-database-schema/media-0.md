---
title: メディアを表示します。
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: メディア ビューでは、ピア ツー ピア セッションで使用される 1 つのメディアの種類に関する情報を格納します。 セッションは 1 つで表されます、テーブル内の複数のレコード 1 つ以上のメディア タイプを使用する場合。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 0cbcb353ec768b9d3ee66f1a10d59b5c4523acea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="media-view"></a><span data-ttu-id="517bd-105">メディアを表示します。</span><span class="sxs-lookup"><span data-stu-id="517bd-105">Media view</span></span>
 
<span data-ttu-id="517bd-106">メディア ビューでは、ピア ツー ピア セッションで使用される 1 つのメディアの種類に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="517bd-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="517bd-107">セッションは 1 つで表されます、テーブル内の複数のレコード 1 つ以上のメディア タイプを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="517bd-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="517bd-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="517bd-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="517bd-109">メディア ビューは適していないセッションのメディアの長さを計算します。</span><span class="sxs-lookup"><span data-stu-id="517bd-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="517bd-110">このビューには、セッションでのメディアの交換のシグナルの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="517bd-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="517bd-111">INVITE 要求、メディアの交換を行うし、開始時刻は、招待状が送信された時刻を示します。招待時間は必ずしもメディアの開始時刻、セッションが受け入れられた後にのみ、メディアが開始されるためです。</span><span class="sxs-lookup"><span data-stu-id="517bd-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="517bd-112">メディア ビューに含まれるすべて[SessionDetails ビュー](sessiondetails-0.md)内の列のさらに下に表示されています。</span><span class="sxs-lookup"><span data-stu-id="517bd-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="517bd-113">**列**</span><span class="sxs-lookup"><span data-stu-id="517bd-113">**Column**</span></span>|<span data-ttu-id="517bd-114">**データ型**</span><span class="sxs-lookup"><span data-stu-id="517bd-114">**Data Type**</span></span>|<span data-ttu-id="517bd-115">**詳細**</span><span class="sxs-lookup"><span data-stu-id="517bd-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="517bd-116">**メディア**</span><span class="sxs-lookup"><span data-stu-id="517bd-116">**Media**</span></span> <br/> |<span data-ttu-id="517bd-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="517bd-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="517bd-118">メディアは次のとおり入力します。</span><span class="sxs-lookup"><span data-stu-id="517bd-118">Media type.</span></span> <span data-ttu-id="517bd-119">詳細については[メディアの表](medialist.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="517bd-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="517bd-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="517bd-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="517bd-121">datetime</span><span class="sxs-lookup"><span data-stu-id="517bd-121">datetime</span></span>  <br/> |<span data-ttu-id="517bd-122">メディアの要求が送信された時刻です。</span><span class="sxs-lookup"><span data-stu-id="517bd-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="517bd-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="517bd-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="517bd-124">datetime</span><span class="sxs-lookup"><span data-stu-id="517bd-124">datetime</span></span>  <br/> |<span data-ttu-id="517bd-125">セッションの終了時間です。</span><span class="sxs-lookup"><span data-stu-id="517bd-125">End time of the session.</span></span>  <br/> |
   

