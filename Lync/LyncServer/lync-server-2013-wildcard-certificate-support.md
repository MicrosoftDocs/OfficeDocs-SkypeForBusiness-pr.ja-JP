---
title: Lync Server 2013 のワイルドカード証明書のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 998787b3f052d2271eb2323bcdb71ddc106b57f6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="f791e-102">Lync Server 2013 でのワイルドカード証明書のサポート</span><span class="sxs-lookup"><span data-stu-id="f791e-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f791e-103">_**トピックの最終更新日:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="f791e-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="f791e-104">Lync Server 2013 は、証明書を使用して通信の暗号化とサーバー id 認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="f791e-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="f791e-105">リーバース プロキシ経由の Web 公開など、状況によっては、サービスを提供するサーバーの完全修飾ドメイン名 (FQDN) と一致する厳密なサブジェクトの別名 (SAN) エントリが不要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f791e-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="f791e-106">そのような場合には、ワイルドカード SAN エントリが含まれる証明書 (一般に "ワイルドカード証明書" といいます) を使用でき、それによって、公的証明機関から請求される証明書コストを削減し、証明書の計画プロセスの複雑さを緩和できます。</span><span class="sxs-lookup"><span data-stu-id="f791e-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f791e-107">統合コミュニケーション (UC) デバイス (電話など) の機能を保持するには、展開された証明書を十分にテストして、ワイルカード証明書を実装した後もデバイスが正しく動作することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f791e-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="f791e-p102">サブジェクト名 (共通名 (CN) ともいいます) としてのワイルドカード エントリは、どの役割でもサポートされません。SAN のワイルドカード エントリ使用は、次のサーバーの役割でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f791e-p102">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role. The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="f791e-110">**リバースプロキシ。**   簡単な URL (会議とダイヤルイン) 発行証明書では、ワイルドカード SAN エントリがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f791e-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="f791e-111">**リバースプロキシ。**   発行証明書の LYNCDISCOVER の san エントリでは、ワイルドカード san エントリがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f791e-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="f791e-112">**ディレクター。**   シンプルな url (会議とダイヤルイン)、およびディレクター web コンポーネントの LyncDiscover および LYNCDISCOVERINTERNAL の san エントリに対して、ワイルドカード SAN エントリがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f791e-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="f791e-113">**フロントエンドサーバー (Standard Edition) およびフロントエンドプール (Enterprise Edition)。**</span><span class="sxs-lookup"><span data-stu-id="f791e-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="f791e-114">簡単な Url (会議とダイヤルイン)、およびフロントエンド web コンポーネントの LyncDiscover および LyncDiscoverInternal の SAN エントリに対して、ワイルドカード SAN エントリがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f791e-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="f791e-115">**Exchange ユニファイドメッセージング (UM)。**   スタンドアロンサーバーとして展開されている場合、サーバーは SAN エントリを使用しません。</span><span class="sxs-lookup"><span data-stu-id="f791e-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="f791e-116">**Microsoft Exchange Server クライアントアクセスサーバー。**   SAN のワイルドカードエントリは、内部クライアントと外部クライアントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f791e-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="f791e-117">**同じサーバー上の exchange ユニファイドメッセージング (UM) と Microsoft Exchange Server クライアントアクセスサーバー。**   ワイルドカード SAN エントリがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f791e-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="f791e-118">次のサーバーの役割は、このトピックの対象外です。</span><span class="sxs-lookup"><span data-stu-id="f791e-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="f791e-119">内部サーバーの役割 (仲介サーバー、アーカイブおよび監視サーバー、存続可能ブランチアプライアンス、または存続可能ブランチサーバーに制限はありません)</span><span class="sxs-lookup"><span data-stu-id="f791e-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="f791e-120">外部エッジサーバーのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f791e-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="f791e-121">内部エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="f791e-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f791e-122">内部エッジサーバーインターフェイスでは、ワイルドカードエントリを SAN に割り当てることができ、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="f791e-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="f791e-123">内部エッジサーバー上の SAN はクエリされず、ワイルドカード SAN エントリの値が制限されます。</span><span class="sxs-lookup"><span data-stu-id="f791e-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="f791e-124">証明書にワイルドカードを使用するなど、証明書の構成の詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f791e-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="f791e-125">Lync Server 2013 の内部サーバーの証明書要件</span><span class="sxs-lookup"><span data-stu-id="f791e-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="f791e-126">Lync Server 2013 での外部ユーザーアクセスの証明書要件</span><span class="sxs-lookup"><span data-stu-id="f791e-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="f791e-127">証明書の概要-Lync Server 2013 での DNS および HLB の負荷分散</span><span class="sxs-lookup"><span data-stu-id="f791e-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="f791e-128">証明書の概要-Lync Server 2013 の単一ディレクター</span><span class="sxs-lookup"><span data-stu-id="f791e-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="f791e-129">証明書の概要-Lync Server 2013 の拡張ディレクタープール、ハードウェアロードバランサー</span><span class="sxs-lookup"><span data-stu-id="f791e-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="f791e-130">証明書の概要-Lync Server 2013 のリバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="f791e-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="f791e-131">オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="f791e-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="f791e-132">ワイルドカードの使用を含む、Exchange 用の証明書の構成の詳細については、「Exchange 2013 製品のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f791e-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

