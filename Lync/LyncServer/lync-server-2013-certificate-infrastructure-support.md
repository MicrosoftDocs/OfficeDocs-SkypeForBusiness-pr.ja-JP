---
title: Lync Server 2013 の証明書インフラストラクチャのサポート
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
ms.openlocfilehash: dc8cb5bdad02de4fcb407d7eb27960258a46dd3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="ad576-102">Lync Server 2013 での証明書インフラストラクチャのサポート</span><span class="sxs-lookup"><span data-stu-id="ad576-102">Certificate infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad576-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ad576-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ad576-104">Lync Server 2013 では、トランスポート層セキュリティ (TLS) と相互 TLS (MTLS) 接続をサポートするために公開キー基盤 (PKI) が必要です。</span><span class="sxs-lookup"><span data-stu-id="ad576-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="ad576-105">既定では、Lync Server 2013 は、クライアントとサーバー間の接続に TLS を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="ad576-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="ad576-106">MTLS は、サーバー間の接続に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad576-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="ad576-107">MTLS 証明書は、Lync Server 2013 の信頼された証明機関 (Ca) によって発行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad576-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="ad576-108">Lync Server は、次の Ca から発行された証明書をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ad576-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="ad576-109">内部 CA から発行された証明書:</span><span class="sxs-lookup"><span data-stu-id="ad576-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="ad576-110">Windows Server 2003 オペレーティングシステム CA</span><span class="sxs-lookup"><span data-stu-id="ad576-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="ad576-111">Windows Server 2008 オペレーティングシステム CA</span><span class="sxs-lookup"><span data-stu-id="ad576-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="ad576-112">Windows Server 2008 R2 オペレーティングシステム CA</span><span class="sxs-lookup"><span data-stu-id="ad576-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="ad576-113">Windows Server 2012 オペレーティングシステム CA</span><span class="sxs-lookup"><span data-stu-id="ad576-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="ad576-114">Windows Server 2012 R2 オペレーティングシステム CA</span><span class="sxs-lookup"><span data-stu-id="ad576-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="ad576-115">パブリック CA から発行された証明書</span><span class="sxs-lookup"><span data-stu-id="ad576-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="ad576-116">他のアプリケーションやサーバー (Exchange 2013 など) との通信には、他のアプリケーションや製品でサポートされている証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="ad576-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="ad576-117">2013リリース、Lync Server 2013、および Exchange 2013 および SharePoint Server を含むその他の Microsoft サーバー製品については、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ad576-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="ad576-118">詳細については、展開ドキュメントまたは運用マニュアルの「 [Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad576-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="ad576-119">Windows 7 オペレーティングシステム、Windows Server 2008 R2 オペレーティングシステム、および Microsoft Office Communicator 2007 Phone Edition を実行しているクライアントからの接続の場合、Lync Server 2013 は、SHA-256 を使用して署名された証明書をサポートしています (ただし必須ではありません)。暗号化ハッシュ関数。</span><span class="sxs-lookup"><span data-stu-id="ad576-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="ad576-120">SHA-256 を使って外部アクセスをサポートするために、外部証明書は SHA-256 を使ってパブリック CA によって発行されます。</span><span class="sxs-lookup"><span data-stu-id="ad576-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="ad576-121">証明書の要件の詳細については、「計画ドキュメントの「 [Lync Server 2013 の証明書インフラストラクチャの要件](lync-server-2013-certificate-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad576-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="ad576-122">証明書でのワイルドカードの使用の詳細については、サポートドキュメントの「 [Lync Server 2013 でのワイルドカード証明書のサポート](lync-server-2013-wildcard-certificate-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad576-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

