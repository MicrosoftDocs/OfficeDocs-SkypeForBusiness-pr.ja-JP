---
title: 'Lync Server 2013: Lync Server 2013 を実行しているコンピューターの一覧を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View a list of computers running Lync Server 2013
ms:assetid: 44eeec27-8b99-44f0-b0bd-622c12393d34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520987(v=OCS.15)
ms:contentKeyID: 48184030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce8b81f213e11f62632f4c74bdf62e3ac64e0168
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-computers-running-lync-server-2013"></a><span data-ttu-id="049cb-102">Lync Server 2013 を実行しているコンピューターの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="049cb-102">View a list of computers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="049cb-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="049cb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="049cb-104">Lync Server 2013 コントロールパネルを使って、トポロジで Lync Server 2013 を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービスの状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="049cb-104">You can use Lync Server 2013 Control Panel to view a list of all the computers that are running Lync Server 2013 in your topology and see the service status of each.</span></span> <span data-ttu-id="049cb-105">リストは、コンピューター、プール、またはサイトによって並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="049cb-105">You can sort the list by computer, pool, or site.</span></span>

<div>

## <a name="to-view-a-list-of-computers-running-lync-server"></a><span data-ttu-id="049cb-106">Lync Server を実行しているコンピューターの一覧を表示するには</span><span class="sxs-lookup"><span data-stu-id="049cb-106">To view a list of computers running Lync Server</span></span>

1.  <span data-ttu-id="049cb-107">Lync Server 2013 の定義済みの管理者ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="049cb-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="049cb-108">Lync Server 2013 で利用できる定義済みの管理者ロールの詳細については、「 [Lync server 2013 でのロールベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="049cb-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="049cb-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="049cb-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="049cb-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="049cb-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="049cb-111">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="049cb-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="049cb-112">[**状態**] ページで、必要に応じて次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="049cb-112">On the **Status** page, do any of the following as needed:</span></span>
    
      - <span data-ttu-id="049cb-113">**コンピューター**、**プール**、または**サイト**の列見出しをクリックし、上矢印または下矢印をクリックして、リストを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="049cb-113">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    
      - <span data-ttu-id="049cb-114">最新のリストを表示するには、[**更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="049cb-114">Click **Refresh** to view the most up-to-date list.</span></span>
    
      - <span data-ttu-id="049cb-115">検索フィールドにコンピューター名を入力して、特定のコンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="049cb-115">Search for a specific computer by typing the computer name in the search field.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="049cb-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="049cb-116">See Also</span></span>


[<span data-ttu-id="049cb-117">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="049cb-117">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

