---
title: Ip アドレス テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Ip アドレス テーブルは、高品質なエクスペリエンスのデータベース内で使用する一意の IP アドレス識別子を IP アドレスをマップします。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: d7d3b5f9192c2385836f42f9c430da5b99752892
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920034"
---
# <a name="ipaddress-table"></a><span data-ttu-id="6ad96-104">Ip アドレス テーブル</span><span class="sxs-lookup"><span data-stu-id="6ad96-104">IPAddress table</span></span>
 
<span data-ttu-id="6ad96-105">Ip アドレス テーブルは、高品質なエクスペリエンスのデータベース内で使用する一意の IP アドレス識別子を IP アドレスをマップします。</span><span class="sxs-lookup"><span data-stu-id="6ad96-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="6ad96-106">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6ad96-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6ad96-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6ad96-107">**Column**</span></span>|<span data-ttu-id="6ad96-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6ad96-108">**Data Type**</span></span>|<span data-ttu-id="6ad96-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="6ad96-109">**Key/Index**</span></span>|<span data-ttu-id="6ad96-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="6ad96-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6ad96-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="6ad96-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="6ad96-112">int</span><span class="sxs-lookup"><span data-stu-id="6ad96-112">int</span></span>  <br/> |<span data-ttu-id="6ad96-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6ad96-113">Primary</span></span>  <br/> |<span data-ttu-id="6ad96-114">指定した IP アドレスを表す一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="6ad96-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="6ad96-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="6ad96-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="6ad96-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="6ad96-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="6ad96-117">一意</span><span class="sxs-lookup"><span data-stu-id="6ad96-117">Unique</span></span>  <br/> |<span data-ttu-id="6ad96-118">一意の IP アドレス (たとえば、189.168.1.1)、IpAddressKey にマップします。</span><span class="sxs-lookup"><span data-stu-id="6ad96-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="6ad96-119">IPv4 または IPv6 アドレスのいずれかがあります。</span><span class="sxs-lookup"><span data-stu-id="6ad96-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

