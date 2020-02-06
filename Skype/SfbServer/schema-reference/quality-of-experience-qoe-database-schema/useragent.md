---
title: UserAgent テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーエージェントのリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つのユーザーエージェントを表します。
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805055"
---
# <a name="useragent-table"></a><span data-ttu-id="7ca1f-104">UserAgent テーブル</span><span class="sxs-lookup"><span data-stu-id="7ca1f-104">UserAgent table</span></span>
 
<span data-ttu-id="7ca1f-105">UserAgent テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーエージェントのリストを格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="7ca1f-106">テーブル内の各レコードは、1つのユーザーエージェントを表します。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="7ca1f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7ca1f-107">**Column**</span></span>|<span data-ttu-id="7ca1f-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7ca1f-108">**Data Type**</span></span>|<span data-ttu-id="7ca1f-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="7ca1f-109">**Key/Index**</span></span>|<span data-ttu-id="7ca1f-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="7ca1f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ca1f-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="7ca1f-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="7ca1f-112">int</span><span class="sxs-lookup"><span data-stu-id="7ca1f-112">int</span></span>  <br/> |<span data-ttu-id="7ca1f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7ca1f-113">Primary</span></span>  <br/> |<span data-ttu-id="7ca1f-114">このユーザーエージェントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="7ca1f-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="7ca1f-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="7ca1f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7ca1f-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7ca1f-117">一意</span><span class="sxs-lookup"><span data-stu-id="7ca1f-117">Unique</span></span>  <br/> |<span data-ttu-id="7ca1f-118">ユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="7ca1f-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="7ca1f-119">**UAType**</span></span> <br/> |<span data-ttu-id="7ca1f-120">smallint</span><span class="sxs-lookup"><span data-stu-id="7ca1f-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="7ca1f-121">1は仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="7ca1f-122">2は、A/V 会議サーバーです。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="7ca1f-123">4は Skype for Business です。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="7ca1f-124">8は IP 電話です。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="7ca1f-125">16は Live Meeting 本体です。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="7ca1f-126">32は展開検証ツール (DVT) です。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="7ca1f-127">64は、Macintosh コンピューター上の Skype for Business Server です。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="7ca1f-128">128は、Skype for Business Server アテンダントです。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="7ca1f-129">256は会議のアナウンスメントサービスです。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="7ca1f-130">512は、会議の自動応答です。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="7ca1f-131">1024は応答グループアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="7ca1f-132">2048は外部の音声制御。</span><span class="sxs-lookup"><span data-stu-id="7ca1f-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

