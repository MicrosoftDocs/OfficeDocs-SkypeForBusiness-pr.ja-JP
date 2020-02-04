---
title: 'Lync Server 2013: 外部ユーザー アクセスに対する証明書要件'
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
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="3f98a-102">Lync Server 2013 における外部ユーザー アクセスに対する証明書要件</span><span class="sxs-lookup"><span data-stu-id="3f98a-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f98a-103">_**最終更新日:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="3f98a-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="3f98a-104">Microsoft Lync Server 2013 通信ソフトウェアは、アクセスおよび web 会議エッジの外部インターフェイスに加えて、A/V 認証サービスによる単一のパブリック証明書の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3f98a-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="3f98a-105">通常、Edge 内部インターフェイスでは、内部証明機関 (CA) によって発行されたプライベート証明書を使用しますが、信頼できる公開 CA から提供されている公開証明書を使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="3f98a-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="3f98a-106">展開内のリバースプロキシは、公開証明書を使用して、リバースプロキシからクライアントへの通信と、HTTP (つまり、HTTP を経由したトランスポートレイヤーのセキュリティ) を使用した内部サーバーへの通信を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="3f98a-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="3f98a-107">Access および web 会議エッジの外部インターフェイスと A/V 認証サービスで使用される公開証明書の要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3f98a-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="3f98a-108">証明書は、サブジェクト代替名をサポートする承認済みのパブリック CA によって発行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f98a-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="3f98a-109">詳細については、Microsoft サポート技術情報の記事929395「Exchange Server および通信サーバーのユニファイドコミュニケーション証明書[http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)パートナー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f98a-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="3f98a-110">エッジプールで証明書を使用する場合は、エッジプールの各エッジサーバーで使用されるものと同じ証明書を使って、エクスポート可能として作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f98a-110">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="3f98a-111">エクスポート可能な秘密キーの要件は、A/V 認証サービスの目的であり、プール内のすべてのエッジサーバーで同じ秘密キーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f98a-111">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="3f98a-112">オーディオ/ビデオサービスの稼働時間を最大化する必要がある場合は、分離型 A/V エッジサービス証明書を実装するための証明書要件を確認します (つまり、他の外部エッジ証明書の目的に関する個別の A/V Edge サービス証明書です)。</span><span class="sxs-lookup"><span data-stu-id="3f98a-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="3f98a-113">詳細については、「 [lync server の計画に影響を与える lync server 2013 の変更点](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)」を参照してください。 lync server [2013 でのエッジサーバーの証明](lync-server-2013-plan-for-edge-server-certificates.md)書と、lync server [2013 での [ステージング AV] および [OAuth 証明書] を使用して、[設定-cscertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3f98a-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="3f98a-114">証明書のサブジェクト名は、アクセスエッジサービスの外部インターフェイスの完全修飾ドメイン名 (FQDN) またはハードウェアロードバランサー VIP (たとえば、access.contoso.com) です。</span><span class="sxs-lookup"><span data-stu-id="3f98a-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="3f98a-115">).</span><span class="sxs-lookup"><span data-stu-id="3f98a-115">).</span></span> <span data-ttu-id="3f98a-116">サブジェクト名にワイルドカード文字を使用することはできません。明示的な名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f98a-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f98a-117">Lync Server 2013 の場合、これは必須ではありませんが、Office Communications Server との互換性を確保することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3f98a-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="3f98a-118">サブジェクト代替名の一覧には、次の Fqdn が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f98a-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="3f98a-119">アクセスエッジサービスの外部インターフェイスまたはハードウェアロードバランサー VIP (たとえば、sip.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="3f98a-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3f98a-120">証明書の件名はアクセスエッジ FQDN と同じですが、トランスポート層セキュリティ (TLS) ではサブジェクト名が無視され、サブジェクトの代替名エントリが使用されるため、アクセスエッジの fqdn を含める必要があります。入力規則.</span><span class="sxs-lookup"><span data-stu-id="3f98a-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="3f98a-121">Web 会議エッジの外部インターフェイスまたはハードウェアのロードバランサー VIP (たとえば、webcon.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="3f98a-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="3f98a-122">クライアントの自動構成またはフェデレーションを使用している場合は、会社内で使用されている SIP ドメイン Fqdn も含めます (たとえば、sip.contoso.com、sip.fabrikam.com)。</span><span class="sxs-lookup"><span data-stu-id="3f98a-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="3f98a-123">A/V Edge サービスでは、サブジェクト名、またはサブジェクトの代替名のエントリは使用されません。</span><span class="sxs-lookup"><span data-stu-id="3f98a-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f98a-124">[サブジェクト代替名] リストの Fqdn の順序は問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="3f98a-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="3f98a-125">複数の負荷分散エッジサーバーをサイトに展開している場合は、各エッジサーバーにインストールされている A/V 認証サービスの証明書が同じ CA からのものであり、同じ秘密キーを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f98a-125">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="3f98a-126">証明書の秘密キーは、1つのエッジサーバーで使用するか、多数のエッジサーバーで使用するかに関係なく、エクスポート可能である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3f98a-126">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="3f98a-127">また、エッジサーバー以外のコンピューターから証明書を要求した場合も、エクスポート可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f98a-127">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="3f98a-128">A/V 認証サービスではサブジェクト名またはサブジェクトの別名を使用しないため、アクセスエッジおよび web 会議エッジに対してサブジェクト名と件名の代替名の要件が満たされている限り、アクセスエッジ証明書を再利用することができます。また、証明書の秘密キーはエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="3f98a-128">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="3f98a-129">エッジ内部インターフェイスに使用されるプライベート (またはパブリック) 証明書の要件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f98a-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="3f98a-130">証明書は、内部 CA または承認された公開証明機関によって発行できます。</span><span class="sxs-lookup"><span data-stu-id="3f98a-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="3f98a-131">証明書のサブジェクト名は、通常、エッジ内部インターフェイス FQDN またはハードウェアロードバランサー VIP (lsedge.contoso.com など) です。</span><span class="sxs-lookup"><span data-stu-id="3f98a-131">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="3f98a-132">ただし、内部でワイルドカード証明書を使用することはできます。</span><span class="sxs-lookup"><span data-stu-id="3f98a-132">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="3f98a-133">件名の代替名リストは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="3f98a-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="3f98a-134">展開サービスが要求するリバースプロキシ:</span><span class="sxs-lookup"><span data-stu-id="3f98a-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="3f98a-135">会議の会議コンテンツへの外部ユーザーアクセス</span><span class="sxs-lookup"><span data-stu-id="3f98a-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="3f98a-136">配布グループのメンバーを展開して表示するための外部ユーザーアクセス</span><span class="sxs-lookup"><span data-stu-id="3f98a-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="3f98a-137">アドレス帳サービスからダウンロード可能なファイルへの外部ユーザーアクセス</span><span class="sxs-lookup"><span data-stu-id="3f98a-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="3f98a-138">Lync Web App クライアントへの外部ユーザーアクセス</span><span class="sxs-lookup"><span data-stu-id="3f98a-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="3f98a-139">[ダイヤルイン会議の設定] web ページへの外部ユーザーアクセス</span><span class="sxs-lookup"><span data-stu-id="3f98a-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="3f98a-140">位置情報サービスへの外部ユーザーアクセス</span><span class="sxs-lookup"><span data-stu-id="3f98a-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="3f98a-141">デバイス更新サービスへの外部デバイスアクセスと更新プログラムの入手</span><span class="sxs-lookup"><span data-stu-id="3f98a-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="3f98a-142">リバースプロキシは、内部サーバー Web コンポーネントの Url を公開します。</span><span class="sxs-lookup"><span data-stu-id="3f98a-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="3f98a-143">Web コンポーネントの Url は、監督、フロントエンドサーバー、またはフロントエンドプールで、トポロジビルダーの**外部 Web サービス**として定義されています。</span><span class="sxs-lookup"><span data-stu-id="3f98a-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="3f98a-144">逆プロキシに割り当てられている証明書のサブジェクトの別名フィールドでは、ワイルドカードエントリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3f98a-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="3f98a-145">リバースプロキシの証明書の要求を構成する方法の詳細については、「 [Lync Server 2013 でリバース HTTP プロキシ用の証明書を要求および構成](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f98a-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3f98a-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f98a-146">See Also</span></span>


[<span data-ttu-id="3f98a-147">Lync Server 2013 のワイルドカード証明書のサポート</span><span class="sxs-lookup"><span data-stu-id="3f98a-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

