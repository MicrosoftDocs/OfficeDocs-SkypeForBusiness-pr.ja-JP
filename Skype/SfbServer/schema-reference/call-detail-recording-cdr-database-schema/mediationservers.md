---
title: MediationServers テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers テーブルはサポートされているテーブルです。 各レコードには、データベース内のレコードを持つ通話に関連する1つの仲介サーバーに関する情報が格納されます。
ms.openlocfilehash: a79c7c1d81f220e034e63263ef8dbf81a13d4024
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295994"
---
# <a name="mediationservers-table"></a><span data-ttu-id="e0be3-104">MediationServers テーブル</span><span class="sxs-lookup"><span data-stu-id="e0be3-104">MediationServers table</span></span>
 
<span data-ttu-id="e0be3-105">MediationServers テーブルはサポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="e0be3-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="e0be3-106">各レコードには、データベース内のレコードを持つ通話に関連する1つの仲介サーバーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="e0be3-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="e0be3-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e0be3-107">**Column**</span></span>|<span data-ttu-id="e0be3-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e0be3-108">**Data Type**</span></span>|<span data-ttu-id="e0be3-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="e0be3-109">**Key/Index**</span></span>|<span data-ttu-id="e0be3-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e0be3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0be3-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="e0be3-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="e0be3-112">int</span><span class="sxs-lookup"><span data-stu-id="e0be3-112">int</span></span>  <br/> |<span data-ttu-id="e0be3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e0be3-113">Primary</span></span>  <br/> |<span data-ttu-id="e0be3-114">この仲介サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="e0be3-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="e0be3-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="e0be3-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="e0be3-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e0be3-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="e0be3-117">仲介サーバー名。</span><span class="sxs-lookup"><span data-stu-id="e0be3-117">Mediation Server name.</span></span>  <br/> |
   

