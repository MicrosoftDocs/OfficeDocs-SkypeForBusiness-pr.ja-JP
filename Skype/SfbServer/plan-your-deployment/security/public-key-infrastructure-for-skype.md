---
title: Skype ビジネス サーバーのための公開キー基盤
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype ビジネス サーバーは、クライアントとサーバー間で、別のサーバーの役割間の信頼のチェーンを確立するためにサーバー認証の証明書に依存します。 Windows Server 2012 R2、Windows Server 2012 の、Windows Server 2008 R2、および Windows Server 2008 公開キー基盤 (PKI) を確立して、この信頼チェーンを検証するためのインフラストラクチャを提供します。
ms.openlocfilehash: e8e1230074dff58c46880b759038834a8d16c444
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889232"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a><span data-ttu-id="0049a-104">Skype ビジネス サーバーのための公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="0049a-104">Public Key Infrastructure for Skype for Business Server</span></span>
 
<span data-ttu-id="0049a-105">Skype ビジネス サーバーは、クライアントとサーバー間で、別のサーバーの役割間の信頼のチェーンを確立するためにサーバー認証の証明書に依存します。</span><span class="sxs-lookup"><span data-stu-id="0049a-105">Skype for Business Server relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="0049a-106">Windows Server 2012 R2、Windows Server 2012 の、Windows Server 2008 R2、および Windows Server 2008 公開キー基盤 (PKI) を確立して、この信頼チェーンを検証するためのインフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="0049a-106">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, and Windows Server 2008 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>
  
<span data-ttu-id="0049a-p103">証明書とはデジタル ID です。証明書は、名前によってサーバーを識別し、そのプロパティを指定します。証明書の情報が有効であるためには、サーバーに接続するクライアントやその他のサーバーが信頼する CA から証明書が発行されている必要があります。サーバーがプライベート ネットワーク上の他のクライアントおよびサーバーとのみ接続する場合は、CA はエンタープライズ CA で問題ありません。サーバーがプライベート ネットワーク外のエンティティと対話する場合は、パブリック CA が必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0049a-p103">Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.</span></span>
  
<span data-ttu-id="0049a-p104">証明書の情報が有効であっても、証明書を提示しているサーバーが、実際に証明書によって提示されているサーバーであることを確認する手段が必要です。ここで Windows PKI が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0049a-p104">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>
  
<span data-ttu-id="0049a-p105">各証明書は、公開キーにリンクされています。証明書で名前が指定されているサーバーには、そのサーバーのみが知る、対応する秘密キーがあります。接続しようとしているクライアントまたはサーバーは、公開キーを使用して無作為な情報の断片を暗号化し、それをサーバーに送信します。サーバーがその情報を復号化し、プレーン テキストに戻すと、接続しようとしているエンティティは、証明書の秘密キーをサーバーが保持していること、つまり、そのサーバーが証明書で指定されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0049a-p105">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0049a-118">すべてのパブリック Ca は、Skype ビジネス サーバー証明書の要件に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="0049a-118">Not all public CAs comply with the requirements of Skype for Business Server certificates.</span></span> <span data-ttu-id="0049a-119">認定されているパブリック CA ベンダーの一覧を参照して、パブリック証明書のニーズに合ったベンダーを探すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0049a-119">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="0049a-120">詳細については、[ユニファイド コミュニケーションの証明書のパートナー](https://go.microsoft.com/fwlink/p/?LinkId=140898)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0049a-120">For details, see [Unified Communications Certificate Partners](https://go.microsoft.com/fwlink/p/?LinkId=140898).</span></span> 
  
## <a name="crl-distribution-points"></a><span data-ttu-id="0049a-121">CRL 配布ポイント</span><span class="sxs-lookup"><span data-stu-id="0049a-121">CRL Distribution Points</span></span>

<span data-ttu-id="0049a-122">ビジネス サーバーの Skype では、1 つまたは複数の証明書失効リスト (CRL) 配布ポイントを格納するためのすべてのサーバー証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="0049a-122">Skype for Business Server requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="0049a-123">CRL 配布ポイント (CDP) とは、証明書の発行後にそれが失効していないこと、および証明書が有効期限内にあることを確認するために、CRL をダウンロードできる場所です。</span><span class="sxs-lookup"><span data-stu-id="0049a-123">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="0049a-124">CRL 配布ポイントは、URL として証明書のプロパティに記述され、通常、セキュア HTTP です。</span><span class="sxs-lookup"><span data-stu-id="0049a-124">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>
  
## <a name="enhanced-key-usage"></a><span data-ttu-id="0049a-125">拡張キー使用法</span><span class="sxs-lookup"><span data-stu-id="0049a-125">Enhanced Key Usage</span></span>

<span data-ttu-id="0049a-126">ビジネス サーバーの Skype では、サーバー認証のための拡張キー使用法 (EKU) をサポートするすべてのサーバー証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="0049a-126">Skype for Business Server requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="0049a-127">サーバー認証用に EKU フィールドを構成することは、サーバーの認証に対して、その証明書が有効であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0049a-127">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="0049a-128">この EKU は、MTLS には不可欠です。</span><span class="sxs-lookup"><span data-stu-id="0049a-128">This EKU is essential for MTLS.</span></span> <span data-ttu-id="0049a-129">EKU には、複数のエントリを指定し、複数の目的に対して証明書を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="0049a-129">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>
  

