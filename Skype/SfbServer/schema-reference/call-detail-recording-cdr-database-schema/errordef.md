---
title: Skype for Business Server 2015 の ErrorDef テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef テーブルには、発生する可能性がある各エラーの種類に関する情報が格納されます。 各レコードは1種類のエラーです。
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296281"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="06bf1-104">Skype for Business Server 2015 の ErrorDef テーブル</span><span class="sxs-lookup"><span data-stu-id="06bf1-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="06bf1-105">ErrorDef テーブルには、発生する可能性がある各エラーの種類に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="06bf1-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="06bf1-106">各レコードは1種類のエラーです。</span><span class="sxs-lookup"><span data-stu-id="06bf1-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="06bf1-107">**列**</span><span class="sxs-lookup"><span data-stu-id="06bf1-107">**Column**</span></span>|<span data-ttu-id="06bf1-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="06bf1-108">**Data Type**</span></span>|<span data-ttu-id="06bf1-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="06bf1-109">**Key/Index**</span></span>|<span data-ttu-id="06bf1-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="06bf1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="06bf1-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="06bf1-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="06bf1-112">int</span><span class="sxs-lookup"><span data-stu-id="06bf1-112">int</span></span>  <br/> |<span data-ttu-id="06bf1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="06bf1-113">Primary</span></span>  <br/> |<span data-ttu-id="06bf1-114">この種類のエラーを識別する固有の ID 番号。</span><span class="sxs-lookup"><span data-stu-id="06bf1-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="06bf1-115">**返信**</span><span class="sxs-lookup"><span data-stu-id="06bf1-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="06bf1-116">int</span><span class="sxs-lookup"><span data-stu-id="06bf1-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="06bf1-117">このエラーに関連付けられた標準 SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="06bf1-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="06bf1-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="06bf1-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="06bf1-119">int</span><span class="sxs-lookup"><span data-stu-id="06bf1-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="06bf1-120">Microsoft 診断 ID。</span><span class="sxs-lookup"><span data-stu-id="06bf1-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="06bf1-121">**発信者の Typeid**</span><span class="sxs-lookup"><span data-stu-id="06bf1-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="06bf1-122">Int</span><span class="sxs-lookup"><span data-stu-id="06bf1-122">Int</span></span>  <br/> |<span data-ttu-id="06bf1-123">外部</span><span class="sxs-lookup"><span data-stu-id="06bf1-123">Foreign</span></span>  <br/> |<span data-ttu-id="06bf1-124">通話の種類。</span><span class="sxs-lookup"><span data-stu-id="06bf1-124">Type of the call.</span></span> <span data-ttu-id="06bf1-125">詳細については、「 [Skype For Business Server 2015 の CallType テーブル](calltype.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06bf1-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="06bf1-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="06bf1-126">**RequestType**</span></span> <br/> |<span data-ttu-id="06bf1-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="06bf1-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="06bf1-128">失敗した要求の種類。</span><span class="sxs-lookup"><span data-stu-id="06bf1-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="06bf1-129">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="06bf1-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="06bf1-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="06bf1-130">**ContentType**</span></span> <br/> |<span data-ttu-id="06bf1-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="06bf1-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="06bf1-132">失敗した要求のコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="06bf1-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="06bf1-133">このデータは、次の syntaxt を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="06bf1-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

