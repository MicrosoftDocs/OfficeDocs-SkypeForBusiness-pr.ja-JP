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
ms.openlocfilehash: 7742baf17240ca810268721c0e47e37f17e555cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815035"
---
# <a name="medialist-table"></a><span data-ttu-id="c9473-103">MediaList テーブル</span><span class="sxs-lookup"><span data-stu-id="c9473-103">MediaList table</span></span>
 
<span data-ttu-id="c9473-104">MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="c9473-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="c9473-105">**列**</span><span class="sxs-lookup"><span data-stu-id="c9473-105">**Column**</span></span>|<span data-ttu-id="c9473-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c9473-106">**Data Type**</span></span>|<span data-ttu-id="c9473-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="c9473-107">**Key/Index**</span></span>|<span data-ttu-id="c9473-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c9473-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c9473-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="c9473-109">**MediaId**</span></span> <br/> |<span data-ttu-id="c9473-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="c9473-110">tinyint</span></span>  <br/> |<span data-ttu-id="c9473-111">Primary</span><span class="sxs-lookup"><span data-stu-id="c9473-111">Primary</span></span>  <br/> |<span data-ttu-id="c9473-112">値: 1 -7</span><span class="sxs-lookup"><span data-stu-id="c9473-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="c9473-113">**メディア**</span><span class="sxs-lookup"><span data-stu-id="c9473-113">**Media**</span></span> <br/> |<span data-ttu-id="c9473-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c9473-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c9473-115">MediaID 値と Media 値の固定マッピング:</span><span class="sxs-lookup"><span data-stu-id="c9473-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="c9473-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="c9473-116">1 -- IM</span></span> <br/>  <span data-ttu-id="c9473-117">2-ファイル送信</span><span class="sxs-lookup"><span data-stu-id="c9473-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="c9473-118">3-リモートアシスタンス</span><span class="sxs-lookup"><span data-stu-id="c9473-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="c9473-119">4-アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="c9473-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="c9473-120">5 -- 音声</span><span class="sxs-lookup"><span data-stu-id="c9473-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="c9473-121">6 -- ビデオ</span><span class="sxs-lookup"><span data-stu-id="c9473-121">6 -- Video</span></span> <br/>  <span data-ttu-id="c9473-122">7-アプリの招待</span><span class="sxs-lookup"><span data-stu-id="c9473-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="c9473-123">LcsCDR.SessionDetailsView.MediaTypes の値でモダリティの種類を特定しようとしている場合は、次の Join スニペットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9473-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
