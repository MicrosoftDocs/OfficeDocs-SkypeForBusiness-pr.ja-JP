---
title: Phones テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 電話はテーブルをサポートします。 テーブル内の各レコードは、データベースにレコードがある VoIP 通話に関連する 1 つの電話の番号に関する情報を格納します。
ms.openlocfilehash: 8ec2095b857ba474a92bf0766d86119500919f51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="phones-table"></a><span data-ttu-id="067eb-104">Phones テーブル</span><span class="sxs-lookup"><span data-stu-id="067eb-104">Phones table</span></span>
 
<span data-ttu-id="067eb-105">電話はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="067eb-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="067eb-106">テーブル内の各レコードは、データベースにレコードがある VoIP 通話に関連する 1 つの電話の番号に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="067eb-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="067eb-107">**列**</span><span class="sxs-lookup"><span data-stu-id="067eb-107">**Column**</span></span>|<span data-ttu-id="067eb-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="067eb-108">**Data Type**</span></span>|<span data-ttu-id="067eb-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="067eb-109">**Key/Index**</span></span>|<span data-ttu-id="067eb-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="067eb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="067eb-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="067eb-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="067eb-112">int</span><span class="sxs-lookup"><span data-stu-id="067eb-112">int</span></span>  <br/> |<span data-ttu-id="067eb-113">Primary</span><span class="sxs-lookup"><span data-stu-id="067eb-113">Primary</span></span>  <br/> |<span data-ttu-id="067eb-114">この電話を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="067eb-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="067eb-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="067eb-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="067eb-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="067eb-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="067eb-117">電話番号です。</span><span class="sxs-lookup"><span data-stu-id="067eb-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="067eb-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="067eb-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="067eb-119">日付時刻</span><span class="sxs-lookup"><span data-stu-id="067eb-119">dateTime</span></span>  <br/> ||<span data-ttu-id="067eb-120">タイム ・ スタンプ (内部使用のみ)。</span><span class="sxs-lookup"><span data-stu-id="067eb-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="067eb-121">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="067eb-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

