---
title: UserAgent テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent テーブルは、データベースに記録されたセッションに参加したさまざまなユーザー エージェントのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのユーザー エージェントを表します。
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799937"
---
# <a name="useragent-table"></a><span data-ttu-id="29d22-104">UserAgent テーブル</span><span class="sxs-lookup"><span data-stu-id="29d22-104">UserAgent table</span></span>
 
<span data-ttu-id="29d22-105">UserAgent テーブルは、データベースに記録されたセッションに参加したさまざまなユーザー エージェントのリストを格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="29d22-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="29d22-106">テーブル内の各レコードは、1 つのユーザー エージェントを表します。</span><span class="sxs-lookup"><span data-stu-id="29d22-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="29d22-107">**列**</span><span class="sxs-lookup"><span data-stu-id="29d22-107">**Column**</span></span>|<span data-ttu-id="29d22-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="29d22-108">**Data Type**</span></span>|<span data-ttu-id="29d22-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="29d22-109">**Key/Index**</span></span>|<span data-ttu-id="29d22-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="29d22-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="29d22-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="29d22-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="29d22-112">int</span><span class="sxs-lookup"><span data-stu-id="29d22-112">int</span></span>  <br/> |<span data-ttu-id="29d22-113">Primary</span><span class="sxs-lookup"><span data-stu-id="29d22-113">Primary</span></span>  <br/> |<span data-ttu-id="29d22-114">このユーザー エージェントを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="29d22-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="29d22-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="29d22-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="29d22-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="29d22-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="29d22-117">一意</span><span class="sxs-lookup"><span data-stu-id="29d22-117">Unique</span></span>  <br/> |<span data-ttu-id="29d22-118">ユーザー エージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="29d22-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="29d22-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="29d22-119">**UAType**</span></span> <br/> |<span data-ttu-id="29d22-120">smallint</span><span class="sxs-lookup"><span data-stu-id="29d22-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="29d22-121">1 は仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="29d22-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="29d22-122">2 は音声ビデオ会議サーバーです。</span><span class="sxs-lookup"><span data-stu-id="29d22-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="29d22-123">4 は Skype for Business です。</span><span class="sxs-lookup"><span data-stu-id="29d22-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="29d22-124">8 は IP 電話です。</span><span class="sxs-lookup"><span data-stu-id="29d22-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="29d22-125">16 は Live Meeting コンソールです。</span><span class="sxs-lookup"><span data-stu-id="29d22-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="29d22-126">32 は展開検証ツール (DVT) です。</span><span class="sxs-lookup"><span data-stu-id="29d22-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="29d22-127">64 は Macintosh コンピューター上の Skype for Business Server です。</span><span class="sxs-lookup"><span data-stu-id="29d22-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="29d22-128">128 は Skype for Business Server Attendant です。</span><span class="sxs-lookup"><span data-stu-id="29d22-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="29d22-129">256 は会議アナウンス サービスです。</span><span class="sxs-lookup"><span data-stu-id="29d22-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="29d22-130">512 は会議自動応答。</span><span class="sxs-lookup"><span data-stu-id="29d22-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="29d22-131">1024 は応答グループ アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="29d22-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="29d22-132">2048 は音声コントロールの外部です。</span><span class="sxs-lookup"><span data-stu-id="29d22-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

