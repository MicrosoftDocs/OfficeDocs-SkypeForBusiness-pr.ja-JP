---
title: 証明書の概要-SIP、XMPP フェデレーション、パブリックインスタントメッセージ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="e2681-102">証明書の概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="e2681-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2681-103">_**最終更新日:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="e2681-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="e2681-104">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server とのフェデレーションに必要な証明書は、通常、エッジサーバーに対して構成、要求、および割り当てる証明書によって満たされます。</span><span class="sxs-lookup"><span data-stu-id="e2681-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="e2681-105">拡張メッセージングとプレゼンスプロトコル (XMPP) パートナーとの通信を有効にして確立するための証明書要件は、お使いの XMPP ドメインのエントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2681-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="e2681-106">サブジェクトの代替名 (SAN) として証明書に含まれているレコードは、XMPP 通信に参加できるドメインです。</span><span class="sxs-lookup"><span data-stu-id="e2681-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="e2681-107">ドメイン全体で XMPP を有効にする場合や、ユーザーのサブセットに対して XMPP を有効にしている場合は、ドメインのルートレベルのドメイン (たとえば、contoso.com) にすることができます (例: corp.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="e2681-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="e2681-108">パブリックインスタントメッセージング接続用の証明書を構成するには、America Online (AOL) には証明書または証明書が必要であることを除いて、他の SIP フェデレーションタイプまたは標準エッジサーバーの証明書とはまったく異なるものがあることに注意してください。エッジプールの場合は、クライアント EKU も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2681-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="e2681-109">クライアント EKU は証明書に追加されたものであり、エッジサーバーに割り当てられている外部公開証明書の一部です。</span><span class="sxs-lookup"><span data-stu-id="e2681-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="e2681-110">エッジサーバーの展開に必要な証明書の要件を満たしていることを確認するには、 **「関連**項目」のセクションに記載されているトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e2681-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2681-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e2681-111">Component</span></span></th>
<th><span data-ttu-id="e2681-112">サブジェクト名</span><span class="sxs-lookup"><span data-stu-id="e2681-112">Subject name</span></span></th>
<th><span data-ttu-id="e2681-113">サブジェクトの代替名 (SAN)</span><span class="sxs-lookup"><span data-stu-id="e2681-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="e2681-114">コメント</span><span class="sxs-lookup"><span data-stu-id="e2681-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2681-115">外部/アクセスエッジ</span><span class="sxs-lookup"><span data-stu-id="e2681-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="e2681-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2681-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e2681-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2681-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="e2681-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2681-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="e2681-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2681-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="e2681-120">Contoso.com XMPP 名前空間をサポートするには</span><span class="sxs-lookup"><span data-stu-id="e2681-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="e2681-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e2681-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="e2681-122">Fabrikam.com SIP 名前空間をサポートするには</span><span class="sxs-lookup"><span data-stu-id="e2681-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="e2681-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e2681-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="e2681-124">Fabrikam.com XMPP 名前空間をサポートするには</span><span class="sxs-lookup"><span data-stu-id="e2681-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="e2681-125">証明書はパブリック CA からである必要があります。また、AOL とのパブリック IM 接続を展開する場合は、サーバーの EKU とクライアントの EKU を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2681-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="e2681-126">証明書は、次のための外部エッジサーバーインターフェイスに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e2681-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2681-127">アクセス エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="e2681-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="e2681-128">Web 会議エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="e2681-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="e2681-129">音声ビデオ エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="e2681-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="e2681-130">技術的には、証明書は A/V Edge に割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="e2681-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="e2681-131">セキュリティで保護された通信と認証は、メディアリレー認証サービス (MRAS) を通じて管理されます。</span><span class="sxs-lookup"><span data-stu-id="e2681-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="e2681-132">MRAS では、エッジサーバーの内部インターフェイスに割り当てられている証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2681-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="e2681-133">San は、トポロジビルダーの定義に基づいて、自動的に証明書に追加されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e2681-133">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="e2681-134">必要に応じて、必要に応じて SAN エントリを追加します。これには、サポートが必要な追加の SIP ドメインや他のエントリも含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2681-134">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="e2681-135">サブジェクト名は SAN でレプリケートされ、正しい操作のために存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2681-135">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2681-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2681-136">See Also</span></span>


[<span data-ttu-id="e2681-137">Lync Server 2013 での XMPP 構成の例  - Google Talk との XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="e2681-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="e2681-138">Lync Server 2013 でエッジ サーバー証明書を計画する</span><span class="sxs-lookup"><span data-stu-id="e2681-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="e2681-139">証明書の概要 - Lync Server 2013 内の NAT を使用したプライベート IP アドレスを持つ単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="e2681-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="e2681-140">証明書の概要 - Lync Server 2013 のパブリック IP アドレスを使用する単一の統合エッジ</span><span class="sxs-lookup"><span data-stu-id="e2681-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="e2681-141">証明書の概要 - Lync Server 2013 での拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="e2681-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="e2681-142">Lync Server 2013 の証明書の概要 - 拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="e2681-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="e2681-143">証明書の概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)</span><span class="sxs-lookup"><span data-stu-id="e2681-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

