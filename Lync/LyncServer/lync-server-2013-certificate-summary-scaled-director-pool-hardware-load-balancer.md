---
title: 証明書の概要-拡張ディレクタープール、ハードウェアロードバランサー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c08fb5710e25bf4504d7cb2d10020138221b22c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507924"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="7a678-102">証明書の概要-Lync Server 2013 の拡張ディレクタープール、ハードウェアロードバランサー</span><span class="sxs-lookup"><span data-stu-id="7a678-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a678-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="7a678-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="7a678-104">ハードウェアロードバランサーを使用するディレクターの証明書要件では、ディレクタープールで受信できるサービスのサブジェクト名とサブジェクトの別名を持つ既定の証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a678-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="7a678-105">プール内の各ディレクターに証明書が要求されます。</span><span class="sxs-lookup"><span data-stu-id="7a678-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="7a678-106">また、サーバー間認証用の OAuth トークンの証明書も各サーバーにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="7a678-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="7a678-107">ロード バランサー機器を使用する拡張ディレクタ用の証明書</span><span class="sxs-lookup"><span data-stu-id="7a678-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a678-108">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7a678-108">Component</span></span></th>
<th><span data-ttu-id="7a678-109">サブジェクト名 (SN)</span><span class="sxs-lookup"><span data-stu-id="7a678-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="7a678-110">サブジェクト名の別名 (SAN)</span><span class="sxs-lookup"><span data-stu-id="7a678-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="7a678-111">Comments</span><span class="sxs-lookup"><span data-stu-id="7a678-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a678-112">既定値</span><span class="sxs-lookup"><span data-stu-id="7a678-112">Default</span></span></p></td>
<td><p><span data-ttu-id="7a678-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7a678-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7a678-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7a678-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="7a678-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7a678-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="7a678-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7a678-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="7a678-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7a678-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="7a678-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7a678-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="7a678-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7a678-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="7a678-120">(オプション) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7a678-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7a678-121">ディレクター証明書は、内部管理の証明機関 (CA) またはパブリック CA のどちらかから要求できます。</span><span class="sxs-lookup"><span data-stu-id="7a678-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="7a678-122">ディレクターは、境界サーバーまたはエッジサーバーのリバースプロキシからの要求に応答します。</span><span class="sxs-lookup"><span data-stu-id="7a678-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="7a678-123">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="7a678-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a678-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="7a678-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="7a678-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7a678-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7a678-126">エントリはありません</span><span class="sxs-lookup"><span data-stu-id="7a678-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="7a678-127">キーの最低の長さは 1024 ですが、キーの推奨される最低の長さが 2048 ビットであるという警告が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a678-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="7a678-p102">OAuthTokenIssuer 証明書は、大規模な環境内のサーバーを認証するための単一目的の証明書であり、社内の CA またはパブリック CA に要求できます。この証明書は必須です。</span><span class="sxs-lookup"><span data-stu-id="7a678-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

