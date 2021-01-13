---
title: Phones テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones テーブルはサポート テーブルです。 テーブル内の各レコードには、データベース内のレコードを持つ VoIP 通話に関係する 1 つの電話番号に関する情報が格納されます。
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823267"
---
# <a name="phones-table"></a><span data-ttu-id="25ab9-104">Phones テーブル</span><span class="sxs-lookup"><span data-stu-id="25ab9-104">Phones table</span></span>
 
<span data-ttu-id="25ab9-105">Phones テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="25ab9-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="25ab9-106">テーブル内の各レコードには、データベース内のレコードを持つ VoIP 通話に関係する 1 つの電話番号に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="25ab9-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="25ab9-107">**列**</span><span class="sxs-lookup"><span data-stu-id="25ab9-107">**Column**</span></span>|<span data-ttu-id="25ab9-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="25ab9-108">**Data Type**</span></span>|<span data-ttu-id="25ab9-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="25ab9-109">**Key/Index**</span></span>|<span data-ttu-id="25ab9-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="25ab9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="25ab9-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="25ab9-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="25ab9-112">int</span><span class="sxs-lookup"><span data-stu-id="25ab9-112">int</span></span>  <br/> |<span data-ttu-id="25ab9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="25ab9-113">Primary</span></span>  <br/> |<span data-ttu-id="25ab9-114">この電話を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="25ab9-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="25ab9-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="25ab9-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="25ab9-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="25ab9-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="25ab9-117">電話番号。</span><span class="sxs-lookup"><span data-stu-id="25ab9-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="25ab9-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="25ab9-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="25ab9-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="25ab9-119">dateTime</span></span>  <br/> ||<span data-ttu-id="25ab9-120">タイム スタンプ (内部使用のみ)。</span><span class="sxs-lookup"><span data-stu-id="25ab9-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="25ab9-121">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="25ab9-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

