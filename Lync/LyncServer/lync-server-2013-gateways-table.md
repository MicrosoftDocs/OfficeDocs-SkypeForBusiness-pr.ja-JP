---
title: 'Lync Server 2013: ゲートウェイテーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b43adbf088e696b38ff8159e87e2b5b4e8608d38
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512664"
---
# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="3aec4-102">Lync Server 2013 のゲートウェイテーブル</span><span class="sxs-lookup"><span data-stu-id="3aec4-102">Gateways table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3aec4-103">_**トピックの最終更新日:** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="3aec4-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="3aec4-104">ゲートウェイテーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="3aec4-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="3aec4-105">各レコードには、データベースにレコードを含む公衆交換電話網 (PSTN) 呼び出しに関係する1つのゲートウェイに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="3aec4-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3aec4-106">Column</span><span class="sxs-lookup"><span data-stu-id="3aec4-106">Column</span></span></th>
<th><span data-ttu-id="3aec4-107">データ型</span><span class="sxs-lookup"><span data-stu-id="3aec4-107">Data Type</span></span></th>
<th><span data-ttu-id="3aec4-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="3aec4-108">Key/Index</span></span></th>
<th><span data-ttu-id="3aec4-109">詳細</span><span class="sxs-lookup"><span data-stu-id="3aec4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3aec4-110"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="3aec4-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aec4-111">int</span><span class="sxs-lookup"><span data-stu-id="3aec4-111">int</span></span></p></td>
<td><p><span data-ttu-id="3aec4-112">Primary</span><span class="sxs-lookup"><span data-stu-id="3aec4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3aec4-113">このゲートウェイを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="3aec4-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aec4-114"><strong>ゲートウェイ</strong></span><span class="sxs-lookup"><span data-stu-id="3aec4-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="3aec4-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aec4-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3aec4-116">ゲートウェイ名。</span><span class="sxs-lookup"><span data-stu-id="3aec4-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

