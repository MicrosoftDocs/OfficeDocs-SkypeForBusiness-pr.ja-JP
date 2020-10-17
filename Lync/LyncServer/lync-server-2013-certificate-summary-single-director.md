---
title: 'Lync Server 2013: 証明書の概要-単一ディレクター'
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
ms.openlocfilehash: ceb2543cece60a32c733d2efad6023fc30bb2bf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517934"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="0a4dd-102">証明書の概要-Lync Server 2013 の単一ディレクター</span><span class="sxs-lookup"><span data-stu-id="0a4dd-102">Certificate summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a4dd-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0a4dd-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="0a4dd-104">単一ディレクターの証明書要件は、ディレクターが受信できるサービスのサブジェクト名とサブジェクトの別名を持つ既定の証明書で構成されます。</span><span class="sxs-lookup"><span data-stu-id="0a4dd-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="0a4dd-105">また、サーバー間認証用の OAuth トークン証明書もあります。</span><span class="sxs-lookup"><span data-stu-id="0a4dd-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="0a4dd-106">ディレクターの証明書</span><span class="sxs-lookup"><span data-stu-id="0a4dd-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a4dd-107">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a4dd-107">Component</span></span></th>
<th><span data-ttu-id="0a4dd-108">サブジェクト名 (SN)</span><span class="sxs-lookup"><span data-stu-id="0a4dd-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="0a4dd-109">サブジェクト名の別名 (SAN)</span><span class="sxs-lookup"><span data-stu-id="0a4dd-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="0a4dd-110">Comments</span><span class="sxs-lookup"><span data-stu-id="0a4dd-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a4dd-111">既定値</span><span class="sxs-lookup"><span data-stu-id="0a4dd-111">Default</span></span></p></td>
<td><p><span data-ttu-id="0a4dd-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0a4dd-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0a4dd-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0a4dd-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="0a4dd-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0a4dd-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="0a4dd-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0a4dd-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="0a4dd-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0a4dd-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="0a4dd-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0a4dd-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="0a4dd-118">(オプション) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0a4dd-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0a4dd-119">ディレクター証明書は、内部管理の証明機関 (CA) またはパブリック CA のどちらかから要求できます。</span><span class="sxs-lookup"><span data-stu-id="0a4dd-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="0a4dd-120">ディレクターは、境界サーバーまたはエッジサーバーのリバースプロキシからの要求に応答します。</span><span class="sxs-lookup"><span data-stu-id="0a4dd-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="0a4dd-121">内部クライアントはディレクターを使用しません。</span><span class="sxs-lookup"><span data-stu-id="0a4dd-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="0a4dd-122">または、簡易 URL のワイルドカード エントリ</span><span class="sxs-lookup"><span data-stu-id="0a4dd-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a4dd-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="0a4dd-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="0a4dd-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0a4dd-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0a4dd-125">エントリはありません</span><span class="sxs-lookup"><span data-stu-id="0a4dd-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="0a4dd-126">キーの最低の長さは 1024 ですが、キーの推奨される最低の長さが 2048 ビットであるという警告が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a4dd-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="0a4dd-p103">OAuthTokenIssuer 証明書は、大規模な環境内のサーバーを認証するための単一目的の証明書であり、社内の CA またはパブリック CA に要求できます。この証明書は必須です。</span><span class="sxs-lookup"><span data-stu-id="0a4dd-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

