---
title: Servers テーブル
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
ms.assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
description: Servers テーブルは、さまざまなサーバーに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのサーバーを表します。
ms.openlocfilehash: acbc929c1c47ebf86e1b58f4c008f4351de35496
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809947"
---
# <a name="servers-table"></a><span data-ttu-id="121fe-104">Servers テーブル</span><span class="sxs-lookup"><span data-stu-id="121fe-104">Servers table</span></span>
 
<span data-ttu-id="121fe-105">Servers テーブルは、さまざまなサーバーに関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="121fe-105">The Servers table is a supporting table that stores information about the various servers.</span></span> <span data-ttu-id="121fe-106">テーブル内の各レコードは、1 つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="121fe-106">Each record in the table represents one server.</span></span>
  
|<span data-ttu-id="121fe-107">**列**</span><span class="sxs-lookup"><span data-stu-id="121fe-107">**Column**</span></span>|<span data-ttu-id="121fe-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="121fe-108">**Data Type**</span></span>|<span data-ttu-id="121fe-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="121fe-109">**Key/Index**</span></span>|<span data-ttu-id="121fe-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="121fe-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="121fe-111">**ServerId**</span><span class="sxs-lookup"><span data-stu-id="121fe-111">**ServerId**</span></span> <br/> |<span data-ttu-id="121fe-112">int</span><span class="sxs-lookup"><span data-stu-id="121fe-112">int</span></span>  <br/> |<span data-ttu-id="121fe-113">Primary</span><span class="sxs-lookup"><span data-stu-id="121fe-113">Primary</span></span>  <br/> |<span data-ttu-id="121fe-114">このサーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="121fe-114">Unique number identifying this server.</span></span>  <br/> |
|<span data-ttu-id="121fe-115">**ServerFQDN**</span><span class="sxs-lookup"><span data-stu-id="121fe-115">**ServerFQDN**</span></span> <br/> |<span data-ttu-id="121fe-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="121fe-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="121fe-117">サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="121fe-117">Server FQDN.</span></span>  <br/> |
   

