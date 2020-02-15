---
title: 'Lync Server 2013: tblServerIdentity'
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
ms.openlocfilehash: 5f6ed7f0eed08dbb4ab3b0d6f41c9ec91fb719f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="c17b5-102">Lync Server 2013 の tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="c17b5-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c17b5-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c17b5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c17b5-104">tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c17b5-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="c17b5-105">Columns</span><span class="sxs-lookup"><span data-stu-id="c17b5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c17b5-106">列</span><span class="sxs-lookup"><span data-stu-id="c17b5-106">Column</span></span></th>
<th><span data-ttu-id="c17b5-107">種類</span><span class="sxs-lookup"><span data-stu-id="c17b5-107">Type</span></span></th>
<th><span data-ttu-id="c17b5-108">説明</span><span class="sxs-lookup"><span data-stu-id="c17b5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c17b5-109">serverID</span><span class="sxs-lookup"><span data-stu-id="c17b5-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="c17b5-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="c17b5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c17b5-111">サーバー ID。</span><span class="sxs-lookup"><span data-stu-id="c17b5-111">Server ID.</span></span> <span data-ttu-id="c17b5-112">中央管理ストアのインスタンス ID に対応します。</span><span class="sxs-lookup"><span data-stu-id="c17b5-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c17b5-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="c17b5-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="c17b5-114">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c17b5-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="c17b5-115">Windows Communication Foundation アドレスを使用したサーバー アドレス。</span><span class="sxs-lookup"><span data-stu-id="c17b5-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c17b5-116">Serverlastping Time</span><span class="sxs-lookup"><span data-stu-id="c17b5-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="c17b5-117">日付型</span><span class="sxs-lookup"><span data-stu-id="c17b5-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="c17b5-118">チャネル サーバーが、実行中であることを示すためにこの行を更新した最新時刻。</span><span class="sxs-lookup"><span data-stu-id="c17b5-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c17b5-119">キー</span><span class="sxs-lookup"><span data-stu-id="c17b5-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c17b5-120">列</span><span class="sxs-lookup"><span data-stu-id="c17b5-120">Column</span></span></th>
<th><span data-ttu-id="c17b5-121">説明</span><span class="sxs-lookup"><span data-stu-id="c17b5-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c17b5-122">serverID</span><span class="sxs-lookup"><span data-stu-id="c17b5-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="c17b5-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="c17b5-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

