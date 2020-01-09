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
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。
ms.openlocfilehash: 243fd3fb705826584f4e786441cdc1faa9075777
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992927"
---
# <a name="medialist-table"></a><span data-ttu-id="41168-103">MediaList テーブル</span><span class="sxs-lookup"><span data-stu-id="41168-103">MediaList table</span></span>
 
<span data-ttu-id="41168-104">MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="41168-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="41168-105">**列**</span><span class="sxs-lookup"><span data-stu-id="41168-105">**Column**</span></span>|<span data-ttu-id="41168-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="41168-106">**Data Type**</span></span>|<span data-ttu-id="41168-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="41168-107">**Key/Index**</span></span>|<span data-ttu-id="41168-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="41168-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41168-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="41168-109">**MediaId**</span></span> <br/> |<span data-ttu-id="41168-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="41168-110">tinyint</span></span>  <br/> |<span data-ttu-id="41168-111">Primary</span><span class="sxs-lookup"><span data-stu-id="41168-111">Primary</span></span>  <br/> |<span data-ttu-id="41168-112">値: 1 -7</span><span class="sxs-lookup"><span data-stu-id="41168-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="41168-113">**メディア**</span><span class="sxs-lookup"><span data-stu-id="41168-113">**Media**</span></span> <br/> |<span data-ttu-id="41168-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="41168-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="41168-115">MediaID 値と Media 値の固定マッピング:</span><span class="sxs-lookup"><span data-stu-id="41168-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="41168-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="41168-116">1 -- IM</span></span> <br/>  <span data-ttu-id="41168-117">2-ファイル送信</span><span class="sxs-lookup"><span data-stu-id="41168-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="41168-118">3-リモートアシスタンス</span><span class="sxs-lookup"><span data-stu-id="41168-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="41168-119">4-アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="41168-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="41168-120">5 -- 音声</span><span class="sxs-lookup"><span data-stu-id="41168-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="41168-121">6 -- ビデオ</span><span class="sxs-lookup"><span data-stu-id="41168-121">6 -- Video</span></span> <br/>  <span data-ttu-id="41168-122">7-アプリの招待</span><span class="sxs-lookup"><span data-stu-id="41168-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="41168-123">LcsCDR.SessionDetailsView.MediaTypes の値でモダリティの種類を特定しようとしている場合は、次の Join スニペットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41168-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
