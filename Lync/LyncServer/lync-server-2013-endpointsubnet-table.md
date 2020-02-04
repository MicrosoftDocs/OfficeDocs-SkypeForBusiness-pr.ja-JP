---
title: 'Lync Server 2013: EndpointSubnet テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: EndpointSubnet table
ms:assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398933(v=OCS.15)
ms:contentKeyID: 48185514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055aa9460fb63e96d20472d6102c249ecf71a78b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpointsubnet-table-in-lync-server-2013"></a><span data-ttu-id="ca75d-102">Lync Server 2013 の EndpointSubnet テーブル</span><span class="sxs-lookup"><span data-stu-id="ca75d-102">EndpointSubnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca75d-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ca75d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ca75d-104">EndpointSubnet テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ca75d-104">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="ca75d-105">各レコードは、エンドポイントから取得された1つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="ca75d-105">Each record represents one subnet captured from endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca75d-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="ca75d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ca75d-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="ca75d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ca75d-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="ca75d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ca75d-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="ca75d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca75d-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="ca75d-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="ca75d-111">int</span><span class="sxs-lookup"><span data-stu-id="ca75d-111">int</span></span></p></td>
<td><p><span data-ttu-id="ca75d-112">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="ca75d-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca75d-113">サブネットの整数表現。</span><span class="sxs-lookup"><span data-stu-id="ca75d-113">Integer representation for the subnet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca75d-114"><strong>Nextupdatupdat</strong></span><span class="sxs-lookup"><span data-stu-id="ca75d-114"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ca75d-115">datetime</span><span class="sxs-lookup"><span data-stu-id="ca75d-115">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ca75d-116">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ca75d-116">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

