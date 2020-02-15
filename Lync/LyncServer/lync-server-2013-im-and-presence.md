---
title: Lync Server 2013 IM およびプレゼンス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a7713f7b09602aed01ac20e5a76a361e04277a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="e1d3e-102">Lync Server 2013 の IM およびプレゼンス</span><span class="sxs-lookup"><span data-stu-id="e1d3e-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1d3e-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="e1d3e-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="e1d3e-104">インスタントメッセージング (IM) とプレゼンスは、任意の Lync Server 展開に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="e1d3e-105">*プレゼンス*情報を使用すると、ユーザーは適切なコミュニケーション方法を使用して、適切なタイミングで仕事仲間にアプローチし、より生産性の高い作業環境にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="e1d3e-106">ユーザーのプレゼンスとは、空き時間、コミュニケーションの意思、追加のメモ (場所や状態など)、およびユーザーに連絡する方法を含む情報のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="e1d3e-107">プレゼンスが Lync Server で拡張され、画像、場所情報、および "使用可能"、"通話中"、"会議中" などの基本状態に加えて、"作業時間"、"応答不可"、"その他" などのプレゼンス状態の豊富なセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="e1d3e-108">管理者は、カスタマイズされた組織固有のプレゼンス状態を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="e1d3e-p102">ユーザーは、連絡先の管理とユーザー アクセスのオプションを使って、他のユーザーが表示できる情報を制御できます。ユーザーは異なるレベルの連絡先を設定でき、それぞれの連絡先は異なるレベルのプレゼンス情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-p102">Contact management and user access options enable users to control what information others can see. Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="e1d3e-p103">連絡先リストを見るだけで、ユーザーは知る必要があるすべての情報を一目で確認できます。シンプルな色付きのアイコンは他のユーザーのプレゼンス状態を示し、写真や場所も表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-p103">By simply looking at a Contacts list, users can find everything they need to know at a glance. Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="e1d3e-113">Lync Server と Outlook や SharePoint などの他の製品との統合により、電子メールメッセージやチームの web サイトなどの連絡先の名前が表示されるたびに、状態と連絡先の情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="e1d3e-114">さらに、Exchange 2013 を展開すると、Lync Server と Exchange 2013 は、いずれかの製品のクライアントがアクセスできる統合連絡先ストアを共有できます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="e1d3e-115">Lync Server でインスタントメッセージングを使用すると、ユーザーはタイムリーに情報をすばやくメッセージすることができます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="e1d3e-116">必要に応じて、ユーザーは MSN、Windows Live、Yahoo\!、AOL などのパブリック IM ネットワークのユーザーと通信することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="e1d3e-117">Windows Live、AOL、および Yahoo とのパブリック IM 接続には、個別のライセンスが必要になる場合があることに注意してください。\!</span><span class="sxs-lookup"><span data-stu-id="e1d3e-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="e1d3e-118">Lync Server には、拡張可能なメッセージングとプレゼンスプロトコル (XMPP) の互換性もあります。このため、ユーザーは、Google Talk などの XMPP サービスのユーザーと IM メッセージやプレゼンス情報を交換できます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="e1d3e-119">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="e1d3e-120">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="e1d3e-121">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="e1d3e-122">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="e1d3e-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="e1d3e-123">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-123">has been announced.</span></span> <span data-ttu-id="e1d3e-124">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="e1d3e-125">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="e1d3e-126">Messenger.</span><span class="sxs-lookup"><span data-stu-id="e1d3e-126">Messenger.</span></span> <span data-ttu-id="e1d3e-127">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="e1d3e-128">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="e1d3e-129">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="e1d3e-130">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="e1d3e-131">会話履歴では、古い IM 会話の経過をたどることができ、何か月も前に IM でやり取りした可能性のある情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="e1d3e-132">常設チャット機能を使用すると、ユーザーは、時間の経過とともに保持されるマルチパーティのトピックベースの会話に参加できます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="e1d3e-133">チャット ルーム (ディスカッション フォーラム) に投稿されたメッセージは永続的 (すなわち、長期間使用可能) にできるので、異なる場所や部門に所属するユーザーが常に同時にオンラインでない場合でも会話に参加できます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="e1d3e-134">組織で法令上の規制に従う必要がある場合、メッセージ アーカイブ機能を展開し、組織内のすべてのユーザーまたは指定した一部のユーザーのみのインスタント メッセージの内容をアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="e1d3e-135">Exchange 2013 も展開する場合、IM アーカイブを Exchange のインプレースホールド機能と統合して、コンプライアンスに対して単一の管理環境を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="e1d3e-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

