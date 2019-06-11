---
title: 'Lync Server 2013: 外部ユーザー アクセスの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a527df5a3bc7b296d17860c7a02876dbc31fbc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a><span data-ttu-id="c1093-102">Lync Server 2013 における外部ユーザー アクセスの概要</span><span class="sxs-lookup"><span data-stu-id="c1093-102">Overview of external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1093-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="c1093-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="c1093-104">このドキュメントでは、*外部ユーザー*という用語を使用して、ファイアウォールの外側から lync Server 2013 および lync 2013 ユーザーと通信する大規模なユーザーのカテゴリを定義しています。</span><span class="sxs-lookup"><span data-stu-id="c1093-104">In this documentation, we use the term *external user* to define a large category of users who communicate with your Lync Server 2013 and Lync 2013 users from outside the firewall.</span></span> <span data-ttu-id="c1093-105">Lync Server 2013 と内部ユーザーとの通信を承認できる外部ユーザー (つまり、ファイアウォール内から Lync Server にサインインしているユーザー) には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c1093-105">External users that you can authorize to communicate Lync Server 2013 with internal users (that is, users who sign in to Lync Server from inside the firewall) can include the following:</span></span>

  - <span data-ttu-id="c1093-106">\*\*\*\*   ファイアウォールの外部から Lync Server にサインインしている組織のリモートユーザーのユーザー。</span><span class="sxs-lookup"><span data-stu-id="c1093-106">**Remote users**   Users of your organization who sign in to Lync Server from outside the firewall.</span></span>

  - <span data-ttu-id="c1093-107">\*\*\*\* Lync server 2010、lync server 2013、または Office Communications server 2007 R2 など、信頼できる顧客またはパートナーの組織のアカウントを持っているユーザーをフェデレーションします。   </span><span class="sxs-lookup"><span data-stu-id="c1093-107">**Federated users**   Users who have an account with a trusted customer or partner organization, such as Lync Server 2010, Lync Server 2013 or Office Communications Server 2007 R2.</span></span> <span data-ttu-id="c1093-108">フェデレーションされたユーザーは、エッジサーバー上の XMPP プロキシと、フロントエンドサーバーまたはプール上の XMPP ゲートウェイを使用して、定義済みパートナー組織のメンバーになることもできます。</span><span class="sxs-lookup"><span data-stu-id="c1093-108">Federated users can also be members of defined partner organizations using extensible messaging and presence protocol (XMPP) by way of the XMPP proxy on the Edge Server and XMPP gateway on the Front End Server or pool.</span></span> <span data-ttu-id="c1093-109">フェデレーションと呼ばれる定義済みの信頼関係は、Active Directory ドメインサービスの信頼関係に関連していないか、または依存していません。</span><span class="sxs-lookup"><span data-stu-id="c1093-109">A defined trust relationship, called a federation, is not related to or dependent upon an Active Directory Domain Services trust relationship.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1093-110">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="c1093-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c1093-111">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="c1093-111">has been announced.</span></span> <span data-ttu-id="c1093-112">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1093-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="c1093-113">**パブリックインスタントメッセージング接続のユーザー**   がパブリックインスタントメッセージング接続サービス (Windows Live、Yahoo) を使って確立した連絡先\!</span><span class="sxs-lookup"><span data-stu-id="c1093-113">**Public Instant Messaging Connectivity users**   Contacts that your users establish through public instant messaging connectivity services (Windows Live, Yahoo\!</span></span> <span data-ttu-id="c1093-114">および AOL)。</span><span class="sxs-lookup"><span data-stu-id="c1093-114">and AOL).</span></span>

  - <span data-ttu-id="c1093-115">**モバイルユーザー**   組織のメンバーで、スマートフォンまたは Lync モバイルクライアントを実行しているタブレットを使用しているユーザーは、内部展開にサインインして、他のクラスのユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="c1093-115">**Mobile users**   Users that are members of your organization that use a smart phone or tablet running a Lync Mobile client sign in to your internal deployment and are able to communicate with the other classes of users.</span></span> <span data-ttu-id="c1093-116">モバイルユーザーは、リバースプロキシ経由で公開されているモビリティーサービスを使って、内部展開にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c1093-116">The mobile user uses mobility services that are published through the reverse proxy to access the internal deployment.</span></span> <span data-ttu-id="c1093-117">Lync Mobile で利用できる機能の詳細については、「モバイルクライアントの比較[http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)表」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1093-117">For details on features and capabilities available to Lync Mobile , see the Mobile Client Comparison Tables at [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777).</span></span>

  - <span data-ttu-id="c1093-118">\*\*\*\*   組織の Active Directory ドメインサービスまたはサポートされているフェデレーションドメイン内にユーザーアカウントを持っておらず、オンプレミスの会議にリモートで参加するための招待を受け取った匿名ユーザー。</span><span class="sxs-lookup"><span data-stu-id="c1093-118">**Anonymous users**   Users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but who have received invitations to participate remotely in an on-premises conference.</span></span>

<span data-ttu-id="c1093-119">エッジの展開では、次の種類の通信に対する外部アクセスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c1093-119">Your edge deployment provides external access for the following types of communication:</span></span>

  - <span data-ttu-id="c1093-120">**Im とプレゼンス**   によって承認された外部ユーザーは、im の会話と会議に参加できます。また、互いのプレゼンス状態に関する情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="c1093-120">**IM and presence**   Authorized external users can participate in IM conversations and conferences, and they can get information about one another’s presence status.</span></span> <span data-ttu-id="c1093-121">パブリック IM サービスプロバイダーのユーザーは、組織内の個々の Lync サーバーユーザーとの IM 会話に参加したり、プレゼンス情報にアクセスしたりすることはできますが、Lync Server を使って IM マルチパーティ会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="c1093-121">Users of public IM service providers can participate in IM conversations with individual Lync Server users in your organization and access presence information, but they cannot participate in IM multiparty conferences using Lync Server.</span></span> <span data-ttu-id="c1093-122">これは、厳密なピアツーピア通信です。</span><span class="sxs-lookup"><span data-stu-id="c1093-122">It is strictly peer-to-peer communication.</span></span> <span data-ttu-id="c1093-123">ファイル送信は、パブリック IM サービスプロバイダーのユーザーに対してはサポートされておらず、ピアツーピア通信での音声/ビデオは、Windows Messenger 2011 ユーザーに対してはサポートされていますが、パブリック IM サービスプロバイダーの他のユーザーには対応していません。</span><span class="sxs-lookup"><span data-stu-id="c1093-123">File transfer is not supported for users of public IM service providers, and audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not other users of public IM service providers.</span></span>
    
    <span data-ttu-id="c1093-124">SIP と XMPP の両方のプロトコルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c1093-124">Both SIP and XMPP protocols are supported.</span></span> <span data-ttu-id="c1093-125">XMPP のサービスを提供するには、「 [Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1093-125">To provide services for XMPP, see [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="c1093-126">**Web 会議**   承認済みの外部ユーザーは、Lync Server の展開でホストされている会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="c1093-126">**Web conferencing**   Authorized external users can participate in conferences that are hosted on your Lync Server deployment.</span></span> <span data-ttu-id="c1093-127">リモートユーザー、フェデレーションユーザー、匿名ユーザーは、web 会議への参加を有効にできますが、パブリック IM ユーザーは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="c1093-127">Remote users, federated users, and anonymous users can be enabled for participation in web conferencing, but public IM users cannot participate in conferences.</span></span> <span data-ttu-id="c1093-128">選択したオプションに応じて、web 会議対応ユーザーはデスクトップとアプリケーションの共有に参加でき、会議の開催者または発表者として機能することができます。</span><span class="sxs-lookup"><span data-stu-id="c1093-128">Depending on the options that you select, web conferencing-enabled users can participate in desktop and application sharing and can act as meeting organizers or presenters.</span></span>

  - <span data-ttu-id="c1093-129">\*\*\*\* 許可された外部ユーザーは、Lync Server 展開でホストされている音声会議やビデオ会議に参加できます。   </span><span class="sxs-lookup"><span data-stu-id="c1093-129">**A/V conferencing**   Authorized external users can participate in audio and video conferences that your Lync Server deployment hosts.</span></span> <span data-ttu-id="c1093-130">ピアツーピア通信での音声/ビデオは、Windows Messenger 2011 ユーザーに対してはサポートされますが、パブリック IM サービスプロバイダーの他のユーザーには対応していません。</span><span class="sxs-lookup"><span data-stu-id="c1093-130">Audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not for other users of public IM service providers.</span></span>

<span data-ttu-id="c1093-131">通信を制御するために、組織内外のユーザーが相互に通信する方法を定義する1つまたは複数のポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c1093-131">In order to control communications, you can configure one or more policies that define how users inside and outside your organization communicate with each other.</span></span> <span data-ttu-id="c1093-132">また、個々の内部ユーザーの設定を構成し、ポリシーを適用することができます。また、外部ユーザーとの通信を制御するために、特定の種類の外部ユーザーのポリシーを適用することもできます</span><span class="sxs-lookup"><span data-stu-id="c1093-132">You can also configure settings and apply policies for individual internal users or for specific types of external users to control communications with external users.</span></span>

<span data-ttu-id="c1093-133">外部アクセスを提供するために使用される Lync Server 2013 の役割:</span><span class="sxs-lookup"><span data-stu-id="c1093-133">Lync Server 2013 roles that are used to provide external access:</span></span>

<span data-ttu-id="c1093-134">**エッジサーバー**   エッジサーバーは、IM、プレゼンス、会議、音声/ビデオ、その他のメディア (ファイル転送など) サービスへの外部アクセスを可能にするサービスを実行するサーバーまたはサーバーのプールです。</span><span class="sxs-lookup"><span data-stu-id="c1093-134">**Edge Server**   The Edge Server is a server or a pool of servers that run the services that allow external access to IM and presence, conferencing, audio/video, and other media (for example, file transfer) services.</span></span> <span data-ttu-id="c1093-135">必要に応じて、他の Lync Server または Office Communications Server 2007 R2 の展開と他の XMPP の展開とのフェデレーションを行うようにエッジサーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c1093-135">Optionally, you can configure the Edge Server to federate with other Lync Server or Office Communications Server 2007 R2 deployments, and other XMPP deployments.</span></span> <span data-ttu-id="c1093-136">オプションのパブリック IM 接続機能が有効になり、エッジサーバーによって構成されます。</span><span class="sxs-lookup"><span data-stu-id="c1093-136">The optional public IM connectivity feature is enabled and configured through the Edge Server.</span></span>

<span data-ttu-id="c1093-137">**ディレクター**   ディレクターは、ユーザー要求を事前認証し、ユーザーのホームフロントエンドサーバーまたはフロントエンドプールへの要求をルーティングしますが、ユーザーアカウントのホームとしては、Lync server 2013 ディレクターの役割を実行している、オプションのサーバーまたはサーバープールです。</span><span class="sxs-lookup"><span data-stu-id="c1093-137">**Director**   The Director is an optional server or server pool running the Lync Server 2013 Director role that pre-authenticates user requests and routes requests to the users’ home Front End Server or Front End pool, but does not home any user accounts.</span></span>

<span data-ttu-id="c1093-138">**リバースプロキシ**   リバースプロキシは、内部ネットワークで利用可能なリソースを公開し、公開されたリソースからクライアントの情報を取得する、専用サーバーの一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="c1093-138">**Reverse Proxy**   A reverse proxy is a general term for specialized servers that publish resources available on the internal network and retrieve information for clients from the published resource.</span></span> <span data-ttu-id="c1093-139">Lync Server 2013 は、リバースプロキシを使用して、会議会議、電話会議の場所、アドレス帳、配布リストの拡張、会議コンテンツのダウンロード、デバイスの更新、モバイルサービスなど、さまざまな機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="c1093-139">Lync Server 2013 uses the reverse proxy to publish a number of features, such as conferencing meetings, conference join locations, the address book, distribution list expansion, downloading meeting content, device updates, Mobility services, and more.</span></span> <span data-ttu-id="c1093-140">必要なリソースの場所を公開するための要件を満たしているリバースプロキシを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1093-140">Any reverse proxy that can meet the requirements for publishing the necessary resource locations can be used.</span></span> <span data-ttu-id="c1093-141">Microsoft Forefront Threat Management Gateway (TMG) 2010 は、必要な公開ルールを示す目的で例として使用されますが、Forefront TMG 2010 は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c1093-141">Microsoft Forefront Threat Management Gateway (TMG) 2010 is used as an example for the purposes of illustrating the publishing rules necessary, but Forefront TMG 2010 is not required.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c1093-142">Lync Server 2013 は、IPv4 と IPv6 の両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c1093-142">Lync Server 2013 supports both IPv4 and IPv6.</span></span> <span data-ttu-id="c1093-143">Windows server&nbsp;2008&nbsp;r2、windows Server 2012、および windows server 2012 R2 では、IPv4 と IPv6 の両方で同時に使用できるデュアルスタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1093-143">Windows Server&nbsp;2008&nbsp;R2, Windows Server 2012, and Windows Server 2012 R2 use a dual stack that can use both IPv4 and IPv6 concurrently.</span></span> <span data-ttu-id="c1093-144">これは、IPv4 から IPv6 への展開の移行の性質が原因で重要です。</span><span class="sxs-lookup"><span data-stu-id="c1093-144">This is important because of the transitional nature of a deployment moving from IPv4 to IPv6.</span></span> <span data-ttu-id="c1093-145">IPv4 は、展開の他の領域で IPv6 を使うことができるいくつかの領域でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c1093-145">IPv4 can be supported in some areas, where in other areas of the deployment, IPv6 can be used.</span></span> <span data-ttu-id="c1093-146">これは、インターネットと社内の展開が関係する場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="c1093-146">This is especially important where the Internet and internal deployments are concerned.</span></span> <span data-ttu-id="c1093-147">外部クライアントは、モビリティ、会議、アドレス帳のダウンロードなどのサービスを使用するためにリバースプロキシ経由で通信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1093-147">External clients must communicate through the reverse proxy to use services such as mobility, meetings, address book download, and others.</span></span> <span data-ttu-id="c1093-148">現時点では、展開されているオペレーティングシステムのバージョンに関係なく、Forefront Threat Management Gateway 2010 およびインターネットセキュリティとアクセラレータサーバー2006は IPv6 アドレスをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c1093-148">Currently, Forefront Threat Management Gateway 2010 and Internet Security and Acceleration Server 2006 do not support IPv6 addressing, regardless of the operating system version that they are deployed on.</span></span> <span data-ttu-id="c1093-149">IPv6 と IPv4 を外部クライアントと関連付けて使用する場合は、それに合わせて計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1093-149">You must plan accordingly in relation to your use of IPv6 and IPv4 as they relate to external clients.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

