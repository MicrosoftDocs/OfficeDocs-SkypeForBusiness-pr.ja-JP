---
title: 'Lync Server 2013: 外部ユーザーアクセスの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf3d85b7e3eae8839e3e65e02dde5955c8145c64
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a><span data-ttu-id="59575-102">Lync Server 2013 の外部ユーザーアクセスの概要</span><span class="sxs-lookup"><span data-stu-id="59575-102">Overview of external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59575-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="59575-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="59575-104">このドキュメントでは、*外部ユーザー*という用語を使用して、ファイアウォールの外側から lync Server 2013 および lync 2013 ユーザーと通信する大規模なユーザーのカテゴリを定義します。</span><span class="sxs-lookup"><span data-stu-id="59575-104">In this documentation, we use the term *external user* to define a large category of users who communicate with your Lync Server 2013 and Lync 2013 users from outside the firewall.</span></span> <span data-ttu-id="59575-105">Lync Server 2013 と内部ユーザーとの通信を承認できる外部ユーザー (つまり、ファイアウォールの内側から Lync Server にサインインしているユーザー) には、以下のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="59575-105">External users that you can authorize to communicate Lync Server 2013 with internal users (that is, users who sign in to Lync Server from inside the firewall) can include the following:</span></span>

  - <span data-ttu-id="59575-106">**リモートユーザー**   組織のユーザーが、ファイアウォールの外側から Lync Server にサインインしている。</span><span class="sxs-lookup"><span data-stu-id="59575-106">**Remote users**   Users of your organization who sign in to Lync Server from outside the firewall.</span></span>

  - <span data-ttu-id="59575-107">**フェデレーションユーザー**   : lync server 2010、lync server 2013、Office Communications server 2007 R2 などの信頼できる顧客またはパートナー組織のアカウントを持つユーザー。</span><span class="sxs-lookup"><span data-stu-id="59575-107">**Federated users**   Users who have an account with a trusted customer or partner organization, such as Lync Server 2010, Lync Server 2013 or Office Communications Server 2007 R2.</span></span> <span data-ttu-id="59575-108">また、フェデレーションユーザーは、エッジサーバー上の XMPP プロキシとフロントエンドサーバーまたはプール上の xmpp ゲートウェイによって、拡張可能なメッセージングとプレゼンスプロトコル (XMPP) を使用して、定義されたパートナー組織のメンバーになることもできます。</span><span class="sxs-lookup"><span data-stu-id="59575-108">Federated users can also be members of defined partner organizations using extensible messaging and presence protocol (XMPP) by way of the XMPP proxy on the Edge Server and XMPP gateway on the Front End Server or pool.</span></span> <span data-ttu-id="59575-109">フェデレーションと呼ばれる定義済みの信頼関係は、Active Directory ドメインサービスの信頼関係に関連していないか、または依存していません。</span><span class="sxs-lookup"><span data-stu-id="59575-109">A defined trust relationship, called a federation, is not related to or dependent upon an Active Directory Domain Services trust relationship.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59575-110">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="59575-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="59575-111">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="59575-111">has been announced.</span></span> <span data-ttu-id="59575-112">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59575-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="59575-113">\*\*\*\*   パブリックインスタントメッセージング接続ユーザーがパブリックインスタントメッセージング接続サービス (Windows Live、Yahoo) を介して確立した連絡先。\!</span><span class="sxs-lookup"><span data-stu-id="59575-113">**Public Instant Messaging Connectivity users**   Contacts that your users establish through public instant messaging connectivity services (Windows Live, Yahoo\!</span></span> <span data-ttu-id="59575-114">および AOL)。</span><span class="sxs-lookup"><span data-stu-id="59575-114">and AOL).</span></span>

  - <span data-ttu-id="59575-115">**モバイルユーザー**   組織のメンバーであり、スマートフォンまたは Lync Mobile クライアントを実行しているタブレットを使用するユーザーは、内部展開にサインインして、他のユーザークラスと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="59575-115">**Mobile users**   Users that are members of your organization that use a smart phone or tablet running a Lync Mobile client sign in to your internal deployment and are able to communicate with the other classes of users.</span></span> <span data-ttu-id="59575-116">モバイルユーザーは、リバースプロキシを介して公開された mobility services を使用して内部展開にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="59575-116">The mobile user uses mobility services that are published through the reverse proxy to access the internal deployment.</span></span> <span data-ttu-id="59575-117">Lync Mobile で利用できる機能の詳細については、「」のモバイルクライアント[https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777)の比較表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59575-117">For details on features and capabilities available to Lync Mobile , see the Mobile Client Comparison Tables at [https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777).</span></span>

  - <span data-ttu-id="59575-118">**匿名ユーザー**   組織の Active Directory ドメインサービスまたはサポートされているフェデレーションドメインでユーザーアカウントを持っていないが、オンプレミスの会議にリモートで参加する招待を受け取っているユーザー。</span><span class="sxs-lookup"><span data-stu-id="59575-118">**Anonymous users**   Users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but who have received invitations to participate remotely in an on-premises conference.</span></span>

<span data-ttu-id="59575-119">エッジ展開は、次の種類の通信に対する外部アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="59575-119">Your edge deployment provides external access for the following types of communication:</span></span>

  - <span data-ttu-id="59575-120">**Im およびプレゼンス**   権限がある外部ユーザーは、im 会話や会議に参加でき、互いのプレゼンス状態に関する情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="59575-120">**IM and presence**   Authorized external users can participate in IM conversations and conferences, and they can get information about one another’s presence status.</span></span> <span data-ttu-id="59575-121">パブリック IM サービスプロバイダーのユーザーは、組織内の個々の Lync Server ユーザーとの IM 会話に参加し、プレゼンス情報にアクセスできますが、Lync Server を使用して IM マルチパーティ会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="59575-121">Users of public IM service providers can participate in IM conversations with individual Lync Server users in your organization and access presence information, but they cannot participate in IM multiparty conferences using Lync Server.</span></span> <span data-ttu-id="59575-122">これは、厳密にピアツーピア通信です。</span><span class="sxs-lookup"><span data-stu-id="59575-122">It is strictly peer-to-peer communication.</span></span> <span data-ttu-id="59575-123">ファイル転送は、パブリック IM サービスプロバイダーのユーザーに対してはサポートされていません。ピアツーピア通信の音声ビデオは、Windows Messenger 2011 ユーザーに対してサポートされていますが、パブリック IM サービスプロバイダーの他のユーザーに対してはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="59575-123">File transfer is not supported for users of public IM service providers, and audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not other users of public IM service providers.</span></span>
    
    <span data-ttu-id="59575-124">SIP と XMPP の両方のプロトコルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="59575-124">Both SIP and XMPP protocols are supported.</span></span> <span data-ttu-id="59575-125">XMPP のサービスを提供するには、「 [Lync Server 2013 での SIP、XMPP フェデレーション、パブリックインスタントメッセージングの計画](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59575-125">To provide services for XMPP, see [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="59575-126">**Web 会議**   の承認済みの外部ユーザーは、Lync Server の展開でホストされている会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="59575-126">**Web conferencing**   Authorized external users can participate in conferences that are hosted on your Lync Server deployment.</span></span> <span data-ttu-id="59575-127">リモート ユーザー、フェデレーション ユーザー、および匿名ユーザーの Web 会議への参加は許可することができますが、パブリック IM ユーザーは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="59575-127">Remote users, federated users, and anonymous users can be enabled for participation in web conferencing, but public IM users cannot participate in conferences.</span></span> <span data-ttu-id="59575-128">選択するオプションに応じて、Web 会議への参加が許可されているユーザーは、デスクトップおよびアプリケーションの共有に参加でき、会議の開催者または発表者の役を務めることができます。</span><span class="sxs-lookup"><span data-stu-id="59575-128">Depending on the options that you select, web conferencing-enabled users can participate in desktop and application sharing and can act as meeting organizers or presenters.</span></span>

  - <span data-ttu-id="59575-129">\*\*\*\*   音声ビデオ会議の承認済みの外部ユーザーは、Lync Server 展開でホストされている音声ビデオ会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="59575-129">**A/V conferencing**   Authorized external users can participate in audio and video conferences that your Lync Server deployment hosts.</span></span> <span data-ttu-id="59575-130">ピアツーピア通信での音声/ビデオは、Windows Messenger 2011 ユーザーに対してサポートされていますが、パブリック IM サービスプロバイダーの他のユーザーに対してはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="59575-130">Audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not for other users of public IM service providers.</span></span>

<span data-ttu-id="59575-131">通信を制御するために、1つまたは複数のポリシーを構成して、組織内外のユーザーが相互に通信する方法を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="59575-131">In order to control communications, you can configure one or more policies that define how users inside and outside your organization communicate with each other.</span></span> <span data-ttu-id="59575-132">また、外部ユーザーとの通信を制御するために、個々の内部ユーザーまたは特定の種類の外部ユーザーに対して、設定を構成し、ポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="59575-132">You can also configure settings and apply policies for individual internal users or for specific types of external users to control communications with external users.</span></span>

<span data-ttu-id="59575-133">外部アクセスを提供するために使用される Lync Server 2013 の役割:</span><span class="sxs-lookup"><span data-stu-id="59575-133">Lync Server 2013 roles that are used to provide external access:</span></span>

<span data-ttu-id="59575-134">**エッジサーバー**   エッジサーバーは、IM、プレゼンス、会議、音声ビデオ、その他のメディア (たとえば、ファイル転送) サービスへの外部アクセスを許可するサービスを実行するサーバーまたはサーバーのプールです。</span><span class="sxs-lookup"><span data-stu-id="59575-134">**Edge Server**   The Edge Server is a server or a pool of servers that run the services that allow external access to IM and presence, conferencing, audio/video, and other media (for example, file transfer) services.</span></span> <span data-ttu-id="59575-135">必要に応じて、他の Lync Server または Office Communications Server 2007 R2 展開やその他の XMPP 展開とフェデレーションされるようにエッジサーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="59575-135">Optionally, you can configure the Edge Server to federate with other Lync Server or Office Communications Server 2007 R2 deployments, and other XMPP deployments.</span></span> <span data-ttu-id="59575-136">オプションのパブリック IM 接続機能は、エッジサーバーを使用して有効にし、構成します。</span><span class="sxs-lookup"><span data-stu-id="59575-136">The optional public IM connectivity feature is enabled and configured through the Edge Server.</span></span>

<span data-ttu-id="59575-137">**ディレクター**   ディレクターは、ユーザーの要求を事前認証し、要求をユーザーのホームフロントエンドサーバーまたはフロントエンドプールにルーティングする、Lync server 2013 ディレクターの役割を実行するオプションのサーバーまたはサーバープールです。ただし、ユーザーアカウントをホームにすることはありません。</span><span class="sxs-lookup"><span data-stu-id="59575-137">**Director**   The Director is an optional server or server pool running the Lync Server 2013 Director role that pre-authenticates user requests and routes requests to the users’ home Front End Server or Front End pool, but does not home any user accounts.</span></span>

<span data-ttu-id="59575-138">**リバースプロキシ**   リバースプロキシは、内部ネットワークで利用可能なリソースを公開し、発行されたリソースからクライアントの情報を取得する、専用のサーバーの一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="59575-138">**Reverse Proxy**   A reverse proxy is a general term for specialized servers that publish resources available on the internal network and retrieve information for clients from the published resource.</span></span> <span data-ttu-id="59575-139">Lync Server 2013 はリバースプロキシを使用して、会議会議、会議参加場所、アドレス帳、配布リストの拡張、会議コンテンツのダウンロード、デバイスの更新、モビリティサービスなど、さまざまな機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="59575-139">Lync Server 2013 uses the reverse proxy to publish a number of features, such as conferencing meetings, conference join locations, the address book, distribution list expansion, downloading meeting content, device updates, Mobility services, and more.</span></span> <span data-ttu-id="59575-140">必要なリソースの場所を公開するための要件を満たすことができるリバースプロキシを使用できます。</span><span class="sxs-lookup"><span data-stu-id="59575-140">Any reverse proxy that can meet the requirements for publishing the necessary resource locations can be used.</span></span> <span data-ttu-id="59575-141">Microsoft Forefront Threat Management Gateway (TMG) 2010 は、必要な公開ルールを示すための例として使用されていますが、Forefront TMG 2010 は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="59575-141">Microsoft Forefront Threat Management Gateway (TMG) 2010 is used as an example for the purposes of illustrating the publishing rules necessary, but Forefront TMG 2010 is not required.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59575-142">Lync Server 2013 は、IPv4 と IPv6 の両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="59575-142">Lync Server 2013 supports both IPv4 and IPv6.</span></span> <span data-ttu-id="59575-143">Windows Server&nbsp;2008&nbsp;r2、windows Server 2012、および windows server 2012 R2 は、IPv4 と IPv6 の両方を同時に使用できるデュアルスタックを使用します。</span><span class="sxs-lookup"><span data-stu-id="59575-143">Windows Server&nbsp;2008&nbsp;R2, Windows Server 2012, and Windows Server 2012 R2 use a dual stack that can use both IPv4 and IPv6 concurrently.</span></span> <span data-ttu-id="59575-144">これは、IPv4 から IPv6 への展開の移行の性質上、重要です。</span><span class="sxs-lookup"><span data-stu-id="59575-144">This is important because of the transitional nature of a deployment moving from IPv4 to IPv6.</span></span> <span data-ttu-id="59575-145">IPv4 は、一部の分野ではサポートされており、他の領域では IPv6 を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="59575-145">IPv4 can be supported in some areas, where in other areas of the deployment, IPv6 can be used.</span></span> <span data-ttu-id="59575-146">これは、インターネットと内部の展開に関して特に重要です。</span><span class="sxs-lookup"><span data-stu-id="59575-146">This is especially important where the Internet and internal deployments are concerned.</span></span> <span data-ttu-id="59575-147">外部クライアントは、モビリティ、会議、アドレス帳のダウンロードなどのサービスを使用するために、リバースプロキシを介して通信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59575-147">External clients must communicate through the reverse proxy to use services such as mobility, meetings, address book download, and others.</span></span> <span data-ttu-id="59575-148">現時点では、Forefront Threat Management Gateway 2010 および Internet Security and アクセラレーションサーバー2006は、展開されているオペレーティングシステムのバージョンに関係なく、IPv6 アドレスをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="59575-148">Currently, Forefront Threat Management Gateway 2010 and Internet Security and Acceleration Server 2006 do not support IPv6 addressing, regardless of the operating system version that they are deployed on.</span></span> <span data-ttu-id="59575-149">外部クライアントに関連する場合は、IPv6 と IPv4 の使用に関して計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59575-149">You must plan accordingly in relation to your use of IPv6 and IPv4 as they relate to external clients.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

