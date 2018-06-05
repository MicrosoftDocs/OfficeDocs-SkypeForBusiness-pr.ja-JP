---
title: MediaList テーブル
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
ms.openlocfilehash: c9309219399fac30e318f8e112dd82269fff5ac2
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569769"
---
# <a name="medialist-table"></a><span data-ttu-id="7b986-103">MediaList テーブル</span><span class="sxs-lookup"><span data-stu-id="7b986-103">MediaList table</span></span>
 
<span data-ttu-id="7b986-104">MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="7b986-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="7b986-105">**列**</span><span class="sxs-lookup"><span data-stu-id="7b986-105">**Column**</span></span>|<span data-ttu-id="7b986-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7b986-106">**Data Type**</span></span>|<span data-ttu-id="7b986-107">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="7b986-107">**Key/Index**</span></span>|<span data-ttu-id="7b986-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="7b986-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b986-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="7b986-109">**MediaId**</span></span> <br/> |<span data-ttu-id="7b986-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b986-110">tinyint</span></span>  <br/> |<span data-ttu-id="7b986-111">Primary</span><span class="sxs-lookup"><span data-stu-id="7b986-111">Primary</span></span>  <br/> |<span data-ttu-id="7b986-112">値: 1 -7</span><span class="sxs-lookup"><span data-stu-id="7b986-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="7b986-113">**メディア**</span><span class="sxs-lookup"><span data-stu-id="7b986-113">**Media**</span></span> <br/> |<span data-ttu-id="7b986-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7b986-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="7b986-115">MediaID 値と Media 値の固定マッピング:</span><span class="sxs-lookup"><span data-stu-id="7b986-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="7b986-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="7b986-116">1 -- IM</span></span> <br/>  <span data-ttu-id="7b986-117">2-ファイル転送</span><span class="sxs-lookup"><span data-stu-id="7b986-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="7b986-118">3-リモート アシスタンス</span><span class="sxs-lookup"><span data-stu-id="7b986-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="7b986-119">4-アプリケーションの共有</span><span class="sxs-lookup"><span data-stu-id="7b986-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="7b986-120">5 -- 音声</span><span class="sxs-lookup"><span data-stu-id="7b986-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="7b986-121">6 -- ビデオ</span><span class="sxs-lookup"><span data-stu-id="7b986-121">6 -- Video</span></span> <br/>  <span data-ttu-id="7b986-122">7-アプリケーションへの招待</span><span class="sxs-lookup"><span data-stu-id="7b986-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="7b986-123">LcsCDR.SessionDetailsView.MediaTypes の値でモダリティの種類を特定しようとしている場合は、次の Join スニペットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b986-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```