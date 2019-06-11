---
title: 'Lync Server 2013: SIPResponseMetaData テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31df563172cce2e6ac9780511665ef563532a7d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="3b0cf-102">Lync Server 2013 の SIPResponseMetaData テーブル</span><span class="sxs-lookup"><span data-stu-id="3b0cf-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b0cf-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3b0cf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3b0cf-104">SIPResponseMetaDataTable には、SIP 応答コードの一覧と、各コードの分類と定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3b0cf-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="3b0cf-105">これらのコードは、SIP デバイスと SIP コミュニケーションセッションに影響を与えるイベントに対応して生成されます。たとえば、応答コード403は、SIP デバイスが要求を行ったときに、サーバーがその要求を受け入れることを拒否したときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="3b0cf-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="3b0cf-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3b0cf-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b0cf-107">列</span><span class="sxs-lookup"><span data-stu-id="3b0cf-107">Column</span></span></th>
<th><span data-ttu-id="3b0cf-108">データ型</span><span class="sxs-lookup"><span data-stu-id="3b0cf-108">Data Type</span></span></th>
<th><span data-ttu-id="3b0cf-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="3b0cf-109">Key/Index</span></span></th>
<th><span data-ttu-id="3b0cf-110">詳細</span><span class="sxs-lookup"><span data-stu-id="3b0cf-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b0cf-111"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="3b0cf-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3b0cf-112">int</span><span class="sxs-lookup"><span data-stu-id="3b0cf-112">int</span></span></p></td>
<td><p><span data-ttu-id="3b0cf-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3b0cf-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3b0cf-114">SIP 応答コードを表す数値。</span><span class="sxs-lookup"><span data-stu-id="3b0cf-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b0cf-115"><strong>クラス</strong></span><span class="sxs-lookup"><span data-stu-id="3b0cf-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="3b0cf-116">int</span><span class="sxs-lookup"><span data-stu-id="3b0cf-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b0cf-117">応答コードの一般的な分類。</span><span class="sxs-lookup"><span data-stu-id="3b0cf-117">General classification for the response code.</span></span> <span data-ttu-id="3b0cf-118">分類には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b0cf-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3b0cf-119">1–情報の返信</span><span class="sxs-lookup"><span data-stu-id="3b0cf-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="3b0cf-120">2–成功応答</span><span class="sxs-lookup"><span data-stu-id="3b0cf-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="3b0cf-121">3–リダイレクション応答</span><span class="sxs-lookup"><span data-stu-id="3b0cf-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="3b0cf-122">4–クライアントエラー応答</span><span class="sxs-lookup"><span data-stu-id="3b0cf-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="3b0cf-123">5--サーバー障害への応答</span><span class="sxs-lookup"><span data-stu-id="3b0cf-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="3b0cf-124">6–グローバルエラー応答</span><span class="sxs-lookup"><span data-stu-id="3b0cf-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b0cf-125"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="3b0cf-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="3b0cf-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3b0cf-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b0cf-127">SIP 応答コードの説明。</span><span class="sxs-lookup"><span data-stu-id="3b0cf-127">Description of the SIP response code.</span></span> <span data-ttu-id="3b0cf-128">たとえば、応答コード181には次の説明があります。</span><span class="sxs-lookup"><span data-stu-id="3b0cf-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="3b0cf-129">通話が転送されています</span><span class="sxs-lookup"><span data-stu-id="3b0cf-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

