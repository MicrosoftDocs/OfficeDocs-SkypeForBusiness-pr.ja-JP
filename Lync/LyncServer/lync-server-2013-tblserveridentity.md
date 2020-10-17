---
title: 'Lync Server 2013: tblServerIdentity'
description: 'Lync Server 2013: tblServerIdentity。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e954618cb373f2cf4f1b7ed929c3aaf6d8875e92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564533"
---
# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="7891a-103">Lync Server 2013 の tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="7891a-103">tblServerIdentity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7891a-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7891a-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7891a-105">tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7891a-105">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="7891a-106">段組み</span><span class="sxs-lookup"><span data-stu-id="7891a-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7891a-107">Column</span><span class="sxs-lookup"><span data-stu-id="7891a-107">Column</span></span></th>
<th><span data-ttu-id="7891a-108">種類</span><span class="sxs-lookup"><span data-stu-id="7891a-108">Type</span></span></th>
<th><span data-ttu-id="7891a-109">説明</span><span class="sxs-lookup"><span data-stu-id="7891a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7891a-110">serverID</span><span class="sxs-lookup"><span data-stu-id="7891a-110">serverID</span></span></p></td>
<td><p><span data-ttu-id="7891a-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="7891a-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7891a-112">サーバー ID。</span><span class="sxs-lookup"><span data-stu-id="7891a-112">Server ID.</span></span> <span data-ttu-id="7891a-113">中央管理ストアのインスタンス ID に対応します。</span><span class="sxs-lookup"><span data-stu-id="7891a-113">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7891a-114">serverAddress</span><span class="sxs-lookup"><span data-stu-id="7891a-114">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="7891a-115">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7891a-115">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7891a-116">Windows Communication Foundation アドレスを使用したサーバー アドレス。</span><span class="sxs-lookup"><span data-stu-id="7891a-116">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7891a-117">Serverlastping Time</span><span class="sxs-lookup"><span data-stu-id="7891a-117">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="7891a-118">日付型</span><span class="sxs-lookup"><span data-stu-id="7891a-118">datetime</span></span></p></td>
<td><p><span data-ttu-id="7891a-119">チャネル サーバーが、実行中であることを示すためにこの行を更新した最新時刻。</span><span class="sxs-lookup"><span data-stu-id="7891a-119">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7891a-120">キー</span><span class="sxs-lookup"><span data-stu-id="7891a-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7891a-121">列</span><span class="sxs-lookup"><span data-stu-id="7891a-121">Column</span></span></th>
<th><span data-ttu-id="7891a-122">説明</span><span class="sxs-lookup"><span data-stu-id="7891a-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7891a-123">serverID</span><span class="sxs-lookup"><span data-stu-id="7891a-123">serverID</span></span></p></td>
<td><p><span data-ttu-id="7891a-124">主キー。</span><span class="sxs-lookup"><span data-stu-id="7891a-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

