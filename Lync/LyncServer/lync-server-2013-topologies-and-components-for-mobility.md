---
title: 'Lync Server 2013: モビリティのトポロジとコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 537eda14f2587e06bd8a1112f2a6a44299b0b78e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="091ec-102">Lync Server 2013 のモビリティのトポロジとコンポーネント</span><span class="sxs-lookup"><span data-stu-id="091ec-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="091ec-103">_**最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="091ec-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="091ec-104">Lync server 2013 には、モバイルデバイスでの Lync モバイルアプリケーションのサポートについて、lync Server 2013 Mcx Mobility Service、Lync Server 2013 自動検出サービス、Lync Server 2013 プッシュ通知サービスという3つのサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="091ec-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="091ec-105">Lync Server 2013 向けの累積的な更新プログラム: 2013 年2月に、Lync 2013 モバイルクライアント向けの無料のサービスが追加されました。ユニファイドコミュニケーション Web API、または UCWA を使用したモビリティサポート。</span><span class="sxs-lookup"><span data-stu-id="091ec-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="091ec-106">このセクションでは、これらのコンポーネントについて簡単に説明し、モバイル機能をサポートする Lync Server 2013 トポロジを示します。</span><span class="sxs-lookup"><span data-stu-id="091ec-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="091ec-107">モバイルサービスは、ハイブリッド展開でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="091ec-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="091ec-108">ユーザーがオンラインになっている場合、モバイル機能をサポートするためにサービスを展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="091ec-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="091ec-109">モバイルユーザーがオンライン id を見つけることができるようにするには、自動検出サービスの設定を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="091ec-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="091ec-110">外部ユーザー接続 (フェデレーション、外部ユーザーアクセス、モバイル機能など) を計画している場合は、Standard Edition server と、フロントエンドサーバーまたはフロントエンドプールでエッジサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="091ec-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="091ec-111">Standard Edition server とフロントエンドサーバーまたはフロントエンドプールには、外部ユーザーが内部展開にアクセスすること、または外部ユーザーとの通信を可能にするために必要なコンポーネントがありません。</span><span class="sxs-lookup"><span data-stu-id="091ec-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="091ec-112">外部ユーザーが共同作業しているか、モバイルを含む内部ユーザーと通信するすべてのシナリオでは、少なくとも1つのエッジサーバーと1つの逆プロキシを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="091ec-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="091ec-113"><EM>プッシュ通知</EM>では、フェデレーションの種類を Lync Online サービスに使用します。これは、プッシュ通知のクリアリングハウス (pnch) をホストします。</span><span class="sxs-lookup"><span data-stu-id="091ec-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="091ec-114">プッシュ通知とは、モバイルデバイスが非アクティブになっているときに、アプリケーションから Apple iPhone、iPad、Windows Phone にプッシュされるサウンド通知、画面上の通知 (テキスト)、バッジを指します。</span><span class="sxs-lookup"><span data-stu-id="091ec-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="091ec-115">PNCH Lync Server からプッシュ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="091ec-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="091ec-116">PNCH がメッセージの通知を受信すると、PNCH は、メッセージが意図されているモバイルクライアントに基づいて、Apple Push Notification Services または Lync Server 2013 プッシュ通知サービスを通じてモバイルクライアントに通知を転送します。</span><span class="sxs-lookup"><span data-stu-id="091ec-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="091ec-117">PNCH は、これらのモバイルクライアントに必要なサービスです。</span><span class="sxs-lookup"><span data-stu-id="091ec-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="091ec-118">Lync Online にフェデレーションを行うために、PNCH はエッジサーバーと証明書を使用して、機密性と認証、ポリシー、適切に構成された domain name system (DNS) レコードを確認します。</span><span class="sxs-lookup"><span data-stu-id="091ec-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="091ec-119">Nokia Symbian および Android ベースの Lync モバイルクライアントでは、PNCH は使用されません。</span><span class="sxs-lookup"><span data-stu-id="091ec-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="091ec-120">エッジサーバーの計画と展開の詳細については、「 <A href="lync-server-2013-planning-for-external-user-access.md">Lync server 2013 での外部ユーザーアクセスの計画</A>」および「 <A href="lync-server-2013-deploying-external-user-access.md">lync server 2013 での外部ユーザーアクセスの展開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="091ec-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="091ec-121">Apple デバイスの Lync 2013 モバイルクライアントは、Lync Server 2013 の累積更新プログラムで導入されました。2013年2月以降、プッシュ通知またはプッシュ通知のクリアリングハウス (PNCH) は使用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="091ec-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="091ec-122">Windows Phone 上の Lync 2013 モバイルクライアントでも、プッシュ通知と (PNCH) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="091ec-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="091ec-123">モバイルコンポーネント</span><span class="sxs-lookup"><span data-stu-id="091ec-123">Mobility Components</span></span>

<span data-ttu-id="091ec-124">モバイル機能をサポートするサービスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="091ec-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="091ec-125">**Lync server 2013 ユニファイドコミュニケーション Web API (ucwa)**   では、lync server 2013 のモバイルおよび Web クライアントとのリアルタイム通信のサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="091ec-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="091ec-126">Lync Server 2013 の累積的な更新プログラムを展開すると、2013年2月のフロントエンドサーバーとディレクターに、インストールにより、内部と外部の web サービス (Ucwa) に仮想ディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="091ec-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="091ec-127">Ucwa 仮想ディレクトリの一部である web コンポーネントは、UCWA 対応クライアントからの呼び出しを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="091ec-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="091ec-128">クライアントアプリは、プレゼンス、連絡先、インスタントメッセージング、VoIP、ビデオ会議、共同作業のために REST インターフェイスを介して通信します。</span><span class="sxs-lookup"><span data-stu-id="091ec-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="091ec-129">UCWA は、P-GET ベースのチャネルを使って、着信通話、インスタントメッセージの受信、クライアントアプリへのメッセージなどのイベントを送信します。</span><span class="sxs-lookup"><span data-stu-id="091ec-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="091ec-130"><EM>REST</EM>または表現は、さまざまな形式で広く採用されている分散システム向けのソフトウェアアーキテクチャスタイルであり、一般の Web サービスの要件にも適しています。</span><span class="sxs-lookup"><span data-stu-id="091ec-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="091ec-131">**Lync Server 2013 モビリティサービス (mcx)**   このサービスは、モバイルデバイスでのインスタントメッセージング (IM)、プレゼンス、連絡先などの Lync 機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="091ec-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="091ec-132">モバイルデバイスで Lync 機能をサポートするには、各プールの各フロントエンドサーバーにモビリティサービスがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="091ec-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="091ec-133">Lync Server 2013 をインストールすると、内部 web サイトとフロントエンドサーバー上の外部 web サイトの両方に新しい仮想ディレクトリ (Mcx) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="091ec-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="091ec-134">Lync server 2013 の累積更新プログラムを含む lync server 2013: 年2月2013では、Lync Server 2010 の累積的な更新プログラムで導入されたモビリティサービスの両方がサポートされます。11月2011、一般的には Mcx、UCWA web コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="091ec-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="091ec-135">この2つのモバイルサービスを組み合わせることで、lync 2010 Mobile クライアントと lync 2013 モバイルクライアントを使用するユーザーは、Lync Server 2013 で相互運用性と使用を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="091ec-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="091ec-136">**Lync server 2013 自動検出サービス**   このサービスは、ユーザーの場所を特定し、モバイルデバイスや他の lync クライアントが lync Server 2013 Web サービスの内部と外部の url、および、ネットワークの場所に関係なく、mcx または UCWA。</span><span class="sxs-lookup"><span data-stu-id="091ec-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="091ec-137">自動検出では、ハードコーディングされたホスト名 (ネットワーク内のユーザー向けの lyncdiscover、ネットワーク外のユーザー向けの lyncdiscoverinternal、ユーザーの SIP ドメイン) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="091ec-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="091ec-138">HTTP または HTTPS を使用しているクライアント接続をサポートします。</span><span class="sxs-lookup"><span data-stu-id="091ec-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="091ec-139">自動検出サービスは、各フロントエンドサーバーにインストールされ、モバイルデバイスで Lync 機能をサポートする各プールの各ディレクターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="091ec-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="091ec-140">自動検出サービスをインストールすると、フロントエンドサーバーとディレクターの両方で、内部 web サイトと外部 web サイトの両方に新しい仮想ディレクトリ (自動検出) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="091ec-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="091ec-141">自動検出サービスは、モバイルクライアントサービスを提供するときに重要なコンポーネントであるため、ここに記載されています。</span><span class="sxs-lookup"><span data-stu-id="091ec-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="091ec-142">Lync Server 2013 での自動検出の役割は、すべてのクライアントに対してサービスを提供するために拡張されています。</span><span class="sxs-lookup"><span data-stu-id="091ec-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="091ec-143">自動検出サービスの計画について詳しくは、「 <A href="lync-server-2013-planning-for-autodiscover.md">Lync Server 2013 での自動検出の計画</A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="091ec-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="091ec-144">**プッシュ通知サービス**   このサービスは、Lync Online データセンターにあるクラウドベースのサービスです。</span><span class="sxs-lookup"><span data-stu-id="091ec-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="091ec-145">サポートされている Apple iOS デバイスまたは Windows Phone の Lync モバイルアプリケーションが非アクティブになっていると、新しいインスタントメッセージ (IM) の招待、不在着信メッセージ、不在着信、ボイスメールなど、これらのデバイスはサポートされていないため、新しいイベントに応答できません。バックグラウンドで実行されているモバイルアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="091ec-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="091ec-146">このような場合には、新しいイベントの通知 (*プッシュ通知*と呼ばれる) がモバイルデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="091ec-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="091ec-147">モバイルサービスはクラウドベースのプッシュ通知サービスに通知を送信します。これにより、Apple Push Notification Service (APNS) (サポートされている Apple iOS デバイスの場合) または Microsoft プッシュ通知サービス (MPNS) に通知が送信されます。) (Windows Phone の場合) がモバイルデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="091ec-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="091ec-148">ユーザーは、モバイルデバイスで通知に応答して、アプリケーションをアクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="091ec-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="091ec-149">Apple と Windows Phone デバイス上の Lync 2010 Mobile では、プッシュ通知が使われます。</span><span class="sxs-lookup"><span data-stu-id="091ec-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="091ec-150">Apple デバイス向け Lync 2013 モバイルクライアントは、Lync Server 2013 の累積更新プログラムで導入されました。年2月 7 2013 日に、プッシュ通知またはプッシュ通知のクリアリングハウス (PNCH) を使用しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="091ec-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="091ec-151">次の図は、UCWA と Lync 2013 モバイルクライアントを使用する Lync Server 2013 トポロジ内でプッシュ通知サービスがどのように適合するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="091ec-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="091ec-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="091ec-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="091ec-153">Lync Server 2010 向けの累積的な更新プログラムで導入されました: 2011 年11月、Mcx サービスは Lync 2010 モバイルクライアントにサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="091ec-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="091ec-154">次の図は、Mcx と Lync 2010 モバイルクライアントを使用したトポロジに適用される、プッシュ通知サービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="091ec-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="091ec-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="091ec-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="091ec-156">サポートされるトポロジ</span><span class="sxs-lookup"><span data-stu-id="091ec-156">Supported Topologies</span></span>

<span data-ttu-id="091ec-157">Lync Server 2013 の累積的な更新プログラムの適用: 2013 年2月に、次のトポロジでの Lync 2013 モバイルクライアント機能の機動性をサポートするために、UCWA web コンポーネントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="091ec-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="091ec-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="091ec-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="091ec-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="091ec-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="091ec-160">エッジサーバーは、Lync Server 2010 Edge サーバーにすることができます。</span><span class="sxs-lookup"><span data-stu-id="091ec-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="091ec-161">Lync server 2013 の累積更新プログラムが適用されていない Lync Server 2013 の展開: 2013 年2月は、Mcx Mobility Service を使用し、Lync 2010 Mobile のサービスのみを提供します。</span><span class="sxs-lookup"><span data-stu-id="091ec-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="091ec-162">モバイルサービスは、2つのネットワークインターフェイスで仲介サーバーの役割と連携しているフロントエンドサーバーでサポートされますが、インターフェイスを構成するための適切な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="091ec-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="091ec-163">仲介サーバーとして通信する特定のインターフェイスと、フロントエンドサーバーとして通信するネットワークインターフェイス IP に IP アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="091ec-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="091ec-164">これを行うには、トポロジビルダーで、既定の [<STRONG>すべての構成された ip アドレスを使用</STRONG>する] ではなく、各サービスの正しい ip アドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="091ec-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="091ec-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="091ec-165">See Also</span></span>


[<span data-ttu-id="091ec-166">Lync Server 2013 の外部ユーザー アクセスの計画</span><span class="sxs-lookup"><span data-stu-id="091ec-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="091ec-167">Lync Server 2013 での外部ユーザー アクセスの展開</span><span class="sxs-lookup"><span data-stu-id="091ec-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="091ec-168">Lync Server 2013 での自動検出の計画</span><span class="sxs-lookup"><span data-stu-id="091ec-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

