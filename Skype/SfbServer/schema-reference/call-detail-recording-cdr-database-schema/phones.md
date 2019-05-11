---
title: Phones テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 電話はテーブルをサポートします。 テーブル内の各レコードは、データベースにレコードがある VoIP 通話に関連する 1 つの電話の番号に関する情報を格納します。
ms.openlocfilehash: ba13a059e043cf2a18c41c28dce1a2a54e694b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930617"
---
# <a name="phones-table"></a><span data-ttu-id="bf66f-104">Phones テーブル</span><span class="sxs-lookup"><span data-stu-id="bf66f-104">Phones table</span></span>
 
<span data-ttu-id="bf66f-105">電話はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bf66f-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="bf66f-106">テーブル内の各レコードは、データベースにレコードがある VoIP 通話に関連する 1 つの電話の番号に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="bf66f-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="bf66f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="bf66f-107">**Column**</span></span>|<span data-ttu-id="bf66f-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="bf66f-108">**Data Type**</span></span>|<span data-ttu-id="bf66f-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="bf66f-109">**Key/Index**</span></span>|<span data-ttu-id="bf66f-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="bf66f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf66f-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="bf66f-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="bf66f-112">int</span><span class="sxs-lookup"><span data-stu-id="bf66f-112">int</span></span>  <br/> |<span data-ttu-id="bf66f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bf66f-113">Primary</span></span>  <br/> |<span data-ttu-id="bf66f-114">この電話を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="bf66f-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="bf66f-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="bf66f-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="bf66f-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="bf66f-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="bf66f-117">電話番号です。</span><span class="sxs-lookup"><span data-stu-id="bf66f-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="bf66f-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="bf66f-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="bf66f-119">日付時刻</span><span class="sxs-lookup"><span data-stu-id="bf66f-119">dateTime</span></span>  <br/> ||<span data-ttu-id="bf66f-120">タイム ・ スタンプ (内部使用のみ)。</span><span class="sxs-lookup"><span data-stu-id="bf66f-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="bf66f-121">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bf66f-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

