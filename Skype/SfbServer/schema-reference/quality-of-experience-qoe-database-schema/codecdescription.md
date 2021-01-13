---
title: CodecDescription テーブル
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
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription テーブルは、対応するコーデックに一意コーデック識別子をマップします。 コーデックは、送受信とブロードキャスト用にデジタル信号をコード化し、再生時にそれらの信号を読み取る目的で使用されます。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831347"
---
# <a name="codecdescription-table"></a><span data-ttu-id="fc575-105">CodecDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="fc575-105">CodecDescription table</span></span>
 
<span data-ttu-id="fc575-106">CodecDescription テーブルは、対応するコーデックに一意コーデック識別子をマップします。</span><span class="sxs-lookup"><span data-stu-id="fc575-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="fc575-107">コーデックは、送受信とブロードキャスト用にデジタル信号をコード化し、再生時にそれらの信号を読み取る目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="fc575-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="fc575-108">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fc575-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="fc575-109">**列**</span><span class="sxs-lookup"><span data-stu-id="fc575-109">**Column**</span></span>|<span data-ttu-id="fc575-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="fc575-110">**Data Type**</span></span>|<span data-ttu-id="fc575-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="fc575-111">**Key/Index**</span></span>|<span data-ttu-id="fc575-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="fc575-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fc575-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="fc575-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="fc575-114">smallint</span><span class="sxs-lookup"><span data-stu-id="fc575-114">smallint</span></span>  <br/> |<span data-ttu-id="fc575-115">Primary</span><span class="sxs-lookup"><span data-stu-id="fc575-115">Primary</span></span>  <br/> |<span data-ttu-id="fc575-116">新しいコーデックに割り当てる一意識別子です。</span><span class="sxs-lookup"><span data-stu-id="fc575-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="fc575-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="fc575-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="fc575-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="fc575-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="fc575-119">一意</span><span class="sxs-lookup"><span data-stu-id="fc575-119">Unique</span></span>  <br/> |<span data-ttu-id="fc575-120">CodecDescriptionKey に対応しているコーデックの一意詳細。</span><span class="sxs-lookup"><span data-stu-id="fc575-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

