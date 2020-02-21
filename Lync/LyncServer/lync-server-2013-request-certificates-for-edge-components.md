---
title: 'Lync Server 2013: エッジコンポーネントの証明書の要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b023ac5c9023e6a301e490e7f081c31628195247
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="aa62a-102">Lync Server 2013 のエッジコンポーネントの証明書を要求する</span><span class="sxs-lookup"><span data-stu-id="aa62a-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa62a-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="aa62a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="aa62a-104">外部ユーザー アクセスのサポートに必要な証明書には、パブリック証明機関 (CA) が発行する証明書および内部のエンタープライズ CA が発行する証明書があります。</span><span class="sxs-lookup"><span data-stu-id="aa62a-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="aa62a-105">エッジサーバーとリバースプロキシの外部インターフェイスに必要な証明書は、パブリック CA によって発行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa62a-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="aa62a-106">内部インターフェイスに必要な証明書は、パブリック CA または内部のエンタープライズ CA のいずれかによって発行された証明書にすることができます。</span><span class="sxs-lookup"><span data-stu-id="aa62a-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="aa62a-107">公開証明書を使用する費用を節約するためにこれらの証明書を作成するには、内部 Windows Server 2008 CA、windows server 2008 R2 CA、windows server 2012 CA、または Windows Server 2012 R2 CA を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aa62a-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aa62a-108">証明書要求、特にパブリック CA への要求の処理には時間がかかるため、エッジ サーバーへの証明書は早めに要求して、エッジ サーバー コンポーネントの展開を開始する頃には使用できるようにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa62a-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="aa62a-109">エッジサーバーの証明書要件の概要については、「 <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 の外部ユーザーアクセスの証明書要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa62a-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="aa62a-110">内部エッジの証明書にパブリック CA を使用するという選択肢もありますが、証明書のコストを最小限に抑える代わりに、これらの他の証明書には内部エンタープライズ CA を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aa62a-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="aa62a-111">エッジサーバーの証明書要件の概要については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa62a-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa62a-112">エッジサーバーをインストールする場合、セットアップには、「 <A href="lync-server-2013-set-up-edge-certificates.md">Lync server 2013 のエッジ証明書の</A>セットアップ」セクションで説明されているように、証明書の要求、割り当て、およびインストールのタスクを容易にする証明書ウィザードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aa62a-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="aa62a-113">エッジサーバーをインストールする前に証明書を要求する必要がある場合 (たとえば、エッジサーバーコンポーネントの実際の展開時に時間を節約する場合など)、証明書をエクスポートして、すべてのを含めることができる限り、内部サーバーを使用することができます。必須のサブジェクトの別名。</span><span class="sxs-lookup"><span data-stu-id="aa62a-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="aa62a-114">このドキュメントでは、内部サーバーを使用して証明書を要求する手順については説明しません。</span><span class="sxs-lookup"><span data-stu-id="aa62a-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="aa62a-115">証明書をパブリック CA に要求する</span><span class="sxs-lookup"><span data-stu-id="aa62a-115">Request certificates from a public CA</span></span>

<span data-ttu-id="aa62a-116">エッジサーバーの展開では、エッジサーバーの外部インターフェイスに対して単一のパブリック証明書が必要です。これは、アクセスエッジサービス、Web 会議エッジサービス、および音声ビデオ認証サービスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa62a-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="aa62a-117">この証明書には、A/V 認証サービスがプール内のすべてのエッジサーバーで同じキーを使用するようにするための、エクスポート可能な秘密キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="aa62a-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="aa62a-118">リバースプロキシは、Microsoft Internet Security and アクセラレーション (ISA) サーバー2006または Microsoft Forefront Threat Management Gateway 2010 で使用されています。また、パブリック証明書も必要です。</span><span class="sxs-lookup"><span data-stu-id="aa62a-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="aa62a-119">証明書を内部エンタープライズ CA に要求する</span><span class="sxs-lookup"><span data-stu-id="aa62a-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="aa62a-p106">内部エッジ インターフェイスに必要な証明書は、パブリック証明機関 (CA) または内部 CA から発行されます。 内部エンタープライズ CA を使用して、証明書のコストを最小限に抑えることができます。 組織で内部 CA が展開されている場合、内部エッジの証明書は内部 CA から発行されます。 内部証明書に内部エンタープライズ CA を使用すると、証明書のコストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="aa62a-p106">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA. You can use an internal enterprise CA to help minimize the cost of certificates. If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA. Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="aa62a-124">エッジコンポーネントの証明書要件の概要については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa62a-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="aa62a-125">パブリック CA を使用した証明書の取得の詳細については、「 [Lync Server 2013 のエッジコンポーネントの証明書を要求](lync-server-2013-request-certificates-for-edge-components.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa62a-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="aa62a-126">証明書の要求、インストール、および割り当ての詳細については、「 [Lync Server 2013 のエッジ証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa62a-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

