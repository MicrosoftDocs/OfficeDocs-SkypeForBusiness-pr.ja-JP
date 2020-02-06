---
title: IPAddress テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress テーブルは、パフォーマンスの高いデータベースの別の場所で使用されている一意の IP アドレス識別子に IP アドレスをマッピングします。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809545"
---
# <a name="ipaddress-table"></a><span data-ttu-id="1ded6-104">IPAddress テーブル</span><span class="sxs-lookup"><span data-stu-id="1ded6-104">IPAddress table</span></span>
 
<span data-ttu-id="1ded6-105">IPAddress テーブルは、パフォーマンスの高いデータベースの別の場所で使用されている一意の IP アドレス識別子に IP アドレスをマッピングします。</span><span class="sxs-lookup"><span data-stu-id="1ded6-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="1ded6-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1ded6-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="1ded6-107">**列**</span><span class="sxs-lookup"><span data-stu-id="1ded6-107">**Column**</span></span>|<span data-ttu-id="1ded6-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1ded6-108">**Data Type**</span></span>|<span data-ttu-id="1ded6-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="1ded6-109">**Key/Index**</span></span>|<span data-ttu-id="1ded6-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1ded6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ded6-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="1ded6-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="1ded6-112">int</span><span class="sxs-lookup"><span data-stu-id="1ded6-112">int</span></span>  <br/> |<span data-ttu-id="1ded6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1ded6-113">Primary</span></span>  <br/> |<span data-ttu-id="1ded6-114">指定した IP アドレスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="1ded6-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="1ded6-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="1ded6-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="1ded6-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="1ded6-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="1ded6-117">一意</span><span class="sxs-lookup"><span data-stu-id="1ded6-117">Unique</span></span>  <br/> |<span data-ttu-id="1ded6-118">IpAddressKey にマップされる固有の IP アドレス (たとえば、189.168.1.1)。</span><span class="sxs-lookup"><span data-stu-id="1ded6-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="1ded6-119">これは IPv4 または IPv6 アドレスのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="1ded6-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

