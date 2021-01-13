---
title: Skype for Business Server 2015 の ConferenceUris テーブル
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris テーブルは、データベースに記録されている会議セッションに参加したさまざまな会議 URI の一覧を格納する補助的なテーブルです。このテーブルの個々のレコードが、1 つの会議 URI を表します。
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816137"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4f60b-104">Skype for Business Server 2015 の ConferenceUris テーブル</span><span class="sxs-lookup"><span data-stu-id="4f60b-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4f60b-p102">ConfereneUris テーブルは、データベースに記録されている会議セッションに参加したさまざまな会議 URI の一覧を格納する補助的なテーブルです。このテーブルの個々のレコードが、1 つの会議 URI を表します。</span><span class="sxs-lookup"><span data-stu-id="4f60b-p102">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="4f60b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4f60b-107">**Column**</span></span>|<span data-ttu-id="4f60b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4f60b-108">**Data Type**</span></span>|<span data-ttu-id="4f60b-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="4f60b-109">**Key/Index**</span></span>|<span data-ttu-id="4f60b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4f60b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4f60b-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4f60b-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4f60b-112">日付型</span><span class="sxs-lookup"><span data-stu-id="4f60b-112">datetime</span></span>  <br/> |<span data-ttu-id="4f60b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4f60b-113">Primary</span></span>  <br/> |<span data-ttu-id="4f60b-114">タイム スタンプ (社内使用向け)。</span><span class="sxs-lookup"><span data-stu-id="4f60b-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="4f60b-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="4f60b-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="4f60b-116">int</span><span class="sxs-lookup"><span data-stu-id="4f60b-116">int</span></span>  <br/> |<span data-ttu-id="4f60b-117">Primary</span><span class="sxs-lookup"><span data-stu-id="4f60b-117">Primary</span></span>  <br/> |<span data-ttu-id="4f60b-118">この会議 URI を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="4f60b-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="4f60b-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="4f60b-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="4f60b-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4f60b-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="4f60b-121">会議 URI。</span><span class="sxs-lookup"><span data-stu-id="4f60b-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="4f60b-122">**チェックサム**</span><span class="sxs-lookup"><span data-stu-id="4f60b-122">**Checksum**</span></span> <br/> |<span data-ttu-id="4f60b-123">int</span><span class="sxs-lookup"><span data-stu-id="4f60b-123">int</span></span>  <br/> ||<span data-ttu-id="4f60b-p103">ConferenceUri のチェックサム。データベース検索の速度を速めるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f60b-p103">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="4f60b-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="4f60b-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="4f60b-127">int</span><span class="sxs-lookup"><span data-stu-id="4f60b-127">int</span></span>  <br/> |<span data-ttu-id="4f60b-128">外部</span><span class="sxs-lookup"><span data-stu-id="4f60b-128">Foreign</span></span>  <br/> |<span data-ttu-id="4f60b-129">URI の種類 (IM 会議の conf:chat、音声ビデオ会議の conf:audio-video など)。</span><span class="sxs-lookup"><span data-stu-id="4f60b-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="4f60b-130">詳細については [、UriTypes テーブルの](uritypes.md) 表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f60b-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

