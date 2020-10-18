---
title: 'Lync Server 2013: tblADCookie'
description: 'Lync Server 2013: tblADCookie。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c3dde3730ede07b204a473c7fe0a5ab68054d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573723"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="60a55-103">Lync Server 2013 の tblADCookie</span><span class="sxs-lookup"><span data-stu-id="60a55-103">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60a55-104">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="60a55-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="60a55-105">tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。</span><span class="sxs-lookup"><span data-stu-id="60a55-105">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="60a55-106">段組み</span><span class="sxs-lookup"><span data-stu-id="60a55-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60a55-107">Column</span><span class="sxs-lookup"><span data-stu-id="60a55-107">Column</span></span></th>
<th><span data-ttu-id="60a55-108">種類</span><span class="sxs-lookup"><span data-stu-id="60a55-108">Type</span></span></th>
<th><span data-ttu-id="60a55-109">説明</span><span class="sxs-lookup"><span data-stu-id="60a55-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60a55-110">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="60a55-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="60a55-111">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="60a55-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="60a55-112">監視対象のドメインのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="60a55-112">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a55-113">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="60a55-113">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="60a55-114">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="60a55-114">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="60a55-115">Active Directory ドメインサービスの同期に使用される現在のドメインコントローラーの完全修飾ドメイン名 (FQDN)。情報の値があります。</span><span class="sxs-lookup"><span data-stu-id="60a55-115">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a55-116">adcContent</span><span class="sxs-lookup"><span data-stu-id="60a55-116">adcContent</span></span></p></td>
<td><p><span data-ttu-id="60a55-117">image (バイナリ)</span><span class="sxs-lookup"><span data-stu-id="60a55-117">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="60a55-118">Active Directory の同期 Cookie。</span><span class="sxs-lookup"><span data-stu-id="60a55-118">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a55-119">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="60a55-119">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="60a55-120">日付型</span><span class="sxs-lookup"><span data-stu-id="60a55-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="60a55-121">行更新時刻でのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="60a55-121">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a55-122">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="60a55-122">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="60a55-123">日付型</span><span class="sxs-lookup"><span data-stu-id="60a55-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="60a55-p101">行が変更のためにロックされるまでの時間。これは、一度に 1 つのチャット サービスのみが Active Directory 同期を行うことを保証するソフトウェア インタロック メカニズムの一部です。</span><span class="sxs-lookup"><span data-stu-id="60a55-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="60a55-126">Keys</span><span class="sxs-lookup"><span data-stu-id="60a55-126">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60a55-127">列 (複数可)</span><span class="sxs-lookup"><span data-stu-id="60a55-127">Column(s)</span></span></th>
<th><span data-ttu-id="60a55-128">説明</span><span class="sxs-lookup"><span data-stu-id="60a55-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60a55-129">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="60a55-129">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="60a55-130">主キー。</span><span class="sxs-lookup"><span data-stu-id="60a55-130">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a55-131">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="60a55-131">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="60a55-132">Principal.prinGuid テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="60a55-132">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

