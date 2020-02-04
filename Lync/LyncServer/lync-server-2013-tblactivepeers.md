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
ms.openlocfilehash: 29d7c5c806e7540cc742781ce364748c47c10b39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="8becc-102">Lync Server 2013 の tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="8becc-102">tblActivePeers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8becc-103">_**最終更新日:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="8becc-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="8becc-104">tblActivePeers には、チャットサービス間の現在のピアツーピア接続が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8becc-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="8becc-105">行</span><span class="sxs-lookup"><span data-stu-id="8becc-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8becc-106">列</span><span class="sxs-lookup"><span data-stu-id="8becc-106">Column</span></span></th>
<th><span data-ttu-id="8becc-107">型</span><span class="sxs-lookup"><span data-stu-id="8becc-107">Type</span></span></th>
<th><span data-ttu-id="8becc-108">説明</span><span class="sxs-lookup"><span data-stu-id="8becc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8becc-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="8becc-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="8becc-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="8becc-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8becc-111">エントリを投稿したサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="8becc-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8becc-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="8becc-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="8becc-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="8becc-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8becc-114">ポスティングサーバーが接続されているピアの ID です。</span><span class="sxs-lookup"><span data-stu-id="8becc-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8becc-115">機能</span><span class="sxs-lookup"><span data-stu-id="8becc-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8becc-116">列</span><span class="sxs-lookup"><span data-stu-id="8becc-116">Column</span></span></th>
<th><span data-ttu-id="8becc-117">説明</span><span class="sxs-lookup"><span data-stu-id="8becc-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8becc-118">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="8becc-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="8becc-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="8becc-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8becc-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="8becc-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="8becc-121">TblServerIdentity テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="8becc-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8becc-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="8becc-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="8becc-123">TblServerIdentity テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="8becc-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

