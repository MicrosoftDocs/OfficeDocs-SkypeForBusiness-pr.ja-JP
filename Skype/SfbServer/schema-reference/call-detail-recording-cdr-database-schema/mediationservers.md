---
title: MediationServers テーブル
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
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers テーブルはサポート テーブルです。 各レコードには、データベース内のレコードを持つ呼び出しに関係する 1 つの仲介サーバーに関する情報が格納されます。
ms.openlocfilehash: e498409087ee5cf41b32b29ec5f66a147290e1ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814767"
---
# <a name="mediationservers-table"></a><span data-ttu-id="55b7d-104">MediationServers テーブル</span><span class="sxs-lookup"><span data-stu-id="55b7d-104">MediationServers table</span></span>
 
<span data-ttu-id="55b7d-105">MediationServers テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="55b7d-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="55b7d-106">各レコードには、データベース内のレコードを持つ呼び出しに関係する 1 つの仲介サーバーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="55b7d-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="55b7d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="55b7d-107">**Column**</span></span>|<span data-ttu-id="55b7d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="55b7d-108">**Data Type**</span></span>|<span data-ttu-id="55b7d-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="55b7d-109">**Key/Index**</span></span>|<span data-ttu-id="55b7d-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="55b7d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55b7d-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="55b7d-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="55b7d-112">int</span><span class="sxs-lookup"><span data-stu-id="55b7d-112">int</span></span>  <br/> |<span data-ttu-id="55b7d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="55b7d-113">Primary</span></span>  <br/> |<span data-ttu-id="55b7d-114">この仲介サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="55b7d-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="55b7d-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="55b7d-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="55b7d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="55b7d-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="55b7d-117">仲介サーバー名。</span><span class="sxs-lookup"><span data-stu-id="55b7d-117">Mediation Server name.</span></span>  <br/> |
   

