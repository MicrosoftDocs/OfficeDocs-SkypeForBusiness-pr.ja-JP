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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers テーブルはサポートされているテーブルです。 各レコードには、データベース内のレコードを持つ通話に関連する1つの仲介サーバーに関する情報が格納されます。
ms.openlocfilehash: 74c1095044bd9bb7183202d115236eba863c62da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815025"
---
# <a name="mediationservers-table"></a><span data-ttu-id="1abd2-104">MediationServers テーブル</span><span class="sxs-lookup"><span data-stu-id="1abd2-104">MediationServers table</span></span>
 
<span data-ttu-id="1abd2-105">MediationServers テーブルはサポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="1abd2-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="1abd2-106">各レコードには、データベース内のレコードを持つ通話に関連する1つの仲介サーバーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1abd2-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="1abd2-107">**列**</span><span class="sxs-lookup"><span data-stu-id="1abd2-107">**Column**</span></span>|<span data-ttu-id="1abd2-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1abd2-108">**Data Type**</span></span>|<span data-ttu-id="1abd2-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="1abd2-109">**Key/Index**</span></span>|<span data-ttu-id="1abd2-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1abd2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1abd2-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="1abd2-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="1abd2-112">int</span><span class="sxs-lookup"><span data-stu-id="1abd2-112">int</span></span>  <br/> |<span data-ttu-id="1abd2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1abd2-113">Primary</span></span>  <br/> |<span data-ttu-id="1abd2-114">この仲介サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="1abd2-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="1abd2-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="1abd2-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="1abd2-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1abd2-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="1abd2-117">仲介サーバー名。</span><span class="sxs-lookup"><span data-stu-id="1abd2-117">Mediation Server name.</span></span>  <br/> |
   

