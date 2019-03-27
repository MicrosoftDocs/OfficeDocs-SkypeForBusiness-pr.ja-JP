---
title: Ip アドレス テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Ip アドレス テーブルは、高品質なエクスペリエンスのデータベース内で使用する一意の IP アドレス識別子を IP アドレスをマップします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876959"
---
# <a name="ipaddress-table"></a><span data-ttu-id="010ae-104">Ip アドレス テーブル</span><span class="sxs-lookup"><span data-stu-id="010ae-104">IPAddress table</span></span>
 
<span data-ttu-id="010ae-105">Ip アドレス テーブルは、高品質なエクスペリエンスのデータベース内で使用する一意の IP アドレス識別子を IP アドレスをマップします。</span><span class="sxs-lookup"><span data-stu-id="010ae-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="010ae-106">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="010ae-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="010ae-107">**列**</span><span class="sxs-lookup"><span data-stu-id="010ae-107">**Column**</span></span>|<span data-ttu-id="010ae-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="010ae-108">**Data Type**</span></span>|<span data-ttu-id="010ae-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="010ae-109">**Key/Index**</span></span>|<span data-ttu-id="010ae-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="010ae-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="010ae-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="010ae-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="010ae-112">int</span><span class="sxs-lookup"><span data-stu-id="010ae-112">int</span></span>  <br/> |<span data-ttu-id="010ae-113">Primary</span><span class="sxs-lookup"><span data-stu-id="010ae-113">Primary</span></span>  <br/> |<span data-ttu-id="010ae-114">指定した IP アドレスを表す一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="010ae-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="010ae-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="010ae-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="010ae-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="010ae-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="010ae-117">一意</span><span class="sxs-lookup"><span data-stu-id="010ae-117">Unique</span></span>  <br/> |<span data-ttu-id="010ae-118">一意の IP アドレス (たとえば、189.168.1.1)、IpAddressKey にマップします。</span><span class="sxs-lookup"><span data-stu-id="010ae-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="010ae-119">IPv4 または IPv6 アドレスのいずれかがあります。</span><span class="sxs-lookup"><span data-stu-id="010ae-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

