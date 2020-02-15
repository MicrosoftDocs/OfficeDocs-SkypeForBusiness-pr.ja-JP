---
title: 'Lync Server 2013: モビリティのトポロジとコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac03d6b98b0b209a50f08e660fe6665b975d2ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="d247e-102">Lync Server 2013 でのモビリティのトポロジとコンポーネント</span><span class="sxs-lookup"><span data-stu-id="d247e-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d247e-103">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="d247e-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="d247e-104">モバイルデバイスで Lync mobile アプリケーションをサポートするために、2013 Lync server 2013 Mcx Mobility Service、Lync Server 2013 自動検出サービス、Lync Server 2013 プッシュ通知サービスの3つのサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d247e-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="d247e-105">Lync Server 2013 の累積的な更新プログラム: 2 月2013は、統合コミュニケーション Web API または UCWA の使用により、Lync 2013 Mobile クライアントのための無料のサービスが追加されています。</span><span class="sxs-lookup"><span data-stu-id="d247e-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="d247e-106">このセクションでは、これらのコンポーネントについて簡単に説明し、モビリティをサポートする Lync Server 2013 トポロジを示します。</span><span class="sxs-lookup"><span data-stu-id="d247e-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d247e-107">モビリティ サービスは、ハイブリッド展開でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="d247e-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="d247e-108">ユーザーが常時オンラインである場合はモビリティをサポートするためのサービスを展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d247e-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="d247e-109">モバイルユーザーがオンライン id を検索できるようにするには、自動検出サービスの設定を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d247e-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d247e-110">外部ユーザーの接続を計画している場合 (フェデレーション、外部ユーザーアクセス、またはモビリティ機能など)、Standard Edition サーバーとフロントエンドサーバーまたはフロントエンドプールでエッジサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d247e-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="d247e-111">Standard Edition サーバーとフロントエンドサーバーまたはフロントエンドプールに、外部ユーザーが内部展開にアクセスできるようにするため、または内部展開で外部ユーザーと通信するために必要なコンポーネントがありません。</span><span class="sxs-lookup"><span data-stu-id="d247e-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="d247e-112">外部ユーザーを共同作業するか、モビリティを含む内部ユーザーと通信するすべてのシナリオについて、少なくとも1つのエッジサーバーと1つのリバースプロキシを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d247e-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="d247e-113"><EM>プッシュ通知</EM>では、プッシュ通知クリアリングハウス (pnch) をホストする Lync Online サービスへのフェデレーションの種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="d247e-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="d247e-114">プッシュ通知は、モバイルデバイスが非アクティブな場合に、アプリケーションによって Apple の iPhone、iPad、および Windows Phone にプッシュされるサウンド通知、画面上の警告 (テキスト)、バッジを表します。</span><span class="sxs-lookup"><span data-stu-id="d247e-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="d247e-115">PNCH は、Lync Server からプッシュ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="d247e-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="d247e-116">PNCH がメッセージの通知を受信すると、PNCH は、メッセージが意図されているモバイルクライアントに基づいて、Apple プッシュ通知サービスまたは Lync Server 2013 プッシュ通知サービスのいずれかを介してモバイルクライアントに通知を転送します。</span><span class="sxs-lookup"><span data-stu-id="d247e-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="d247e-117">PNCH は、これらのモバイル クライアントにとって必須のサービスです。</span><span class="sxs-lookup"><span data-stu-id="d247e-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="d247e-118">Lync Online とのフェデレーションを行うために、PNCH はエッジサーバーと証明書を使用して、機密性と認証、ポリシー、および適切に構成されたドメインネームシステム (DNS) レコードを確保します。</span><span class="sxs-lookup"><span data-stu-id="d247e-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="d247e-119">Nokia Symbian および Android ベースの Lync Mobile クライアントでは、PNCH は使用されません。</span><span class="sxs-lookup"><span data-stu-id="d247e-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="d247e-120">エッジサーバーの計画および展開の詳細については、「 <A href="lync-server-2013-planning-for-external-user-access.md">lync server 2013 での外部ユーザーアクセスの計画</A>」および「 <A href="lync-server-2013-deploying-external-user-access.md">lync server 2013 での外部ユーザーアクセスの展開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d247e-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="d247e-121">Lync Server 2013 用の累積的な更新プログラムで導入された、lync 2013 モバイルクライアント (Lync Server 用): 2 月2013は、プッシュ通知またはプッシュ通知クリアリングハウス (PNCH) を使用しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d247e-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="d247e-122">Windows Phone の Lync 2013 モバイルクライアントは、引き続きプッシュ通知と (PNCH) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d247e-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="d247e-123">モビリティ コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d247e-123">Mobility Components</span></span>

<span data-ttu-id="d247e-124">モビリティをサポートするサービスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d247e-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="d247e-125">**Lync server 2013 統合コミュニケーション Web API (ucwa)**   lync server 2013 のモバイルおよび Web クライアントとのリアルタイム通信のサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d247e-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="d247e-126">Lync Server 2013 の累積的な更新プログラム (2013 年2月) をフロントエンドサーバーとディレクターに展開すると、インストール時に内部および外部の web サービス (Ucwa) に仮想ディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d247e-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="d247e-127">Ucwa 仮想ディレクトリの一部である web コンポーネントは、UCWA が有効なクライアントからの呼び出しを受け付けます。</span><span class="sxs-lookup"><span data-stu-id="d247e-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="d247e-128">クライアントアプリは、プレゼンス、連絡先、インスタントメッセージング、VoIP、ビデオ会議、およびコラボレーションのための REST インターフェイスを介して通信します。</span><span class="sxs-lookup"><span data-stu-id="d247e-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="d247e-129">UCWA は、P-GET ベースのチャネルを使用して、着信呼び出し、インスタントメッセージの受信、クライアントアプリへのメッセージなどのイベントを送信します。</span><span class="sxs-lookup"><span data-stu-id="d247e-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d247e-130"><EM>REST</EM>または表現的な状態転送は、多くのフォームで広く採用されており、一般の Web サービスの要件に適している分散システムのソフトウェアアーキテクチャスタイルです。</span><span class="sxs-lookup"><span data-stu-id="d247e-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="d247e-131">**Lync Server 2013 Mobility service (mcx)**   このサービスは、モバイルデバイスでのインスタントメッセージング (IM)、プレゼンス、連絡先などの Lync 機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d247e-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="d247e-132">Mobility Service は、各プールのすべてのフロントエンドサーバーにインストールされ、モバイルデバイスで Lync 機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d247e-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="d247e-133">Lync Server 2013 をインストールすると、内部 web サイトとフロントエンドサーバー上の外部 web サイトの両方に新しい仮想ディレクトリ (Mcx) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d247e-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d247e-134">Lync server 2013 の累積的な更新プログラム (Lync server 2013): 2 月2013は、Lync Server 2010 用の累積的な更新プログラムで導入された Mobility service の両方をサポートしています。 11 2011 月 (一般に Mcx)、UCWA web コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d247e-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="d247e-135">これら2つの mobility service の組み合わせにより、lync Server 2013 で lync 2010 mobile および Lync 2013 Mobile クライアントを使用するユーザーが相互運用性を提供し、使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d247e-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="d247e-136">**Lync server 2013 自動検出サービス**   このサービスは、ユーザーの場所を識別し、モバイルデバイスやその他の lync クライアントが、ネットワークの場所に関係なく、lync Server 2013 Web サービスの内部 url と外部 url、mcx または ucwa の url などのリソースを検索できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d247e-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="d247e-137">自動検出では、ハードコードされたホスト名 (ネットワーク内のユーザーの場合は lyncdiscoverinternal、ネットワーク外部のユーザーの場合は lyncdiscover、ユーザーの SIP ドメイン) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d247e-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="d247e-138">HTTP または HTTPS のどちらかを使用するクライアント接続をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d247e-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="d247e-139">自動検出サービスは、すべてのフロントエンドサーバーと、各プールのすべてのディレクターにインストールされます。これは、モバイルデバイスで Lync 機能をサポートするためのものです。</span><span class="sxs-lookup"><span data-stu-id="d247e-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="d247e-140">自動検出サービスをインストールすると、フロントエンドサーバーとディレクターの両方で、内部 web サイトと外部 web サイトの両方に新しい仮想ディレクトリ (自動検出) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d247e-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d247e-141">自動検出サービスは、モバイルクライアントサービスを提供する際に重要なコンポーネントであるため、ここにリストされています。</span><span class="sxs-lookup"><span data-stu-id="d247e-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="d247e-142">Lync Server 2013 での自動検出の役割は、すべてのクライアントにサービスを提供するように拡張されています。</span><span class="sxs-lookup"><span data-stu-id="d247e-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="d247e-143">自動検出サービスの計画の詳細については、「 <A href="lync-server-2013-planning-for-autodiscover.md">Lync Server 2013 での自動検出の計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d247e-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="d247e-144">**プッシュ通知サービス**   このサービスは、Lync Online データセンターにあるクラウドベースのサービスです。</span><span class="sxs-lookup"><span data-stu-id="d247e-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="d247e-145">サポートされている Apple iOS デバイスまたは Windows Phone の Lync モバイルアプリケーションが非アクティブな場合、新しいインスタントメッセージング (IM) 招待、不在着信メッセージ、不在着信、ボイスメールなどの新しいイベントに応答することはできません。これらのデバイスではサポートされていません。バックグラウンドで実行されているモバイルアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="d247e-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="d247e-146">このような場合、新しいイベント (*プッシュ通知*と呼ばれる) の通知がモバイルデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="d247e-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="d247e-147">Mobility Service は通知をクラウドベースのプッシュ通知サービスに送信します。これにより、Apple Push Notification Service (APNS) (サポートされている Apple iOS デバイスの場合) または Microsoft プッシュ通知サービス (MPNS) に通知が送信されます。) (Windows Phone の場合) をクリックすると、モバイルデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="d247e-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="d247e-148">その後、ユーザーはモバイルデバイスで通知に応答して、アプリケーションをアクティブにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d247e-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="d247e-149">Apple および Windows Phone デバイス上の Lync 2010 Mobile は、プッシュ通知を使用します。</span><span class="sxs-lookup"><span data-stu-id="d247e-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="d247e-150">Lync Server 2013 用の累積的な更新プログラムで導入された、lync 2013 モバイルクライアント (Lync Server 用): 2 月2013は、プッシュ通知またはプッシュ通知クリアリングハウス (PNCH) を使用しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d247e-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="d247e-151">次の図は、UCWA および Lync 2013 モバイルクライアントを使用する Lync Server 2013 トポロジ内でプッシュ通知サービスがどのように配置されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="d247e-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="d247e-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="d247e-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="d247e-153">Lync Server 2010 の累積的な更新プログラム (2011 年11月) で導入された Mcx サービスは、Lync 2010 Mobile クライアントにサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d247e-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="d247e-154">次の図は、Mcx および Lync 2010 モバイルクライアントを使用するトポロジに適用されるプッシュ通知サービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="d247e-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="d247e-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="d247e-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="d247e-156">サポートされるトポロジ</span><span class="sxs-lookup"><span data-stu-id="d247e-156">Supported Topologies</span></span>

<span data-ttu-id="d247e-157">Lync Server 2013 の累積的な更新プログラムの適用: 2 月2013は、次のトポロジで Lync 2013 Mobile クライアント機能のモビリティをサポートするために UCWA web コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="d247e-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="d247e-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d247e-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="d247e-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="d247e-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="d247e-160">エッジサーバーは、Lync Server 2010 エッジサーバーにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d247e-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="d247e-161">Lync server 2013 の Lync Server 2013 の累積的な更新プログラムを適用せずに展開する場合: 2 月2013は Mcx Mobility Service を使用し、Lync 2010 Mobile に対してのみサービスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="d247e-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d247e-162">Mobility Service は、2つのネットワークインターフェイスを使用する仲介サーバーの役割と併置されたフロントエンドサーバーでサポートされていますが、インターフェイスを構成するために適切な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d247e-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="d247e-163">仲介サーバーとして通信する特定のインターフェイスに IP アドレスを割り当てる必要があります。また、フロントエンドサーバーとして通信するネットワークインターフェイスの IP アドレスも割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d247e-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="d247e-164">トポロジビルダーでは、[<STRONG>すべての構成済み ip アドレスを使用</STRONG>する] ではなく、各サービスの正しい ip アドレスを選択することで、トポロジビルダーでこの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d247e-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d247e-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="d247e-165">See Also</span></span>


[<span data-ttu-id="d247e-166">Lync Server 2013 での外部ユーザーアクセスの計画</span><span class="sxs-lookup"><span data-stu-id="d247e-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="d247e-167">Lync Server 2013 での外部ユーザーアクセスの展開</span><span class="sxs-lookup"><span data-stu-id="d247e-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="d247e-168">Lync Server 2013 での自動検出の計画</span><span class="sxs-lookup"><span data-stu-id="d247e-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

