---
title: ビジネス サーバー 2015 の Skype での ConferenceUris テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris テーブルは、さまざまな会議をデータベースに記録されている会議セッションに参加している Uri のリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つの会議の URI を表します。
ms.openlocfilehash: 6f373774b652e9858af84dd4c16b51fcb3c5d493
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213215"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0619d-104">ビジネス サーバー 2015 の Skype での ConferenceUris テーブル</span><span class="sxs-lookup"><span data-stu-id="0619d-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0619d-105">ConfereneUris テーブルは、さまざまな会議をデータベースに記録されている会議セッションに参加している Uri のリストを格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="0619d-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="0619d-106">テーブル内の各レコードは、1 つの会議の URI を表します。</span><span class="sxs-lookup"><span data-stu-id="0619d-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="0619d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0619d-107">**Column**</span></span>|<span data-ttu-id="0619d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="0619d-108">**Data Type**</span></span>|<span data-ttu-id="0619d-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="0619d-109">**Key/Index**</span></span>|<span data-ttu-id="0619d-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="0619d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0619d-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="0619d-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="0619d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0619d-112">datetime</span></span>  <br/> |<span data-ttu-id="0619d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0619d-113">Primary</span></span>  <br/> |<span data-ttu-id="0619d-114">タイム ・ スタンプ、内部のために使用します。</span><span class="sxs-lookup"><span data-stu-id="0619d-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="0619d-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="0619d-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="0619d-116">int</span><span class="sxs-lookup"><span data-stu-id="0619d-116">int</span></span>  <br/> |<span data-ttu-id="0619d-117">Primary</span><span class="sxs-lookup"><span data-stu-id="0619d-117">Primary</span></span>  <br/> |<span data-ttu-id="0619d-118">この会議の URI を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="0619d-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="0619d-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="0619d-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="0619d-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0619d-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="0619d-121">会議 URI です。</span><span class="sxs-lookup"><span data-stu-id="0619d-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="0619d-122">**チェックサム**</span><span class="sxs-lookup"><span data-stu-id="0619d-122">**Checksum**</span></span> <br/> |<span data-ttu-id="0619d-123">int</span><span class="sxs-lookup"><span data-stu-id="0619d-123">int</span></span>  <br/> ||<span data-ttu-id="0619d-124">ConferenceUri のチェックサムです。</span><span class="sxs-lookup"><span data-stu-id="0619d-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="0619d-125">使用するデータベースの検索の速度が向上します。</span><span class="sxs-lookup"><span data-stu-id="0619d-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="0619d-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="0619d-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="0619d-127">int</span><span class="sxs-lookup"><span data-stu-id="0619d-127">int</span></span>  <br/> |<span data-ttu-id="0619d-128">外部</span><span class="sxs-lookup"><span data-stu-id="0619d-128">Foreign</span></span>  <br/> |<span data-ttu-id="0619d-129">IM 会議、または conf:audio の conf:chat など、URI の種類-オーディオ/ビデオ会議のビデオ。</span><span class="sxs-lookup"><span data-stu-id="0619d-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="0619d-130">詳細については、 [UriTypes テーブル](uritypes.md)のテーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0619d-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

