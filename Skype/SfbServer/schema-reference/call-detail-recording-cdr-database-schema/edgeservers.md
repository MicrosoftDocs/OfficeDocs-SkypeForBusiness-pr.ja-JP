---
title: Skype for Business Server 2015 の EdgeServers テーブル
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
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers テーブルはサポート テーブルです。 各レコードには、データベースにレコードがある呼び出しに関係する 1 つのエッジ サーバーに関する情報が格納されます。
ms.openlocfilehash: 98f37ecbf976fb08ae27e080f5e9e498558131fb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813207"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="19193-104">Skype for Business Server 2015 の EdgeServers テーブル</span><span class="sxs-lookup"><span data-stu-id="19193-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="19193-105">EdgeServers テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="19193-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="19193-106">各レコードには、データベースにレコードがある呼び出しに関係する 1 つのエッジ サーバーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="19193-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="19193-107">**列**</span><span class="sxs-lookup"><span data-stu-id="19193-107">**Column**</span></span>|<span data-ttu-id="19193-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="19193-108">**Data Type**</span></span>|<span data-ttu-id="19193-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="19193-109">**Key/Index**</span></span>|<span data-ttu-id="19193-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="19193-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="19193-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="19193-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="19193-112">int</span><span class="sxs-lookup"><span data-stu-id="19193-112">int</span></span>  <br/> |<span data-ttu-id="19193-113">Primary</span><span class="sxs-lookup"><span data-stu-id="19193-113">Primary</span></span>  <br/> |<span data-ttu-id="19193-114">このエッジ サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="19193-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="19193-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="19193-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="19193-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="19193-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="19193-117">エッジ サーバー名。</span><span class="sxs-lookup"><span data-stu-id="19193-117">Edge Server name.</span></span>  <br/> |
   

