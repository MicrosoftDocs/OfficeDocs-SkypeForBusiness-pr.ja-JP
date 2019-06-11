---
title: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7bdd939f838a9f72191d3aae27b9a4a56d26be3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="ef980-102">Lync Server 2013 の tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="ef980-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef980-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ef980-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ef980-104">tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef980-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="ef980-105">行</span><span class="sxs-lookup"><span data-stu-id="ef980-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef980-106">列</span><span class="sxs-lookup"><span data-stu-id="ef980-106">Column</span></span></th>
<th><span data-ttu-id="ef980-107">型</span><span class="sxs-lookup"><span data-stu-id="ef980-107">Type</span></span></th>
<th><span data-ttu-id="ef980-108">説明</span><span class="sxs-lookup"><span data-stu-id="ef980-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef980-109">serverID</span><span class="sxs-lookup"><span data-stu-id="ef980-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="ef980-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="ef980-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ef980-111">サーバー ID。</span><span class="sxs-lookup"><span data-stu-id="ef980-111">Server ID.</span></span> <span data-ttu-id="ef980-112">中央管理ストアのインスタンス ID に対応しています。</span><span class="sxs-lookup"><span data-stu-id="ef980-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef980-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="ef980-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="ef980-114">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="ef980-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ef980-115">Windows Communication Foundation アドレスを使用したサーバーアドレス。</span><span class="sxs-lookup"><span data-stu-id="ef980-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef980-116">Serverlastping 時間</span><span class="sxs-lookup"><span data-stu-id="ef980-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="ef980-117">datetime</span><span class="sxs-lookup"><span data-stu-id="ef980-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="ef980-118">チャネルサーバーがこの行を更新して、実行中の証拠を与える最新の時刻。</span><span class="sxs-lookup"><span data-stu-id="ef980-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="ef980-119">キー</span><span class="sxs-lookup"><span data-stu-id="ef980-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef980-120">列</span><span class="sxs-lookup"><span data-stu-id="ef980-120">Column</span></span></th>
<th><span data-ttu-id="ef980-121">説明</span><span class="sxs-lookup"><span data-stu-id="ef980-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef980-122">serverID</span><span class="sxs-lookup"><span data-stu-id="ef980-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="ef980-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="ef980-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

