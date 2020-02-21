---
title: 'Lync Server 2013: tblActivePeers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a47ac4368dd424b08cfb47c6d867bc20144e45c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="81d68-102">Lync Server 2013 の tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="81d68-102">tblActivePeers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81d68-103">_**トピックの最終更新日:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="81d68-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="81d68-104">tblActivePeers には、チャット サービス間の現在のピアツーピア接続が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81d68-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="81d68-105">Columns</span><span class="sxs-lookup"><span data-stu-id="81d68-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81d68-106">列</span><span class="sxs-lookup"><span data-stu-id="81d68-106">Column</span></span></th>
<th><span data-ttu-id="81d68-107">種類</span><span class="sxs-lookup"><span data-stu-id="81d68-107">Type</span></span></th>
<th><span data-ttu-id="81d68-108">説明</span><span class="sxs-lookup"><span data-stu-id="81d68-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81d68-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="81d68-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="81d68-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="81d68-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="81d68-111">エントリを投稿したサーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="81d68-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81d68-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="81d68-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="81d68-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="81d68-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="81d68-114">投稿元サーバーが接続しているピアの ID。</span><span class="sxs-lookup"><span data-stu-id="81d68-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="81d68-115">Keys</span><span class="sxs-lookup"><span data-stu-id="81d68-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81d68-116">列</span><span class="sxs-lookup"><span data-stu-id="81d68-116">Column</span></span></th>
<th><span data-ttu-id="81d68-117">説明</span><span class="sxs-lookup"><span data-stu-id="81d68-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81d68-118">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="81d68-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="81d68-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="81d68-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81d68-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="81d68-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="81d68-121">tblServerIdentity.serverID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="81d68-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81d68-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="81d68-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="81d68-123">tblServerIdentity.serverID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="81d68-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

