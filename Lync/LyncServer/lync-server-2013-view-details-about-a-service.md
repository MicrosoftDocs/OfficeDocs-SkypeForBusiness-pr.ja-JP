---
title: 'Lync Server 2013: サービスに関する詳細の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8268720754f0f34fa24a5a5c7beef9ac21b5d3e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="55fe5-102">Lync Server 2013 のサービスに関する詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="55fe5-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55fe5-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="55fe5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="55fe5-104">Lync Server コントロールパネルを使用して、トポロジ内の特定のコンピューターで実行されている各サービスの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="55fe5-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="55fe5-105">各サービスの状態と、関連付けられたデータベース、ポート、依存サービスなどの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="55fe5-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="55fe5-106">サービスの詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="55fe5-106">To view details for a service</span></span>

1.  <span data-ttu-id="55fe5-107">Lync Server 2013 の定義済みの管理者の役割のいずれかに割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="55fe5-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="55fe5-108">Lync Server 2013 で使用できる定義済みの管理者の役割の詳細については、「 [Lync server 2013 で役割ベースのアクセス制御を計画する](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55fe5-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="55fe5-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="55fe5-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="55fe5-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55fe5-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="55fe5-111">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fe5-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="55fe5-112">[**状態**] ページで、一覧を並べ替えるか検索して、表示するコンピューターをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fe5-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="55fe5-113">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fe5-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="55fe5-114">[**コンピューター詳細の表示**] ウィンドウで、必要な場合はサービスの一覧を並べ替えてから、表示するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fe5-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="55fe5-115">必要に応じて、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55fe5-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="55fe5-116">指定したサービスの最新の状態を表示するには、[**サービスの状態の取得**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fe5-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="55fe5-117">指定したサービスの詳細を表示するには、[**プロパティ**] をクリックしてから、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fe5-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="55fe5-118">トポロジ内のすべてのコンピューターの一覧を返すには、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fe5-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55fe5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="55fe5-119">See Also</span></span>


[<span data-ttu-id="55fe5-120">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="55fe5-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

