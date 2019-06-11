---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="74270-102">Lync Server 2013 の tblADCookie</span><span class="sxs-lookup"><span data-stu-id="74270-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74270-103">_**最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="74270-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="74270-104">tblADCookie には、現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれています。</span><span class="sxs-lookup"><span data-stu-id="74270-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="74270-105">行</span><span class="sxs-lookup"><span data-stu-id="74270-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74270-106">列</span><span class="sxs-lookup"><span data-stu-id="74270-106">Column</span></span></th>
<th><span data-ttu-id="74270-107">型</span><span class="sxs-lookup"><span data-stu-id="74270-107">Type</span></span></th>
<th><span data-ttu-id="74270-108">説明</span><span class="sxs-lookup"><span data-stu-id="74270-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74270-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="74270-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="74270-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="74270-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="74270-111">監視されているドメインのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="74270-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74270-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="74270-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="74270-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="74270-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="74270-114">Active Directory ドメインサービスの同期に使用される、現在のドメインコントローラーの完全修飾ドメイン名 (FQDN) です。情報があります。</span><span class="sxs-lookup"><span data-stu-id="74270-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74270-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="74270-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="74270-116">image (バイナリ)</span><span class="sxs-lookup"><span data-stu-id="74270-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="74270-117">Active Directory 同期 cookie。</span><span class="sxs-lookup"><span data-stu-id="74270-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74270-118">最終更新日</span><span class="sxs-lookup"><span data-stu-id="74270-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="74270-119">datetime</span><span class="sxs-lookup"><span data-stu-id="74270-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="74270-120">行の更新時刻を含むタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="74270-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74270-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="74270-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="74270-122">datetime</span><span class="sxs-lookup"><span data-stu-id="74270-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="74270-123">変更のために行がロックされるまでの時間です。</span><span class="sxs-lookup"><span data-stu-id="74270-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="74270-124">これは、チャットサービスの1つだけが同時に Active Directory の同期を行うことができるようにするソフトウェアの連結メカニズムの一部です。</span><span class="sxs-lookup"><span data-stu-id="74270-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="74270-125">機能</span><span class="sxs-lookup"><span data-stu-id="74270-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74270-126">列</span><span class="sxs-lookup"><span data-stu-id="74270-126">Column(s)</span></span></th>
<th><span data-ttu-id="74270-127">説明</span><span class="sxs-lookup"><span data-stu-id="74270-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74270-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="74270-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="74270-129">主キー。</span><span class="sxs-lookup"><span data-stu-id="74270-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74270-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="74270-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="74270-131">プリンシパルで参照される外部キー (prinGuid テーブル)。</span><span class="sxs-lookup"><span data-stu-id="74270-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

