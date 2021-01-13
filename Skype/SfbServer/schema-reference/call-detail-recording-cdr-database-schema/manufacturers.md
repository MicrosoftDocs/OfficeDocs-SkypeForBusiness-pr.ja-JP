---
title: Skype for Business Server 2015 の Manufacturers テーブル
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
ms.assetid: 734608b3-5a3a-4b61-87dc-9a8551401d06
description: Manufacturers テーブルはサポート テーブルです。 各レコードには、1 つのデバイス (電話) 製造元に関する情報が格納されます。
ms.openlocfilehash: f3cdd6e33732eb226cc2d99ff403495ac19f5567
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821487"
---
# <a name="manufacturers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d689d-104">Skype for Business Server 2015 の Manufacturers テーブル</span><span class="sxs-lookup"><span data-stu-id="d689d-104">Manufacturers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d689d-105">Manufacturers テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="d689d-105">The Manufacturers table is a supporting table.</span></span> <span data-ttu-id="d689d-106">各レコードには、1 つのデバイス (電話) 製造元に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="d689d-106">Each record stores information about one device (desk phone) manufacturer.</span></span>
  
|<span data-ttu-id="d689d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d689d-107">**Column**</span></span>|<span data-ttu-id="d689d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d689d-108">**Data Type**</span></span>|<span data-ttu-id="d689d-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="d689d-109">**Key/Index**</span></span>|<span data-ttu-id="d689d-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="d689d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d689d-111">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="d689d-111">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="d689d-112">int</span><span class="sxs-lookup"><span data-stu-id="d689d-112">int</span></span>  <br/> |<span data-ttu-id="d689d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d689d-113">Primary</span></span>  <br/> |<span data-ttu-id="d689d-114">この製造元を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="d689d-114">Unique number identifying this manufacturer.</span></span>  <br/> |
|<span data-ttu-id="d689d-115">**製造元**</span><span class="sxs-lookup"><span data-stu-id="d689d-115">**Manufacturer**</span></span> <br/> |<span data-ttu-id="d689d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d689d-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="d689d-117">製造元名。</span><span class="sxs-lookup"><span data-stu-id="d689d-117">Manufacturer name.</span></span>  <br/> |
   

