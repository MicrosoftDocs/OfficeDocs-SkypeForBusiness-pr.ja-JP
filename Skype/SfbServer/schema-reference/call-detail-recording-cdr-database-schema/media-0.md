---
title: メディアビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: メディアビューには、ピアツーピアセッションで使用される1つのメディアの種類に関する情報が格納されます。 複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296001"
---
# <a name="media-view"></a><span data-ttu-id="09cef-105">メディアビュー</span><span class="sxs-lookup"><span data-stu-id="09cef-105">Media view</span></span>
 
<span data-ttu-id="09cef-106">メディアビューには、ピアツーピアセッションで使用される1つのメディアの種類に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="09cef-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="09cef-107">複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。</span><span class="sxs-lookup"><span data-stu-id="09cef-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="09cef-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="09cef-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09cef-109">メディア表示は、セッションのメディア再生時間の計算に使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="09cef-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="09cef-110">このビューには、セッションでのメディア交換の通知の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09cef-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="09cef-111">メディア交換は INVITE 要求によって実行され、StartTime は招待が送信された時間を示します。この招待時刻は、メディアの開始時刻を意味するわけではありません。これは、セッションが受け入れられた後にのみメディアが開始されるためです。</span><span class="sxs-lookup"><span data-stu-id="09cef-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="09cef-112">メディアビューには、次に示すように、 [Sessiondetails ビュー](sessiondetails-0.md)にすべての列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09cef-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="09cef-113">**列**</span><span class="sxs-lookup"><span data-stu-id="09cef-113">**Column**</span></span>|<span data-ttu-id="09cef-114">**データ型**</span><span class="sxs-lookup"><span data-stu-id="09cef-114">**Data Type**</span></span>|<span data-ttu-id="09cef-115">**詳細**</span><span class="sxs-lookup"><span data-stu-id="09cef-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="09cef-116">**メディア**</span><span class="sxs-lookup"><span data-stu-id="09cef-116">**Media**</span></span> <br/> |<span data-ttu-id="09cef-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="09cef-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="09cef-118">メディアの種類。</span><span class="sxs-lookup"><span data-stu-id="09cef-118">Media type.</span></span> <span data-ttu-id="09cef-119">詳細については、 [Medialist の表](medialist.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09cef-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="09cef-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="09cef-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="09cef-121">datetime</span><span class="sxs-lookup"><span data-stu-id="09cef-121">datetime</span></span>  <br/> |<span data-ttu-id="09cef-122">メディア要求が送信された時刻。</span><span class="sxs-lookup"><span data-stu-id="09cef-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="09cef-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="09cef-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="09cef-124">datetime</span><span class="sxs-lookup"><span data-stu-id="09cef-124">datetime</span></span>  <br/> |<span data-ttu-id="09cef-125">セッションの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="09cef-125">End time of the session.</span></span>  <br/> |
   

