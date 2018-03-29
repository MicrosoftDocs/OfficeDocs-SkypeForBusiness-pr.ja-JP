---
title: ビジネス サーバー 2015 の Skype の CallType テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType の表は、可能な呼び出しの種類の一覧を格納する静的なテーブルです。
ms.openlocfilehash: e2353176a69db9eada137525561541d26caa7a8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d4a80-103">ビジネス サーバー 2015 の Skype の CallType テーブル</span><span class="sxs-lookup"><span data-stu-id="d4a80-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d4a80-104">CallType の表は、可能な呼び出しの種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="d4a80-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="d4a80-105">**列**</span><span class="sxs-lookup"><span data-stu-id="d4a80-105">**Column**</span></span>|<span data-ttu-id="d4a80-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d4a80-106">**Data Type**</span></span>|<span data-ttu-id="d4a80-107">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="d4a80-107">**Key/Index**</span></span>|<span data-ttu-id="d4a80-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="d4a80-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d4a80-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="d4a80-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="d4a80-110">int</span><span class="sxs-lookup"><span data-stu-id="d4a80-110">int</span></span>  <br/> |<span data-ttu-id="d4a80-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d4a80-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="d4a80-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="d4a80-112">**CallType**</span></span> <br/> |<span data-ttu-id="d4a80-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="d4a80-113">nvarchar</span></span>  <br/> || <span data-ttu-id="d4a80-114">使用可能な値:</span><span class="sxs-lookup"><span data-stu-id="d4a80-114">Allowed values:</span></span> <br/>  <span data-ttu-id="d4a80-115">0 - 不明</span><span class="sxs-lookup"><span data-stu-id="d4a80-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="d4a80-116">1-インスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="d4a80-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="d4a80-117">2 - アプリケーションの共有</span><span class="sxs-lookup"><span data-stu-id="d4a80-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="d4a80-118">3-オーディオ</span><span class="sxs-lookup"><span data-stu-id="d4a80-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="d4a80-119">4-オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="d4a80-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="d4a80-120">5-ファイル転送</span><span class="sxs-lookup"><span data-stu-id="d4a80-120">5 - File Transfer</span></span> <br/> |
   

