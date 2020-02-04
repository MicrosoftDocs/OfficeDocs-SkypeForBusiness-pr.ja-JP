---
title: 'Lync Server 2013: ネットワーク構成ダイアグラムを編集する'
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
ms.openlocfilehash: dc199098d27364c3bc5f512a48d2e512c7c9d984
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="391fe-102">Lync Server 2013 でのネットワーク構成図の編集</span><span class="sxs-lookup"><span data-stu-id="391fe-102">Editing the network configuration diagram in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="391fe-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="391fe-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="391fe-104">デザイナーが Lync Server 2013、計画ツールで行うことの大半は、IP アドレスとネットワークダイアグラム上のエントリの完全修飾ドメイン名 (Fqdn) のエントリを定義することで構成されています。</span><span class="sxs-lookup"><span data-stu-id="391fe-104">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="391fe-105">このページに入力された情報は、計画ツールに含まれているレポートやその他の情報に引き継がれます。</span><span class="sxs-lookup"><span data-stu-id="391fe-105">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="391fe-106">![計画ツール、ネットワーク図](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "計画ツール、ネットワーク図")</span><span class="sxs-lookup"><span data-stu-id="391fe-106">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="391fe-107">計画ツールでは、IP アドレスと Fqdn の既定のテキストを含むネットワークダイアグラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="391fe-107">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="391fe-108">ネットワーク ダイアグラムを編集して値を入力するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="391fe-108">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="391fe-p102">ネットワークのセクションを選択して作業を開始します。たとえば、**access1.contoso.com** というテキストをダブルクリックします。表示されるダイアログ ボックスで、サーバー access1.contoso.com の実際の FQDN と実際の IP アドレスを入力します (131.107.155.3 を置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="391fe-p102">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="391fe-112">[**OK**] をクリックしてエントリを保存します。</span><span class="sxs-lookup"><span data-stu-id="391fe-112">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="391fe-113">IP アドレスと FQDN の編集を続行し、プール内のサーバーのドメイン ネーム システム (DNS) 負荷分散に使用するハードウェア ロード バランサーまたはサーバーのエントリの仮想 IP アドレスを入力していきます。</span><span class="sxs-lookup"><span data-stu-id="391fe-113">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="391fe-p103">計画ツールには便利な機能があり、設計者がプール内の各サーバーを個別に編集する代わりに IP アドレス範囲およびサーバー ホスト名を増分して割り当てることができます。次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="391fe-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="391fe-p104">プールされているフロント エンド サーバーをダブルクリックします。ダイアログ ボックスが表示されたら、[**このクラスター内の対応するすべてのサーバーの開始点としてこの IP と FQDN を使用しますか?**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="391fe-p104">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="391fe-118">たとえば、最初のサーバーの開始値は fe0101.contoso.com で、IP アドレスは 192.168.21.122 です。</span><span class="sxs-lookup"><span data-stu-id="391fe-118">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="391fe-119">[**フロント エンド サーバーの FQDN**] に「**fe0.contoso.com**」、[**フロント エンド サーバーの IP アドレス**] に「**192.168.21.131**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="391fe-119">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="391fe-120">自動増分機能により、プール内のすべてのサーバーが fe01 ～ fe06 に更新され、すべての IP アドレスが 192.168.21.131 ～ 136 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="391fe-120">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="391fe-121">すべての編集が完了したら、次の手順を実行してトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="391fe-121">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="391fe-122">計画ツールのデザインを保存するには、[**ファイル**] をクリックし、[**トポロジの保存**] または [**トポロジを名前を付けて保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="391fe-122">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="391fe-123">[**名前を付けて計画ツールを保存**] ダイアログ ボックスが表示された場合、[**ファイル名**] にファイル名を入力して [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="391fe-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="391fe-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="391fe-124">See Also</span></span>


[<span data-ttu-id="391fe-125">Lync Server 2013 での設計の編集</span><span class="sxs-lookup"><span data-stu-id="391fe-125">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

