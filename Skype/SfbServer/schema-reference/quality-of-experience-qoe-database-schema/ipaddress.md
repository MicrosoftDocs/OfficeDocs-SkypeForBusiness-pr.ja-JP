---
title: IPAddress テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress テーブルは、IP アドレスを体感品質データベースの他の場所で使用される一意の IP アドレス識別子にマップします。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802777"
---
# <a name="ipaddress-table"></a><span data-ttu-id="3fbf4-104">IPAddress テーブル</span><span class="sxs-lookup"><span data-stu-id="3fbf4-104">IPAddress table</span></span>
 
<span data-ttu-id="3fbf4-105">IPAddress テーブルは、IP アドレスを体感品質データベースの他の場所で使用される一意の IP アドレス識別子にマップします。</span><span class="sxs-lookup"><span data-stu-id="3fbf4-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="3fbf4-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3fbf4-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3fbf4-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3fbf4-107">**Column**</span></span>|<span data-ttu-id="3fbf4-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3fbf4-108">**Data Type**</span></span>|<span data-ttu-id="3fbf4-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="3fbf4-109">**Key/Index**</span></span>|<span data-ttu-id="3fbf4-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3fbf4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3fbf4-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="3fbf4-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="3fbf4-112">int</span><span class="sxs-lookup"><span data-stu-id="3fbf4-112">int</span></span>  <br/> |<span data-ttu-id="3fbf4-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3fbf4-113">Primary</span></span>  <br/> |<span data-ttu-id="3fbf4-114">指定した IP アドレスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="3fbf4-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="3fbf4-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="3fbf4-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="3fbf4-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="3fbf4-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="3fbf4-117">一意</span><span class="sxs-lookup"><span data-stu-id="3fbf4-117">Unique</span></span>  <br/> |<span data-ttu-id="3fbf4-p103">IpAddressKey にマップされる一意の IP アドレス (189.168.1.1 など)。これは IPv4 または IPv6 アドレスです。</span><span class="sxs-lookup"><span data-stu-id="3fbf4-p103">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

