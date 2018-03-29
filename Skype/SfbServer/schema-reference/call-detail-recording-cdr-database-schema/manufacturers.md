---
title: ビジネス サーバー 2015 の Skype の製造元テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 734608b3-5a3a-4b61-87dc-9a8551401d06
description: メーカーはテーブルをサポートします。 各レコードは、1 つのデバイス (机上電話) の製造元に関する情報を格納します。
ms.openlocfilehash: 675f90b2260110537913e5eae8039dee3cd5d93a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manufacturers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ea1c4-104">ビジネス サーバー 2015 の Skype の製造元テーブル</span><span class="sxs-lookup"><span data-stu-id="ea1c4-104">Manufacturers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ea1c4-105">メーカーはテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ea1c4-105">The Manufacturers table is a supporting table.</span></span> <span data-ttu-id="ea1c4-106">各レコードは、1 つのデバイス (机上電話) の製造元に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="ea1c4-106">Each record stores information about one device (desk phone) manufacturer.</span></span>
  
|<span data-ttu-id="ea1c4-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ea1c4-107">**Column**</span></span>|<span data-ttu-id="ea1c4-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ea1c4-108">**Data Type**</span></span>|<span data-ttu-id="ea1c4-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="ea1c4-109">**Key/Index**</span></span>|<span data-ttu-id="ea1c4-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ea1c4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ea1c4-111">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="ea1c4-111">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="ea1c4-112">int</span><span class="sxs-lookup"><span data-stu-id="ea1c4-112">int</span></span>  <br/> |<span data-ttu-id="ea1c4-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ea1c4-113">Primary</span></span>  <br/> |<span data-ttu-id="ea1c4-114">この製造元を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="ea1c4-114">Unique number identifying this manufacturer.</span></span>  <br/> |
|<span data-ttu-id="ea1c4-115">**[製造元]**</span><span class="sxs-lookup"><span data-stu-id="ea1c4-115">**Manufacturer**</span></span> <br/> |<span data-ttu-id="ea1c4-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ea1c4-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="ea1c4-117">製造元の名前です。</span><span class="sxs-lookup"><span data-stu-id="ea1c4-117">Manufacturer name.</span></span>  <br/> |
   

