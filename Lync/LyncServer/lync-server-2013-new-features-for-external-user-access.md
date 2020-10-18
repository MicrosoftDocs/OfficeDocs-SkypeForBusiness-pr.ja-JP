---
title: 'Lync Server 2013: 外部ユーザーアクセスの新機能'
description: 'Lync Server 2013: 外部ユーザーアクセスの新機能。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9d960a469334a836c453e8ae3bbf51f1b66bb93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578843"
---
# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="89806-103">Lync Server 2013 の外部ユーザーアクセスの新機能</span><span class="sxs-lookup"><span data-stu-id="89806-103">New features for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89806-104">_**トピックの最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="89806-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="89806-105">Lync Server 2013 には、ユーザーの機能や通信方法を拡張する新機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="89806-105">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="89806-106">また、Lync Server 2013 では、組織で使用できるサービスをより適切に統合および拡張するための既存のサービスへの変更が導入されています。</span><span class="sxs-lookup"><span data-stu-id="89806-106">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="89806-107">Lync Server 2013 エッジサーバーサービスの計画と展開に影響する可能性のある変更の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="89806-107">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="89806-108">**IPv6 アドレス指定**     のサポートLync Server 2013 は、すべてのエッジサーバーサービスの IPv6 アドレスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="89806-108">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="89806-109">Windows Server の構成を使用してインターフェイスの IPv6 アドレスを指定した場合は、トポロジビルダーの IP アドレス構成を使用して、エッジサーバー構成で IPv6 アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89806-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89806-110">Lync Server 2013 での IPv6 アドレスの使用は、組織が展開するルーターとファイアウォールでの IPv6 のサポート、およびインターネットサービスプロバイダーによるサポートに依存します。</span><span class="sxs-lookup"><span data-stu-id="89806-110">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="89806-111">**拡張可能なメッセージングとプレゼンスプロトコル (XMPP)**    Lync Server 2013 には、完全に統合された XMPP プロキシ (エッジサーバーに展開されたもの) と、フロントエンドサーバーに展開された XMPP ゲートウェイが導入されています。</span><span class="sxs-lookup"><span data-stu-id="89806-111">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="89806-112">オプションのコンポーネントとして XMPP フェデレーションを展開できます。</span><span class="sxs-lookup"><span data-stu-id="89806-112">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="89806-113">XMPP プロキシと XMPP ゲートウェイを追加して構成すると、Microsoft Lync 2013 ユーザーがインスタントメッセージング (IM) とプレゼンスの XMPP ベースのパートナーから連絡先を追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="89806-113">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89806-114">現時点では、Lync Server 2013 の XMPP サービスは、Lync クライアントと XMPP ベースの連絡先間でインスタントメッセージングとプレゼンスを提供するだけです。</span><span class="sxs-lookup"><span data-stu-id="89806-114">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="89806-115">**モバイルクライアント**     用のモビリティサービスLync server 2010 のお客様向け更新プログラムで導入されました。 Lync Server 2013 のモバイルサービスでは、サポートされる Apple iOS、Android、Windows Phone、または Nokia のモバイルデバイスを使用して、携帯電話やタブレットデバイスの Microsoft Lync Mobile クライアントが、インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます</span><span class="sxs-lookup"><span data-stu-id="89806-115">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="89806-116">また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、いくつかのエンタープライズ VoIP 機能もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="89806-116">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89806-117">モビリティ サービスは、フロントエンド サーバーに展開されたリバース プロキシと公開されたサービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="89806-117">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="89806-118">エッジ サーバーの変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="89806-118">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="89806-119">**ディレクターはオプションの役割**    Lync Server 2013 トポロジ内のディレクターサーバーの役割は変更されていません。</span><span class="sxs-lookup"><span data-stu-id="89806-119">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="89806-120">fea-director-server-roleが推奨される役割からオプションの役割に変更されることにより、fea-director-server-roleの価値が下がるというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="89806-120">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="89806-121">推奨されている役割からオプションの役割にディレクターを変更しても、ディレクターの値は減少しませんが、サーバーの数とその他のハードウェア要件 (ディレクターのハードウェアロードバランサーなど) の削減により、機能が損なわれることが強調されています。</span><span class="sxs-lookup"><span data-stu-id="89806-121">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="89806-122">フロントエンドサーバーは、提供されるサービスに影響を与えることなく、ディレクターと同じジョブを実行できるため、必要に応じて、ディレクターを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="89806-122">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="89806-123">フロントエンドサーバーによって同じサービスが提供されるという確信を持って、ディレクターを安全に除外することができます。</span><span class="sxs-lookup"><span data-stu-id="89806-123">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="89806-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="89806-124">See Also</span></span>


[<span data-ttu-id="89806-125">Lync Server 2013 での IPv6 の計画と構成</span><span class="sxs-lookup"><span data-stu-id="89806-125">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="89806-126">Lync Server 2013 での外部ユーザーアクセスの計画</span><span class="sxs-lookup"><span data-stu-id="89806-126">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="89806-127">Lync Server 2013 での拡張メッセージングおよびプレゼンスプロトコル (XMPP) フェデレーションの計画</span><span class="sxs-lookup"><span data-stu-id="89806-127">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

