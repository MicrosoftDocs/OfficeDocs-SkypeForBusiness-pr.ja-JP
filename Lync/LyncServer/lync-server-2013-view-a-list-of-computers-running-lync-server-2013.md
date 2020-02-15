---
title: 'Lync Server 2013: Lync Server 2013 を実行しているコンピューターの一覧を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of computers running Lync Server 2013
ms:assetid: 44eeec27-8b99-44f0-b0bd-622c12393d34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520987(v=OCS.15)
ms:contentKeyID: 48184030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05193ab70846918bd4106883583e42da03b541fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-computers-running-lync-server-2013"></a><span data-ttu-id="9047d-102">Lync Server 2013 を実行しているコンピューターの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="9047d-102">View a list of computers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9047d-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9047d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9047d-104">Lync server 2013 コントロールパネルを使用して、トポロジで Lync Server 2013 を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービスの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9047d-104">You can use Lync Server 2013 Control Panel to view a list of all the computers that are running Lync Server 2013 in your topology and see the service status of each.</span></span> <span data-ttu-id="9047d-105">この一覧は、コンピューター、プール、またはサイトごとに並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="9047d-105">You can sort the list by computer, pool, or site.</span></span>

<div>

## <a name="to-view-a-list-of-computers-running-lync-server"></a><span data-ttu-id="9047d-106">Lync Server を実行しているコンピューターの一覧を表示するには</span><span class="sxs-lookup"><span data-stu-id="9047d-106">To view a list of computers running Lync Server</span></span>

1.  <span data-ttu-id="9047d-107">Lync Server 2013 の定義済みの管理者の役割のいずれかに割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9047d-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="9047d-108">Lync Server 2013 で使用できる定義済みの管理者の役割の詳細については、「 [Lync server 2013 で役割ベースのアクセス制御を計画する](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9047d-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="9047d-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9047d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9047d-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9047d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9047d-111">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9047d-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="9047d-112">[**状態**] ページで、必要に応じて、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9047d-112">On the **Status** page, do any of the following as needed:</span></span>
    
      - <span data-ttu-id="9047d-113">[**コンピューター**]、[**プール**]、または [**サイト**] 列の見出しをクリックし、上矢印または下矢印をクリックして、一覧を並べ変えます。</span><span class="sxs-lookup"><span data-stu-id="9047d-113">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    
      - <span data-ttu-id="9047d-114">[**更新**] をクリックして、最新の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="9047d-114">Click **Refresh** to view the most up-to-date list.</span></span>
    
      - <span data-ttu-id="9047d-115">検索フィールドにコンピューター名を入力することで、特定のコンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="9047d-115">Search for a specific computer by typing the computer name in the search field.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9047d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9047d-116">See Also</span></span>


[<span data-ttu-id="9047d-117">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="9047d-117">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

