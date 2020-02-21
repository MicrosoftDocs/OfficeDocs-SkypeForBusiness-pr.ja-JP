---
title: 'Lync Server 2013: Lync Server サービスを開始または停止する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b95e9a49978499d16749f643cdd10d71637daf9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="1d103-102">Lync Server 2013 サービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="1d103-102">Start or stop Lync Server 2013 services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d103-103">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="1d103-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="1d103-104">Lync Server コントロールパネルを使用して、特定のコンピューターで実行されているすべての Lync Server 2013 サービスを開始または停止したり、特定のサービスを開始または停止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1d103-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="1d103-105">コンピューター上のすべての Lync Server サービスを開始または停止するには</span><span class="sxs-lookup"><span data-stu-id="1d103-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="1d103-106">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1d103-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="1d103-107">CsServerAdministrator または CsAdministrator の RBAC の役割が割り当てられているかどうかは、次のようなコマンドを実行することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="1d103-107">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="1d103-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1d103-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d103-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d103-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d103-110">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="1d103-111">[**状態**] ページで、必要に応じてリストを並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを見つけ、クリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="1d103-112">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-112">Click **Action**.</span></span>

6.  <span data-ttu-id="1d103-113">[**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-113">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="1d103-114">特定のサービスを開始または停止するには</span><span class="sxs-lookup"><span data-stu-id="1d103-114">To start or stop a specific service</span></span>

1.  <span data-ttu-id="1d103-115">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1d103-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d103-116">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1d103-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d103-117">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d103-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d103-118">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="1d103-119">[**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="1d103-120">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="1d103-121">必要に応じて、サービスのリストを並べ替え、開始または停止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-121">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="1d103-122">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-122">Click **Action**.</span></span>

8.  <span data-ttu-id="1d103-123">[**サービスの開始**] または [**サービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-123">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="1d103-124">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d103-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d103-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d103-125">See Also</span></span>


[<span data-ttu-id="1d103-126">Lync Server 2013 でのサービスのセッションを禁止する</span><span class="sxs-lookup"><span data-stu-id="1d103-126">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="1d103-127">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="1d103-127">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

