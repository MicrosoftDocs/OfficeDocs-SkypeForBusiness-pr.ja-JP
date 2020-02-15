---
title: 'Lync Server 2013: TLS と MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7681b3394a640a64966e3b9c739ea085e6c0f2f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="29e1c-102">Lync Server 2013 の TLS と MTLS</span><span class="sxs-lookup"><span data-stu-id="29e1c-102">TLS and MTLS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29e1c-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="29e1c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="29e1c-104">トランスポート層セキュリティ (TLS) と相互トランスポート層セキュリティ (MTLS) プロトコルは、インターネット上で暗号化された通信とエンドポイント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="29e1c-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="29e1c-105">Microsoft Lync Server 2013 は、これら2つのプロトコルを使用して、信頼されたサーバーのネットワークを作成し、そのネットワーク上のすべての通信が暗号化されるようにします。</span><span class="sxs-lookup"><span data-stu-id="29e1c-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="29e1c-106">サーバー間のすべての SIP 通信は MTLS 経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="29e1c-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="29e1c-107">クライアントからサーバーへの SIP 通信は TLS 経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="29e1c-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="29e1c-108">TLS を使用すると、ユーザーはクライアントソフトウェアを使用して、接続先の Lync Server 2013 サーバーを認証できます。</span><span class="sxs-lookup"><span data-stu-id="29e1c-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="29e1c-109">TLS 接続の場合、クライアントはサーバーから有効な証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="29e1c-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="29e1c-110">有効にするには、証明書がクライアントによっても信頼された CA によって発行されていて、サーバーの DNS 名が証明書の DNS 名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e1c-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="29e1c-111">証明書が有効な場合、クライアントは証明書の公開キーを使用して、通信に使用される対称暗号化キーを暗号化します。そのため、証明書の元の所有者のみが秘密キーを使用して通信の内容を復号化できます。</span><span class="sxs-lookup"><span data-stu-id="29e1c-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="29e1c-112">その結果、接続は信頼され、その時点から、他の信頼されたサーバーまたはクライアントによるチャレンジは行われません。</span><span class="sxs-lookup"><span data-stu-id="29e1c-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="29e1c-113">このコンテキストでは、Web サービスで使用される Secure Sockets Layer (SSL) を TLS ベースとして関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="29e1c-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="29e1c-114">サーバー間接続は相互認証のために MTLS に依存します。</span><span class="sxs-lookup"><span data-stu-id="29e1c-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="29e1c-115">MTLS 接続では、メッセージを送信したサーバーとそれを受信するサーバーが、相互に信頼された CA からの証明書を交換します。</span><span class="sxs-lookup"><span data-stu-id="29e1c-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="29e1c-116">証明書によって、各サーバーの id が他のサーバーに対して証明されます。</span><span class="sxs-lookup"><span data-stu-id="29e1c-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="29e1c-117">Lync Server 2013 の展開では、エンタープライズ CA によって発行された証明書の有効期間中で、発行元 CA によって取り消されていないものは、Active Directory ドメインのすべてのメンバーが、すべての内部クライアントおよびサーバーで自動的に有効と見なされます。そのドメイン内のエンタープライズ CA を信頼します。</span><span class="sxs-lookup"><span data-stu-id="29e1c-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="29e1c-118">フェデレーションのシナリオでは、発行元の CA が両方のフェデレーションパートナーによって信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e1c-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="29e1c-119">各パートナーは、必要に応じて、その CA が他のパートナーによっても信頼されている場合は、異なる CA を使用できます。</span><span class="sxs-lookup"><span data-stu-id="29e1c-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="29e1c-120">この信頼は、エッジサーバーが信頼されたルート ca にパートナーのルート CA 証明書を持っているか、または両方の所有者によって信頼されているサードパーティの CA を使用することによって、最も簡単に実現できます。</span><span class="sxs-lookup"><span data-stu-id="29e1c-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="29e1c-121">TLS と MTLS は、盗聴と man-in-the-middle 攻撃の両方を防止するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="29e1c-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="29e1c-122">Man-in-the-middle 攻撃では、攻撃者は2つのネットワークエンティティ間の通信を、いずれかの当事者を認識することなく、攻撃者のコンピューターを経由して再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="29e1c-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="29e1c-123">TLS および Lync Server 2013 の信頼済みサーバー (トポロジビルダーで指定されたもののみ) の仕様では、公開キー暗号化を使用して調整されたエンドツーエンドの暗号化を使用することによって、アプリケーション層で部分的に攻撃を受けるリスクを軽減します。2つのエンドポイント間、および攻撃者は、対応する秘密キーを持つ有効な信頼された証明書を持っており、クライアントが通信を暗号化するために通信するサービスの名前に発行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e1c-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="29e1c-124">ただし、最終的には、ネットワークインフラストラクチャ (この場合は、企業 DNS) について、セキュリティに関するベストプラクティスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e1c-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="29e1c-125">Lync Server 2013 は、ドメインコントローラーとグローバルカタログが信頼されているのと同じ方法で DNS サーバーが信頼されていると想定していますが、dns は、攻撃者のサーバーが正常に応答しないようにすることによって、dns ハイジャック攻撃に対する保護レベルを提供します。詐称された名前への要求。</span><span class="sxs-lookup"><span data-stu-id="29e1c-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="29e1c-126">次の図は、Lync Server 2013 が MTLS を使用して、信頼されたサーバーのネットワークを作成する方法の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="29e1c-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="29e1c-127">**Lync Server ネットワークの信頼された接続**</span><span class="sxs-lookup"><span data-stu-id="29e1c-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="29e1c-128">![437749da2-c372-4fkbs 2-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da2-c372-4fkbs 2-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="29e1c-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

