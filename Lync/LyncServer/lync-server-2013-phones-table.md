---
title: 'Lync Server 2013: Phones テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920454a5db71c1e6f3cd2ea2ae1134d149b4f297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="cbf14-102">Lync Server 2013 の Phones テーブル</span><span class="sxs-lookup"><span data-stu-id="cbf14-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbf14-103">_**最終更新日:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="cbf14-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="cbf14-104">電話の表はサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="cbf14-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="cbf14-105">テーブル内の各レコードには、データベース内にレコードがある VoIP 通話に関連する1つの電話番号に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="cbf14-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbf14-106">列</span><span class="sxs-lookup"><span data-stu-id="cbf14-106">Column</span></span></th>
<th><span data-ttu-id="cbf14-107">データ型</span><span class="sxs-lookup"><span data-stu-id="cbf14-107">Data Type</span></span></th>
<th><span data-ttu-id="cbf14-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="cbf14-108">Key/Index</span></span></th>
<th><span data-ttu-id="cbf14-109">詳細</span><span class="sxs-lookup"><span data-stu-id="cbf14-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbf14-110"><strong>PhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="cbf14-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="cbf14-111">int</span><span class="sxs-lookup"><span data-stu-id="cbf14-111">int</span></span></p></td>
<td><p><span data-ttu-id="cbf14-112">Primary</span><span class="sxs-lookup"><span data-stu-id="cbf14-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="cbf14-113">この電話を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="cbf14-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbf14-114"><strong>電話の Uri</strong></span><span class="sxs-lookup"><span data-stu-id="cbf14-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cbf14-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cbf14-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cbf14-116">電話番号。</span><span class="sxs-lookup"><span data-stu-id="cbf14-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbf14-117"><strong>Nextupdatupdat</strong></span><span class="sxs-lookup"><span data-stu-id="cbf14-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="cbf14-118">dateTime</span><span class="sxs-lookup"><span data-stu-id="cbf14-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbf14-119">タイムスタンプ (内部使用のみ)。</span><span class="sxs-lookup"><span data-stu-id="cbf14-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="cbf14-120">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cbf14-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

