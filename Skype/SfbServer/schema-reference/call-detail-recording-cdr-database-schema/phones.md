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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 電話の表はサポートテーブルです。 テーブル内の各レコードには、データベース内にレコードがある VoIP 通話に関連する1つの電話番号に関する情報が格納されます。
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295945"
---
# <a name="phones-table"></a><span data-ttu-id="28c02-104">Phones テーブル</span><span class="sxs-lookup"><span data-stu-id="28c02-104">Phones table</span></span>
 
<span data-ttu-id="28c02-105">電話の表はサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="28c02-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="28c02-106">テーブル内の各レコードには、データベース内にレコードがある VoIP 通話に関連する1つの電話番号に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="28c02-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="28c02-107">**列**</span><span class="sxs-lookup"><span data-stu-id="28c02-107">**Column**</span></span>|<span data-ttu-id="28c02-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="28c02-108">**Data Type**</span></span>|<span data-ttu-id="28c02-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="28c02-109">**Key/Index**</span></span>|<span data-ttu-id="28c02-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="28c02-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28c02-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="28c02-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="28c02-112">int</span><span class="sxs-lookup"><span data-stu-id="28c02-112">int</span></span>  <br/> |<span data-ttu-id="28c02-113">Primary</span><span class="sxs-lookup"><span data-stu-id="28c02-113">Primary</span></span>  <br/> |<span data-ttu-id="28c02-114">この電話を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="28c02-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="28c02-115">**電話の Uri**</span><span class="sxs-lookup"><span data-stu-id="28c02-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="28c02-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="28c02-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="28c02-117">電話番号。</span><span class="sxs-lookup"><span data-stu-id="28c02-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="28c02-118">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="28c02-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="28c02-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="28c02-119">dateTime</span></span>  <br/> ||<span data-ttu-id="28c02-120">タイムスタンプ (内部使用のみ)。</span><span class="sxs-lookup"><span data-stu-id="28c02-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="28c02-121">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="28c02-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

