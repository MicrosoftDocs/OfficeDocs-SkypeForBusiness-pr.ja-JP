---
title: 'Lync Server 2013: 証明書の概要 - DNS および HLB による負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e145e2f1ac3d331906713584b365adf7cd48aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="fdea0-102">証明書の概要 - Lync Server 2013 の DNS および HLB による負荷分散</span><span class="sxs-lookup"><span data-stu-id="fdea0-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdea0-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="fdea0-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="fdea0-104">DNS の負荷分散とハードウェアのロードバランサーを備えたディレクターの証明書要件は、監督が受信できるサービスのサブジェクト名とサブジェクトの代替名を持つ既定の証明書を使います。</span><span class="sxs-lookup"><span data-stu-id="fdea0-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="fdea0-105">プール内の各ディレクターに対して証明書が要求されます。</span><span class="sxs-lookup"><span data-stu-id="fdea0-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="fdea0-106">ハードウェアロードバランサーでは、リバースプロキシからのトラフィックだけが負荷分散されることに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="fdea0-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="fdea0-107">さらに、サーバー間認証のための OAuth トークン証明書が、各サーバーにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="fdea0-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="fdea0-108">ディレクター用の証明書</span><span class="sxs-lookup"><span data-stu-id="fdea0-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdea0-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fdea0-109">Component</span></span></th>
<th><span data-ttu-id="fdea0-110">サブジェクト名 (SN)</span><span class="sxs-lookup"><span data-stu-id="fdea0-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="fdea0-111">サブジェクトの代替名 (SAN)</span><span class="sxs-lookup"><span data-stu-id="fdea0-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="fdea0-112">コメント</span><span class="sxs-lookup"><span data-stu-id="fdea0-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdea0-113">Default</span><span class="sxs-lookup"><span data-stu-id="fdea0-113">Default</span></span></p></td>
<td><p><span data-ttu-id="fdea0-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fdea0-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fdea0-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fdea0-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="fdea0-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fdea0-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="fdea0-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fdea0-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="fdea0-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fdea0-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="fdea0-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fdea0-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="fdea0-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fdea0-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="fdea0-121">(必要に応じて) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="fdea0-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fdea0-122">ディレクター証明書は、内部管理の証明機関 (CA) またはパブリック CA から要求することができます。</span><span class="sxs-lookup"><span data-stu-id="fdea0-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="fdea0-123">ディレクターは、境界サーバーまたはエッジサーバーのリバースプロキシからの要求に応答します。</span><span class="sxs-lookup"><span data-stu-id="fdea0-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="fdea0-124">内部クライアントでは、監督は使用されません。</span><span class="sxs-lookup"><span data-stu-id="fdea0-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="fdea0-125">または、単純な Url のワイルドカードエントリ</span><span class="sxs-lookup"><span data-stu-id="fdea0-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdea0-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="fdea0-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="fdea0-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fdea0-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fdea0-128">エントリがありません</span><span class="sxs-lookup"><span data-stu-id="fdea0-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="fdea0-129">最小のキー長は1024ですが、最小の推奨されるキーの長さは2048ビットであるという警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="fdea0-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="fdea0-130">OAuthTokenIssuer 証明書は、大規模な環境でサーバーを認証することを目的とした単一目的の証明書であり、内部 CA またはパブリック CA から要求することができます。</span><span class="sxs-lookup"><span data-stu-id="fdea0-130">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="fdea0-131">証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="fdea0-131">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

