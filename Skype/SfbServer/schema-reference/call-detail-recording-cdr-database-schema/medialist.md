---
title: MediaList テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。
ms.openlocfilehash: e7d739b27bf45b5f5a21183c30bd5b07108b4a9d
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888516"
---
# <a name="medialist-table"></a><span data-ttu-id="d11c9-103">MediaList テーブル</span><span class="sxs-lookup"><span data-stu-id="d11c9-103">MediaList table</span></span>
 
<span data-ttu-id="d11c9-104">MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="d11c9-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="d11c9-105">**列**</span><span class="sxs-lookup"><span data-stu-id="d11c9-105">**Column**</span></span>|<span data-ttu-id="d11c9-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d11c9-106">**Data Type**</span></span>|<span data-ttu-id="d11c9-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="d11c9-107">**Key/Index**</span></span>|<span data-ttu-id="d11c9-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="d11c9-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d11c9-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="d11c9-109">**MediaId**</span></span> <br/> |<span data-ttu-id="d11c9-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="d11c9-110">tinyint</span></span>  <br/> |<span data-ttu-id="d11c9-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d11c9-111">Primary</span></span>  <br/> |<span data-ttu-id="d11c9-112">値: 1 -7</span><span class="sxs-lookup"><span data-stu-id="d11c9-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="d11c9-113">**メディア**</span><span class="sxs-lookup"><span data-stu-id="d11c9-113">**Media**</span></span> <br/> |<span data-ttu-id="d11c9-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d11c9-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="d11c9-115">MediaID 値と Media 値の固定マッピング:</span><span class="sxs-lookup"><span data-stu-id="d11c9-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="d11c9-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="d11c9-116">1 -- IM</span></span> <br/>  <span data-ttu-id="d11c9-117">2-ファイル送信</span><span class="sxs-lookup"><span data-stu-id="d11c9-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="d11c9-118">3-リモートアシスタンス</span><span class="sxs-lookup"><span data-stu-id="d11c9-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="d11c9-119">4-アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="d11c9-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="d11c9-120">5 -- 音声</span><span class="sxs-lookup"><span data-stu-id="d11c9-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="d11c9-121">6 -- ビデオ</span><span class="sxs-lookup"><span data-stu-id="d11c9-121">6 -- Video</span></span> <br/>  <span data-ttu-id="d11c9-122">7-アプリの招待</span><span class="sxs-lookup"><span data-stu-id="d11c9-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="d11c9-123">LcsCDR.SessionDetailsView.MediaTypes の値でモダリティの種類を特定しようとしている場合は、次の Join スニペットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11c9-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
