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
ms.openlocfilehash: 8b1b5096c087661bf5afadd2668d6d1bb7ac8330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="e035a-102">Lync Server 2013 の tblADCookie</span><span class="sxs-lookup"><span data-stu-id="e035a-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e035a-103">_**最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="e035a-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="e035a-104">tblADCookie には、現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e035a-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="e035a-105">行</span><span class="sxs-lookup"><span data-stu-id="e035a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e035a-106">列</span><span class="sxs-lookup"><span data-stu-id="e035a-106">Column</span></span></th>
<th><span data-ttu-id="e035a-107">型</span><span class="sxs-lookup"><span data-stu-id="e035a-107">Type</span></span></th>
<th><span data-ttu-id="e035a-108">説明</span><span class="sxs-lookup"><span data-stu-id="e035a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e035a-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e035a-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="e035a-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="e035a-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="e035a-111">監視されているドメインのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="e035a-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e035a-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="e035a-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="e035a-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="e035a-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="e035a-114">Active Directory ドメインサービスの同期に使用される、現在のドメインコントローラーの完全修飾ドメイン名 (FQDN) です。情報があります。</span><span class="sxs-lookup"><span data-stu-id="e035a-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e035a-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="e035a-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="e035a-116">image (バイナリ)</span><span class="sxs-lookup"><span data-stu-id="e035a-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="e035a-117">Active Directory 同期 cookie。</span><span class="sxs-lookup"><span data-stu-id="e035a-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e035a-118">最終更新日</span><span class="sxs-lookup"><span data-stu-id="e035a-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="e035a-119">datetime</span><span class="sxs-lookup"><span data-stu-id="e035a-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="e035a-120">行の更新時刻を含むタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="e035a-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e035a-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="e035a-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="e035a-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e035a-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e035a-123">変更のために行がロックされるまでの時間です。</span><span class="sxs-lookup"><span data-stu-id="e035a-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="e035a-124">これは、チャットサービスの1つだけが同時に Active Directory の同期を行うことができるようにするソフトウェアの連結メカニズムの一部です。</span><span class="sxs-lookup"><span data-stu-id="e035a-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e035a-125">機能</span><span class="sxs-lookup"><span data-stu-id="e035a-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e035a-126">列</span><span class="sxs-lookup"><span data-stu-id="e035a-126">Column(s)</span></span></th>
<th><span data-ttu-id="e035a-127">説明</span><span class="sxs-lookup"><span data-stu-id="e035a-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e035a-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e035a-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="e035a-129">主キー。</span><span class="sxs-lookup"><span data-stu-id="e035a-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e035a-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e035a-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="e035a-131">プリンシパルで参照される外部キー (prinGuid テーブル)。</span><span class="sxs-lookup"><span data-stu-id="e035a-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

