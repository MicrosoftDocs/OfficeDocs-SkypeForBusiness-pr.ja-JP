---
title: 'Lync Server 2013: 自動クライアントサインインの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afd8ac315222a5582bde9802c22ab7b4911ddfe3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="f07c2-102">Lync Server 2013 での自動クライアントサインインの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="f07c2-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f07c2-103">_**最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="f07c2-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="f07c2-104">このセクションでは、自動クライアントサインインに必要なドメインネームシステム (DNS) レコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f07c2-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="f07c2-105">Standard Edition サーバーまたはフロントエンドプールを展開するときに、自動検出を使用して適切な Standard Edition サーバーまたはフロントエンドプールにサインインするようにクライアントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f07c2-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="f07c2-106">クライアントが Lync Server 2013 に手動で接続することを計画している場合は、このトピックをスキップできます。</span><span class="sxs-lookup"><span data-stu-id="f07c2-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="f07c2-107">自動クライアントサインインをサポートするには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f07c2-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="f07c2-108">クライアントのサインイン要求の配布と認証を行う単一のサーバーまたはプールを指定します。</span><span class="sxs-lookup"><span data-stu-id="f07c2-108">Designate a single server or pool to distribute and authenticate client sign-in requests.</span></span> <span data-ttu-id="f07c2-109">組織内のユーザーをホストしている既存のサーバーまたはプールの場合もあれば、ユーザーをホストしない場合は、専用のサーバーまたはプールを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f07c2-109">This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users.</span></span> <span data-ttu-id="f07c2-110">高可用性を実現するには、この関数のフロントエンドプールを指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f07c2-110">For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="f07c2-111">このサーバーまたはプールの自動クライアントサインインをサポートするための内部 DNS SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="f07c2-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f07c2-112">次のレコード要件では、SIP ドメインは、ユーザーに割り当てられている SIP Uri のホスト部分を指します。</span><span class="sxs-lookup"><span data-stu-id="f07c2-112">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users.</span></span> <span data-ttu-id="f07c2-113">たとえば、SIP Uri の形式が \* @contoso の場合は、contoso.com が SIP ドメインです。</span><span class="sxs-lookup"><span data-stu-id="f07c2-113">For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain.</span></span> <span data-ttu-id="f07c2-114">SIP ドメインは、多くの場合、内部の Active Directory ドメインとは異なります。</span><span class="sxs-lookup"><span data-stu-id="f07c2-114">The SIP domain is often different from the internal Active Directory domain.</span></span> <span data-ttu-id="f07c2-115">組織では、複数の SIP ドメインをサポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f07c2-115">An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="f07c2-116">クライアントの自動構成を有効にするには、次のレコードのいずれかを、Lync からのサインイン要求を配信するフロントエンドプールまたは Standard Edition サーバーの完全修飾ドメイン名 (FQDN) にマップする内部 DNS SRV レコードを作成する必要があります。客</span><span class="sxs-lookup"><span data-stu-id="f07c2-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="f07c2-117">\_sipinternaltls.\_tcp。\<ドメイン\> -内部 TLS 接続の場合</span><span class="sxs-lookup"><span data-stu-id="f07c2-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="f07c2-118">フロントエンドプールまたは Standard Edition サーバー用の SRV レコードを1つだけ作成する必要があります。また、その場合は、サインイン要求を配布します。</span><span class="sxs-lookup"><span data-stu-id="f07c2-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="f07c2-119">次の表では、contoso.com と retail.contoso.com の SIP ドメインをサポートする架空の会社の Contoso に必要なレコードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="f07c2-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="f07c2-120">複数の SIP ドメインでの自動クライアントサインインに必要な DNS レコードの例</span><span class="sxs-lookup"><span data-stu-id="f07c2-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f07c2-121">サインイン要求の配布に使用するフロントエンドプールの FQDN</span><span class="sxs-lookup"><span data-stu-id="f07c2-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="f07c2-122">SIP ドメイン</span><span class="sxs-lookup"><span data-stu-id="f07c2-122">SIP domain</span></span></th>
<th><span data-ttu-id="f07c2-123">DNS SRV レコード</span><span class="sxs-lookup"><span data-stu-id="f07c2-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f07c2-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f07c2-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f07c2-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f07c2-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f07c2-126">Pool01.contoso.com にマップされる、ポート5061経由の _sipinternaltls ドメインの SRV レコード</span><span class="sxs-lookup"><span data-stu-id="f07c2-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f07c2-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f07c2-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f07c2-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f07c2-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f07c2-129">Pool01.contoso.com にマップされている、ポート5061経由の _sipinternaltls ドメインの SRV レコード</span><span class="sxs-lookup"><span data-stu-id="f07c2-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f07c2-130">既定では、DNS レコードのクエリは、ユーザー名と SRV レコードのドメイン間の厳密なドメイン名の照合に従います。</span><span class="sxs-lookup"><span data-stu-id="f07c2-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="f07c2-131">クライアントの DNS クエリでサフィックスの照合を使う場合は、DisableStrictDNSNaming グループポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f07c2-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="f07c2-132">詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 でのクライアントとデバイスの計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f07c2-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="f07c2-133">自動クライアントサインインに必要な証明書と DNS レコードの例</span><span class="sxs-lookup"><span data-stu-id="f07c2-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="f07c2-134">この例では、前の表に示した例と同じ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="f07c2-134">This example uses the same example names in the preceding table.</span></span> <span data-ttu-id="f07c2-135">Contoso 組織では、contoso.com と retail.contoso.com の SIP ドメインをサポートしており、すべてのユーザーが SIP URI を次のいずれかの形式で使用しています。</span><span class="sxs-lookup"><span data-stu-id="f07c2-135">The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="f07c2-136">\<ユーザー\>@retail contoso.com</span><span class="sxs-lookup"><span data-stu-id="f07c2-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="f07c2-137">\<ユーザー\>@contoso .com</span><span class="sxs-lookup"><span data-stu-id="f07c2-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

