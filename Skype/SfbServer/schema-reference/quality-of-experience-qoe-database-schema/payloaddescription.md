---
title: PayloadDescription テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription はテーブルをサポートします。 各レコードは、オーディオまたはビデオのセッションで使用される 1 つのコーデックを表します。
ms.openlocfilehash: fb4acb8182db920e25305b2be72cbc19700792bb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="payloaddescription-table"></a><span data-ttu-id="9ad88-104">PayloadDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="9ad88-104">PayloadDescription table</span></span>
 
<span data-ttu-id="9ad88-105">PayloadDescription はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9ad88-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="9ad88-106">各レコードは、オーディオまたはビデオのセッションで使用される 1 つのコーデックを表します。</span><span class="sxs-lookup"><span data-stu-id="9ad88-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="9ad88-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9ad88-107">**Column**</span></span>|<span data-ttu-id="9ad88-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9ad88-108">**Data Type**</span></span>|<span data-ttu-id="9ad88-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="9ad88-109">**Key/Index**</span></span>|<span data-ttu-id="9ad88-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9ad88-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9ad88-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="9ad88-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="9ad88-112">int</span><span class="sxs-lookup"><span data-stu-id="9ad88-112">int</span></span>  <br/> |<span data-ttu-id="9ad88-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9ad88-113">Primary</span></span>  <br/> |<span data-ttu-id="9ad88-114">コーデックを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="9ad88-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="9ad88-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="9ad88-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="9ad88-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9ad88-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9ad88-117">一意</span><span class="sxs-lookup"><span data-stu-id="9ad88-117">Unique</span></span>  <br/> |<span data-ttu-id="9ad88-118">コーデックの名前です。</span><span class="sxs-lookup"><span data-stu-id="9ad88-118">Codec name.</span></span>  <br/> |
   

