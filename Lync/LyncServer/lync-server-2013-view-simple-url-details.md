---
title: 'Lync Server 2013: 簡単な URL の詳細の表示'
description: 'Lync Server 2013: 簡単な URL の詳細を表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View simple URL details
ms:assetid: 6ab00f2c-e1d5-4698-a58f-04b72260f9ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521010(v=OCS.15)
ms:contentKeyID: 48184399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ceede3697248415018a92ac77fb20670fbcd8d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579613"
---
# <a name="view-simple-url-details-in-lync-server-2013"></a><span data-ttu-id="4fa81-103">Lync Server 2013 での簡単な URL の詳細の表示</span><span class="sxs-lookup"><span data-stu-id="4fa81-103">View simple URL details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fa81-104">_**トピックの最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="4fa81-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="4fa81-105">Lync server 2013 コントロールパネルを使用して、Lync Server 2013 環境の簡単な URL の詳細を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4fa81-105">You can use Lync Server 2013 Control Panel to view simple URL details for your Lync Server 2013 environment.</span></span> <span data-ttu-id="4fa81-106">簡易 URL を使用すると、ユーザーは会議への参加が容易になり、管理者は管理ツールへのアクセスが容易になります。</span><span class="sxs-lookup"><span data-stu-id="4fa81-106">Simple URLs make it easier for users to join meetings, and they make it easier for administrators to get to administrative tools.</span></span> <span data-ttu-id="4fa81-107">詳細については、「 [Lync Server 2013 の簡易 url の計画](lync-server-2013-planning-for-simple-urls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fa81-107">For details, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<div>

## <a name="to-view-simple-url-details"></a><span data-ttu-id="4fa81-108">簡易 URL の詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="4fa81-108">To view Simple URL details</span></span>

1.  <span data-ttu-id="4fa81-109">CsServerAdministrator、CsAdministrator、CsHelpDesk、または CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4fa81-109">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="4fa81-110">Lync Server 2013 で使用できる定義済みの管理者の役割の詳細については、「 [Lync server 2013 で役割ベースのアクセス制御を計画する](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fa81-110">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="4fa81-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4fa81-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4fa81-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fa81-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4fa81-113">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**簡易 URL**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fa81-113">In the left navigation bar, click **Topology** and then click **Simple URL**.</span></span>

4.  <span data-ttu-id="4fa81-114">[**簡易 URL**] ページの列見出しをクリックし、必要に応じて一覧を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="4fa81-114">On the **Simple URL** page, click a column heading to sort the list, if needed.</span></span>

5.  <span data-ttu-id="4fa81-115">簡易 URL の詳細を表示する名前を選択し、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fa81-115">Select the name for which you want to see simple URL details, and then click **Properties**.</span></span>

6.  <span data-ttu-id="4fa81-116">詳細を見終わったら [**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fa81-116">When you are finished viewing details, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fa81-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fa81-117">See Also</span></span>


[<span data-ttu-id="4fa81-118">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="4fa81-118">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

