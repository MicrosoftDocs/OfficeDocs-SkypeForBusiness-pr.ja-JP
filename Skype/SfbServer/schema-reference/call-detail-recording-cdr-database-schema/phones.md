---
title: Phones テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 電話の表はサポートテーブルです。 テーブル内の各レコードには、データベース内にレコードがある VoIP 通話に関連する1つの電話番号に関する情報が格納されます。
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815005"
---
# <a name="phones-table"></a><span data-ttu-id="bd398-104">Phones テーブル</span><span class="sxs-lookup"><span data-stu-id="bd398-104">Phones table</span></span>
 
<span data-ttu-id="bd398-105">電話の表はサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="bd398-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="bd398-106">テーブル内の各レコードには、データベース内にレコードがある VoIP 通話に関連する1つの電話番号に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="bd398-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="bd398-107">**列**</span><span class="sxs-lookup"><span data-stu-id="bd398-107">**Column**</span></span>|<span data-ttu-id="bd398-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="bd398-108">**Data Type**</span></span>|<span data-ttu-id="bd398-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="bd398-109">**Key/Index**</span></span>|<span data-ttu-id="bd398-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="bd398-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd398-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="bd398-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="bd398-112">int</span><span class="sxs-lookup"><span data-stu-id="bd398-112">int</span></span>  <br/> |<span data-ttu-id="bd398-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bd398-113">Primary</span></span>  <br/> |<span data-ttu-id="bd398-114">この電話を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="bd398-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="bd398-115">**電話の Uri**</span><span class="sxs-lookup"><span data-stu-id="bd398-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="bd398-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bd398-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="bd398-117">電話番号。</span><span class="sxs-lookup"><span data-stu-id="bd398-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="bd398-118">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="bd398-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="bd398-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="bd398-119">dateTime</span></span>  <br/> ||<span data-ttu-id="bd398-120">タイムスタンプ (内部使用のみ)。</span><span class="sxs-lookup"><span data-stu-id="bd398-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="bd398-121">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bd398-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

