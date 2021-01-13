---
title: Skype for Business Server の公開キー基盤
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype for Business Server は、証明書を使用してサーバー認証を行い、クライアントとサーバー間、および異なるサーバーの役割間の信頼チェーンを確立します。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、および Windows Server 2008 公開キー基盤 (PKI) は、この信頼チェーンを確立および検証するためのインフラストラクチャを提供します。
ms.openlocfilehash: 3ee9411b5a9259ba7c66c46bf657bb5ee43ab52e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832147"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a><span data-ttu-id="db703-104">Skype for Business Server の公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="db703-104">Public Key Infrastructure for Skype for Business Server</span></span>
 
<span data-ttu-id="db703-105">Skype for Business Server は、証明書を使用してサーバー認証を行い、クライアントとサーバー間、および異なるサーバーの役割間の信頼チェーンを確立します。</span><span class="sxs-lookup"><span data-stu-id="db703-105">Skype for Business Server relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="db703-106">Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、および Windows Server 2008 公開キー基盤 (PKI) は、この信頼チェーンを確立および検証するためのインフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="db703-106">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, and Windows Server 2008 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>
  
<span data-ttu-id="db703-107">証明書とはデジタル ID です。</span><span class="sxs-lookup"><span data-stu-id="db703-107">Certificates are digital IDs.</span></span> <span data-ttu-id="db703-108">証明書は、名前によってサーバーを識別し、そのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="db703-108">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="db703-109">証明書の情報が有効な場合は、サーバーに接続するクライアントまたは他のサーバーによって信頼されている CA が証明書を発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db703-109">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="db703-110">サーバーがプライベート ネットワーク上の他のクライアントおよびサーバーとのみ接続する場合は、CA はエンタープライズ CA で問題ありません。</span><span class="sxs-lookup"><span data-stu-id="db703-110">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="db703-111">サーバーがプライベート ネットワーク外のエンティティと対話する場合は、パブリック CA が必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="db703-111">If the server interacts with entities outside the private network, a public CA might be required.</span></span>
  
<span data-ttu-id="db703-p104">証明書の情報が有効であっても、証明書を提示しているサーバーが、実際に証明書によって提示されているサーバーであることを確認する手段が必要です。ここで Windows PKI が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="db703-p104">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>
  
<span data-ttu-id="db703-p105">各証明書は、公開キーにリンクされています。証明書で名前が指定されているサーバーには、そのサーバーのみが知る、対応する秘密キーがあります。接続しようとしているクライアントまたはサーバーは、公開キーを使用して無作為な情報の断片を暗号化し、それをサーバーに送信します。サーバーがその情報を復号化し、プレーン テキストに戻すと、接続しようとしているエンティティは、証明書の秘密キーをサーバーが保持していること、つまり、そのサーバーが証明書で指定されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="db703-p105">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="db703-118">すべてのパブリック CA が Skype for Business Server 証明書の要件に準拠している場合ではありません。</span><span class="sxs-lookup"><span data-stu-id="db703-118">Not all public CAs comply with the requirements of Skype for Business Server certificates.</span></span> <span data-ttu-id="db703-119">認定されているパブリック CA ベンダーの一覧を参照して、パブリック証明書のニーズに合ったベンダーを探すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="db703-119">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="db703-120">詳細については [、「Unified Communications Certificate Partners」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=140898)。</span><span class="sxs-lookup"><span data-stu-id="db703-120">For details, see [Unified Communications Certificate Partners](https://go.microsoft.com/fwlink/p/?LinkId=140898).</span></span> 
  
## <a name="crl-distribution-points"></a><span data-ttu-id="db703-121">CRL 配布ポイント</span><span class="sxs-lookup"><span data-stu-id="db703-121">CRL Distribution Points</span></span>

<span data-ttu-id="db703-122">Skype for Business Server では、すべてのサーバー証明書に 1 つ以上の証明書失効リスト (CRL) 配布ポイントが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="db703-122">Skype for Business Server requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="db703-123">CRL 配布ポイント (CDP) は、証明書が発行されて有効期間内に証明書が失効していないか確認するために、CRL をダウンロードできる場所です。</span><span class="sxs-lookup"><span data-stu-id="db703-123">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="db703-124">CRL 配布ポイントは、証明書のプロパティに URL として示され、通常はセキュリティで保護された HTTP です。</span><span class="sxs-lookup"><span data-stu-id="db703-124">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>
  
## <a name="enhanced-key-usage"></a><span data-ttu-id="db703-125">拡張キー使用法</span><span class="sxs-lookup"><span data-stu-id="db703-125">Enhanced Key Usage</span></span>

<span data-ttu-id="db703-126">Skype for Business Server では、サーバー認証の目的で、拡張キー使用法 (EKU) をサポートするためにすべてのサーバー証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="db703-126">Skype for Business Server requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="db703-127">サーバー認証用に EKU フィールドを構成すると、証明書はサーバーを認証する目的で有効になります。</span><span class="sxs-lookup"><span data-stu-id="db703-127">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="db703-128">この EKU は MTLS に不可欠です。</span><span class="sxs-lookup"><span data-stu-id="db703-128">This EKU is essential for MTLS.</span></span> <span data-ttu-id="db703-129">EKU に複数のエントリを含め、複数の目的に対して証明書を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="db703-129">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>
  

