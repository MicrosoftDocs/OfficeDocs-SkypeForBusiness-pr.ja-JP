---
title: 'Lync Server 2013: SIPResponseMetaData テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bbfec0e3d1dae6d4799fbb109e081a8f7a1a299
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="8279c-102">Lync Server 2013 の SIPResponseMetaData テーブル</span><span class="sxs-lookup"><span data-stu-id="8279c-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8279c-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8279c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8279c-p101">SIPResponseMetaDataTable には、SIP 応答コードと、各コードの分類と定義の一覧が含まれます。これらのコードは SIP デバイスおよび SIP 通信セッションに影響を与えるイベントへの応答して生成されます。たとえば、応答コード 403 は、SIP デバイスが要求を行い、サーバーがその要求の実行を拒否したときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="8279c-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="8279c-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8279c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8279c-107">列</span><span class="sxs-lookup"><span data-stu-id="8279c-107">Column</span></span></th>
<th><span data-ttu-id="8279c-108">データ型</span><span class="sxs-lookup"><span data-stu-id="8279c-108">Data Type</span></span></th>
<th><span data-ttu-id="8279c-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="8279c-109">Key/Index</span></span></th>
<th><span data-ttu-id="8279c-110">詳細</span><span class="sxs-lookup"><span data-stu-id="8279c-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8279c-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="8279c-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="8279c-112">int</span><span class="sxs-lookup"><span data-stu-id="8279c-112">int</span></span></p></td>
<td><p><span data-ttu-id="8279c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8279c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="8279c-114">SIP 応答コードを表す数値。</span><span class="sxs-lookup"><span data-stu-id="8279c-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8279c-115"><strong>クラス</strong></span><span class="sxs-lookup"><span data-stu-id="8279c-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="8279c-116">int</span><span class="sxs-lookup"><span data-stu-id="8279c-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8279c-p102">応答コードの一般的な分類。以下の分類があります。</span><span class="sxs-lookup"><span data-stu-id="8279c-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="8279c-119">1 – 情報応答</span><span class="sxs-lookup"><span data-stu-id="8279c-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="8279c-120">2 – 正常応答</span><span class="sxs-lookup"><span data-stu-id="8279c-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="8279c-121">3 – リダイレクト応答</span><span class="sxs-lookup"><span data-stu-id="8279c-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="8279c-122">4 – クライアント エラー応答</span><span class="sxs-lookup"><span data-stu-id="8279c-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="8279c-123">5--サーバーエラー応答</span><span class="sxs-lookup"><span data-stu-id="8279c-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="8279c-124">6 – グローバル エラー応答</span><span class="sxs-lookup"><span data-stu-id="8279c-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8279c-125"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="8279c-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="8279c-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8279c-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8279c-p103">SIP 応答コードの説明。たとえば、コード 181 には以下の説明があります。</span><span class="sxs-lookup"><span data-stu-id="8279c-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="8279c-129">Call Is Being Forwarded (呼び出しを転送中)</span><span class="sxs-lookup"><span data-stu-id="8279c-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

