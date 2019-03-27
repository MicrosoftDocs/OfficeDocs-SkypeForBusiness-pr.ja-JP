---
title: PayloadDescription テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 320542593479e3051992e8079abfdf9f54b0efc0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874201"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="0991b-104">PayloadDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="0991b-104">PayloadDescription table</span></span>
 
<span data-ttu-id="0991b-105">PayloadDescription はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0991b-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="0991b-106">各レコードは、オーディオまたはビデオのセッションで使用される 1 つのコーデックを表します。</span><span class="sxs-lookup"><span data-stu-id="0991b-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="0991b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0991b-107">**Column**</span></span>|<span data-ttu-id="0991b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="0991b-108">**Data Type**</span></span>|<span data-ttu-id="0991b-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="0991b-109">**Key/Index**</span></span>|<span data-ttu-id="0991b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="0991b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0991b-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="0991b-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="0991b-112">int</span><span class="sxs-lookup"><span data-stu-id="0991b-112">int</span></span>  <br/> |<span data-ttu-id="0991b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0991b-113">Primary</span></span>  <br/> |<span data-ttu-id="0991b-114">コーデックを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="0991b-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="0991b-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="0991b-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="0991b-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0991b-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0991b-117">一意</span><span class="sxs-lookup"><span data-stu-id="0991b-117">Unique</span></span>  <br/> |<span data-ttu-id="0991b-118">コーデックの名前です。</span><span class="sxs-lookup"><span data-stu-id="0991b-118">Codec name.</span></span>  <br/> |
   

