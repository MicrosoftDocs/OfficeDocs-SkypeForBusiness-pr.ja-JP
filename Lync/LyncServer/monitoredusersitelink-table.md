---
title: MonitoredUserSiteLink テーブル
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: MonitoredUserSiteLink table
ms:assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398233(v=OCS.15)
ms:contentKeyID: 48183508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7996b4c06496a39bc7db5f4cd5b4adbb83c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoredusersitelink-table"></a><span data-ttu-id="d455e-102">MonitoredUserSiteLink テーブル</span><span class="sxs-lookup"><span data-stu-id="d455e-102">MonitoredUserSiteLink table</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d455e-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d455e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d455e-104">MonitoredUserSiteLink リンクテーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="d455e-104">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="d455e-105">各レコードは、2つのユーザーサイト間のリンク1つを表します。</span><span class="sxs-lookup"><span data-stu-id="d455e-105">Each record represents one link between two user sites.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d455e-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="d455e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d455e-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="d455e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d455e-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="d455e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d455e-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="d455e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d455e-110"><strong>UserSite1Key</strong></span><span class="sxs-lookup"><span data-stu-id="d455e-110"><strong>UserSite1Key</strong></span></span></p></td>
<td><p><span data-ttu-id="d455e-111">int</span><span class="sxs-lookup"><span data-stu-id="d455e-111">int</span></span></p></td>
<td><p><span data-ttu-id="d455e-112">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="d455e-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d455e-113"><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の Usersite テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="d455e-113">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d455e-114"><strong>UserSite2Key</strong></span><span class="sxs-lookup"><span data-stu-id="d455e-114"><strong>UserSite2Key</strong></span></span></p></td>
<td><p><span data-ttu-id="d455e-115">int</span><span class="sxs-lookup"><span data-stu-id="d455e-115">int</span></span></p></td>
<td><p><span data-ttu-id="d455e-116">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="d455e-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d455e-117"><a href="lync-server-2013-usersite-table.md">Lync Server 2013 で Usersite テーブル</a>から参照します。</span><span class="sxs-lookup"><span data-stu-id="d455e-117">Reference from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

