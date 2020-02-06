---
title: Servers テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
description: Servers テーブルは、さまざまなサーバーに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのサーバーを表します。
ms.openlocfilehash: e2e2c86e96f7f929a218a5efa86100d3c383e339
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814925"
---
# <a name="servers-table"></a><span data-ttu-id="9e8fb-104">Servers テーブル</span><span class="sxs-lookup"><span data-stu-id="9e8fb-104">Servers table</span></span>
 
<span data-ttu-id="9e8fb-105">Servers テーブルは、さまざまなサーバーに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="9e8fb-105">The Servers table is a supporting table that stores information about the various servers.</span></span> <span data-ttu-id="9e8fb-106">テーブル内の各レコードは、1つのサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="9e8fb-106">Each record in the table represents one server.</span></span>
  
|<span data-ttu-id="9e8fb-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9e8fb-107">**Column**</span></span>|<span data-ttu-id="9e8fb-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9e8fb-108">**Data Type**</span></span>|<span data-ttu-id="9e8fb-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="9e8fb-109">**Key/Index**</span></span>|<span data-ttu-id="9e8fb-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9e8fb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e8fb-111">**ServerId**</span><span class="sxs-lookup"><span data-stu-id="9e8fb-111">**ServerId**</span></span> <br/> |<span data-ttu-id="9e8fb-112">int</span><span class="sxs-lookup"><span data-stu-id="9e8fb-112">int</span></span>  <br/> |<span data-ttu-id="9e8fb-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9e8fb-113">Primary</span></span>  <br/> |<span data-ttu-id="9e8fb-114">このサーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="9e8fb-114">Unique number identifying this server.</span></span>  <br/> |
|<span data-ttu-id="9e8fb-115">**ServerFQDN**</span><span class="sxs-lookup"><span data-stu-id="9e8fb-115">**ServerFQDN**</span></span> <br/> |<span data-ttu-id="9e8fb-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9e8fb-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="9e8fb-117">サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="9e8fb-117">Server FQDN.</span></span>  <br/> |
   

