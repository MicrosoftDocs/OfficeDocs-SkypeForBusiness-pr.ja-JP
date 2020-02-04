---
title: 'Lync Server 2013: モビリティの証明書の要件'
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
ms.openlocfilehash: 680eaf205959b67d8fef93ff56d379ae8cd293bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="b8761-102">Lync Server 2013 のモビリティの証明書の要件</span><span class="sxs-lookup"><span data-stu-id="b8761-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8761-103">_**最終更新日:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="b8761-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="b8761-104">モバイルクライアントの自動検出をサポートし、モバイルクライアントの自動検出をサポートしている場合は、モバイルクライアントからのセキュリティで保護された接続をサポートするために、証明書に特定のサブジェクト代替名エントリを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8761-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="b8761-105">次の証明書に対して自動検出を行うには、サブジェクトの代替名エントリを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8761-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="b8761-106">ディレクター プール</span><span class="sxs-lookup"><span data-stu-id="b8761-106">Director pool</span></span>

  - <span data-ttu-id="b8761-107">フロントエンド プール</span><span class="sxs-lookup"><span data-stu-id="b8761-107">Front End pool</span></span>

  - <span data-ttu-id="b8761-108">リバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="b8761-108">Reverse proxy</span></span>

<span data-ttu-id="b8761-109">このセクションでは、自動検出用に証明書に必要なサブジェクトの代替名エントリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b8761-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8761-110">内部証明機関を使った証明書の再発行は、通常は単純なプロセスですが、複数のサブジェクト代替名エントリをリバースプロキシによって使用されるパブリック証明書に追加するのはコストがかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="b8761-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="b8761-111">多数の SIP ドメインがあり、サブジェクトの代替名を追加した場合は、HTTPS (既定の構成) を使う代わりに、最初の自動検出サービス要求に対して HTTP を使うようにリバースプロキシを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b8761-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="b8761-112">詳細については、「 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 でのモビリティの技術要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8761-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="b8761-113">ディレクタープール証明書の要件</span><span class="sxs-lookup"><span data-stu-id="b8761-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8761-114">説明</span><span class="sxs-lookup"><span data-stu-id="b8761-114">Description</span></span></th>
<th><span data-ttu-id="b8761-115">サブジェクトの代替名エントリ</span><span class="sxs-lookup"><span data-stu-id="b8761-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8761-116">内部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="b8761-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b8761-117">SAN = lyncdiscoverinternal。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b8761-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8761-118">外部自動検出サービスの URL</span><span class="sxs-lookup"><span data-stu-id="b8761-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b8761-119">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b8761-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b8761-120">または、SAN = \* を使用することもできます。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b8761-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="b8761-121">フロントエンドプール証明書の要件</span><span class="sxs-lookup"><span data-stu-id="b8761-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8761-122">説明</span><span class="sxs-lookup"><span data-stu-id="b8761-122">Description</span></span></th>
<th><span data-ttu-id="b8761-123">サブジェクトの代替名エントリ</span><span class="sxs-lookup"><span data-stu-id="b8761-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8761-124">内部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="b8761-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b8761-125">SAN = lyncdiscoverinternal。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b8761-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8761-126">外部自動検出サービスの URL</span><span class="sxs-lookup"><span data-stu-id="b8761-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b8761-127">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b8761-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b8761-128">または、SAN = \* を使用することもできます。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b8761-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="b8761-129">リバースプロキシ (パブリック CA) 証明書の要件</span><span class="sxs-lookup"><span data-stu-id="b8761-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8761-130">説明</span><span class="sxs-lookup"><span data-stu-id="b8761-130">Description</span></span></th>
<th><span data-ttu-id="b8761-131">サブジェクトの代替名エントリ</span><span class="sxs-lookup"><span data-stu-id="b8761-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8761-132">外部自動検出サービスの URL</span><span class="sxs-lookup"><span data-stu-id="b8761-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b8761-133">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b8761-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b8761-134">この SAN を、リバースプロキシの SSL リスナーに割り当てられている証明書に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b8761-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b8761-135">リバースプロキシリスナーには、外部 Web サービスの URL (たとえば、オプションのディレクターを展開した場合は、SAN = lyncwebextpool01、dirwebexternal.contoso.com など) のサブジェクト代替名があります。</span><span class="sxs-lookup"><span data-stu-id="b8761-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

