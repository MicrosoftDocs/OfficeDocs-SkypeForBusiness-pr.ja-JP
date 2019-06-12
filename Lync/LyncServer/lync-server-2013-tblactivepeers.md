---
title: 'Lync Server 2013: tblActivePeers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb6089cfa3f3a9da8103dd0d0691031dac05d05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="36601-102">Lync Server 2013 の tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="36601-102">tblActivePeers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36601-103">_**最終更新日:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="36601-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="36601-104">tblActivePeers には、チャットサービス間の現在のピアツーピア接続が含まれています。</span><span class="sxs-lookup"><span data-stu-id="36601-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="36601-105">行</span><span class="sxs-lookup"><span data-stu-id="36601-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36601-106">列</span><span class="sxs-lookup"><span data-stu-id="36601-106">Column</span></span></th>
<th><span data-ttu-id="36601-107">型</span><span class="sxs-lookup"><span data-stu-id="36601-107">Type</span></span></th>
<th><span data-ttu-id="36601-108">説明</span><span class="sxs-lookup"><span data-stu-id="36601-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36601-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="36601-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="36601-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="36601-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="36601-111">エントリを投稿したサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="36601-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36601-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="36601-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="36601-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="36601-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="36601-114">ポスティングサーバーが接続されているピアの ID です。</span><span class="sxs-lookup"><span data-stu-id="36601-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="36601-115">機能</span><span class="sxs-lookup"><span data-stu-id="36601-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36601-116">列</span><span class="sxs-lookup"><span data-stu-id="36601-116">Column</span></span></th>
<th><span data-ttu-id="36601-117">説明</span><span class="sxs-lookup"><span data-stu-id="36601-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36601-118">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="36601-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="36601-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="36601-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36601-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="36601-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="36601-121">TblServerIdentity テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="36601-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36601-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="36601-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="36601-123">TblServerIdentity テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="36601-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

