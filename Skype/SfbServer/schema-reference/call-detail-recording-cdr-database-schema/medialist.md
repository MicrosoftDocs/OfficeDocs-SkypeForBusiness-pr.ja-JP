---
title: MediaList テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813137"
---
# <a name="medialist-table"></a><span data-ttu-id="4b6c4-103">MediaList テーブル</span><span class="sxs-lookup"><span data-stu-id="4b6c4-103">MediaList table</span></span>
 
<span data-ttu-id="4b6c4-104">MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="4b6c4-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="4b6c4-105">**列**</span><span class="sxs-lookup"><span data-stu-id="4b6c4-105">**Column**</span></span>|<span data-ttu-id="4b6c4-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4b6c4-106">**Data Type**</span></span>|<span data-ttu-id="4b6c4-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="4b6c4-107">**Key/Index**</span></span>|<span data-ttu-id="4b6c4-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4b6c4-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b6c4-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="4b6c4-109">**MediaId**</span></span> <br/> |<span data-ttu-id="4b6c4-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="4b6c4-110">tinyint</span></span>  <br/> |<span data-ttu-id="4b6c4-111">Primary</span><span class="sxs-lookup"><span data-stu-id="4b6c4-111">Primary</span></span>  <br/> |<span data-ttu-id="4b6c4-112">値: 1 ~ 7</span><span class="sxs-lookup"><span data-stu-id="4b6c4-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="4b6c4-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="4b6c4-113">**Media**</span></span> <br/> |<span data-ttu-id="4b6c4-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4b6c4-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="4b6c4-115">MediaID と Media 値の静的マッピング:</span><span class="sxs-lookup"><span data-stu-id="4b6c4-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="4b6c4-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="4b6c4-116">1 -- IM</span></span> <br/>  <span data-ttu-id="4b6c4-117">2 - ファイル転送</span><span class="sxs-lookup"><span data-stu-id="4b6c4-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="4b6c4-118">3 - リモート アシスタンス</span><span class="sxs-lookup"><span data-stu-id="4b6c4-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="4b6c4-119">4 - アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="4b6c4-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="4b6c4-120">5 -- 音声</span><span class="sxs-lookup"><span data-stu-id="4b6c4-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="4b6c4-121">6 -- ビデオ</span><span class="sxs-lookup"><span data-stu-id="4b6c4-121">6 -- Video</span></span> <br/>  <span data-ttu-id="4b6c4-122">7 - アプリの招待</span><span class="sxs-lookup"><span data-stu-id="4b6c4-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="4b6c4-123">LcsCDR.SessionDetailsView.MediaTypes の値のモダリティの種類を決定する場合は、次の Join スニペットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b6c4-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
