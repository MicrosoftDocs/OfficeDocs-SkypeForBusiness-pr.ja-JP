---
title: Skype for Business Server 2015 のゲートウェイテーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: ゲートウェイテーブルは、サポートされているテーブルです。 各レコードには、データベース内にレコードがある公衆交換電話網 (PSTN) 通話に関連する1つのゲートウェイに関する情報が格納されます。
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296183"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ad0bc-104">Skype for Business Server 2015 のゲートウェイテーブル</span><span class="sxs-lookup"><span data-stu-id="ad0bc-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ad0bc-105">ゲートウェイテーブルは、サポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ad0bc-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="ad0bc-106">各レコードには、データベース内にレコードがある公衆交換電話網 (PSTN) 通話に関連する1つのゲートウェイに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="ad0bc-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="ad0bc-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ad0bc-107">**Column**</span></span>|<span data-ttu-id="ad0bc-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ad0bc-108">**Data Type**</span></span>|<span data-ttu-id="ad0bc-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="ad0bc-109">**Key/Index**</span></span>|<span data-ttu-id="ad0bc-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ad0bc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad0bc-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="ad0bc-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="ad0bc-112">int</span><span class="sxs-lookup"><span data-stu-id="ad0bc-112">int</span></span>  <br/> |<span data-ttu-id="ad0bc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ad0bc-113">Primary</span></span>  <br/> |<span data-ttu-id="ad0bc-114">このゲートウェイを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="ad0bc-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="ad0bc-115">**ゲートウェイ**</span><span class="sxs-lookup"><span data-stu-id="ad0bc-115">**Gateway**</span></span> <br/> |<span data-ttu-id="ad0bc-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ad0bc-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="ad0bc-117">ゲートウェイ名。</span><span class="sxs-lookup"><span data-stu-id="ad0bc-117">Gateway name.</span></span>  <br/> |
   

