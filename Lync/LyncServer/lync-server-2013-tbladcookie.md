---
title: 'Lync Server 2013: tblADCookie'
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
ms.openlocfilehash: bf372f3dfc39f3ca90cbe0019af09e8d9dd33d26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509514"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="ed124-102">Lync Server 2013 の tblADCookie</span><span class="sxs-lookup"><span data-stu-id="ed124-102">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed124-103">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="ed124-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="ed124-104">tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。</span><span class="sxs-lookup"><span data-stu-id="ed124-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="ed124-105">段組み</span><span class="sxs-lookup"><span data-stu-id="ed124-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed124-106">Column</span><span class="sxs-lookup"><span data-stu-id="ed124-106">Column</span></span></th>
<th><span data-ttu-id="ed124-107">種類</span><span class="sxs-lookup"><span data-stu-id="ed124-107">Type</span></span></th>
<th><span data-ttu-id="ed124-108">説明</span><span class="sxs-lookup"><span data-stu-id="ed124-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed124-109">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="ed124-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="ed124-110">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="ed124-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="ed124-111">監視対象のドメインのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="ed124-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed124-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="ed124-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="ed124-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="ed124-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="ed124-114">Active Directory ドメインサービスの同期に使用される現在のドメインコントローラーの完全修飾ドメイン名 (FQDN)。情報の値があります。</span><span class="sxs-lookup"><span data-stu-id="ed124-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed124-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="ed124-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="ed124-116">image (バイナリ)</span><span class="sxs-lookup"><span data-stu-id="ed124-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="ed124-117">Active Directory の同期 Cookie。</span><span class="sxs-lookup"><span data-stu-id="ed124-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed124-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="ed124-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="ed124-119">日付型</span><span class="sxs-lookup"><span data-stu-id="ed124-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="ed124-120">行更新時刻でのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="ed124-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed124-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="ed124-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="ed124-122">日付型</span><span class="sxs-lookup"><span data-stu-id="ed124-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="ed124-p101">行が変更のためにロックされるまでの時間。これは、一度に 1 つのチャット サービスのみが Active Directory 同期を行うことを保証するソフトウェア インタロック メカニズムの一部です。</span><span class="sxs-lookup"><span data-stu-id="ed124-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ed124-125">Keys</span><span class="sxs-lookup"><span data-stu-id="ed124-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed124-126">列 (複数可)</span><span class="sxs-lookup"><span data-stu-id="ed124-126">Column(s)</span></span></th>
<th><span data-ttu-id="ed124-127">説明</span><span class="sxs-lookup"><span data-stu-id="ed124-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed124-128">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="ed124-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="ed124-129">主キー。</span><span class="sxs-lookup"><span data-stu-id="ed124-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed124-130">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="ed124-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="ed124-131">Principal.prinGuid テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="ed124-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

