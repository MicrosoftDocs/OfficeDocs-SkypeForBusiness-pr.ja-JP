---
title: Lync Server 2013 IM とプレゼンス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18eb3d4a7fa5daaa59817d2eefde7af3a8e3f494
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="e71e5-102">Lync Server 2013 IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="e71e5-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e71e5-103">_**最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="e71e5-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="e71e5-104">インスタントメッセージング (IM) とプレゼンスは、任意の Lync Server 展開に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="e71e5-105">*プレゼンス*情報を使用すると、ユーザーは適切なコミュニケーション方法で同僚と連絡をとって、より生産的な作業環境を実現できます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="e71e5-106">ユーザーのプレゼンスは、空き時間情報、コミュニケーションの意思、その他のメモ (場所と状態など)、およびユーザーに連絡する方法を含む情報の集まりです。</span><span class="sxs-lookup"><span data-stu-id="e71e5-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="e71e5-107">プレゼンスは、Lync Server で、画像、場所情報、および "機能をオフにする"、"応答不可"、"退席中" など、"使用可能"、"取り込み中"、"会議中" などの基本的な状態を含む、プレゼンス状態が強化されています。</span><span class="sxs-lookup"><span data-stu-id="e71e5-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="e71e5-108">管理者は、カスタマイズされた、組織固有のプレゼンス状態を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="e71e5-109">[連絡先管理] および [ユーザーアクセス] オプションを使うと、他のユーザーが表示できる情報を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-109">Contact management and user access options enable users to control what information others can see.</span></span> <span data-ttu-id="e71e5-110">ユーザーは異なるレベルの連絡先を設定することができ、それぞれに異なるレベルのプレゼンス情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-110">Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="e71e5-111">連絡先リストを見るだけで、ユーザーはひとめで知っておく必要がある情報をすべて見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-111">By simply looking at a Contacts list, users can find everything they need to know at a glance.</span></span> <span data-ttu-id="e71e5-112">シンプルな色付きのアイコンは、他のユーザーのプレゼンス状態を示します。また、画像と場所も表示されます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-112">Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="e71e5-113">Lync Server と Outlook や SharePoint などの他の製品との統合により、連絡先の名前 (メールメッセージやチームの web サイトなど) が表示されるたびに、状態と連絡先の情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="e71e5-114">また、Exchange 2013 を展開した場合、Lync Server と Exchange 2013 では、いずれかの製品のクライアントからアクセスできるユニファイド連絡先ストアを共有できます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="e71e5-115">Lync Server でインスタントメッセージングを使用すると、ユーザーはタイムリーな情報を使用して互いに簡単にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="e71e5-116">必要に応じて、ユーザーは、MSN、Windows Live、Yahoo\!、AOL などのパブリック IM ネットワークのユーザーと通信することもできます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="e71e5-117">Windows Live、AOL、Yahoo とのパブリック IM 接続には個別のライセンスが必要になる場合があることに注意してください。\!</span><span class="sxs-lookup"><span data-stu-id="e71e5-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="e71e5-118">Lync Server には、拡張メッセージングとプレゼンスプロトコル (XMPP) の互換性も含まれているため、ユーザーは、Google Talk などの XMPP サービスのユーザーと IM メッセージとプレゼンス情報を交換することができます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="e71e5-119">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e71e5-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="e71e5-120">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="e71e5-121">サービスが終了するまでの Messenger。</span><span class="sxs-lookup"><span data-stu-id="e71e5-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="e71e5-122">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="e71e5-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="e71e5-123">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="e71e5-123">has been announced.</span></span> <span data-ttu-id="e71e5-124">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71e5-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="e71e5-125">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="e71e5-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="e71e5-126">Messenger.</span><span class="sxs-lookup"><span data-stu-id="e71e5-126">Messenger.</span></span> <span data-ttu-id="e71e5-127">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</span><span class="sxs-lookup"><span data-stu-id="e71e5-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="e71e5-128">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="e71e5-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="e71e5-129">Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e71e5-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="e71e5-130">Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="e71e5-131">会話履歴を使用すると、ユーザーは以前の IM 会話を追跡し、IM 月数前に伝えられた情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="e71e5-132">常設チャット機能を使うと、ユーザーはマルチパーティのトピックベースの会話に参加することができます。これにより、時間の経過と共に維持されます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="e71e5-133">チャットルーム (ディスカッションフォーラム) に投稿されたメッセージは、常にオンラインではない場合でも、異なる場所や部門のメンバーが参加できるように、継続的に (つまり、時間の経過と共に利用可能) することができます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="e71e5-134">組織でコンプライアンスの規則に従う必要がある場合は、メッセージアーカイブ機能を展開して、組織内のすべてのユーザーに対して、または指定した特定のユーザーのみにインスタントメッセージのコンテンツをアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="e71e5-135">また、Exchange 2013 を展開する場合は、IM アーカイブを Exchange のインプレースホールド機能と統合することで、コンプライアンスのために単一の管理エクスペリエンスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="e71e5-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

