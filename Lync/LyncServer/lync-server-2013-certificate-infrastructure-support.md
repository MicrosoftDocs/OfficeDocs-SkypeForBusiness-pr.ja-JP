---
title: Lync Server 2013 証明書インフラストラクチャのサポート
description: Lync Server 2013 証明書インフラストラクチャのサポート。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc08719e5b1c58a4dc3c1cab07db5e9842d46d5c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544233"
---
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="0cbbf-103">Lync Server 2013 での証明書インフラストラクチャのサポート</span><span class="sxs-lookup"><span data-stu-id="0cbbf-103">Certificate infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cbbf-104">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="0cbbf-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0cbbf-105">Lync Server 2013 は、トランスポート層セキュリティ (TLS) と相互 TLS (MTLS) 接続をサポートするために公開キー基盤 (PKI) を必要とします。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-105">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="0cbbf-106">既定では、Lync Server 2013 は、クライアントとサーバー間の接続に TLS を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-106">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="0cbbf-107">MTLS は、サーバー間の接続に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-107">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="0cbbf-108">MTLS 証明書は、Lync Server 2013 の信頼された証明機関 (CAs) によって発行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-108">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="0cbbf-109">Lync Server は、次の Ca から発行された証明書をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-109">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="0cbbf-110">内部 CA から発行される証明書:</span><span class="sxs-lookup"><span data-stu-id="0cbbf-110">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="0cbbf-111">Windows Server 2003 オペレーティングシステムの CA</span><span class="sxs-lookup"><span data-stu-id="0cbbf-111">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="0cbbf-112">Windows Server 2008 オペレーティングシステムの CA</span><span class="sxs-lookup"><span data-stu-id="0cbbf-112">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="0cbbf-113">Windows Server 2008 R2 オペレーティングシステムの CA</span><span class="sxs-lookup"><span data-stu-id="0cbbf-113">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="0cbbf-114">Windows Server 2012 オペレーティングシステムの CA</span><span class="sxs-lookup"><span data-stu-id="0cbbf-114">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="0cbbf-115">Windows Server 2012 R2 オペレーティングシステムの CA</span><span class="sxs-lookup"><span data-stu-id="0cbbf-115">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="0cbbf-116">パブリック CA から発行される証明書</span><span class="sxs-lookup"><span data-stu-id="0cbbf-116">Certificates issued from a public CA</span></span>

<span data-ttu-id="0cbbf-117">Exchange 2013 などの他のアプリケーションやサーバーと通信するには、他のアプリケーションと製品でサポートされている証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-117">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="0cbbf-118">2013リリース、Lync Server 2013、および Exchange 2013 および SharePoint Server を含むその他の Microsoft サーバー製品については、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-118">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="0cbbf-119">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-119">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="0cbbf-120">Windows 7 オペレーティングシステム、Windows Server 2008 R2 オペレーティングシステム、および Microsoft Office Communicator 2007 Phone Edition を実行しているクライアントからの接続については、Lync Server 2013 では、SHA-256 暗号化ハッシュ関数を使用して署名された証明書をサポートしていますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-120">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="0cbbf-121">SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-121">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="0cbbf-122">証明書の要件の詳細については、「計画」のドキュメントの「 [Lync Server 2013 の証明書インフラストラクチャ要件](lync-server-2013-certificate-infrastructure-requirements.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-122">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="0cbbf-123">証明書でのワイルドカードの使用の詳細については、「サポート」のドキュメントの「 [Lync Server 2013 でのワイルドカード証明書のサポート](lync-server-2013-wildcard-certificate-support.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cbbf-123">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

