---
title: 'Lync Server 2013: 証明書の概要-DNS と HLB 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 743818f81f5083e9c5d3a7877d2518d05176a5e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499294"
---
# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="83061-102">証明書の概要-Lync Server 2013 での DNS および HLB の負荷分散</span><span class="sxs-lookup"><span data-stu-id="83061-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83061-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="83061-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="83061-104">ディレクターの証明書要件。 DNS 負荷分散とロードバランサー機器は、ディレクターが受信できるサービスのサブジェクト名とサブジェクトの別名を持つ既定の証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="83061-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="83061-105">プール内の各ディレクターに証明書が要求されます。</span><span class="sxs-lookup"><span data-stu-id="83061-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="83061-106">ハードウェア ロード バランサーはリバース プロキシからのトラフィックだけを負荷分散することを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="83061-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="83061-107">さらに、サーバー間認証のために各サーバーにインストールされる OAuth トークンがあります。</span><span class="sxs-lookup"><span data-stu-id="83061-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="83061-108">ディレクターの証明書</span><span class="sxs-lookup"><span data-stu-id="83061-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83061-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="83061-109">Component</span></span></th>
<th><span data-ttu-id="83061-110">サブジェクト名 (SN)</span><span class="sxs-lookup"><span data-stu-id="83061-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="83061-111">サブジェクト名の別名 (SAN)</span><span class="sxs-lookup"><span data-stu-id="83061-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="83061-112">Comments</span><span class="sxs-lookup"><span data-stu-id="83061-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83061-113">既定値</span><span class="sxs-lookup"><span data-stu-id="83061-113">Default</span></span></p></td>
<td><p><span data-ttu-id="83061-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="83061-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="83061-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="83061-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="83061-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="83061-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="83061-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83061-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="83061-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83061-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="83061-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83061-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="83061-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83061-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="83061-121">(オプション) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83061-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83061-122">ディレクター証明書は、内部管理の証明機関 (CA) またはパブリック CA のどちらかから要求できます。</span><span class="sxs-lookup"><span data-stu-id="83061-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="83061-123">ディレクターは、境界サーバーまたはエッジサーバーのリバースプロキシからの要求に応答します。</span><span class="sxs-lookup"><span data-stu-id="83061-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="83061-124">内部クライアントはディレクターを使用しません。</span><span class="sxs-lookup"><span data-stu-id="83061-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="83061-125">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="83061-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83061-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="83061-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="83061-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="83061-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="83061-128">エントリはありません</span><span class="sxs-lookup"><span data-stu-id="83061-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="83061-129">キーの最低の長さは 1024 ですが、キーの推奨される最低の長さが 2048 ビットであるという警告が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="83061-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="83061-p103">OAuthTokenIssuer 証明書は、大規模な環境内のサーバーを認証するための単一目的の証明書であり、社内の CA またはパブリック CA に要求できます。この証明書は必須です。</span><span class="sxs-lookup"><span data-stu-id="83061-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

