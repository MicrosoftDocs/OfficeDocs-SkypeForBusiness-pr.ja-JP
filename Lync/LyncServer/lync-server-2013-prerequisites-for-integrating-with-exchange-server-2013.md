---
title: 'Lync Server 2013: Exchange Server 2013 と統合するための前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a381f765c9c91e9c5e218d66320d542a11bf878
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="b1b48-102">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合するための前提条件</span><span class="sxs-lookup"><span data-stu-id="b1b48-102">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1b48-103">_**最終更新日:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="b1b48-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="b1b48-104">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合する前に、すべての必須手順が完了していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b48-104">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="b1b48-105">場合によっては、Exchange 2013 と Lync Server 2013 の両方が完全にインストールされて実行されるまで、統合を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="b1b48-105">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="b1b48-106">Exchange のインストールの詳細については、「Exchange 2013 の計画[http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)と展開に関するドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b48-106">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="b1b48-107">Lync Server 2013 のインストールの詳細については、の計画と[http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)展開に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b48-107">For details about installing Lync Server 2013, see the planning and deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="b1b48-108">サーバーが起動して実行されたら、Lync Server 2013 と Exchange 2013 の両方にサーバー間認証証明書を割り当てる必要があります。これらの証明書を使用すると、Lync Server および Exchange で情報を交換したり、互いに通信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b1b48-108">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="b1b48-109">Exchange 2013 をインストールすると、Microsoft Exchange Server 認証証明書という名前の自己署名証明書が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b1b48-109">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="b1b48-110">この証明書はローカルコンピューターの証明書ストアに含まれている可能性があります。これは、Exchange 2013 のサーバー間認証に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b48-110">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="b1b48-111">Exchange 2013 での証明書の割り当ての詳細については、「のメールフロー [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)とクライアントアクセスの構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b48-111">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="b1b48-112">Lync Server 2013 の場合は、既存の Lync Server 証明書をサーバー間認証証明書として使うことができます。たとえば、既定の証明書を OAuthTokenIssuer 証明書として使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="b1b48-112">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="b1b48-113">Lync Server 2013 では、次のような方法で提供されるサーバー間認証用の証明書として、任意の Web サーバー証明書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b1b48-113">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="b1b48-114">証明書の [Subject] (サブジェクト) フィールドに SIP ドメインの名前が含まれている。</span><span class="sxs-lookup"><span data-stu-id="b1b48-114">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="b1b48-115">これと同じ証明書がすべてのフロントエンド サーバーで OAuthTokenIssuer 証明書として構成されている。</span><span class="sxs-lookup"><span data-stu-id="b1b48-115">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="b1b48-116">証明書の長さが 2,048 ビット以上。</span><span class="sxs-lookup"><span data-stu-id="b1b48-116">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="b1b48-117">Microsoft Lync Server 2013 のサーバー間認証証明書の詳細については、「[サーバー対サーバー認証証明書を Microsoft Lync server 2013 に割り当てる](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b48-117">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="b1b48-118">証明書が割り当てられたら、Exchange 2013 で自動検出サービスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b48-118">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="b1b48-119">Exchange 2013 では、自動検出サービスによってユーザープロファイルが構成され、ユーザーがシステムにログオンしたときに Exchange services へのアクセスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b1b48-119">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="b1b48-120">ユーザーが autodiscover サービスに電子メール アドレスとパスワードを入力すると、このサービスからユーザーへ次の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b1b48-120">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="b1b48-121">Exchange 2013 への内部および外部接続の接続情報。</span><span class="sxs-lookup"><span data-stu-id="b1b48-121">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="b1b48-122">ユーザーのメールボックス サーバーの場所。</span><span class="sxs-lookup"><span data-stu-id="b1b48-122">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="b1b48-123">空き時間情報、ユニファイド メッセージング、およびオフライン アドレス帳などの Outlook 機能の URL。</span><span class="sxs-lookup"><span data-stu-id="b1b48-123">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="b1b48-124">Outlook Anywhere のサーバー設定。</span><span class="sxs-lookup"><span data-stu-id="b1b48-124">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="b1b48-125">自動検出サービスは、Lync Server 2013 と Exchange 2013 を統合する前に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b48-125">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="b1b48-126">自動検出サービスが構成されているかどうかを確認するには、Exchange 管理シェルから次のコマンドを実行して、AutoDiscoverServiceInternalUri プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="b1b48-126">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="b1b48-p106">この値が空白の場合、autodiscover サービスに URI を割り当てる必要があります。通常、この URI は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b1b48-p106">If this value is blank, you must assign a URI to the autodiscover service. Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="b1b48-129">autodiscover の URI は、次のようなコマンドを実行すると割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b1b48-129">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="b1b48-130">自動検出サービスの詳細については、の「自動検出サービス[http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b48-130">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="b1b48-131">自動検出サービスが構成されたら、Lync Server OAuth 構成の設定を変更する必要があります。これにより、Lync サーバーは自動検出サービスの場所を把握することができます。</span><span class="sxs-lookup"><span data-stu-id="b1b48-131">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="b1b48-132">Lync Server 2013 で OAuth 構成設定を変更するには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1b48-132">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="b1b48-133">このコマンドを実行する場合は、Exchange サーバーで実行されている自動検出サービスの URI を指定していることを確認し**ます**。また、自動検出を使用して、(サービスで使用される xml ファイルを示す)**自動**検出ではなく、サービスの場所を指すようにします。</span><span class="sxs-lookup"><span data-stu-id="b1b48-133">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="b1b48-134">上のコマンドの Identity パラメーターは省略可能です。これは、Lync Server では、OAuth 構成設定のグローバルコレクションを1つだけ持つことができるためです。</span><span class="sxs-lookup"><span data-stu-id="b1b48-134">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="b1b48-135">これは、次のように単純なコマンドを使用して自動検出 URL を構成できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b1b48-135">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="b1b48-136">Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span><span class="sxs-lookup"><span data-stu-id="b1b48-136">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="b1b48-p109">OAuth というテクノロジは、多くの大手 Web サイトで使用されている標準的な認証プロトコルです。OAuth では、ユーザーの資格情報とパスワードがコンピューター間で渡されることはありません。その代わりに、セキュリティ トークンの交換に基づいて認証と承認が行われます。これらのトークンによって、特定のリソースのセットに対する特定の時間のアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="b1b48-p109">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites. With OAuth, user credentials and passwords are not passed from one computer to another. Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="b1b48-140">自動検出サービスの構成に加えて、Exchange サーバーを参照するサービスの DNS レコードも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b48-140">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="b1b48-141">たとえば、自動検出サービスが autodiscover.litwareinc.com にある場合は、Exchange サーバーの完全修飾ドメイン名に解決される autodiscover.litwareinc.com の DNS レコードを作成する必要があります (たとえば、atl-exchange-001.litwareinc.com)。</span><span class="sxs-lookup"><span data-stu-id="b1b48-141">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

