---
title: 'Lync Server 2013: フロントエンドサーバー、インスタントメッセージング、およびプレゼンスの要件の定義'
description: 'Lync Server 2013: フロントエンドサーバー、インスタントメッセージング、およびプレゼンスの要件を定義します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923132b32d5aef80191b19a7b85c3f17276e5946
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545373"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="46d59-103">Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの要件の定義</span><span class="sxs-lookup"><span data-stu-id="46d59-103">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46d59-104">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="46d59-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="46d59-105">インスタント メッセージング (IM) とプレゼンスの計画における主なタスクは、ユーザーのために十分な数のフロント エンド サーバーを確保することです。</span><span class="sxs-lookup"><span data-stu-id="46d59-105">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="46d59-106">外部ユーザーとの通信の有効化</span><span class="sxs-lookup"><span data-stu-id="46d59-106">Enabling Communication with External Users</span></span>

<span data-ttu-id="46d59-107">ユーザーが外部ユーザーと通信できるようにすることで、Lync Server に対する投資のメリットを大幅に向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="46d59-107">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="46d59-108">外部ユーザーには次のユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="46d59-108">External users can include:</span></span>

  - <span data-ttu-id="46d59-109">**リモートユーザー**    自分の組織のユーザーで、ファイアウォールの外側で作業し、ラップトップやその他の Lync Server デバイスを使用している場合。</span><span class="sxs-lookup"><span data-stu-id="46d59-109">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="46d59-110">**フェデレーションユーザー**    Lync Server を実行しているユーザーと共同で作業する企業のユーザー。</span><span class="sxs-lookup"><span data-stu-id="46d59-110">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="46d59-111">こちら側のユーザーがこれらのユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d59-111">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="46d59-112">**パブリックユーザー**    インターネットサービス、Yahoo、AOL の Windows Live ネットワークによって提供される IM サービスなどのパブリック IM サービスのユーザー、 \! および Google Talk などの拡張可能なメッセージングとプレゼンスプロトコル (XMPP) を使用するプロバイダーおよびサーバーのユーザー。</span><span class="sxs-lookup"><span data-stu-id="46d59-112">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46d59-113">ただし、Windows Live、AOL、Yahoo! とのパブリック IM 接続には、個別のライセンスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="46d59-113">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="46d59-114">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="46d59-114">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="46d59-115">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="46d59-115">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="46d59-116">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="46d59-116">Messenger until the service shut down date.</span></span> <span data-ttu-id="46d59-117">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="46d59-117">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="46d59-118">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="46d59-118">has been announced.</span></span> <span data-ttu-id="46d59-119">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d59-119">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="46d59-120">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="46d59-120">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="46d59-121">Messenger.</span><span class="sxs-lookup"><span data-stu-id="46d59-121">Messenger.</span></span> <span data-ttu-id="46d59-122">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="46d59-122">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="46d59-123">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="46d59-123">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="46d59-124">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="46d59-124">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="46d59-125">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="46d59-125">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="46d59-126">これらのシナリオのいずれかまたはすべてを有効にするには、Lync server の展開と外部ユーザーとの間でセキュリティで保護された通信を有効にするためにエッジサーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d59-126">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="46d59-127">組織のリモート ユーザーとフェデレーション組織のユーザーは、IM を使用して互いのプレゼンスと通信を確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="46d59-127">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="46d59-128">外部ユーザーとの通信の有効化の詳細については、「計画」のドキュメントの「 [planning for external user access In Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d59-128">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="46d59-129">IM コンテンツのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="46d59-129">Archiving IM Content</span></span>

<span data-ttu-id="46d59-130">Lync Server は、組織が法令遵守規制に従う必要がある場合に使用できる機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="46d59-130">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="46d59-131">アーカイブを使用すると、組織内のすべてのユーザーまたは指定した特定のユーザーに対して、IM メッセージの内容をアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="46d59-131">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="46d59-132">詳細については、「計画」のドキュメントの「 [planning For アーカイビング In Lync Server 2013](lync-server-2013-planning-for-archiving.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d59-132">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="46d59-133">Microsoft Exchange Server 2013 が展開されている場合は、Exchange データのアーカイブと Lync Server データのアーカイブを統合し、単一のツールを使用して両方の種類のアーカイブデータを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="46d59-133">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="46d59-134">詳細については、microsoft [Exchange server 2013 アーカイブを使用するように Microsoft Lync Server 2013 を構成する](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d59-134">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

