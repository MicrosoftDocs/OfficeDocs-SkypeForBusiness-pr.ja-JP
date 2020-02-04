---
title: 'Lync Server 2013: パブリック インスタント メッセージングのサポート'
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
ms.openlocfilehash: c3e3207d1a7a12f4db379e4d58615cffdfb45036
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="a9af3-102">Lync Server 2013 でのパブリック インスタント メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="a9af3-102">Public instant messaging support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9af3-103">_**最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="a9af3-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="a9af3-104">Lync Server 2013 では、ライセンス供与されたパブリックインスタントメッセージング (IM) 接続プロバイダーの使用、および Lync Server から構成済みの XMPP へのアクセスを可能にする、拡張メッセージングとプレゼンスプロトコル (XMPP) の使用がサポートされています。Lync 2013 クライアントを使用したドメインパートナー。</span><span class="sxs-lookup"><span data-stu-id="a9af3-104">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="a9af3-105">パブリック IM 接続プロバイダーのサポート</span><span class="sxs-lookup"><span data-stu-id="a9af3-105">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="a9af3-106">現在サポートされているパブリックインスタントメッセージング接続パートナーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9af3-106">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="a9af3-107">America Online</span><span class="sxs-lookup"><span data-stu-id="a9af3-107">America Online</span></span>

  - <span data-ttu-id="a9af3-108">Windows Live</span><span class="sxs-lookup"><span data-stu-id="a9af3-108">Windows Live</span></span>

  - <span data-ttu-id="a9af3-109">!\!</span><span class="sxs-lookup"><span data-stu-id="a9af3-109">Yahoo\!</span></span>

<span data-ttu-id="a9af3-110">Windows Live ユーザーとの通信には、Lync Server 2013 でピアツーピアの IM、音声通話、ビデオ通話がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a9af3-110">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="a9af3-111">AOL および Yahoo\!との通信には、Lync Server 2013 でピアツーピア IM がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a9af3-111">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="a9af3-112">別のライセンスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9af3-112">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="a9af3-113">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a9af3-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="a9af3-114">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="a9af3-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="a9af3-115">サービスが終了するまでの Messenger。</span><span class="sxs-lookup"><span data-stu-id="a9af3-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="a9af3-116">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="a9af3-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="a9af3-117">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="a9af3-117">has been announced.</span></span> <span data-ttu-id="a9af3-118">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9af3-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="a9af3-119">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="a9af3-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="a9af3-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="a9af3-120">Messenger.</span></span> <span data-ttu-id="a9af3-121">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</span><span class="sxs-lookup"><span data-stu-id="a9af3-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="a9af3-122">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="a9af3-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="a9af3-123">Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a9af3-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="a9af3-124">Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="a9af3-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="a9af3-125">XMPP フェデレーションサポート</span><span class="sxs-lookup"><span data-stu-id="a9af3-125">XMPP Federation Support</span></span>

<span data-ttu-id="a9af3-126">XMPP フェデレーションは、GTalk などのパブリックプロバイダーを使用する構成済みの XMPP ドメインユーザーとの Lync ユーザーとの通信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a9af3-126">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk.</span></span> <span data-ttu-id="a9af3-127">次のようなユーザーとのコミュニケーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9af3-127">Communications with these users can include the following:</span></span>

  - <span data-ttu-id="a9af3-128">ピアツーピアの IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="a9af3-128">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="a9af3-129">Lync クライアントでの XMPP フェデレーション連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="a9af3-129">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

