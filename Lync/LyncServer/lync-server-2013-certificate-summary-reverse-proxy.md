---
title: 'Lync Server 2013: 証明書の概要-リバースプロキシ'
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
ms.openlocfilehash: 460d36723cd084ad4593318cdd04f5e05b90d08a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="70fa7-102">証明書の概要-Lync Server 2013 のリバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="70fa7-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70fa7-103">_**トピックの最終更新日:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="70fa7-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="70fa7-104">リバースプロキシの証明書要件は、エッジサーバーよりもはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="70fa7-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="70fa7-105">提供されているフローチャートは必要な要件を示します。</span><span class="sxs-lookup"><span data-stu-id="70fa7-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="70fa7-106">付属の表では、エッジサーバーのディスカッションで確認されたシナリオに関して、一般的な証明書のサブジェクト名とサブジェクトの別名を示しています。</span><span class="sxs-lookup"><span data-stu-id="70fa7-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="70fa7-107">エッジサーバーのシナリオの詳細については、「 [Lync server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70fa7-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="70fa7-108">**リバース プロキシの証明書のフロー チャート**</span><span class="sxs-lookup"><span data-stu-id="70fa7-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="70fa7-109">![エッジ サーバーの証明書のフロー チャート](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "エッジ サーバーの証明書のフロー チャート")</span><span class="sxs-lookup"><span data-stu-id="70fa7-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="70fa7-110">リバース プロキシ: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70fa7-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70fa7-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="70fa7-111">Component</span></span></th>
<th><span data-ttu-id="70fa7-112">サブジェクト名</span><span class="sxs-lookup"><span data-stu-id="70fa7-112">Subject name</span></span></th>
<th><span data-ttu-id="70fa7-113">サブジェクトの別名 (SAN)/順序</span><span class="sxs-lookup"><span data-stu-id="70fa7-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="70fa7-114">コメント</span><span class="sxs-lookup"><span data-stu-id="70fa7-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70fa7-115">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="70fa7-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="70fa7-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70fa7-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70fa7-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70fa7-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="70fa7-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70fa7-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="70fa7-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70fa7-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="70fa7-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70fa7-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="70fa7-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70fa7-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="70fa7-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70fa7-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="70fa7-123">(省略可能):\* contoso.com</span><span class="sxs-lookup"><span data-stu-id="70fa7-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70fa7-124">証明書は公的 CA によって発行され、サーバー EKU を含んでいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="70fa7-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="70fa7-125">サービスには、アドレス帳サービス、会議用の Office Web Apps、および Lync IP デバイス公開ルールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="70fa7-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="70fa7-126">サブジェクトの別名には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="70fa7-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="70fa7-127">フロントエンドサーバーまたはフロントエンドプールの外部 Web サービス FQDN</span><span class="sxs-lookup"><span data-stu-id="70fa7-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="70fa7-128">ディレクターまたはディレクタープール用の外部 Web サービス FQDN</span><span class="sxs-lookup"><span data-stu-id="70fa7-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="70fa7-129">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="70fa7-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="70fa7-130">オンライン会議の公開ルール</span><span class="sxs-lookup"><span data-stu-id="70fa7-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="70fa7-131">会議用の Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="70fa7-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="70fa7-132">Lyncdiscover (自動検出)</span><span class="sxs-lookup"><span data-stu-id="70fa7-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="70fa7-133">オプションのワイルドカードは meet と dialin SAN の両方を置き換えます</span><span class="sxs-lookup"><span data-stu-id="70fa7-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

