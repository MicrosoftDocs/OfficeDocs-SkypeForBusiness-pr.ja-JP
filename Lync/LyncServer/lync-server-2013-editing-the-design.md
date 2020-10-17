---
title: 'Lync Server 2013: 設計の編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68a1a4257279f786d35c89153e0cf2154b39a6b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501114"
---
# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="7e461-102">Lync Server 2013 での設計の編集</span><span class="sxs-lookup"><span data-stu-id="7e461-102">Editing the design in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e461-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7e461-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7e461-104">最初のインタビューの質問を完了したら、サイトの完全修飾ドメイン名 (FQDN) と IP アドレスを編集できます。</span><span class="sxs-lookup"><span data-stu-id="7e461-104">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="7e461-105">これを行うには、**[グローバル トポロジ]** ページで、編集するサイトをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e461-105">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="7e461-106">計画ツールでは、選択したサイトのサイトトポロジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e461-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="7e461-107">サイト ページの下部には、次の 4 つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="7e461-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="7e461-108">![計画ツールサイトトポロジ](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "計画ツールサイトトポロジ")</span><span class="sxs-lookup"><span data-stu-id="7e461-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="7e461-109">サイト トポロジ – 現在表示されているページで、推奨されるビジュアルなトポロジの概要が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e461-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="7e461-110">エッジネットワーク図–エッジネットワークの図のページでは、計画ツールでの作業の大部分がデザイナーによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="7e461-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="7e461-111">図は、推奨される Lync Server 2013 トポロジのネットワーク構成を表示します。これには、サーバー、プール、およびハードウェアおよびドメインネームシステム (DNS) ロードバランサーの IP アドレスと Fqdn の編集可能なエントリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e461-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="7e461-112">エッジ管理レポート – 次の合計 4 つのレポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e461-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="7e461-113">![エッジ管理レポートページ](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "エッジ管理レポートページ")</span><span class="sxs-lookup"><span data-stu-id="7e461-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="7e461-114">概要レポート – エッジ ネットワーク構成の設定に関する一般的なレポート。</span><span class="sxs-lookup"><span data-stu-id="7e461-114">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="7e461-115">[ **エッジネットワーク図** ] ページの値を、実際の展開で使用されるトポロジの TCP/IP および FQDN 値に編集すると、それらのアドレスと名前がここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e461-115">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="7e461-116">それ以外の場合は、既定のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e461-116">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="7e461-117">証明書レポート – トポロジで必要な証明書のサブジェクト名とサブジェクトの別名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e461-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="7e461-118">ファイアウォール レポート – インフラストラクチャで周辺ファイアウォールを構成するために必要な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e461-118">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="7e461-119">これには、IP アドレス (既定または編集された値)、サーバーの役割、送信元の IP アドレスとポート、送信先 IP とポート、トランスポートプロトコル、アプリケーションプロトコル、関連メモが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e461-119">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="7e461-120">DNS レポート– dns レポートには、作成する必要がある DNS エントリの関連情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e461-120">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="7e461-121">正しい動作に必要なレコードの種類、FQDN、IP アドレス、およびコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e461-121">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="7e461-122">サイトの概要: サイトの概要は、最初のインタビューの質問に回答するか、または **設計サイト**の値を入力することによって、選択した選択の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="7e461-122">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="7e461-123">容量情報も記載されています。</span><span class="sxs-lookup"><span data-stu-id="7e461-123">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e461-124">サイトの概要ページの情報は、設計ごとにカスタマイズされるため、ここで説明しているすべてのセクションや情報が含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e461-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="7e461-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e461-125">See Also</span></span>


[<span data-ttu-id="7e461-126">Lync Server 2013 でのネットワーク構成ダイアグラムの編集</span><span class="sxs-lookup"><span data-stu-id="7e461-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

