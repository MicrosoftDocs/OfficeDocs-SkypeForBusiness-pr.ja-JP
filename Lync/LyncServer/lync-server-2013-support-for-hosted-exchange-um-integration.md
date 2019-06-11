---
title: 'Lync Server 2013: ホスト型 Exchange UM 統合のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="2147b-102">Lync Server 2013 でのホスト型 Exchange UM 統合のサポート</span><span class="sxs-lookup"><span data-stu-id="2147b-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2147b-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2147b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2147b-104">Lync server 2013 ExUM ルーティングアプリケーションでは、オンプレミス環境での Exchange ユニファイドメッセージング (UM) との統合をサポートしています。ここでは、Lync Server 2013 と Exchange UM が企業内のローカルにインストールされている場合、または a によってホストされている Exchange UM を使用している場合です。次の図に示すように、サービスプロバイダ。</span><span class="sxs-lookup"><span data-stu-id="2147b-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="2147b-105">![オンプレミスの Lync Server EXCHANGE UM の展開](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "オンプレミスの Lync Server EXCHANGE UM の展開")</span><span class="sxs-lookup"><span data-stu-id="2147b-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="2147b-106">次のモードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2147b-106">The following modes are supported:</span></span>

  - <span data-ttu-id="2147b-107">**オンプレミスモード**   の Lync Server 2013 および Exchange UM は、両方とも企業内のローカルサーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="2147b-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="2147b-108">**クロスプレミスモード**   の Lync Server 2013 は、企業内のローカルサーバーに展開され、exchange UM は Microsoft Exchange online のデータセンターなどのオンラインサービスプロバイダーの機能でホストされます。</span><span class="sxs-lookup"><span data-stu-id="2147b-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="2147b-109">**混在モード**   Lync Server 2013 の展開では、組織内の Microsoft Exchange Server を実行しているローカルサーバー上の一部のユーザーメールボックスと、ホスティングされている exchange service データセンターにある一部のメールボックスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="2147b-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2147b-110">混在モードは、評価中にユーザーをホストされた Exchange UM に移行するときに、移行ソリューションとして使用することができます。また、他のユーザーを移行した後で、一部のユーザーの Exchange UM サービスをオンプレミスのままにしておくと、永続的な解決策として使用できます。</span><span class="sxs-lookup"><span data-stu-id="2147b-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="2147b-111">Lync Server 2013 をホストされた Exchange UM と統合するには、*共有 SIP アドレス空間*(*分割ドメイン*とも呼ばれます) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2147b-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="2147b-112">この構成では、Lync Server 2013 とサードパーティがホストする Exchange UM サービスプロバイダーは両方とも、同じ SIP ドメインアドレス空間にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2147b-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="2147b-113">詳細については、計画ドキュメントの「 [Lync Server 2013 の Hosted EXCHANGE UM 統合アーキテクチャ](lync-server-2013-hosted-exchange-um-integration-architecture.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2147b-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

