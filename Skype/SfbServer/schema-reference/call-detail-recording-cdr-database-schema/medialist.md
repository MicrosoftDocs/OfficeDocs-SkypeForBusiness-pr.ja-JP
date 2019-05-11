---
title: MediaList テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。
ms.openlocfilehash: 3eaa40cb5ae03129edaa36effa7b40012fc38429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930652"
---
# <a name="medialist-table"></a><span data-ttu-id="1454a-103">MediaList テーブル</span><span class="sxs-lookup"><span data-stu-id="1454a-103">MediaList table</span></span>
 
<span data-ttu-id="1454a-104">MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="1454a-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="1454a-105">**列**</span><span class="sxs-lookup"><span data-stu-id="1454a-105">**Column**</span></span>|<span data-ttu-id="1454a-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1454a-106">**Data Type**</span></span>|<span data-ttu-id="1454a-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="1454a-107">**Key/Index**</span></span>|<span data-ttu-id="1454a-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1454a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1454a-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="1454a-109">**MediaId**</span></span> <br/> |<span data-ttu-id="1454a-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1454a-110">tinyint</span></span>  <br/> |<span data-ttu-id="1454a-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1454a-111">Primary</span></span>  <br/> |<span data-ttu-id="1454a-112">値: 1 -7</span><span class="sxs-lookup"><span data-stu-id="1454a-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="1454a-113">**メディア**</span><span class="sxs-lookup"><span data-stu-id="1454a-113">**Media**</span></span> <br/> |<span data-ttu-id="1454a-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1454a-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1454a-115">MediaID 値と Media 値の固定マッピング:</span><span class="sxs-lookup"><span data-stu-id="1454a-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="1454a-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="1454a-116">1 -- IM</span></span> <br/>  <span data-ttu-id="1454a-117">2-ファイル転送</span><span class="sxs-lookup"><span data-stu-id="1454a-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="1454a-118">3-リモート アシスタンス</span><span class="sxs-lookup"><span data-stu-id="1454a-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="1454a-119">4-アプリケーションの共有</span><span class="sxs-lookup"><span data-stu-id="1454a-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="1454a-120">5 -- 音声</span><span class="sxs-lookup"><span data-stu-id="1454a-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="1454a-121">6 -- ビデオ</span><span class="sxs-lookup"><span data-stu-id="1454a-121">6 -- Video</span></span> <br/>  <span data-ttu-id="1454a-122">7-アプリケーションへの招待</span><span class="sxs-lookup"><span data-stu-id="1454a-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="1454a-123">LcsCDR.SessionDetailsView.MediaTypes の値でモダリティの種類を特定しようとしている場合は、次の Join スニペットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1454a-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
