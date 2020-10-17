---
title: 'Lync Server 2013: ネットワーク構成ダイアグラムの編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc137b6dfd8fa33e3826f7d6b59f1bb649a3189
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501104"
---
# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="d5d7a-102">Lync Server 2013 でのネットワーク構成ダイアグラムの編集</span><span class="sxs-lookup"><span data-stu-id="d5d7a-102">Editing the network configuration diagram in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5d7a-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d5d7a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d5d7a-104">設計者が Lync Server 2013 で行う作業のほとんどは、計画ツールであり、ネットワークダイアグラム上のエントリの IP アドレスと完全修飾ドメイン名 (Fqdn) のエントリを定義することによって構成されます。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-104">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="d5d7a-105">このページに入力された情報は、計画ツールに含まれるレポートやその他の情報に引き継がれます。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-105">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="d5d7a-106">![計画ツール、ネットワーク図](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "計画ツール、ネットワーク図")</span><span class="sxs-lookup"><span data-stu-id="d5d7a-106">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="d5d7a-107">計画ツールは、IP アドレスと Fqdn の既定のテキストを使用してネットワーク図を作成します。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-107">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="d5d7a-108">ネットワーク ダイアグラムを編集して値を入力するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-108">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="d5d7a-109">作業を開始するネットワークの部分を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-109">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="d5d7a-110">たとえば、テキスト **access1.contoso.com**をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-110">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="d5d7a-111">表示されるダイアログボックスで、サーバー access1.contoso.com の実際の FQDN と実際の IP アドレスを入力し、131.107.155.3 を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-111">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="d5d7a-112">**[OK]** をクリックしてエントリを保存します。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-112">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="d5d7a-113">IP アドレスと FQDN の編集を続行し、プール内のサーバーのドメイン ネーム システム (DNS) 負荷分散に使用するハードウェア ロード バランサーまたはサーバーのエントリの仮想 IP アドレスを入力していきます。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-113">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="d5d7a-p103">計画ツールには便利な機能があり、設計者がプール内の各サーバーを個別に編集する代わりに IP アドレス範囲およびサーバー ホスト名を増分して割り当てることができます。次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="d5d7a-116">プールされたフロントエンドサーバーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-116">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="d5d7a-117">ダイアログボックスが開いたら、[ **このクラスター内のすべての同等のサーバーの開始点として ip と FQDN を使用しますか?**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-117">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="d5d7a-118">たとえば、最初のサーバーの開始値は fe0101.contoso.com で、IP アドレスは192.168.21.122 です。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-118">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="d5d7a-119">「 **Fe0.contoso.com** に **フロントエンドサーバーの FQDN**」と入力し、「 **192.168.21.131** 」と入力し **て、[** **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-119">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="d5d7a-120">自動インクリメント機能は、プール内のすべてのサーバーをがそれぞれ経由で fe01 に更新し、すべての IP アドレスを192.168.21.131 から136に更新します。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-120">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="d5d7a-121">すべての編集を完了したら、次の手順を実行してトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-121">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="d5d7a-122">計画ツールのデザインを保存するには、[ **ファイル**] をクリックし、[ **トポロジの保存** ] または [トポロジに名前を付け **て保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-122">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="d5d7a-123">**[名前を付けて計画ツールを保存]** ダイアログ ボックスが表示された場合、**[ファイル名]** にファイル名を入力して **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5d7a-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d5d7a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5d7a-124">See Also</span></span>


[<span data-ttu-id="d5d7a-125">Lync Server 2013 での設計の編集</span><span class="sxs-lookup"><span data-stu-id="d5d7a-125">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

