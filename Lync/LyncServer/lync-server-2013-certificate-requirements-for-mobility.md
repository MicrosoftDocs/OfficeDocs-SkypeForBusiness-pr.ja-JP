---
title: 'Lync Server 2013: モビリティの証明書の要件'
description: 'Lync Server 2013: モビリティの証明書の要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51af74b3efc1ffcb4fe38d7431e315f9b55af943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575203"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="7fe84-103">Lync Server 2013 でのモビリティの証明書要件</span><span class="sxs-lookup"><span data-stu-id="7fe84-103">Certificate requirements for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fe84-104">_**トピックの最終更新日:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="7fe84-104">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="7fe84-105">モビリティ機能を展開し、モバイルクライアントの自動検出をサポートする場合は、モバイルクライアントからのセキュリティで保護された接続をサポートするために、証明書に特定のサブジェクトの別名エントリを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fe84-105">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="7fe84-106">次の証明書に、自動検出のサブジェクトの別名エントリを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fe84-106">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="7fe84-107">ディレクター プール</span><span class="sxs-lookup"><span data-stu-id="7fe84-107">Director pool</span></span>

  - <span data-ttu-id="7fe84-108">フロント エンド プール</span><span class="sxs-lookup"><span data-stu-id="7fe84-108">Front End pool</span></span>

  - <span data-ttu-id="7fe84-109">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="7fe84-109">Reverse proxy</span></span>

<span data-ttu-id="7fe84-110">このセクションでは、自動検出のために証明書で必要とされるサブジェクトの別名エントリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7fe84-110">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7fe84-111">通常、内部の証明機関を使用した証明書の再発行は簡単なプロセスですが、サブジェクトの複数の別名エントリを、リバース プロキシで使用されるパブリック証明書に追加するには、高い費用がかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7fe84-111">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="7fe84-112">多数の SIP ドメインがあり、サブジェクトの別名が非常に高価になっている場合は、HTTPS (既定の構成) ではなく、最初の自動検出サービス要求に HTTP を使用するようにリバースプロキシを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7fe84-112">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="7fe84-113">詳細については、「 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 でのモビリティの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fe84-113">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="7fe84-114">ディレクター プールの証明書の要件</span><span class="sxs-lookup"><span data-stu-id="7fe84-114">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fe84-115">説明</span><span class="sxs-lookup"><span data-stu-id="7fe84-115">Description</span></span></th>
<th><span data-ttu-id="7fe84-116">サブジェクト名の別名エントリ</span><span class="sxs-lookup"><span data-stu-id="7fe84-116">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fe84-117">内部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="7fe84-117">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7fe84-118">SAN = lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe84-118">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe84-119">外部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="7fe84-119">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7fe84-120">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe84-120">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7fe84-121">または、SAN = \* を使用することもできます。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe84-121">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="7fe84-122">フロント エンド プールの証明書の要件</span><span class="sxs-lookup"><span data-stu-id="7fe84-122">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fe84-123">説明</span><span class="sxs-lookup"><span data-stu-id="7fe84-123">Description</span></span></th>
<th><span data-ttu-id="7fe84-124">サブジェクト名の別名エントリ</span><span class="sxs-lookup"><span data-stu-id="7fe84-124">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fe84-125">内部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="7fe84-125">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7fe84-126">SAN = lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe84-126">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fe84-127">外部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="7fe84-127">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7fe84-128">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe84-128">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7fe84-129">または、SAN = \* を使用することもできます。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe84-129">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="7fe84-130">リバース プロキシ (パブリック CA) の証明書の要件</span><span class="sxs-lookup"><span data-stu-id="7fe84-130">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fe84-131">説明</span><span class="sxs-lookup"><span data-stu-id="7fe84-131">Description</span></span></th>
<th><span data-ttu-id="7fe84-132">サブジェクト名の別名エントリ</span><span class="sxs-lookup"><span data-stu-id="7fe84-132">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fe84-133">外部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="7fe84-133">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7fe84-134">SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7fe84-134">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7fe84-135">リバースプロキシ上の SSL リスナーに割り当てられた証明書にこの SAN を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7fe84-135">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7fe84-136">リバースプロキシリスナーには、外部 Web サービスの URL (たとえば、SAN = lyncwebextpool01.contoso.com、およびオプションのディレクターを展開している場合は dirwebexternal.contoso.com) のサブジェクトの別名があります。</span><span class="sxs-lookup"><span data-stu-id="7fe84-136">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

