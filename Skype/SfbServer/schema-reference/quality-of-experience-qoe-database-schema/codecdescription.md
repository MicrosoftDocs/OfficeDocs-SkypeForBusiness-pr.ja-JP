---
title: CodecDescription テーブル
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
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription テーブルでは、一意のコーデック識別子が対応するコーデックにマップされます。 コーデックは、伝送とブロードキャスト用のデジタルシグナルをエンコードし、再生のためにそれらのシグナルをデコードするために使われます。 この表は Microsoft Lync Server 2013 で導入されました
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810365"
---
# <a name="codecdescription-table"></a><span data-ttu-id="8c3b6-105">CodecDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="8c3b6-105">CodecDescription table</span></span>
 
<span data-ttu-id="8c3b6-106">CodecDescription テーブルでは、一意のコーデック識別子が対応するコーデックにマップされます。</span><span class="sxs-lookup"><span data-stu-id="8c3b6-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="8c3b6-107">コーデックは、伝送とブロードキャスト用のデジタルシグナルをエンコードし、再生のためにそれらのシグナルをデコードするために使われます。</span><span class="sxs-lookup"><span data-stu-id="8c3b6-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="8c3b6-108">この表は Microsoft Lync Server 2013 で導入されました</span><span class="sxs-lookup"><span data-stu-id="8c3b6-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="8c3b6-109">**列**</span><span class="sxs-lookup"><span data-stu-id="8c3b6-109">**Column**</span></span>|<span data-ttu-id="8c3b6-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="8c3b6-110">**Data Type**</span></span>|<span data-ttu-id="8c3b6-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="8c3b6-111">**Key/Index**</span></span>|<span data-ttu-id="8c3b6-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="8c3b6-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8c3b6-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="8c3b6-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="8c3b6-114">smallint</span><span class="sxs-lookup"><span data-stu-id="8c3b6-114">smallint</span></span>  <br/> |<span data-ttu-id="8c3b6-115">Primary</span><span class="sxs-lookup"><span data-stu-id="8c3b6-115">Primary</span></span>  <br/> |<span data-ttu-id="8c3b6-116">コーデックに割り当てられている一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="8c3b6-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="8c3b6-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="8c3b6-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="8c3b6-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8c3b6-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="8c3b6-119">一意</span><span class="sxs-lookup"><span data-stu-id="8c3b6-119">Unique</span></span>  <br/> |<span data-ttu-id="8c3b6-120">CodecDescriptionKey に対応するコーデックの固有の説明です。</span><span class="sxs-lookup"><span data-stu-id="8c3b6-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

