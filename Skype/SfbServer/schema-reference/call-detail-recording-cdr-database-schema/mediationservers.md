---
title: MediationServers テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers はテーブルをサポートします。 各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つの仲介サーバーに関する情報を格納します。
ms.openlocfilehash: 25f6c14a903ffde424cba1c2a6bb3292040b2391
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930547"
---
# <a name="mediationservers-table"></a><span data-ttu-id="2528b-104">MediationServers テーブル</span><span class="sxs-lookup"><span data-stu-id="2528b-104">MediationServers table</span></span>
 
<span data-ttu-id="2528b-105">MediationServers はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2528b-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="2528b-106">各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つの仲介サーバーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="2528b-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="2528b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2528b-107">**Column**</span></span>|<span data-ttu-id="2528b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2528b-108">**Data Type**</span></span>|<span data-ttu-id="2528b-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="2528b-109">**Key/Index**</span></span>|<span data-ttu-id="2528b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2528b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2528b-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="2528b-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="2528b-112">int</span><span class="sxs-lookup"><span data-stu-id="2528b-112">int</span></span>  <br/> |<span data-ttu-id="2528b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2528b-113">Primary</span></span>  <br/> |<span data-ttu-id="2528b-114">この仲介サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="2528b-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="2528b-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="2528b-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="2528b-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2528b-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="2528b-117">仲介サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="2528b-117">Mediation Server name.</span></span>  <br/> |
   

