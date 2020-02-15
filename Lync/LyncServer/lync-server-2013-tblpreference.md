---
title: 'Lync Server 2013: tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3976cb18336477c00a901116a125149b8c67ddeb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="1450f-102">Lync Server 2013 の tblPreference</span><span class="sxs-lookup"><span data-stu-id="1450f-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1450f-103">_**トピックの最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="1450f-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="1450f-104">tblPreference には、ユーザーのクライアントの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1450f-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="1450f-105">これは通常、Lync 2013 より前のクライアントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="1450f-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="1450f-106">Columns</span><span class="sxs-lookup"><span data-stu-id="1450f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1450f-107">列</span><span class="sxs-lookup"><span data-stu-id="1450f-107">Column</span></span></th>
<th><span data-ttu-id="1450f-108">種類</span><span class="sxs-lookup"><span data-stu-id="1450f-108">Type</span></span></th>
<th><span data-ttu-id="1450f-109">説明</span><span class="sxs-lookup"><span data-stu-id="1450f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1450f-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="1450f-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="1450f-111">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="1450f-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="1450f-112">「User sip uri &lt;&gt;| username」などの形式のラベル。&lt;設定&gt;。</span><span class="sxs-lookup"><span data-stu-id="1450f-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1450f-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="1450f-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="1450f-114">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="1450f-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1450f-115">バージョン管理のための連続した番号 (ラベルごと)。</span><span class="sxs-lookup"><span data-stu-id="1450f-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1450f-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="1450f-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="1450f-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="1450f-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="1450f-118">エンコードされたコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="1450f-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1450f-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="1450f-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="1450f-120">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="1450f-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1450f-121">プリファレンスを更新したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="1450f-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="1450f-122">キー</span><span class="sxs-lookup"><span data-stu-id="1450f-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1450f-123">列</span><span class="sxs-lookup"><span data-stu-id="1450f-123">Column</span></span></th>
<th><span data-ttu-id="1450f-124">説明</span><span class="sxs-lookup"><span data-stu-id="1450f-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1450f-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="1450f-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="1450f-126">主キー。</span><span class="sxs-lookup"><span data-stu-id="1450f-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

