---
title: 'Lync Server 2013: エッジサーバーの証明書の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3fc6ab9bfb6d145b324c079e4bf746354e7329f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519854"
---
# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="b3319-102">Lync Server 2013 でエッジサーバー証明書を計画する</span><span class="sxs-lookup"><span data-stu-id="b3319-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3319-103">_**トピックの最終更新日:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="b3319-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="b3319-104">Lync Server 2013 では、エッジの証明書の作成が簡略化されています。</span><span class="sxs-lookup"><span data-stu-id="b3319-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="b3319-105">**エッジ サーバーの証明書のフロー チャート**</span><span class="sxs-lookup"><span data-stu-id="b3319-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="b3319-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="b3319-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="b3319-107">単一のパブリック証明書を作成し、その証明書用に定義されたエクスポート可能な秘密キーがあることを確認した後、証明書ウィザードを使用して次のエッジ サーバー外部インターフェイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b3319-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3319-108">ワイルドカード証明書は Lync Server ではサポートされていませんが、リバースプロキシを介して簡易 Url を要約するために使用される場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="b3319-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="b3319-109">展開で提供される SIP ドメイン名、Web 会議エッジサービス、音声ビデオエッジサービス、および XMPP ドメインごとに、個別のサブジェクト代替名 (San) を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3319-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b3319-110">Lync Server 2013 で導入された、現在の証明書の有効期限が切れる前に、オーディオ/ビデオ認証証明書をステージングするには、追加の計画が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b3319-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="b3319-111">外部エッジインターフェイスに複数の目的を持つ1つの証明書を使用するのではなく、アクセスエッジサービスと Web 会議エッジサービスに1つずつ、音声ビデオエッジサービスに1つの証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3319-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="b3319-112">詳細については、「 <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Lync Server 2013 のステージングの AV および OAuth 証明書」を</A>参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3319-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3319-113">エッジサーバーのプールの場合は、各エッジサーバーに秘密キーを持つ証明書をエクスポートし、各エッジサーバーサービスに証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b3319-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="b3319-114">内部エッジサーバー証明書に対して同じ手順を実行し、証明書を秘密キーと共にエクスポートして、各内部エッジインターフェイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b3319-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="b3319-115">証明書用に割り当てられたエクスポート可能な秘密キーがあることの確認</span><span class="sxs-lookup"><span data-stu-id="b3319-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="b3319-116">アクセスエッジサービス (証明書ウィザードでは、 **SIP アクセスエッジ** と呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="b3319-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="b3319-117">Web 会議エッジサービス (証明書ウィザードの [ **Web 会議エッジ** ] と呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="b3319-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="b3319-118">音声ビデオ認証サービス (証明書ウィザードでは、[**音声エッジ外部**] と呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="b3319-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="b3319-119">エクスポート可能な秘密キーを持つ単一の内部証明書を作成し、各エッジ サーバー内部インターフェイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b3319-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="b3319-120">エッジ サーバー (証明書ウィザードでは、[**エッジ内部**] と呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="b3319-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3319-121">エッジサーバーサービスごとに異なる証明書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b3319-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="b3319-122">別の証明書を選択することをお勧めする理由は、音声ビデオエッジサービスの証明書に新しいローリング証明書機能を使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="b3319-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="b3319-123">この機能の場合は、音声ビデオエッジサービス証明書をアクセスエッジサービスと Web 会議エッジサービスから分離することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b3319-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="b3319-124">各サービスに対して個別の証明書を取得して割り当てることを選択した場合は、音声ビデオエッジサービスに対してエクスポート可能な秘密キーを要求する必要があります (これが実際には音声ビデオ認証サービスであることを示します)。また、各エッジサーバーの音声ビデオエッジの外部インターフェイスに同じ証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b3319-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3319-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3319-125">See Also</span></span>


[<span data-ttu-id="b3319-126">Lync Server 2013 での AV および OAuth 証明書のステージング (セットを使用)-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="b3319-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="b3319-127">エッジサーバーの計画に影響する Lync Server 2013 の変更点</span><span class="sxs-lookup"><span data-stu-id="b3319-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

