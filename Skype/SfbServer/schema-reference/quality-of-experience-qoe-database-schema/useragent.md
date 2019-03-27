---
title: UserAgent テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent テーブルは、データベースに記録されているセッションに参加したさまざまなユーザー エージェントのリストを格納するサポート テーブルです。 テーブル内の各レコードが 1 つのユーザー エージェントを表す
ms.openlocfilehash: 17cb395569e8a634925be27705b878b104a3b70a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893105"
---
# <a name="useragent-table"></a><span data-ttu-id="0df12-104">UserAgent テーブル</span><span class="sxs-lookup"><span data-stu-id="0df12-104">UserAgent table</span></span>
 
<span data-ttu-id="0df12-105">UserAgent テーブルは、データベースに記録されているセッションに参加したさまざまなユーザー エージェントのリストを格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="0df12-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0df12-106">テーブル内の各レコードが 1 つのユーザー エージェントを表す</span><span class="sxs-lookup"><span data-stu-id="0df12-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="0df12-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0df12-107">**Column**</span></span>|<span data-ttu-id="0df12-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="0df12-108">**Data Type**</span></span>|<span data-ttu-id="0df12-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="0df12-109">**Key/Index**</span></span>|<span data-ttu-id="0df12-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="0df12-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0df12-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="0df12-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="0df12-112">int</span><span class="sxs-lookup"><span data-stu-id="0df12-112">int</span></span>  <br/> |<span data-ttu-id="0df12-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0df12-113">Primary</span></span>  <br/> |<span data-ttu-id="0df12-114">このユーザー エージェントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="0df12-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="0df12-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="0df12-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="0df12-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0df12-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0df12-117">一意</span><span class="sxs-lookup"><span data-stu-id="0df12-117">Unique</span></span>  <br/> |<span data-ttu-id="0df12-118">ユーザー エージェント文字列です。</span><span class="sxs-lookup"><span data-stu-id="0df12-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="0df12-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="0df12-119">**UAType**</span></span> <br/> |<span data-ttu-id="0df12-120">smallint</span><span class="sxs-lookup"><span data-stu-id="0df12-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="0df12-121">1 は、仲介サーバーです。</span><span class="sxs-lookup"><span data-stu-id="0df12-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="0df12-122">2 は、A/V 会議サーバーです。</span><span class="sxs-lookup"><span data-stu-id="0df12-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="0df12-123">4 は、ビジネスの Skype です。</span><span class="sxs-lookup"><span data-stu-id="0df12-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="0df12-124">8 は、IP 電話です。</span><span class="sxs-lookup"><span data-stu-id="0df12-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="0df12-125">16 は、Live Meeting コンソールです。</span><span class="sxs-lookup"><span data-stu-id="0df12-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="0df12-126">32 は、配置検証ツール (DVT) です。</span><span class="sxs-lookup"><span data-stu-id="0df12-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="0df12-127">64 は、Macintosh コンピューターで Skype のビジネス サーバーです。</span><span class="sxs-lookup"><span data-stu-id="0df12-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="0df12-128">128 は、ビジネスのサーバーの応答の Skype です。</span><span class="sxs-lookup"><span data-stu-id="0df12-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="0df12-129">256 は、会議のお知らせサービスです。</span><span class="sxs-lookup"><span data-stu-id="0df12-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="0df12-130">512 は、会議の自動応答です。</span><span class="sxs-lookup"><span data-stu-id="0df12-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="0df12-131">1024 は、応答グループ アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="0df12-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="0df12-132">2048 は、外側の音声コントロールです。</span><span class="sxs-lookup"><span data-stu-id="0df12-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

