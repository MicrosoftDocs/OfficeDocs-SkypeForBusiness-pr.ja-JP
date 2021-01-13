---
title: Skype for Business Server 2015 の ErrorDef テーブル
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef テーブルには、発生する可能性がある各種類のエラーに関する情報が格納されます。 各レコードは 1 種類のエラーです。
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821727"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6bf98-104">Skype for Business Server 2015 の ErrorDef テーブル</span><span class="sxs-lookup"><span data-stu-id="6bf98-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6bf98-105">ErrorDef テーブルには、発生する可能性がある各種類のエラーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="6bf98-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="6bf98-106">各レコードは 1 種類のエラーです。</span><span class="sxs-lookup"><span data-stu-id="6bf98-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="6bf98-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6bf98-107">**Column**</span></span>|<span data-ttu-id="6bf98-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6bf98-108">**Data Type**</span></span>|<span data-ttu-id="6bf98-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="6bf98-109">**Key/Index**</span></span>|<span data-ttu-id="6bf98-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="6bf98-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6bf98-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="6bf98-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="6bf98-112">int</span><span class="sxs-lookup"><span data-stu-id="6bf98-112">int</span></span>  <br/> |<span data-ttu-id="6bf98-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6bf98-113">Primary</span></span>  <br/> |<span data-ttu-id="6bf98-114">この種類のエラーを識別する一意の ID 番号。</span><span class="sxs-lookup"><span data-stu-id="6bf98-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="6bf98-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="6bf98-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="6bf98-116">int</span><span class="sxs-lookup"><span data-stu-id="6bf98-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="6bf98-117">このエラーに関連付けられている標準的な SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="6bf98-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="6bf98-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="6bf98-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="6bf98-119">int</span><span class="sxs-lookup"><span data-stu-id="6bf98-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="6bf98-120">Microsoft 診断 ID。</span><span class="sxs-lookup"><span data-stu-id="6bf98-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="6bf98-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="6bf98-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="6bf98-122">Int</span><span class="sxs-lookup"><span data-stu-id="6bf98-122">Int</span></span>  <br/> |<span data-ttu-id="6bf98-123">外部</span><span class="sxs-lookup"><span data-stu-id="6bf98-123">Foreign</span></span>  <br/> |<span data-ttu-id="6bf98-124">通話の種類。</span><span class="sxs-lookup"><span data-stu-id="6bf98-124">Type of the call.</span></span> <span data-ttu-id="6bf98-125">詳細については [、Skype for Business Server 2015](calltype.md) の CallType テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bf98-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6bf98-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="6bf98-126">**RequestType**</span></span> <br/> |<span data-ttu-id="6bf98-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="6bf98-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="6bf98-128">失敗した要求の種類。</span><span class="sxs-lookup"><span data-stu-id="6bf98-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="6bf98-129">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="6bf98-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="6bf98-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="6bf98-130">**ContentType**</span></span> <br/> |<span data-ttu-id="6bf98-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="6bf98-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="6bf98-132">失敗した要求のコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="6bf98-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="6bf98-133">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="6bf98-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

