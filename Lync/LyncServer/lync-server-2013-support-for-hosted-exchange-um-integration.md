---
title: Lync Server 2013 hosted Exchange UM 統合のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0625d983f05e5b9b22bf5086d0689c117b2ecda
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="a91f6-102">Lync Server 2013 での hosted Exchange UM 統合のサポート</span><span class="sxs-lookup"><span data-stu-id="a91f6-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a91f6-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a91f6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a91f6-104">Lync Server 2013 ExUM ルーティングアプリケーションは、オンプレミス環境での Exchange ユニファイドメッセージング (UM) との統合をサポートしています。これは、Lync Server の2013と Exchange UM の両方が企業内でローカルにインストールされているか、または、によってホストされる Exchange UM と共存しています。次の図に示すように、サービスプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="a91f6-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="a91f6-105">![オンプレミスの Lync Server Exchange UM 展開](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "オンプレミスの Lync Server Exchange UM 展開")</span><span class="sxs-lookup"><span data-stu-id="a91f6-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="a91f6-106">次のモードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a91f6-106">The following modes are supported:</span></span>

  - <span data-ttu-id="a91f6-107">**オンプレミスモード**   Lync Server 2013 と Exchange UM は、どちらも企業内のローカルサーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="a91f6-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="a91f6-108">**クロスプレミスモード**   Lync Server 2013 は、企業内のローカルサーバーに展開され、exchange UM は Microsoft Exchange online データセンターなどのオンラインサービスプロバイダーの施設でホストされます。</span><span class="sxs-lookup"><span data-stu-id="a91f6-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="a91f6-109">**混在モード**   Lync Server 2013 の展開には、企業内の Microsoft Exchange Server を実行しているローカルサーバーに所属するユーザーメールボックスと、ホストされている Exchange サービスデータセンターに所属する一部のメールボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="a91f6-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91f6-110">混在モードは、評価時に、ユーザーをホストされた Exchange UM に移行するための移行ソリューションとして、または他のユーザーの移行後に社内の Exchange UM サービスを社内に保持することを選択した場合の永続的なソリューションとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="a91f6-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="a91f6-111">Lync Server 2013 を hosted Exchange UM と統合するには、*共有 SIP アドレススペース*(*分割ドメイン*とも呼ばれます) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a91f6-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="a91f6-112">この構成では、Lync Server 2013 とサードパーティのホストされた Exchange UM サービスプロバイダーの両方が、同じ SIP ドメインアドレススペースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a91f6-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="a91f6-113">詳細については、「計画」のドキュメントの「 [Lync Server 2013 の Hosted EXCHANGE UM 統合アーキテクチャ](lync-server-2013-hosted-exchange-um-integration-architecture.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a91f6-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

