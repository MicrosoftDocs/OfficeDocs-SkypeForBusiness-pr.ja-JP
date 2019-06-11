---
title: 'Lync Server 2013: 証明書の概要 - リバース プロキシ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a10259ac4a0beb6d79897b26bf446b109801a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="b8e3d-102">証明書の概要 - Lync Server 2013 リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="b8e3d-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8e3d-103">_**最終更新日:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="b8e3d-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="b8e3d-104">リバースプロキシの証明書の要件は、エッジサーバーよりもずっと簡単です。</span><span class="sxs-lookup"><span data-stu-id="b8e3d-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="b8e3d-105">提供されたフローチャートは、必要な要件を示します。</span><span class="sxs-lookup"><span data-stu-id="b8e3d-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="b8e3d-106">この表に示すのは、microsoft が Edge Server のディスカッションでレビューしたシナリオに関連する、一般的な証明書のサブジェクト名とサブジェクトの別名を示しています。</span><span class="sxs-lookup"><span data-stu-id="b8e3d-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="b8e3d-107">エッジサーバーのシナリオについて詳しくは、「 [Lync server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8e3d-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="b8e3d-108">**リバースプロキシ用の証明書フローチャート**</span><span class="sxs-lookup"><span data-stu-id="b8e3d-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="b8e3d-109">![エッジサーバーの証明書フローチャート](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "エッジサーバーの証明書フローチャート")</span><span class="sxs-lookup"><span data-stu-id="b8e3d-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="b8e3d-110">リバースプロキシ: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8e3d-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8e3d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b8e3d-111">Component</span></span></th>
<th><span data-ttu-id="b8e3d-112">サブジェクト名</span><span class="sxs-lookup"><span data-stu-id="b8e3d-112">Subject name</span></span></th>
<th><span data-ttu-id="b8e3d-113">サブジェクト代替名 (SAN) の/Order</span><span class="sxs-lookup"><span data-stu-id="b8e3d-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="b8e3d-114">コメント</span><span class="sxs-lookup"><span data-stu-id="b8e3d-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8e3d-115">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="b8e3d-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="b8e3d-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8e3d-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8e3d-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8e3d-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="b8e3d-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8e3d-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="b8e3d-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8e3d-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="b8e3d-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8e3d-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="b8e3d-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8e3d-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="b8e3d-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8e3d-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="b8e3d-123">(省略可能):\* contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8e3d-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b8e3d-124">証明書は、公開 CA とサーバー EKU によって発行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8e3d-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="b8e3d-125">サービスには、アドレス帳サービス、配布グループ展開会議用 Office Web Apps、Lync IP デバイス発行ルールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b8e3d-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="b8e3d-126">サブジェクトの代替名には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b8e3d-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="b8e3d-127">フロントエンドサーバーまたはフロントエンドプール用の外部 Web サービス FQDN</span><span class="sxs-lookup"><span data-stu-id="b8e3d-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="b8e3d-128">ディレクターまたはディレクタープール用の外部 Web サービス FQDN</span><span class="sxs-lookup"><span data-stu-id="b8e3d-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="b8e3d-129">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="b8e3d-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="b8e3d-130">オンライン会議の公開ルール</span><span class="sxs-lookup"><span data-stu-id="b8e3d-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="b8e3d-131">会議用の Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="b8e3d-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="b8e3d-132">Lyncdiscover (自動検出)</span><span class="sxs-lookup"><span data-stu-id="b8e3d-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="b8e3d-133">会議の開始とダイヤルインの両方のオプションワイルドカード</span><span class="sxs-lookup"><span data-stu-id="b8e3d-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

