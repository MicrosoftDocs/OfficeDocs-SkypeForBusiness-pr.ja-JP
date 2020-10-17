---
title: 'Lync Server 2013: パブリックインスタントメッセージングのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026ceb24ef3e046d6d800db4ba82381c8905b99d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512404"
---
# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="96efe-102">Lync Server 2013 でのパブリックインスタントメッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="96efe-102">Public instant messaging support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96efe-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="96efe-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="96efe-104">Lync Server 2013 は、ライセンス付きのパブリックインスタントメッセージング (IM) 接続プロバイダーの使用と、lync Server が Lync 2013 クライアントを使用して構成された XMPP ドメインパートナーにアクセスできるようにする特別な種類のフェデレーションを実装するための拡張メッセージングおよびプレゼンスプロトコル (XMPP) の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="96efe-104">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="96efe-105">パブリック IM 接続プロバイダーのサポート</span><span class="sxs-lookup"><span data-stu-id="96efe-105">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="96efe-106">現在サポートされているパブリック インスタント メッセージング接続パートナーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="96efe-106">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="96efe-107">America Online</span><span class="sxs-lookup"><span data-stu-id="96efe-107">America Online</span></span>

  - <span data-ttu-id="96efe-108">Windows Live</span><span class="sxs-lookup"><span data-stu-id="96efe-108">Windows Live</span></span>

  - <span data-ttu-id="96efe-109">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="96efe-109">Yahoo\!</span></span>

<span data-ttu-id="96efe-110">Windows Live ユーザーとの通信の場合、Lync Server 2013 は、ピアツーピア IM および音声通話およびビデオ通話をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="96efe-110">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="96efe-111">AOL および Yahoo との通信で \! は、Lync Server 2013 はピアツーピア IM をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="96efe-111">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="96efe-112">別のライセンスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="96efe-112">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="96efe-113">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="96efe-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="96efe-114">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="96efe-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="96efe-115">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="96efe-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="96efe-116">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="96efe-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="96efe-117">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="96efe-117">has been announced.</span></span> <span data-ttu-id="96efe-118">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96efe-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="96efe-119">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="96efe-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="96efe-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="96efe-120">Messenger.</span></span> <span data-ttu-id="96efe-121">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="96efe-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="96efe-122">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="96efe-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="96efe-123">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="96efe-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="96efe-124">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="96efe-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="96efe-125">XMPP フェデレーションのサポート</span><span class="sxs-lookup"><span data-stu-id="96efe-125">XMPP Federation Support</span></span>

<span data-ttu-id="96efe-p105">XMPP フェデレーションにより、Lync ユーザーは GTalk などのパブリック プロバイダーを使用する構成済み XMPP ドメイン ユーザーと通信することができます。これらのユーザーとの通信では、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="96efe-p105">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk. Communications with these users can include the following:</span></span>

  - <span data-ttu-id="96efe-128">ピアツーピア IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="96efe-128">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="96efe-129">Lync クライアントでの XMPP フェデレーションからの連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="96efe-129">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

