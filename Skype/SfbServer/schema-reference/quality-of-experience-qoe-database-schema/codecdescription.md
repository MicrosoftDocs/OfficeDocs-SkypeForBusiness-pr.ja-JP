---
title: CodecDescription テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription テーブルでは、コーデックの一意の識別子を対応するコーデックにマップします。 伝送およびブロードキャストでは、デジタル信号をエンコードするためにコーデックを使用し、再生するため、それらの信号をデコードします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 9881c802e332801d4990bf01894d5f8b68150fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920104"
---
# <a name="codecdescription-table"></a><span data-ttu-id="e0c46-105">CodecDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="e0c46-105">CodecDescription table</span></span>
 
<span data-ttu-id="e0c46-106">CodecDescription テーブルでは、コーデックの一意の識別子を対応するコーデックにマップします。</span><span class="sxs-lookup"><span data-stu-id="e0c46-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="e0c46-107">伝送およびブロードキャストでは、デジタル信号をエンコードするためにコーデックを使用し、再生するため、それらの信号をデコードします。</span><span class="sxs-lookup"><span data-stu-id="e0c46-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="e0c46-108">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e0c46-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="e0c46-109">**列**</span><span class="sxs-lookup"><span data-stu-id="e0c46-109">**Column**</span></span>|<span data-ttu-id="e0c46-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e0c46-110">**Data Type**</span></span>|<span data-ttu-id="e0c46-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="e0c46-111">**Key/Index**</span></span>|<span data-ttu-id="e0c46-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e0c46-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0c46-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="e0c46-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="e0c46-114">smallint</span><span class="sxs-lookup"><span data-stu-id="e0c46-114">smallint</span></span>  <br/> |<span data-ttu-id="e0c46-115">Primary</span><span class="sxs-lookup"><span data-stu-id="e0c46-115">Primary</span></span>  <br/> |<span data-ttu-id="e0c46-116">コーデックに割り当てられている一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="e0c46-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="e0c46-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="e0c46-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="e0c46-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="e0c46-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="e0c46-119">一意</span><span class="sxs-lookup"><span data-stu-id="e0c46-119">Unique</span></span>  <br/> |<span data-ttu-id="e0c46-120">CodecDescriptionKey に対応するコーデックの一意の説明です。</span><span class="sxs-lookup"><span data-stu-id="e0c46-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

