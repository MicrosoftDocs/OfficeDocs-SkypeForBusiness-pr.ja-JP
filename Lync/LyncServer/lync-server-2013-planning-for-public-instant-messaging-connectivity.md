---
title: 'Lync Server 2013: パブリックインスタントメッセージング接続の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52bc8a563a45e75b01932ee716df90f1cf2ca7da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="5716d-102">Lync Server 2013 でのパブリックインスタントメッセージング接続の計画</span><span class="sxs-lookup"><span data-stu-id="5716d-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5716d-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="5716d-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="5716d-104">パブリックインスタントメッセージング接続はフェデレーションのクラスであり、内部および外部の Lync Server 2013 ユーザーが次のいずれかの連絡先を追加できるように構成されています。</span><span class="sxs-lookup"><span data-stu-id="5716d-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="5716d-105">メッセンジャーの連絡先</span><span class="sxs-lookup"><span data-stu-id="5716d-105">Messenger contacts</span></span>

  - <span data-ttu-id="5716d-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="5716d-106">Yahoo\!</span></span> <span data-ttu-id="5716d-107">contacts</span><span class="sxs-lookup"><span data-stu-id="5716d-107">contacts</span></span>

  - <span data-ttu-id="5716d-108">America Online (AOL) の連絡先</span><span class="sxs-lookup"><span data-stu-id="5716d-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="5716d-109">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス (PIC USL) は、新規購入または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5716d-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="5716d-110">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="5716d-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="5716d-111">サービスの終了日までの Messenger。</span><span class="sxs-lookup"><span data-stu-id="5716d-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="5716d-112">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="5716d-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="5716d-113">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="5716d-113">has been announced.</span></span> <span data-ttu-id="5716d-114">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5716d-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="5716d-115">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの1か月あたりのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="5716d-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="5716d-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="5716d-116">Messenger.</span></span> <span data-ttu-id="5716d-117">このサービスを提供する Microsoft の機能は、Yahoo! からのサポートを受けています。これは、更新されない基になる契約です。</span><span class="sxs-lookup"><span data-stu-id="5716d-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="5716d-118">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="5716d-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5716d-119">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5716d-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="5716d-120">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を通じて数十万のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5716d-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="5716d-121">このクラスのフェデレーションには、計画に関する次のような考慮が必要です。</span><span class="sxs-lookup"><span data-stu-id="5716d-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="5716d-122">Windows Live Messenger ユーザーは、インスタントメッセージングに加えて、Lync Server 2013 ユーザーとのピアツーピアの音声ビデオ通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5716d-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="5716d-123">エッジサーバーは、特定のポートとプロトコルの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="5716d-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="5716d-124">詳細については、「 [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を確認する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5716d-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="5716d-125">Yahoo インスタントメッセージングには、フェデレーションを提供する一般的なエッジサーバーの計画と展開で通常使用される要件以外に、固有の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="5716d-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="5716d-126">America Online では、アクセスエッジサービスに割り当てられているエッジサーバー証明書にクライアント拡張キー使用法 (EKU) が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5716d-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5716d-127">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5716d-127">In This Section</span></span>

  - [<span data-ttu-id="5716d-128">証明書の概要-Lync Server 2013 でのパブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="5716d-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="5716d-129">ポートの概要-Lync Server 2013 でのパブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="5716d-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="5716d-130">[DNS の概要-Lync Server 2013 でのパブリックインスタントメッセージング接続](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5716d-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

