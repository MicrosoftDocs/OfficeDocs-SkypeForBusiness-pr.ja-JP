---
title: 'Lync Server 2013: 証明書の概要-リバースプロキシ'
description: 'Lync Server 2013: 証明書の概要-リバースプロキシ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc250d6de2eb1a0b6c3ad3495c8df62942f9a81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572303"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="0b1fe-103">証明書の概要-Lync Server 2013 のリバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="0b1fe-103">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b1fe-104">_**トピックの最終更新日:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="0b1fe-104">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="0b1fe-105">リバースプロキシの証明書要件は、エッジサーバーよりもはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="0b1fe-105">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="0b1fe-106">提供されているフローチャートは必要な要件を示します。</span><span class="sxs-lookup"><span data-stu-id="0b1fe-106">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="0b1fe-107">付属の表では、エッジサーバーのディスカッションで確認されたシナリオに関して、一般的な証明書のサブジェクト名とサブジェクトの別名を示しています。</span><span class="sxs-lookup"><span data-stu-id="0b1fe-107">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="0b1fe-108">エッジサーバーのシナリオの詳細については、「 [Lync server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b1fe-108">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="0b1fe-109">**リバース プロキシの証明書のフロー チャート**</span><span class="sxs-lookup"><span data-stu-id="0b1fe-109">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="0b1fe-110">![エッジ サーバーの証明書のフロー チャート](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "エッジ サーバーの証明書のフロー チャート")</span><span class="sxs-lookup"><span data-stu-id="0b1fe-110">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="0b1fe-111">リバース プロキシ: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0b1fe-111">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b1fe-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0b1fe-112">Component</span></span></th>
<th><span data-ttu-id="0b1fe-113">サブジェクト名</span><span class="sxs-lookup"><span data-stu-id="0b1fe-113">Subject name</span></span></th>
<th><span data-ttu-id="0b1fe-114">サブジェクトの別名 (SAN)/順序</span><span class="sxs-lookup"><span data-stu-id="0b1fe-114">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="0b1fe-115">Comments</span><span class="sxs-lookup"><span data-stu-id="0b1fe-115">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b1fe-116">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="0b1fe-116">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="0b1fe-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b1fe-117">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0b1fe-118">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b1fe-118">webext.contoso.com</span></span></p>
<p><span data-ttu-id="0b1fe-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b1fe-119">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="0b1fe-120">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b1fe-120">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="0b1fe-121">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b1fe-121">meet.contoso.com</span></span></p>
<p><span data-ttu-id="0b1fe-122">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b1fe-122">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="0b1fe-123">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b1fe-123">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="0b1fe-124">(省略可能):\* contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b1fe-124">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0b1fe-125">証明書は公的 CA によって発行され、サーバー EKU を含んでいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b1fe-125">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="0b1fe-126">サービスには、アドレス帳サービス、会議用の Office Web Apps、および Lync IP デバイス公開ルールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b1fe-126">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="0b1fe-127">サブジェクトの別名には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="0b1fe-127">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="0b1fe-128">フロントエンドサーバーまたはフロントエンドプールの外部 Web サービス FQDN</span><span class="sxs-lookup"><span data-stu-id="0b1fe-128">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="0b1fe-129">ディレクターまたはディレクタープール用の外部 Web サービス FQDN</span><span class="sxs-lookup"><span data-stu-id="0b1fe-129">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="0b1fe-130">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="0b1fe-130">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="0b1fe-131">オンライン会議の公開ルール</span><span class="sxs-lookup"><span data-stu-id="0b1fe-131">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="0b1fe-132">会議用の Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="0b1fe-132">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="0b1fe-133">Lyncdiscover (自動検出)</span><span class="sxs-lookup"><span data-stu-id="0b1fe-133">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="0b1fe-134">オプションのワイルドカードは meet と dialin SAN の両方を置き換えます</span><span class="sxs-lookup"><span data-stu-id="0b1fe-134">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

