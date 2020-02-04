---
title: 'Lync Server 2013: 証明書の概要 - 単一ディレクター'
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
ms.openlocfilehash: f18fcec270104be1620402ddee0c665c0f3f3a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="5600e-102">証明書の概要 - Lync Server 2013 の単一ディレクター</span><span class="sxs-lookup"><span data-stu-id="5600e-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5600e-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="5600e-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="5600e-104">1つのディレクターの証明書要件は、監督が受信できるサービスのサブジェクト名とサブジェクトの代替名を持つ既定の証明書で構成されます。</span><span class="sxs-lookup"><span data-stu-id="5600e-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="5600e-105">さらに、サーバー間認証のための OAuth トークン証明書も用意されています。</span><span class="sxs-lookup"><span data-stu-id="5600e-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="5600e-106">ディレクター用の証明書</span><span class="sxs-lookup"><span data-stu-id="5600e-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5600e-107">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5600e-107">Component</span></span></th>
<th><span data-ttu-id="5600e-108">サブジェクト名 (SN)</span><span class="sxs-lookup"><span data-stu-id="5600e-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="5600e-109">サブジェクトの代替名 (SAN)</span><span class="sxs-lookup"><span data-stu-id="5600e-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="5600e-110">コメント</span><span class="sxs-lookup"><span data-stu-id="5600e-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5600e-111">Default</span><span class="sxs-lookup"><span data-stu-id="5600e-111">Default</span></span></p></td>
<td><p><span data-ttu-id="5600e-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5600e-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5600e-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5600e-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="5600e-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5600e-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="5600e-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5600e-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="5600e-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5600e-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="5600e-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5600e-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="5600e-118">(必要に応じて) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="5600e-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5600e-119">ディレクター証明書は、内部管理の証明機関 (CA) またはパブリック CA から要求することができます。</span><span class="sxs-lookup"><span data-stu-id="5600e-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="5600e-120">ディレクターは、境界サーバーまたはエッジサーバーのリバースプロキシからの要求に応答します。</span><span class="sxs-lookup"><span data-stu-id="5600e-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="5600e-121">内部クライアントでは、監督は使用されません。</span><span class="sxs-lookup"><span data-stu-id="5600e-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="5600e-122">または、単純な Url のワイルドカードエントリ</span><span class="sxs-lookup"><span data-stu-id="5600e-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5600e-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="5600e-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="5600e-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5600e-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="5600e-125">エントリがありません</span><span class="sxs-lookup"><span data-stu-id="5600e-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="5600e-126">最小のキー長は1024ですが、最小の推奨されるキーの長さは2048ビットであるという警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5600e-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="5600e-127">OAuthTokenIssuer 証明書は、大規模な環境でサーバーを認証することを目的とした単一目的の証明書であり、内部 CA またはパブリック CA から要求することができます。</span><span class="sxs-lookup"><span data-stu-id="5600e-127">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="5600e-128">証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="5600e-128">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

