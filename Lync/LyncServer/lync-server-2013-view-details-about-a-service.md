---
title: 'Lync Server 2013: サービスについての詳細を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65fd84ad7290f3b82130f04d8b81955f6ffb4921
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="f7193-102">Lync Server 2013 でサービスに関する詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="f7193-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7193-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f7193-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f7193-104">Lync Server コントロールパネルを使うと、トポロジ内の特定のコンピューターで実行されている各サービスの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f7193-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="f7193-105">各サービスの状態と、関連するデータベース、ポート、依存サービスなどの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f7193-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="f7193-106">サービスの詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="f7193-106">To view details for a service</span></span>

1.  <span data-ttu-id="f7193-107">Lync Server 2013 の定義済みの管理者ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f7193-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="f7193-108">Lync Server 2013 で利用できる定義済みの管理者ロールの詳細については、「 [Lync server 2013 でのロールベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7193-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="f7193-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7193-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f7193-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7193-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f7193-111">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7193-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="f7193-112">[**状態**] ページで、リストを並べ替えるか検索して、表示するコンピューターをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7193-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="f7193-113">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7193-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="f7193-114">[**コンピューターの詳細の表示**] ウィンドウで、必要に応じてサービスの一覧を並べ替えて、表示するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7193-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="f7193-115">必要に応じて、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f7193-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="f7193-116">特定のサービスの最新の状態を表示するには、[**サービスの状態を取得**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7193-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="f7193-117">特定のサービスの詳細を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7193-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="f7193-118">トポロジに含まれるすべてのコンピューターの一覧に戻るには、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7193-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7193-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7193-119">See Also</span></span>


[<span data-ttu-id="f7193-120">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="f7193-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

