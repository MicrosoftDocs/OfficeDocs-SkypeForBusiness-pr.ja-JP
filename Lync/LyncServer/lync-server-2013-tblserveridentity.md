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
ms.openlocfilehash: 2379622ee5b1121367c35b4baac98d6c79d61023
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="0e780-102">Lync Server 2013 の tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="0e780-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e780-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0e780-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0e780-104">tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e780-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="0e780-105">行</span><span class="sxs-lookup"><span data-stu-id="0e780-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e780-106">列</span><span class="sxs-lookup"><span data-stu-id="0e780-106">Column</span></span></th>
<th><span data-ttu-id="0e780-107">型</span><span class="sxs-lookup"><span data-stu-id="0e780-107">Type</span></span></th>
<th><span data-ttu-id="0e780-108">説明</span><span class="sxs-lookup"><span data-stu-id="0e780-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e780-109">serverID</span><span class="sxs-lookup"><span data-stu-id="0e780-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="0e780-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="0e780-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0e780-111">サーバー ID。</span><span class="sxs-lookup"><span data-stu-id="0e780-111">Server ID.</span></span> <span data-ttu-id="0e780-112">中央管理ストアのインスタンス ID に対応しています。</span><span class="sxs-lookup"><span data-stu-id="0e780-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e780-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="0e780-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="0e780-114">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="0e780-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0e780-115">Windows Communication Foundation アドレスを使用したサーバーアドレス。</span><span class="sxs-lookup"><span data-stu-id="0e780-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e780-116">Serverlastping 時間</span><span class="sxs-lookup"><span data-stu-id="0e780-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="0e780-117">datetime</span><span class="sxs-lookup"><span data-stu-id="0e780-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e780-118">チャネルサーバーがこの行を更新して、実行中の証拠を与える最新の時刻。</span><span class="sxs-lookup"><span data-stu-id="0e780-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0e780-119">キー</span><span class="sxs-lookup"><span data-stu-id="0e780-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e780-120">列</span><span class="sxs-lookup"><span data-stu-id="0e780-120">Column</span></span></th>
<th><span data-ttu-id="0e780-121">説明</span><span class="sxs-lookup"><span data-stu-id="0e780-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e780-122">serverID</span><span class="sxs-lookup"><span data-stu-id="0e780-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="0e780-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="0e780-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

