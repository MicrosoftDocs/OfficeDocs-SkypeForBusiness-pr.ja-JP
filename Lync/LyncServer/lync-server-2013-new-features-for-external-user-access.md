---
title: 'Lync Server 2013: 外部ユーザーアクセスの新機能'
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
ms.openlocfilehash: e85c9e83a6dde06c7c091241bea903a3ddd1d813
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="d2e2a-102">Lync Server 2013 の外部ユーザーアクセスの新機能</span><span class="sxs-lookup"><span data-stu-id="d2e2a-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2e2a-103">_**トピックの最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="d2e2a-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="d2e2a-104">Lync Server 2013 には、ユーザーの機能や通信方法を拡張する新機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="d2e2a-105">また、Lync Server 2013 では、組織で使用できるサービスをより適切に統合および拡張するための既存のサービスへの変更が導入されています。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="d2e2a-106">Lync Server 2013 エッジサーバーサービスの計画と展開に影響する可能性のある変更の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="d2e2a-107">**Ipv6 アドレス指定**   のサポート Lync server 2013 は、すべてのエッジサーバーサービスの ipv6 アドレスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="d2e2a-108">Windows Server の構成を使用してインターフェイスの IPv6 アドレスを指定した場合は、トポロジビルダーの IP アドレス構成を使用して、エッジサーバー構成で IPv6 アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d2e2a-109">Lync Server 2013 での IPv6 アドレスの使用は、組織が展開するルーターとファイアウォールでの IPv6 のサポート、およびインターネットサービスプロバイダーによるサポートに依存します。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="d2e2a-110">**拡張可能なメッセージングおよびプレゼンスプロトコル (xmpp)**   Lync Server 2013 には、完全に統合された xmpp プロキシ (エッジサーバーに展開される) と、フロントエンドサーバーに展開された xmpp ゲートウェイが導入されています。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="d2e2a-111">オプションのコンポーネントとして XMPP フェデレーションを展開できます。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="d2e2a-112">XMPP プロキシと XMPP ゲートウェイを追加して構成すると、Microsoft Lync 2013 ユーザーがインスタントメッセージング (IM) とプレゼンスの XMPP ベースのパートナーから連絡先を追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2e2a-113">現時点では、Lync Server 2013 の XMPP サービスは、Lync クライアントと XMPP ベースの連絡先間でインスタントメッセージングとプレゼンスを提供するだけです。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="d2e2a-114">**Mobile クライアント**   用のモビリティサービス lync server 2010 のモバイルサービス、lync server 2013 のモビリティサービスでは、サポートされている Apple iOS、Android、Windows Phone、または Nokia のモバイルデバイスを使用して、携帯電話やタブレットデバイスの Microsoft Lync mobile クライアントが、インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="d2e2a-115">また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、いくつかのエンタープライズ VoIP 機能もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2e2a-116">モビリティ サービスは、フロントエンド サーバーに展開されたリバース プロキシと公開されたサービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="d2e2a-117">エッジ サーバーの変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="d2e2a-118">**ディレクターはオプションの役割**   Lync server 2013 トポロジ内のディレクターサーバーの役割は変更されていません。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="d2e2a-119">fea-director-server-roleが推奨される役割からオプションの役割に変更されることにより、fea-director-server-roleの価値が下がるというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="d2e2a-120">推奨されている役割からオプションの役割にディレクターを変更しても、ディレクターの値は減少しませんが、サーバーの数とその他のハードウェア要件 (ディレクターのハードウェアロードバランサーなど) の要件が減少することが強調されます。機能の侵害。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="d2e2a-121">フロントエンドサーバーは、提供されるサービスに影響を与えることなく、ディレクターと同じジョブを実行できるため、必要に応じて、ディレクターを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="d2e2a-122">フロントエンドサーバーによって同じサービスが提供されるという確信を持って、ディレクターを安全に除外することができます。</span><span class="sxs-lookup"><span data-stu-id="d2e2a-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d2e2a-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2e2a-123">See Also</span></span>


[<span data-ttu-id="d2e2a-124">Lync Server 2013 での IPv6 の計画と構成</span><span class="sxs-lookup"><span data-stu-id="d2e2a-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="d2e2a-125">Lync Server 2013 での外部ユーザーアクセスの計画</span><span class="sxs-lookup"><span data-stu-id="d2e2a-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="d2e2a-126">Lync Server 2013 での拡張メッセージングおよびプレゼンスプロトコル (XMPP) フェデレーションの計画</span><span class="sxs-lookup"><span data-stu-id="d2e2a-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

