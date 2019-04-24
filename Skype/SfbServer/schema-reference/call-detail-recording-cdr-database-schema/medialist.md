---
title: MediaList テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。
ms.openlocfilehash: 72ae6dbb145c3bb284f1090b01585591e4e773bf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212909"
---
# <a name="medialist-table"></a><span data-ttu-id="037c0-103">MediaList テーブル</span><span class="sxs-lookup"><span data-stu-id="037c0-103">MediaList table</span></span>
 
<span data-ttu-id="037c0-104">MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="037c0-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="037c0-105">**列**</span><span class="sxs-lookup"><span data-stu-id="037c0-105">**Column**</span></span>|<span data-ttu-id="037c0-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="037c0-106">**Data Type**</span></span>|<span data-ttu-id="037c0-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="037c0-107">**Key/Index**</span></span>|<span data-ttu-id="037c0-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="037c0-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="037c0-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="037c0-109">**MediaId**</span></span> <br/> |<span data-ttu-id="037c0-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="037c0-110">tinyint</span></span>  <br/> |<span data-ttu-id="037c0-111">Primary</span><span class="sxs-lookup"><span data-stu-id="037c0-111">Primary</span></span>  <br/> |<span data-ttu-id="037c0-112">値: 1 -7</span><span class="sxs-lookup"><span data-stu-id="037c0-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="037c0-113">**メディア**</span><span class="sxs-lookup"><span data-stu-id="037c0-113">**Media**</span></span> <br/> |<span data-ttu-id="037c0-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="037c0-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="037c0-115">MediaID 値と Media 値の固定マッピング:</span><span class="sxs-lookup"><span data-stu-id="037c0-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="037c0-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="037c0-116">1 -- IM</span></span> <br/>  <span data-ttu-id="037c0-117">2-ファイル転送</span><span class="sxs-lookup"><span data-stu-id="037c0-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="037c0-118">3-リモート アシスタンス</span><span class="sxs-lookup"><span data-stu-id="037c0-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="037c0-119">4-アプリケーションの共有</span><span class="sxs-lookup"><span data-stu-id="037c0-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="037c0-120">5 -- 音声</span><span class="sxs-lookup"><span data-stu-id="037c0-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="037c0-121">6 -- ビデオ</span><span class="sxs-lookup"><span data-stu-id="037c0-121">6 -- Video</span></span> <br/>  <span data-ttu-id="037c0-122">7-アプリケーションへの招待</span><span class="sxs-lookup"><span data-stu-id="037c0-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="037c0-123">LcsCDR.SessionDetailsView.MediaTypes の値でモダリティの種類を特定しようとしている場合は、次の Join スニペットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="037c0-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
