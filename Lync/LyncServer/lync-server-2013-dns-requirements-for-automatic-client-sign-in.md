---
title: 'Lync Server 2013: 自動クライアントサインインの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b022d9780d1498f70fd5918894a1412996731004
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="2b6eb-102">Lync Server 2013 での自動クライアントサインインの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="2b6eb-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b6eb-103">_**トピックの最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="2b6eb-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="2b6eb-104">ここでは、自動クライアント サインインに必要なドメイン ネーム システム (DNS) レコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="2b6eb-105">Standard Edition サーバーまたはフロントエンド プールを展開するときに、クライアントが自動検出を使用して適切な Standard Edition サーバーまたはフロントエンド プールにサインインするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="2b6eb-106">クライアントが Lync Server 2013 に手動で接続することを計画している場合は、このトピックを省略できます。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="2b6eb-107">自動クライアント サインインをサポートするには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="2b6eb-p102">クライアントのサインイン要求を分散および認証する 1 つのサーバーまたはプールを指定します。 組織内のユーザーをホストする既存のサーバーまたはプールを使用できます。ユーザーをホストしない、この目的専用のサーバーまたはプールを指定することもできます。 可用性を高めるには、この機能用のフロントエンド プールを指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-p102">Designate a single server or pool to distribute and authenticate client sign-in requests. This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users. For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="2b6eb-111">このサーバーまたはプールで自動クライアント サインインをサポートする内部 DNS SRV レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2b6eb-p103">次のレコード要件では、SIP ドメインは、ユーザーに割り当てられる SIP URI のホスト部分です。たとえば、SIP URI が \*@contoso.com という形式の場合は、contoso.com が SIP ドメインです。SIP ドメインは、内部 Active Directory ドメインと異なる場合がよくあります。また、1 つの組織が複数の SIP ドメインをサポートする場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-p103">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users. For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain. The SIP domain is often different from the internal Active Directory domain. An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="2b6eb-116">クライアントの自動構成を有効にするには、次のレコードのいずれかを、Lync からのサインイン要求を配布するフロントエンドプールまたは Standard Edition サーバーの完全修飾ドメイン名 (FQDN) にマップする内部 DNS SRV レコードを作成する必要があります。クライアント</span><span class="sxs-lookup"><span data-stu-id="2b6eb-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="2b6eb-117">\_sipinternaltls.\_tcp。\<ドメイン\> -内部 TLS 接続の場合</span><span class="sxs-lookup"><span data-stu-id="2b6eb-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="2b6eb-118">SRV レコードは、サインイン要求を分散させるフロントエンド プールまたは Standard Edition サーバーに対して 1 つだけ作成します。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="2b6eb-119">次の表は、架空の Contoso という会社に必要なレコードの例をいくつか示しています。この会社では、contoso.com と retail.contoso.com という SIP ドメインをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="2b6eb-120">複数の SIP ドメインを持つクライアントの自動サインインに必要な DNS レコードの例</span><span class="sxs-lookup"><span data-stu-id="2b6eb-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b6eb-121">サインイン要求の分散に使用されるフロントエンド プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="2b6eb-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="2b6eb-122">SIP ドメイン</span><span class="sxs-lookup"><span data-stu-id="2b6eb-122">SIP domain</span></span></th>
<th><span data-ttu-id="2b6eb-123">DNS SRV レコード</span><span class="sxs-lookup"><span data-stu-id="2b6eb-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b6eb-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b6eb-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2b6eb-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b6eb-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2b6eb-126">pool01.contoso.com にマップするポート 5061 経由の _sipinternaltls._tcp.contoso.com ドメイン用の SRV レコード</span><span class="sxs-lookup"><span data-stu-id="2b6eb-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b6eb-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b6eb-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2b6eb-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b6eb-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2b6eb-129">pool01.contoso.com にマップするポート 5061 経由の _sipinternaltls._tcp.retail.contoso.com ドメイン用 SRV レコード</span><span class="sxs-lookup"><span data-stu-id="2b6eb-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2b6eb-130">既定では、DNS レコードのクエリは、ユーザー名のドメインと SRV レコードの間で一致する厳密なドメイン名に従います。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="2b6eb-131">サフィックスの一致を使用するクライアント DNS クエリを使用する場合は、DisableStrictDNSNaming グループ ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="2b6eb-132">詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-clients-and-devices.md">planning for clients and devices In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="2b6eb-133">自動クライアント サインインに必要な証明書および DNS レコードの例</span><span class="sxs-lookup"><span data-stu-id="2b6eb-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="2b6eb-p105">この例では、前の表と同じ例の名前を使用します。 Contoso 社の組織は contoso.com および retail.contoso.com の SIP ドメインをサポートし、そのユーザー全員の SIP URI が次のいずれかの形式となります。</span><span class="sxs-lookup"><span data-stu-id="2b6eb-p105">This example uses the same example names in the preceding table. The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="2b6eb-136">\<ユーザー\>@retail contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b6eb-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="2b6eb-137">\<ユーザー\>@contoso .com</span><span class="sxs-lookup"><span data-stu-id="2b6eb-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

