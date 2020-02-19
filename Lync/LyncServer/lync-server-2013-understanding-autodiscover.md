---
title: 'Lync Server 2013: 自動検出について'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 033f3a12ccbe0817f586aa7eb868679fa44541fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="9b419-102">Lync Server 2013 の自動検出について</span><span class="sxs-lookup"><span data-stu-id="9b419-102">Understanding Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b419-103">_**トピックの最終更新日:** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="9b419-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="9b419-104">Lync Server 2013 自動検出サービスは、Lync Server 2010:11 月 11 2011 日の累積的な更新プログラムの一部として、Microsoft Lync Server 2010 で最初に導入された機能です。</span><span class="sxs-lookup"><span data-stu-id="9b419-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="9b419-105">修正に加えて、この累積的な更新プログラムは Lync Mobile および Lync 2013 クライアントのサポートを提供していました。</span><span class="sxs-lookup"><span data-stu-id="9b419-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="9b419-106">Lync Server 2013 では、自動検出サービスは、外部および内部のモバイルクライアントの操作の重要な部分であり、自動検出も、Windows 8 用の最近導入された Lync Windows ストアアプリなどの新しいクライアントにまで拡張されます。</span><span class="sxs-lookup"><span data-stu-id="9b419-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="9b419-107">自動検出は、Lync 2013 デスクトップクライアントでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b419-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="9b419-108">自動検出は、必要なドメインネームシステム (DNS) レコード lyncdiscover によって Lync Server で認識され**ます。\<ドメイン\> **および**lyncdiscoverinternal。\<ドメイン\>**。</span><span class="sxs-lookup"><span data-stu-id="9b419-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>** and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="9b419-109">さらに、Lync 2010 および Lync 2013 デスクトップクライアントの新しいバージョンでは、lyncdiscover の場合にのみ DNS SRV レコードを使用して、ドメインネームシステム (DNS) SRV レコードよりも自動検出を優先します。\<domain\>または lyncdiscoverinternal。\<ドメイン\>が応答しないか、解決されません。</span><span class="sxs-lookup"><span data-stu-id="9b419-109">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\> or lyncdiscoverinternal.\<domain\> does not respond or does not resolve.</span></span> <span data-ttu-id="9b419-110">Windows 8 および Lync Mobile 用の Lync Windows ストアアプリは、自動検出のみを使用し、従来の DNS SRV レコードを参照することはありません。</span><span class="sxs-lookup"><span data-stu-id="9b419-110">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="9b419-111">Lync Server 2013 では、自動検出が拡張され、クライアントが使用できる要素、機能、および通信方法をクライアントに通知します。</span><span class="sxs-lookup"><span data-stu-id="9b419-111">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="9b419-112">情報はクライアントから送信された要求を通じて伝達され、Lync Server web サービスは、クライアントが利用できるものという名前の明示的に定義された応答で応答します。また、これらの機能には自動検出の形式で応答します。応答ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="9b419-112">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="9b419-113">Web サービスがこのドキュメントを使用してクライアントに機能を伝達する方法など、自動検出応答ドキュメントを理解するための最善の方法は、dissect して、Lync web サービス自動検出応答ドキュメントからの一般的な応答で各行を定義することです。</span><span class="sxs-lookup"><span data-stu-id="9b419-113">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9b419-114">この後の詳細では、ユーザーは認証要求に応答して既にホームサーバーに認証されています。</span><span class="sxs-lookup"><span data-stu-id="9b419-114">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9b419-115">Lync 自動検出 Web サービスは、microsoft <STRONG>Developer Network</STRONG> (MSDN) ライブラリの [<STRONG>オープン仕様</STRONG>] セクションにある<STRONG>microsoft Office プロトコル</STRONG>で定義されています。</span><span class="sxs-lookup"><span data-stu-id="9b419-115">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="9b419-116">詳細については、「」の「完全な仕様書」、「Lync 自動<A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>検出 Web サービスプロトコル」、および「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b419-116">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="9b419-117">認証の詳細については、「」の「OC Authentication <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>Web Service Protocol」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b419-117">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="9b419-118">Lync Server Web サービスの自動検出応答</span><span class="sxs-lookup"><span data-stu-id="9b419-118">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="9b419-119">自動検出要求が送信されたときに返される応答は、内部または外部クライアントに対して同じです。</span><span class="sxs-lookup"><span data-stu-id="9b419-119">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="9b419-120">場所に対応する一部のパラメーターは変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9b419-120">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="9b419-121">クライアント要求を受信したが、実際のプールが、接続されているもの以外の場合は、そのユーザーに対してユーザーのホームプールが設定されます。</span><span class="sxs-lookup"><span data-stu-id="9b419-121">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="9b419-122">ユーザーアカウントが異なるプールにあり、同じ office からログインしている同僚は、多少異なる応答をします。</span><span class="sxs-lookup"><span data-stu-id="9b419-122">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="9b419-123">応答は、そのユーザーの適切なフロントエンドサーバーまたはフロントエンドプールを示します。</span><span class="sxs-lookup"><span data-stu-id="9b419-123">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="9b419-124">自動検出応答ドキュメントの例:</span><span class="sxs-lookup"><span data-stu-id="9b419-124">An example of an Autodiscover Response document:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="9b419-125">自動検出応答ドキュメントの詳細</span><span class="sxs-lookup"><span data-stu-id="9b419-125">Autodiscover Response Document Details</span></span>

<span data-ttu-id="9b419-126">自動検出応答ドキュメントは、次の2つの形式のいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9b419-126">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="9b419-127">既定の形式は、JavaScript Object Notation (JSON) です。</span><span class="sxs-lookup"><span data-stu-id="9b419-127">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="9b419-128">もう1つの形式は、拡張マークアップ言語 (XML) ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="9b419-128">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="9b419-129">この例では、XML を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b419-129">The XML is used for this example.</span></span> <span data-ttu-id="9b419-130">ドキュメントには、形式を決定する定義済みスキーマがあるため、要求と応答は予測できます。</span><span class="sxs-lookup"><span data-stu-id="9b419-130">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="9b419-131">使用されるスキーマを記述するドキュメント内の行は、要求または応答の最初の行です。</span><span class="sxs-lookup"><span data-stu-id="9b419-131">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="9b419-132">**Accesslocation = "external"** の定義は、要求が外部ユーザーから行われたことを示します。</span><span class="sxs-lookup"><span data-stu-id="9b419-132">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="9b419-133">SipServerInternalAccess と SipServerExternalAccess は現在使用されていません。</span><span class="sxs-lookup"><span data-stu-id="9b419-133">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="9b419-134">これらのエントリは、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="9b419-134">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="9b419-135">SipClientInternalAccess and SipClientExternalAccess は、内部または外部のクライアントが定義された SIP サーバーへのアクセスに使用する完全修飾ドメイン名とポートを説明します。</span><span class="sxs-lookup"><span data-stu-id="9b419-135">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="9b419-136">Lync デスクトップクライアントおよび Lync Windows ストアアプリは、これらのエントリを、その場所 (内部または外部) に基づいて、ディレクターまたはフロントエンドサーバーを検索するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9b419-136">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="9b419-137">参照`Autodiscover`には、自動検出サービスのサービスエントリポイントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b419-137">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="9b419-138">Token 属性には、サービスの名前が含まれ、href はサービスが存在するクライアントに対して定義される URL です。</span><span class="sxs-lookup"><span data-stu-id="9b419-138">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="9b419-139">外部ネットワーク上のクライアントは、 `External/Autodiscover`を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b419-139">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="9b419-140">自動検出サービスは、展開プロセスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9b419-140">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="9b419-141">`Internal/Autodiscover`は現在使用されておらず、将来の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="9b419-141">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="9b419-142">参照`AuthBroker`には、内部および外部認証ブローカーサービス (この場合は sip-pstn) のサービスエントリポイントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b419-142">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="9b419-143">Token 属性には、サービスの名前が含まれ、href はサービスが存在するクライアントに対して定義される URL です。</span><span class="sxs-lookup"><span data-stu-id="9b419-143">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="9b419-144">使用`Internal/AuthBroker`している内部ネットワーク上のクライアント。</span><span class="sxs-lookup"><span data-stu-id="9b419-144">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="9b419-145">外部ネットワーク上のクライアントは、 `External/AuthBroker`を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b419-145">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="9b419-146">AuthBroker サービスは、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9b419-146">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="9b419-147">この`WebScheduler`トークンは、Lync Server 会議の web ベースのスケジュールに対するクライアントアクセスの url を参照します。</span><span class="sxs-lookup"><span data-stu-id="9b419-147">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="9b419-148">現時点では、 `External/WebScheduler`がのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b419-148">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="9b419-149">WebScheduler は、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9b419-149">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="9b419-150">`Internal/Mcx`および`External/Mcx`は、Mobility service の場所です。 Lync Server 2010 用の累積的な更新プログラム (11 月 2011) で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9b419-150">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="9b419-151">これらの参照は、サポートされているすべてのデバイスで Lync 2010 Mobile によって引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b419-151">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="9b419-152">Mcx サービスは、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9b419-152">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="9b419-153">**Internal/ucwa**、 **External/Ucwa**および**Ucwa**は、クライアントが統合コミュニケーション Web アプリケーションプログラミングインターフェイス (ucwa API、または単に ucwa) にアクセスする手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="9b419-153">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="9b419-154">`Internal/Ucwa``External/Ucwa`仮想ディレクトリは、将来の機能拡張のために予約されたアクセスポイントであり、使用されません。</span><span class="sxs-lookup"><span data-stu-id="9b419-154">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="9b419-155">サポート`Ucwa`されているすべてのデバイスで、仮想ディレクトリが Microsoft lync Mobile (lync Server 2013 で導入されました) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b419-155">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="9b419-156">UCWA サービスは、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9b419-156">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="9b419-157">`Internal/XFrame`**外部/xframe**および**xframe**は、ucwa ベースのサーバーアプリケーションへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9b419-157">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="9b419-158">XFrame は、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9b419-158">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="9b419-159">トークン`Self`は、要求を行っているクライアント (ユーザー応答の種類) に固有の情報を参照します。</span><span class="sxs-lookup"><span data-stu-id="9b419-159">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="9b419-160">この要求を行ったクライアントは外部であり、この自動検出の参照は自動検出サービスのユーザー部分に対するものです。</span><span class="sxs-lookup"><span data-stu-id="9b419-160">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9b419-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b419-161">See Also</span></span>


[<span data-ttu-id="9b419-162">Lync Server 2013 の外部ユーザーアクセスコンポーネントのシステム要件</span><span class="sxs-lookup"><span data-stu-id="9b419-162">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="9b419-163">Lync Server 2013 での自動検出の計画</span><span class="sxs-lookup"><span data-stu-id="9b419-163">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

