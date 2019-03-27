---
title: MediationServers テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers はテーブルをサポートします。 各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つの仲介サーバーに関する情報を格納します。
ms.openlocfilehash: 77173fbb81bc2046a1906c61456f607ec7f2b5b3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877071"
---
# <a name="mediationservers-table"></a><span data-ttu-id="d56f1-104">MediationServers テーブル</span><span class="sxs-lookup"><span data-stu-id="d56f1-104">MediationServers table</span></span>
 
<span data-ttu-id="d56f1-105">MediationServers はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d56f1-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="d56f1-106">各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つの仲介サーバーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="d56f1-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="d56f1-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d56f1-107">**Column**</span></span>|<span data-ttu-id="d56f1-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d56f1-108">**Data Type**</span></span>|<span data-ttu-id="d56f1-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="d56f1-109">**Key/Index**</span></span>|<span data-ttu-id="d56f1-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="d56f1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d56f1-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="d56f1-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="d56f1-112">int</span><span class="sxs-lookup"><span data-stu-id="d56f1-112">int</span></span>  <br/> |<span data-ttu-id="d56f1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d56f1-113">Primary</span></span>  <br/> |<span data-ttu-id="d56f1-114">この仲介サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="d56f1-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="d56f1-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="d56f1-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="d56f1-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d56f1-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="d56f1-117">仲介サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="d56f1-117">Mediation Server name.</span></span>  <br/> |
   

