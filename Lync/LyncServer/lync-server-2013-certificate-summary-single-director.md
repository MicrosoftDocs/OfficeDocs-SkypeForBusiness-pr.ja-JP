---
title: 'Lync Server 2013: 証明書の概要-単一ディレクター'
description: 'Lync Server 2013: 証明書の概要-単一のディレクター。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cf930a73d9989ec44f52f1d70ee9e0f900e4d6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572163"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="01407-103">証明書の概要-Lync Server 2013 の単一ディレクター</span><span class="sxs-lookup"><span data-stu-id="01407-103">Certificate summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01407-104">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="01407-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="01407-105">単一ディレクターの証明書要件は、ディレクターが受信できるサービスのサブジェクト名とサブジェクトの別名を持つ既定の証明書で構成されます。</span><span class="sxs-lookup"><span data-stu-id="01407-105">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="01407-106">また、サーバー間認証用の OAuth トークン証明書もあります。</span><span class="sxs-lookup"><span data-stu-id="01407-106">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="01407-107">ディレクターの証明書</span><span class="sxs-lookup"><span data-stu-id="01407-107">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01407-108">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="01407-108">Component</span></span></th>
<th><span data-ttu-id="01407-109">サブジェクト名 (SN)</span><span class="sxs-lookup"><span data-stu-id="01407-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="01407-110">サブジェクト名の別名 (SAN)</span><span class="sxs-lookup"><span data-stu-id="01407-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="01407-111">Comments</span><span class="sxs-lookup"><span data-stu-id="01407-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01407-112">既定値</span><span class="sxs-lookup"><span data-stu-id="01407-112">Default</span></span></p></td>
<td><p><span data-ttu-id="01407-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="01407-113">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="01407-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="01407-114">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="01407-115">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01407-115">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="01407-116">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01407-116">meet.contoso.com</span></span></p>
<p><span data-ttu-id="01407-117">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01407-117">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="01407-118">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01407-118">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="01407-119">(オプション) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01407-119">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01407-120">ディレクター証明書は、内部管理の証明機関 (CA) またはパブリック CA のどちらかから要求できます。</span><span class="sxs-lookup"><span data-stu-id="01407-120">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="01407-121">ディレクターは、境界サーバーまたはエッジサーバーのリバースプロキシからの要求に応答します。</span><span class="sxs-lookup"><span data-stu-id="01407-121">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="01407-122">内部クライアントはディレクターを使用しません。</span><span class="sxs-lookup"><span data-stu-id="01407-122">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="01407-123">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="01407-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01407-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="01407-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="01407-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="01407-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="01407-126">エントリはありません</span><span class="sxs-lookup"><span data-stu-id="01407-126">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="01407-127">キーの最低の長さは 1024 ですが、キーの推奨される最低の長さが 2048 ビットであるという警告が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="01407-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="01407-p103">OAuthTokenIssuer 証明書は、大規模な環境内のサーバーを認証するための単一目的の証明書であり、社内の CA またはパブリック CA に要求できます。この証明書は必須です。</span><span class="sxs-lookup"><span data-stu-id="01407-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

