---
title: Skype for Business Server 2015 の EdgeServers テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers テーブルは、サポートテーブルです。 各レコードには、データベース内のレコードが含まれる通話に関連する1つの Edge サーバーに関する情報が格納されます。
ms.openlocfilehash: a78acd3b6297bbef3348ef87047c8cb7f0893231
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296344"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="56fe8-104">Skype for Business Server 2015 の EdgeServers テーブル</span><span class="sxs-lookup"><span data-stu-id="56fe8-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="56fe8-105">EdgeServers テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="56fe8-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="56fe8-106">各レコードには、データベース内のレコードが含まれる通話に関連する1つの Edge サーバーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="56fe8-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="56fe8-107">**列**</span><span class="sxs-lookup"><span data-stu-id="56fe8-107">**Column**</span></span>|<span data-ttu-id="56fe8-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="56fe8-108">**Data Type**</span></span>|<span data-ttu-id="56fe8-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="56fe8-109">**Key/Index**</span></span>|<span data-ttu-id="56fe8-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="56fe8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56fe8-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="56fe8-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="56fe8-112">int</span><span class="sxs-lookup"><span data-stu-id="56fe8-112">int</span></span>  <br/> |<span data-ttu-id="56fe8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="56fe8-113">Primary</span></span>  <br/> |<span data-ttu-id="56fe8-114">このエッジサーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="56fe8-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="56fe8-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="56fe8-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="56fe8-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="56fe8-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="56fe8-117">エッジサーバー名。</span><span class="sxs-lookup"><span data-stu-id="56fe8-117">Edge Server name.</span></span>  <br/> |
   

