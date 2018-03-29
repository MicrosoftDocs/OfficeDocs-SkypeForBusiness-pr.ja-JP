---
title: UriTypes テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes テーブルには、URI (一意リソース識別子)、各種ビジネス サーバー 2015 の Skype の監視が含まれています。
ms.openlocfilehash: 00c70c166716ad879257e7b18db80dd760ce4ec4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="uritypes-table"></a><span data-ttu-id="e1118-103">UriTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="e1118-103">UriTypes table</span></span>
 
<span data-ttu-id="e1118-104">UriTypes テーブルには、URI (一意リソース識別子)、各種ビジネス サーバー 2015 の Skype の監視が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1118-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="e1118-105">**列**</span><span class="sxs-lookup"><span data-stu-id="e1118-105">**Column**</span></span>|<span data-ttu-id="e1118-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e1118-106">**Data Type**</span></span>|<span data-ttu-id="e1118-107">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="e1118-107">**Key/Index**</span></span>|<span data-ttu-id="e1118-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e1118-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e1118-109">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="e1118-109">**UriTypeId**</span></span> <br/> |<span data-ttu-id="e1118-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e1118-110">tinyint</span></span>  <br/> |<span data-ttu-id="e1118-111">Primary</span><span class="sxs-lookup"><span data-stu-id="e1118-111">Primary</span></span>  <br/> |<span data-ttu-id="e1118-112">URI の種類に割り当てられている一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="e1118-112">Unique identifier assigned to a URI type.</span></span>  <br/> |
|<span data-ttu-id="e1118-113">**UriType**</span><span class="sxs-lookup"><span data-stu-id="e1118-113">**UriType**</span></span> <br/> |<span data-ttu-id="e1118-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e1118-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e1118-115">URI の種類の説明です。</span><span class="sxs-lookup"><span data-stu-id="e1118-115">Descriptions of the different URI types.</span></span> <span data-ttu-id="e1118-116">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e1118-116">Allowed values are:</span></span> <br/>  <span data-ttu-id="e1118-117">0 - 電話の Uri</span><span class="sxs-lookup"><span data-stu-id="e1118-117">0 - Phone Uri</span></span> <br/>  <span data-ttu-id="e1118-118">1-ユーザーの Uri</span><span class="sxs-lookup"><span data-stu-id="e1118-118">1 - User Uri</span></span> <br/> |
   

