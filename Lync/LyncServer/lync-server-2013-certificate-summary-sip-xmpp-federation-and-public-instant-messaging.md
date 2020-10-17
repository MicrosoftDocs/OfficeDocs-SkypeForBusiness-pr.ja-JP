---
title: 証明書の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング
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
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517874"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="36ab0-102">証明書の概要-Lync Server 2013 の SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="36ab0-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36ab0-103">_**トピックの最終更新日:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="36ab0-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="36ab0-104">Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server とのフェデレーションに必要な証明書は、通常、構成した証明書、およびエッジサーバーの要求と割り当てによって満たされます。</span><span class="sxs-lookup"><span data-stu-id="36ab0-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="36ab0-105">拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) パートナーとの通信を有効または確立するための証明書の要件は、XMPP ドメインのエントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ab0-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="36ab0-106">サブジェクトの別名 (SAN) として証明書に含まれているレコードは、XMPP 通信に参加できるドメインになります。</span><span class="sxs-lookup"><span data-stu-id="36ab0-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="36ab0-107">ドメイン全体に対して XMPP を有効にする場合はドメインをルートレベル ドメイン (例: contoso.com) とし、ユーザーのサブセットに対して XMPP を有効にする場合は子ドメイン (例: corp.contoso.com、finance.contoso.com) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="36ab0-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="36ab0-108">パブリックインスタントメッセージング接続の証明書を構成するには、他の SIP フェデレーションタイプまたは標準エッジサーバー証明書には何も存在しないことに注意してください。ただし、America Online (AOL) には、クライアント EKU を含む証明書または証明書 (エッジプールの場合) が必要です。</span><span class="sxs-lookup"><span data-stu-id="36ab0-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="36ab0-109">クライアント EKU は証明書に追加され、エッジサーバーに割り当てられている外部公開証明書の一部です。</span><span class="sxs-lookup"><span data-stu-id="36ab0-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="36ab0-110">エッジサーバーの展開について正しい証明書要件を満たしていることを確認するには、 **「関連**項目」のセクションに記載されているトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="36ab0-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

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
<th><span data-ttu-id="36ab0-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="36ab0-111">Component</span></span></th>
<th><span data-ttu-id="36ab0-112">サブジェクト名</span><span class="sxs-lookup"><span data-stu-id="36ab0-112">Subject name</span></span></th>
<th><span data-ttu-id="36ab0-113">サブジェクト名の別名 (SAN)</span><span class="sxs-lookup"><span data-stu-id="36ab0-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="36ab0-114">Comments</span><span class="sxs-lookup"><span data-stu-id="36ab0-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36ab0-115">外部/アクセス エッジ</span><span class="sxs-lookup"><span data-stu-id="36ab0-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="36ab0-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="36ab0-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="36ab0-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="36ab0-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="36ab0-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="36ab0-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="36ab0-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="36ab0-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="36ab0-120">Contoso.com XMPP 名前空間をサポートするには</span><span class="sxs-lookup"><span data-stu-id="36ab0-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="36ab0-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="36ab0-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="36ab0-122">Fabrikam.com SIP 名前空間をサポートするには</span><span class="sxs-lookup"><span data-stu-id="36ab0-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="36ab0-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="36ab0-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="36ab0-124">Fabrikam.com XMPP 名前空間をサポートするには</span><span class="sxs-lookup"><span data-stu-id="36ab0-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="36ab0-125">証明書は、パブリック CA からのものである必要があり、AOL とのパブリック IM 接続を展開する場合は、サーバー EKU とクライアント EKU を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ab0-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="36ab0-126">証明書は、次のような外部エッジサーバーインターフェイスに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="36ab0-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="36ab0-127">アクセス エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="36ab0-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="36ab0-128">Web 会議エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="36ab0-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="36ab0-129">音声ビデオ エッジ サービス</span><span class="sxs-lookup"><span data-stu-id="36ab0-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="36ab0-130">技術的には、音声ビデオエッジに証明書が割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="36ab0-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="36ab0-131">セキュリティで保護された通信と認証は、メディアリレー認証サービス (MRAS) を通じて管理されます。</span><span class="sxs-lookup"><span data-stu-id="36ab0-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="36ab0-132">MRAS は、エッジサーバーの内部インターフェイスに割り当てられた証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="36ab0-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="36ab0-p105">SAN は、トポロジ ビルダーの定義に基づいて自動的に証明書に追加されます。追加の SIP ドメインで必要な SAN エントリや、サポートする必要がある他のエントリを追加します。SAN にはサブジェクト名がレプリケートされるため、正常に動作するためにはサブジェクト名が存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ab0-p105">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36ab0-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="36ab0-136">See Also</span></span>


[<span data-ttu-id="36ab0-137">Lync Server 2013 の XMPP 構成の例-Google Talk との XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="36ab0-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="36ab0-138">Lync Server 2013 でエッジサーバー証明書を計画する</span><span class="sxs-lookup"><span data-stu-id="36ab0-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="36ab0-139">証明書の概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="36ab0-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="36ab0-140">証明書の概要-Lync Server 2013 のパブリック IP アドレスを使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="36ab0-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="36ab0-141">証明書の概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="36ab0-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="36ab0-142">証明書の概要-Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="36ab0-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="36ab0-143">証明書の概要-Lync Server 2013 でのハードウェアロードバランサーを使用した拡張統合エッジ</span><span class="sxs-lookup"><span data-stu-id="36ab0-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

