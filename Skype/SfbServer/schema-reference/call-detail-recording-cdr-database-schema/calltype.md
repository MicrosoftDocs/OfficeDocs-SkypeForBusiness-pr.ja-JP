---
title: ビジネス サーバー 2015 の Skype の CallType テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 29e5ed85de5917092ad00cd0e1aa60fec1a31b22
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213362"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ae39b-103">ビジネス サーバー 2015 の Skype の CallType テーブル</span><span class="sxs-lookup"><span data-stu-id="ae39b-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ae39b-104">CallType の表は、可能な呼び出しの種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ae39b-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="ae39b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ae39b-105">**Column**</span></span>|<span data-ttu-id="ae39b-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ae39b-106">**Data Type**</span></span>|<span data-ttu-id="ae39b-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="ae39b-107">**Key/Index**</span></span>|<span data-ttu-id="ae39b-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ae39b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ae39b-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="ae39b-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="ae39b-110">int</span><span class="sxs-lookup"><span data-stu-id="ae39b-110">int</span></span>  <br/> |<span data-ttu-id="ae39b-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ae39b-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="ae39b-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="ae39b-112">**CallType**</span></span> <br/> |<span data-ttu-id="ae39b-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="ae39b-113">nvarchar</span></span>  <br/> || <span data-ttu-id="ae39b-114">使用可能な値:</span><span class="sxs-lookup"><span data-stu-id="ae39b-114">Allowed values:</span></span> <br/>  <span data-ttu-id="ae39b-115">0 - 不明</span><span class="sxs-lookup"><span data-stu-id="ae39b-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="ae39b-116">1-インスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="ae39b-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="ae39b-117">2 - アプリケーションの共有</span><span class="sxs-lookup"><span data-stu-id="ae39b-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="ae39b-118">3-オーディオ</span><span class="sxs-lookup"><span data-stu-id="ae39b-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="ae39b-119">4-オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="ae39b-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="ae39b-120">5-ファイル転送</span><span class="sxs-lookup"><span data-stu-id="ae39b-120">5 - File Transfer</span></span> <br/> |
   

