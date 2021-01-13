---
title: メディア ビュー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Media ビューには、ピアツーピア セッションで使用される 1 つのメディア種類に関する情報が格納されます。 複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831792"
---
# <a name="media-view"></a><span data-ttu-id="d4456-105">メディア ビュー</span><span class="sxs-lookup"><span data-stu-id="d4456-105">Media view</span></span>
 
<span data-ttu-id="d4456-106">Media ビューには、ピアツーピア セッションで使用される 1 つのメディア種類に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="d4456-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="d4456-107">複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。</span><span class="sxs-lookup"><span data-stu-id="d4456-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="d4456-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d4456-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4456-p103">Media ビューを使用してセッションでのメディアの継続時間を計算することはできません。このビューには、セッションでのメディア交換の信号の詳細が格納されます。メディア交換は INVITE 要求によって行われ、StartTime は INVITE が送信された時刻を示します。メディアはセッションが受け付けられた後にのみ開始するので、招待時間は必ずしもメディアの開始時刻を意味しません。</span><span class="sxs-lookup"><span data-stu-id="d4456-p103">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="d4456-112">メディア ビューには [、SessionDetails](sessiondetails-0.md) ビューのすべての列と、以下の列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4456-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="d4456-113">**列**</span><span class="sxs-lookup"><span data-stu-id="d4456-113">**Column**</span></span>|<span data-ttu-id="d4456-114">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d4456-114">**Data Type**</span></span>|<span data-ttu-id="d4456-115">**詳細**</span><span class="sxs-lookup"><span data-stu-id="d4456-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4456-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="d4456-116">**Media**</span></span> <br/> |<span data-ttu-id="d4456-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d4456-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d4456-118">メディア種類。</span><span class="sxs-lookup"><span data-stu-id="d4456-118">Media type.</span></span> <span data-ttu-id="d4456-119">詳しくは [、MediaList の表](medialist.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d4456-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d4456-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="d4456-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="d4456-121">日付型</span><span class="sxs-lookup"><span data-stu-id="d4456-121">datetime</span></span>  <br/> |<span data-ttu-id="d4456-122">メディア要求が送信された時刻。</span><span class="sxs-lookup"><span data-stu-id="d4456-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="d4456-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="d4456-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="d4456-124">日付型</span><span class="sxs-lookup"><span data-stu-id="d4456-124">datetime</span></span>  <br/> |<span data-ttu-id="d4456-125">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="d4456-125">End time of the session.</span></span>  <br/> |
   

