---
title: Lync Server 2013 証明書インフラストラクチャの要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e8c96c6b4ad5e19abf2d1f41024932c710786cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="65cc3-102">Lync Server 2013 の証明書インフラストラクチャ要件</span><span class="sxs-lookup"><span data-stu-id="65cc3-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65cc3-103">_**トピックの最終更新日:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="65cc3-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="65cc3-104">Lync Server 2013 は、TLS および相互 TLS (MTLS) 接続をサポートするために公開キー基盤 (PKI) を必要とします。</span><span class="sxs-lookup"><span data-stu-id="65cc3-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="65cc3-105">Lync Server は、次の目的で証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="65cc3-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="65cc3-106">クライアントとサーバー間の TLS 接続</span><span class="sxs-lookup"><span data-stu-id="65cc3-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="65cc3-107">サーバー間の MTLS 接続</span><span class="sxs-lookup"><span data-stu-id="65cc3-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="65cc3-108">パートナーの自動 DNS 検出を使用するフェデレーション</span><span class="sxs-lookup"><span data-stu-id="65cc3-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="65cc3-109">インスタント メッセージング (IM) 用のリモート ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="65cc3-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="65cc3-110">音声/ビデオ (A/V) セッション、アプリケーション共有、および会議への外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="65cc3-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="65cc3-111">Web サービスの自動検出を使用するモバイル要求</span><span class="sxs-lookup"><span data-stu-id="65cc3-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="65cc3-112">Lync Server では、次の一般的な要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="65cc3-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="65cc3-113">すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。</span><span class="sxs-lookup"><span data-stu-id="65cc3-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="65cc3-114">すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。</span><span class="sxs-lookup"><span data-stu-id="65cc3-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="65cc3-115">すべての証明書は、オペレーティングシステムでサポートされている署名アルゴリズムを使用して署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cc3-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="65cc3-116">Lync Server 2013 では、ダイジェストサイズ (224、256、384、および512ビット) の SHA-1 および SHA-1 スイートがサポートされており、オペレーティングシステムの要件を満たしているか、それを超えています。</span><span class="sxs-lookup"><span data-stu-id="65cc3-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="65cc3-117">オペレーティングシステムのサポートについ[https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002)ては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cc3-117">For operating system support, see [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65cc3-118">RSASSA-PSS 署名アルゴリズムを使用することはサポートされていません。その他の問題の中では、ログイン時にエラーが発生し、転送の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65cc3-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="65cc3-119">Lync Server を実行している内部サーバーでは、自動登録がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="65cc3-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="65cc3-120">Lync Server エッジサーバーでは、自動登録がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65cc3-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="65cc3-121">Windows Server 2003 の CA に対して Web ベースの証明書要求を送信する場合は、Windows Server 2003 (SP2 適用済み) または Windows XP を実行しているコンピューターから送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cc3-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="65cc3-122">KB922706 は、Windows Server 2003 証明書サービスの Web 登録について Web 証明書の登録に関わる問題解決をサポートしますが、Windows Server 2008、Windows Vista、または Windows 7 を使用して、Windows Server 2003 CA から証明書を要求できるようにはなりません。</span><span class="sxs-lookup"><span data-stu-id="65cc3-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="65cc3-123">1024、2048、4096の暗号化キーの長さがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="65cc3-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="65cc3-124">2048以上のキーの長さは推奨されています。</span><span class="sxs-lookup"><span data-stu-id="65cc3-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="65cc3-125">既定のダイジェスト、つまりハッシュ署名は RSA です。</span><span class="sxs-lookup"><span data-stu-id="65cc3-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="65cc3-126">ECDH\_P256、ecdh\_P384、および ecdh\_P521 の各アルゴリズムもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="65cc3-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="65cc3-127">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="65cc3-127">In This Section</span></span>

  - [<span data-ttu-id="65cc3-128">Lync Server 2013 の内部サーバーの証明書要件</span><span class="sxs-lookup"><span data-stu-id="65cc3-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="65cc3-129">Lync Server 2013 での外部ユーザーアクセスの証明書要件</span><span class="sxs-lookup"><span data-stu-id="65cc3-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="65cc3-130">Lync Server 2013 の常設チャットサーバーの証明書要件</span><span class="sxs-lookup"><span data-stu-id="65cc3-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="65cc3-131">Lync Server 2013 でのモビリティの証明書要件</span><span class="sxs-lookup"><span data-stu-id="65cc3-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

