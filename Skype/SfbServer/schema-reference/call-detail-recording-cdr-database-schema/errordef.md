---
title: ビジネス サーバー 2015 の Skype での ErrorDef テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef テーブルでは、発生するエラーの種類に関する情報を格納します。 各レコードは、1 つの種類のエラーです。
ms.openlocfilehash: cec601dad24dda522477bfcd7b1e80d0efc45799
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213110"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6880e-104">ビジネス サーバー 2015 の Skype での ErrorDef テーブル</span><span class="sxs-lookup"><span data-stu-id="6880e-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6880e-105">ErrorDef テーブルでは、発生するエラーの種類に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6880e-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="6880e-106">各レコードは、1 つの種類のエラーです。</span><span class="sxs-lookup"><span data-stu-id="6880e-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="6880e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6880e-107">**Column**</span></span>|<span data-ttu-id="6880e-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6880e-108">**Data Type**</span></span>|<span data-ttu-id="6880e-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="6880e-109">**Key/Index**</span></span>|<span data-ttu-id="6880e-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="6880e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6880e-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="6880e-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="6880e-112">int</span><span class="sxs-lookup"><span data-stu-id="6880e-112">int</span></span>  <br/> |<span data-ttu-id="6880e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6880e-113">Primary</span></span>  <br/> |<span data-ttu-id="6880e-114">この種類のエラーを識別する一意の ID 番号です。</span><span class="sxs-lookup"><span data-stu-id="6880e-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="6880e-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="6880e-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="6880e-116">int</span><span class="sxs-lookup"><span data-stu-id="6880e-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="6880e-117">このエラーに関連付けられている標準の SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="6880e-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="6880e-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="6880e-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="6880e-119">int</span><span class="sxs-lookup"><span data-stu-id="6880e-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="6880e-120">マイクロソフトの診断 id。</span><span class="sxs-lookup"><span data-stu-id="6880e-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="6880e-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="6880e-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="6880e-122">Int</span><span class="sxs-lookup"><span data-stu-id="6880e-122">Int</span></span>  <br/> |<span data-ttu-id="6880e-123">外部</span><span class="sxs-lookup"><span data-stu-id="6880e-123">Foreign</span></span>  <br/> |<span data-ttu-id="6880e-124">呼び出しの種類です。</span><span class="sxs-lookup"><span data-stu-id="6880e-124">Type of the call.</span></span> <span data-ttu-id="6880e-125">[ビジネス サーバー 2015 の Skype の CallType テーブル](calltype.md)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6880e-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6880e-126">**修飾子の一覧**</span><span class="sxs-lookup"><span data-stu-id="6880e-126">**RequestType**</span></span> <br/> |<span data-ttu-id="6880e-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="6880e-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="6880e-128">失敗した要求の種類です。</span><span class="sxs-lookup"><span data-stu-id="6880e-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="6880e-129">このデータは、この構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="6880e-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="6880e-130">**コンテンツ タイプ**</span><span class="sxs-lookup"><span data-stu-id="6880e-130">**ContentType**</span></span> <br/> |<span data-ttu-id="6880e-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="6880e-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="6880e-132">失敗した要求のコンテンツ タイプ。</span><span class="sxs-lookup"><span data-stu-id="6880e-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="6880e-133">このデータは、この syntaxt を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="6880e-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

