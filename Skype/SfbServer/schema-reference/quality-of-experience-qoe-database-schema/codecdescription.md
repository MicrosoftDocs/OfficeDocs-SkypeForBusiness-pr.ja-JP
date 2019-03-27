---
title: CodecDescription テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription テーブルでは、コーデックの一意の識別子を対応するコーデックにマップします。 伝送およびブロードキャストでは、デジタル信号をエンコードするためにコーデックを使用し、再生するため、それらの信号をデコードします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: efda27afe9312c25add8be0f74364384aed53b3e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896499"
---
# <a name="codecdescription-table"></a><span data-ttu-id="73816-105">CodecDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="73816-105">CodecDescription table</span></span>
 
<span data-ttu-id="73816-106">CodecDescription テーブルでは、コーデックの一意の識別子を対応するコーデックにマップします。</span><span class="sxs-lookup"><span data-stu-id="73816-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="73816-107">伝送およびブロードキャストでは、デジタル信号をエンコードするためにコーデックを使用し、再生するため、それらの信号をデコードします。</span><span class="sxs-lookup"><span data-stu-id="73816-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="73816-108">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="73816-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="73816-109">**列**</span><span class="sxs-lookup"><span data-stu-id="73816-109">**Column**</span></span>|<span data-ttu-id="73816-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="73816-110">**Data Type**</span></span>|<span data-ttu-id="73816-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="73816-111">**Key/Index**</span></span>|<span data-ttu-id="73816-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="73816-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="73816-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="73816-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="73816-114">smallint</span><span class="sxs-lookup"><span data-stu-id="73816-114">smallint</span></span>  <br/> |<span data-ttu-id="73816-115">Primary</span><span class="sxs-lookup"><span data-stu-id="73816-115">Primary</span></span>  <br/> |<span data-ttu-id="73816-116">コーデックに割り当てられている一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="73816-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="73816-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="73816-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="73816-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="73816-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="73816-119">一意</span><span class="sxs-lookup"><span data-stu-id="73816-119">Unique</span></span>  <br/> |<span data-ttu-id="73816-120">CodecDescriptionKey に対応するコーデックの一意の説明です。</span><span class="sxs-lookup"><span data-stu-id="73816-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

