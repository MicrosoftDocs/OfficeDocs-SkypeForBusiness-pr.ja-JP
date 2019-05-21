---
title: Skype for Business Server 2015 の ConferenceUris テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris テーブルは、データベースに記録された会議セッションに参加しているさまざまな会議の Uri のリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つの会議 URI を表します。
ms.openlocfilehash: 60f9952fa1fcc5b1a1a651c44beaed894a387b81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296393"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="80fe7-104">Skype for Business Server 2015 の ConferenceUris テーブル</span><span class="sxs-lookup"><span data-stu-id="80fe7-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="80fe7-105">ConfereneUris テーブルは、データベースに記録された会議セッションに参加しているさまざまな会議の Uri のリストを格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="80fe7-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="80fe7-106">テーブル内の各レコードは、1つの会議 URI を表します。</span><span class="sxs-lookup"><span data-stu-id="80fe7-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="80fe7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="80fe7-107">**Column**</span></span>|<span data-ttu-id="80fe7-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="80fe7-108">**Data Type**</span></span>|<span data-ttu-id="80fe7-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="80fe7-109">**Key/Index**</span></span>|<span data-ttu-id="80fe7-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="80fe7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="80fe7-111">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="80fe7-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="80fe7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="80fe7-112">datetime</span></span>  <br/> |<span data-ttu-id="80fe7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="80fe7-113">Primary</span></span>  <br/> |<span data-ttu-id="80fe7-114">タイムスタンプ、内部使用。</span><span class="sxs-lookup"><span data-stu-id="80fe7-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="80fe7-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="80fe7-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="80fe7-116">int</span><span class="sxs-lookup"><span data-stu-id="80fe7-116">int</span></span>  <br/> |<span data-ttu-id="80fe7-117">Primary</span><span class="sxs-lookup"><span data-stu-id="80fe7-117">Primary</span></span>  <br/> |<span data-ttu-id="80fe7-118">この会議 URI を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="80fe7-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="80fe7-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="80fe7-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="80fe7-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="80fe7-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="80fe7-121">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="80fe7-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="80fe7-122">**サム**</span><span class="sxs-lookup"><span data-stu-id="80fe7-122">**Checksum**</span></span> <br/> |<span data-ttu-id="80fe7-123">int</span><span class="sxs-lookup"><span data-stu-id="80fe7-123">int</span></span>  <br/> ||<span data-ttu-id="80fe7-124">ConferenceUri のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="80fe7-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="80fe7-125">データベースの検索速度を上げるために使われます。</span><span class="sxs-lookup"><span data-stu-id="80fe7-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="80fe7-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="80fe7-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="80fe7-127">int</span><span class="sxs-lookup"><span data-stu-id="80fe7-127">int</span></span>  <br/> |<span data-ttu-id="80fe7-128">外部</span><span class="sxs-lookup"><span data-stu-id="80fe7-128">Foreign</span></span>  <br/> |<span data-ttu-id="80fe7-129">URI の種類 ("conf: IM 会議用チャット" または "conf: 音声/ビデオ会議用のオーディオビデオ" など)。</span><span class="sxs-lookup"><span data-stu-id="80fe7-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="80fe7-130">詳細については、 [UriTypes テーブル](uritypes.md)の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80fe7-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

