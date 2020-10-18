---
title: 'Lync Server 2013: サービスのセッションを禁止する'
description: 'Lync Server 2013: サービスのセッションを禁止します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 846a9da5330c3e64f61c27dfadd883f0c43a0ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579813"
---
# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="4fcc3-103">Lync Server 2013 でのサービスのセッションを禁止する</span><span class="sxs-lookup"><span data-stu-id="4fcc3-103">Prevent sessions for services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fcc3-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4fcc3-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4fcc3-105">Lync server コントロールパネルを使用して、特定のコンピューターで実行されているすべての Lync Server 2013 サービスの新しいセッションを禁止したり、特定の Lync Server 2013 サービスの新しいセッションを禁止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-105">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="4fcc3-106">コンピューター上のすべての Lync Server サービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="4fcc3-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="4fcc3-107">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="4fcc3-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4fcc3-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4fcc3-110">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="4fcc3-111">[ **状態** ] ページで、必要に応じてリストを並べ替えまたは検索し、新しいセッションを禁止するサービスを実行しているコンピューターを見つけてクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="4fcc3-112">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-112">Click **Action**.</span></span>

6.  <span data-ttu-id="4fcc3-113">[ **すべてのサービスの新しいセッションを禁止する] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-113">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="4fcc3-114">特定のサービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="4fcc3-114">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="4fcc3-115">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="4fcc3-116">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4fcc3-117">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4fcc3-118">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="4fcc3-119">[**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="4fcc3-120">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="4fcc3-121">必要に応じてサービスの一覧を並べ替え、新しいセッションを禁止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-121">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="4fcc3-122">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-122">Click **Action**.</span></span>

8.  <span data-ttu-id="4fcc3-123">[ **サービスの新しいセッションを禁止する] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-123">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="4fcc3-124">[閉じる] \*\*\*\* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fcc3-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fcc3-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fcc3-125">See Also</span></span>


[<span data-ttu-id="4fcc3-126">Lync Server 2013 トポロジの管理</span><span class="sxs-lookup"><span data-stu-id="4fcc3-126">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

