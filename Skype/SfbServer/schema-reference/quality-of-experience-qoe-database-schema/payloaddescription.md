---
title: PayloadDescription テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription テーブルは、サポート テーブルです。 各レコードが、音声セッションまたはビデオ セッションで使用される 1 つのコーデックを表します。
ms.openlocfilehash: c9476aea28993a053096a095469d2d4e13251581
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806297"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="7dd95-104">PayloadDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="7dd95-104">PayloadDescription table</span></span>
 
<span data-ttu-id="7dd95-p102">PayloadDescription テーブルは、サポート テーブルです。各レコードが、音声セッションまたはビデオ セッションで使用される 1 つのコーデックを表します。</span><span class="sxs-lookup"><span data-stu-id="7dd95-p102">The PayloadDescription table is a supporting table. Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="7dd95-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7dd95-107">**Column**</span></span>|<span data-ttu-id="7dd95-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7dd95-108">**Data Type**</span></span>|<span data-ttu-id="7dd95-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="7dd95-109">**Key/Index**</span></span>|<span data-ttu-id="7dd95-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="7dd95-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7dd95-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="7dd95-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="7dd95-112">int</span><span class="sxs-lookup"><span data-stu-id="7dd95-112">int</span></span>  <br/> |<span data-ttu-id="7dd95-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7dd95-113">Primary</span></span>  <br/> |<span data-ttu-id="7dd95-114">コーデックを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="7dd95-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="7dd95-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="7dd95-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="7dd95-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7dd95-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7dd95-117">一意</span><span class="sxs-lookup"><span data-stu-id="7dd95-117">Unique</span></span>  <br/> |<span data-ttu-id="7dd95-118">コーデック名。</span><span class="sxs-lookup"><span data-stu-id="7dd95-118">Codec name.</span></span>  <br/> |
   

