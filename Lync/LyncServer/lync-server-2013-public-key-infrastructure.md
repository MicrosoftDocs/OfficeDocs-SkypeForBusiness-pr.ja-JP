---
title: 'Lync Server 2013: 公開キー基盤'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec711ad773aeb1b3b426e929b2d87d033f8d8004
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="ef180-102">Lync Server 2013 の公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="ef180-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef180-103">_**トピックの最終更新日:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="ef180-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="ef180-104">Microsoft Lync Server 2013 は、サーバー認証に証明書を使用し、クライアントとサーバーの間、およびさまざまなサーバーの役割間の信頼チェーンを確立します。</span><span class="sxs-lookup"><span data-stu-id="ef180-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="ef180-105">Windows Server 2012 R2、Windows server 2012、Windows Server 2008 R2、Windows Server 2008、および Windows Server 2003 公開キー基盤 (PKI) は、この信頼チェーンを確立して検証するためのインフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="ef180-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="ef180-106">証明書とはデジタル ID です。</span><span class="sxs-lookup"><span data-stu-id="ef180-106">Certificates are digital IDs.</span></span> <span data-ttu-id="ef180-107">証明書は、名前によってサーバーを識別し、そのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ef180-107">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="ef180-108">証明書の情報が有効であることを確認するには、サーバーに接続するクライアントまたは他のサーバーによって信頼されている CA が証明書を発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef180-108">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="ef180-109">サーバーがプライベート ネットワーク上の他のクライアントおよびサーバーとのみ接続する場合は、CA はエンタープライズ CA で問題ありません。</span><span class="sxs-lookup"><span data-stu-id="ef180-109">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="ef180-110">サーバーがプライベート ネットワーク外のエンティティと対話する場合は、パブリック CA が必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef180-110">If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="ef180-p103">証明書の情報が有効であっても、証明書を提示しているサーバーが、実際に証明書によって提示されているサーバーであることを確認する手段が必要です。ここで Windows PKI が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ef180-p103">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="ef180-p104">各証明書は、公開キーにリンクされています。証明書で名前が指定されているサーバーには、そのサーバーのみが知る、対応する秘密キーがあります。接続しようとしているクライアントまたはサーバーは、公開キーを使用して無作為な情報の断片を暗号化し、それをサーバーに送信します。サーバーがその情報を復号化し、プレーン テキストに戻すと、接続しようとしているエンティティは、証明書の秘密キーをサーバーが保持していること、つまり、そのサーバーが証明書で指定されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ef180-p104">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef180-117">すべてのパブリック Ca が Lync Server 2013 証明書の要件に準拠しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ef180-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="ef180-118">認定されているパブリック CA ベンダーの一覧を参照して、パブリック証明書のニーズに合ったベンダーを探すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef180-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="ef180-119">詳細については、「統合コミュニケーション<A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>証明書パートナー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef180-119">For details, see Unified Communications Certificate Partners at <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="ef180-120">CRL 配布ポイント</span><span class="sxs-lookup"><span data-stu-id="ef180-120">CRL Distribution Points</span></span>

<span data-ttu-id="ef180-121">Lync Server 2013 には、すべてのサーバー証明書に1つ以上の証明書失効リスト (CRL) 配布ポイントが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef180-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="ef180-122">CRL 配布ポイント (Cdp) は、発行後に証明書が失効しておらず、証明書が有効期間内にあることを確認するために、Crl をダウンロードできる場所です。</span><span class="sxs-lookup"><span data-stu-id="ef180-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="ef180-123">CRL 配布ポイントは、証明書のプロパティに URL として記載されています。通常、HTTP はセキュリティで保護されています。</span><span class="sxs-lookup"><span data-stu-id="ef180-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="ef180-124">拡張キー使用法</span><span class="sxs-lookup"><span data-stu-id="ef180-124">Enhanced Key Usage</span></span>

<span data-ttu-id="ef180-125">Lync Server 2013 では、サーバー認証のために拡張キー使用法 (EKU) をサポートするすべてのサーバー証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="ef180-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="ef180-126">サーバー認証の EKU フィールドを構成することは、証明書がサーバーの認証を目的として有効であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ef180-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="ef180-127">この EKU は、MTLS にとって不可欠です。</span><span class="sxs-lookup"><span data-stu-id="ef180-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="ef180-128">EKU に複数のエントリを含めることができます。これにより、複数の目的に対して証明書を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ef180-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef180-129">Live Communications Server 2003 および Live Communications Server 2005 からの送信 MTLS 接続には、クライアント認証 EKU が必要ですが、これは不要になりました。</span><span class="sxs-lookup"><span data-stu-id="ef180-129">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required.</span></span> <span data-ttu-id="ef180-130">ただし、この EKU は、パブリック IM 接続を使用して AOL に接続するエッジサーバー上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef180-130">However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

