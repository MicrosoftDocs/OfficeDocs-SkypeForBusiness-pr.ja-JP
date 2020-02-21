---
title: 'Lync Server 2013: 外部ユーザーアクセスの証明書要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda45706b8c55bf99120ec3776702060998a6921
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="46d7d-102">Lync Server 2013 での外部ユーザーアクセスの証明書要件</span><span class="sxs-lookup"><span data-stu-id="46d7d-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46d7d-103">_**トピックの最終更新日:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="46d7d-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="46d7d-104">Microsoft Lync Server 2013 communications software は、アクセスおよび web 会議エッジの外部インターフェイスに対する単一のパブリック証明書、および音声ビデオ認証サービスの使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="46d7d-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="46d7d-105">エッジ内部インターフェイスでは、通常であれば内部証明機関 (CA) が発行するプライベート証明書を使用しますが、信頼されたパブリック CA が発行したものであればパブリック証明書も使用できます。</span><span class="sxs-lookup"><span data-stu-id="46d7d-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="46d7d-106">展開のリバース プロキシでは、パブリック証明書を使用し、リバース プロキシからクライアントへの通信およびリバース プロキシから内部サーバーへの通信を、HTTP を使用して暗号化します (つまり、Transport Layer Security over HTTP)。</span><span class="sxs-lookup"><span data-stu-id="46d7d-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="46d7d-107">以下に、アクセスおよび Web 会議のエッジ外部インターフェイスで使用されるパブリック証明書、および音声ビデオ認証サービスの要件を示します。</span><span class="sxs-lookup"><span data-stu-id="46d7d-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="46d7d-108">証明書は、サブジェクトの別名をサポートする承認されたパブリック CA によって発行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d7d-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="46d7d-109">詳細については、Microsoft サポート技術情報の記事929395「Exchange Server と通信サーバーのための統合コミュニケーション証明[https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)書パートナー」 () を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d7d-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="46d7d-p103">証明書をエッジ プールで使用する場合は、エッジ プール内の各エッジ サーバーで使用される同じ証明書を使用して、エクスポート可能として作成する必要があります。エクスポート可能な秘密キーの要件は音声ビデオ認証サービスのためのもので、プール内のすべてのエッジ サーバーで同じ秘密キーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d7d-p103">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool. The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="46d7d-112">音声ビデオサービスの稼働時間を最大にする場合は、分離された音声ビデオエッジサービス証明書を実装するための証明書の要件を確認します (つまり、他の外部エッジ証明書の目的からの個別の音声ビデオエッジサービス証明書)。</span><span class="sxs-lookup"><span data-stu-id="46d7d-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="46d7d-113">詳細については、「[変更2013点](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)」を参照してください。エッジサーバーの計画、「lync server [2013 でのエッジサーバー証明書の計画](lync-server-2013-plan-for-edge-server-certificates.md)」、および「Lync server [2013 のステージングの AV および OAuth 証明書を使用した設定-cscertificate」](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d7d-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="46d7d-114">証明書のサブジェクト名は、アクセスエッジサービスの外部インターフェイスの完全修飾ドメイン名 (FQDN) またはハードウェアロードバランサーの VIP (たとえば、access.contoso.com) です。</span><span class="sxs-lookup"><span data-stu-id="46d7d-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="46d7d-115">).</span><span class="sxs-lookup"><span data-stu-id="46d7d-115">).</span></span> <span data-ttu-id="46d7d-116">サブジェクト名にワイルドカード文字を使用することはできません。明示的な名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d7d-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46d7d-117">Lync Server 2013 の場合、これは要件ではありませんが、Office Communications Server との互換性を維持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="46d7d-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="46d7d-118">サブジェクトの別名リストには、以下のコンポーネントの FQDN が含まれています。</span><span class="sxs-lookup"><span data-stu-id="46d7d-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="46d7d-119">アクセスエッジサービスの外部インターフェイスまたはハードウェアロードバランサーの VIP (たとえば、sip.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="46d7d-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="46d7d-120">証明書のサブジェクト名はアクセス エッジの FQDN と等しくなりますが、サブジェクトの別名にもアクセス エッジの FQDN を含める必要があります。これは、トランスポート層セキュリティ (TLS) がサブジェクト名を無視し、検証でサブジェクトの別名エントリを使用するからです。</span><span class="sxs-lookup"><span data-stu-id="46d7d-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="46d7d-121">Web 会議エッジ外部インターフェイスまたはハードウェア ロード バランサーの VIP (たとえば、webcon.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="46d7d-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="46d7d-122">クライアントの自動構成またはフェデレーションを使用し、会社内で使用されるすべての SIP ドメインの FQDN を含める場合 (たとえば、sip.contoso.com や sip.fabrikam.com)。</span><span class="sxs-lookup"><span data-stu-id="46d7d-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="46d7d-123">音声ビデオエッジサービスでは、サブジェクト名またはサブジェクトの別名エントリは使用されません。</span><span class="sxs-lookup"><span data-stu-id="46d7d-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46d7d-124">サブジェクトの別名リストでの FQDN の順番は問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="46d7d-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="46d7d-p106">1 つのサイトで負荷分散が有効な複数のエッジ サーバーを展開する場合、各エッジ サーバーにインストールする音声ビデオ認証サービス証明書は、同じ CA が発行したもので、同じ秘密キーを使用する必要があります。証明書の秘密キーは、1 つのエッジ サーバーと多くのエッジ サーバーのどちらで使用するかに関係なく、エクスポート可能にする必要があります。また、エッジ サーバー以外のコンピューターから証明書を要求する場合にもエクスポート可能にする必要があります。音声ビデオ認証サービスはサブジェクト名またはサブジェクトの別名を使用しないので、サブジェクト名およびサブジェクトの別名の要件がアクセス エッジおよび Web 会議エッジに対して満たされていて、証明書の秘密キーがエクスポート可能である限り、アクセス エッジ証明書を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="46d7d-p106">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key. Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers. It must also be exportable if you request the certificate from any computer other than the Edge Server. Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="46d7d-129">エッジ内部インターフェイスで使用するプライベート (またはパブリック) 証明書の要件は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="46d7d-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="46d7d-130">証明書は、内部 CA または承認されたパブリック証明書 CA が発行できます。</span><span class="sxs-lookup"><span data-stu-id="46d7d-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="46d7d-p107">証明書のサブジェクト名は、通常、エッジ内部インターフェイスの FQDN またはハードウェア ロード バランサーの VIP (たとえば、lsedge.contoso.com) です。 ただし、エッジ内部でワイルドカード証明書を使用できます。</span><span class="sxs-lookup"><span data-stu-id="46d7d-p107">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com). However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="46d7d-133">必須のサブジェクトの別名リストはありません。</span><span class="sxs-lookup"><span data-stu-id="46d7d-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="46d7d-134">展開サービス内のリバース プロキシは、以下のことを要求します。</span><span class="sxs-lookup"><span data-stu-id="46d7d-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="46d7d-135">会議の会議コンテンツへの外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="46d7d-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="46d7d-136">配布グループのメンバーを展開および表示するための外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="46d7d-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="46d7d-137">アドレス帳サービスからダウンロード可能なファイルへの外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="46d7d-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="46d7d-138">Lync Web App クライアントへの外部ユーザーアクセス</span><span class="sxs-lookup"><span data-stu-id="46d7d-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="46d7d-139">[ダイヤルイン会議の設定] Web ページへの外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="46d7d-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="46d7d-140">場所情報サービスへの外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="46d7d-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="46d7d-141">デバイス更新サービスおよび更新の取得への外部デバイス アクセス</span><span class="sxs-lookup"><span data-stu-id="46d7d-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="46d7d-142">リバース プロキシは、内部サーバーの Web コンポーネント URL を発行します。</span><span class="sxs-lookup"><span data-stu-id="46d7d-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="46d7d-143">Web コンポーネントの Url は、トポロジビルダーの**外部 Web サービス**として、ディレクター、フロントエンドサーバー、またはフロントエンドプールで定義されます。</span><span class="sxs-lookup"><span data-stu-id="46d7d-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="46d7d-144">リバース プロキシに割り当てられている証明書のサブジェクトの別名フィールドでは、ワイルドカードの入力がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="46d7d-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="46d7d-145">リバースプロキシの証明書要求を構成する方法の詳細については、「 [Lync Server 2013 のリバース HTTP プロキシの証明書を要求および構成](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d7d-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="46d7d-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="46d7d-146">See Also</span></span>


[<span data-ttu-id="46d7d-147">Lync Server 2013 でのワイルドカード証明書のサポート</span><span class="sxs-lookup"><span data-stu-id="46d7d-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

