---
title: PayloadDescription テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription テーブルは、サポートテーブルです。 各レコードは、オーディオセッションまたはビデオセッションで使用される1つのコーデックを表します。
ms.openlocfilehash: 3a5719d7fbfe23eb8c1457565a36df0a02617fde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807495"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="f26ac-104">PayloadDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="f26ac-104">PayloadDescription table</span></span>
 
<span data-ttu-id="f26ac-105">PayloadDescription テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="f26ac-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="f26ac-106">各レコードは、オーディオセッションまたはビデオセッションで使用される1つのコーデックを表します。</span><span class="sxs-lookup"><span data-stu-id="f26ac-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="f26ac-107">**列**</span><span class="sxs-lookup"><span data-stu-id="f26ac-107">**Column**</span></span>|<span data-ttu-id="f26ac-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="f26ac-108">**Data Type**</span></span>|<span data-ttu-id="f26ac-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="f26ac-109">**Key/Index**</span></span>|<span data-ttu-id="f26ac-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="f26ac-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f26ac-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="f26ac-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="f26ac-112">int</span><span class="sxs-lookup"><span data-stu-id="f26ac-112">int</span></span>  <br/> |<span data-ttu-id="f26ac-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f26ac-113">Primary</span></span>  <br/> |<span data-ttu-id="f26ac-114">コーデックを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="f26ac-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="f26ac-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="f26ac-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="f26ac-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f26ac-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f26ac-117">一意</span><span class="sxs-lookup"><span data-stu-id="f26ac-117">Unique</span></span>  <br/> |<span data-ttu-id="f26ac-118">コーデック名。</span><span class="sxs-lookup"><span data-stu-id="f26ac-118">Codec name.</span></span>  <br/> |
   

