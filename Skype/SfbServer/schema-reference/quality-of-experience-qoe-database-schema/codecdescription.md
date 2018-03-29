---
title: CodecDescription テーブル
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
ms.openlocfilehash: 49dea2867ef7614fab3015efbd24e6ec47da8c55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="codecdescription-table"></a><span data-ttu-id="b35bc-105">CodecDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="b35bc-105">CodecDescription table</span></span>
 
<span data-ttu-id="b35bc-106">CodecDescription テーブルでは、コーデックの一意の識別子を対応するコーデックにマップします。</span><span class="sxs-lookup"><span data-stu-id="b35bc-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="b35bc-107">伝送およびブロードキャストでは、デジタル信号をエンコードするためにコーデックを使用し、再生するため、それらの信号をデコードします。</span><span class="sxs-lookup"><span data-stu-id="b35bc-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="b35bc-108">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b35bc-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="b35bc-109">**列**</span><span class="sxs-lookup"><span data-stu-id="b35bc-109">**Column**</span></span>|<span data-ttu-id="b35bc-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="b35bc-110">**Data Type**</span></span>|<span data-ttu-id="b35bc-111">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="b35bc-111">**Key/Index**</span></span>|<span data-ttu-id="b35bc-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="b35bc-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b35bc-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="b35bc-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="b35bc-114">smallint</span><span class="sxs-lookup"><span data-stu-id="b35bc-114">smallint</span></span>  <br/> |<span data-ttu-id="b35bc-115">Primary</span><span class="sxs-lookup"><span data-stu-id="b35bc-115">Primary</span></span>  <br/> |<span data-ttu-id="b35bc-116">コーデックに割り当てられている一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="b35bc-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="b35bc-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="b35bc-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="b35bc-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="b35bc-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="b35bc-119">一意</span><span class="sxs-lookup"><span data-stu-id="b35bc-119">Unique</span></span>  <br/> |<span data-ttu-id="b35bc-120">CodecDescriptionKey に対応するコーデックの一意の説明です。</span><span class="sxs-lookup"><span data-stu-id="b35bc-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

