---
title: Skype for Business Server 2015 でトポロジを編集する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: 最初のインタビューの質問が完了すると、サイトの完全修飾ドメイン名 (FQDN) と IP アドレスを編集できます。 これを行うには、[グローバル トポロジ] ページで、編集するサイトをダブルクリックします。
ms.openlocfilehash: 9a345c753195c32907d078d5ee4a267b8b96d6b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093185"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="6667f-104">Skype for Business Server 2015 でトポロジを編集する</span><span class="sxs-lookup"><span data-stu-id="6667f-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="6667f-105">最初のインタビューの質問が完了すると、サイトの完全修飾ドメイン名 (FQDN) と IP アドレスを編集できます。</span><span class="sxs-lookup"><span data-stu-id="6667f-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="6667f-106">これを行うには、**[グローバル トポロジ]** ページで、編集するサイトをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6667f-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="6667f-107">計画ツールは、選択したサイトのサイト トポロジを表示します。</span><span class="sxs-lookup"><span data-stu-id="6667f-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="6667f-108">サイト ページの下部には、次の 4 つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="6667f-108">At the bottom of the site page are four tabs:</span></span>

![計画ツール サイト トポロジ](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="6667f-110">サイト トポロジ - 推奨されるトポロジの視覚的な概要を示す現在表示されているページ。</span><span class="sxs-lookup"><span data-stu-id="6667f-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="6667f-111">エッジ ネットワークダイアグラム - [エッジ ネットワークダイアグラム] ページは、デザイナーが計画ツールのほとんどの作業を行う場所です。</span><span class="sxs-lookup"><span data-stu-id="6667f-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="6667f-112">この図には、推奨される Skype for Business Server 2015 トポロジのネットワーク構成が表示され、サーバー、プール、およびハードウェアおよびドメイン ネーム システム (DNS) ロード バランサーの IP アドレスと FQDN の編集可能なエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="6667f-113">エッジ管理レポート - エッジ管理レポートには、合計 4 つのレポートが含まれる。</span><span class="sxs-lookup"><span data-stu-id="6667f-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![[エッジ管理レポート] ページ](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="6667f-115">概要レポート - エッジ ネットワーク構成の設定の一般的なレポートです。</span><span class="sxs-lookup"><span data-stu-id="6667f-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="6667f-116">[エッジ ネットワーク ダイアグラム]ページの値を、実際の展開で使用されるトポロジ TCP/IP および FQDN 値に編集すると、これらのアドレスと名前がここで表されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="6667f-117">それ以外の場合は、既定のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="6667f-118">証明書レポート - 証明書レポートには、トポロジに必要な証明書のサブジェクト名とサブジェクトの代替名が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="6667f-119">ファイアウォール レポート - ファイアウォール レポートには、インフラストラクチャで境界ファイアウォールを構成するために必要な情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="6667f-120">これには、IP アドレス (既定または編集された値)、サーバーの役割、送信元 IP とポート、宛先 IP とポート、トランスポート プロトコル、アプリケーション プロトコル、および関連するメモが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6667f-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="6667f-121">DNS レポート - DNS レポートには、作成する必要がある DNS エントリに関連する情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="6667f-122">正しい動作に必要なレコードの種類、FQDN、IP アドレス、およびコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6667f-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="6667f-123">サイトの概要 - サイトの概要は、最初のインタビューの質問に回答するか、デザイン サイトの値を入力して行った選択の概要 **を示します**。</span><span class="sxs-lookup"><span data-stu-id="6667f-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="6667f-124">容量情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6667f-125">サイトの概要ページの情報は、設計ごとにカスタマイズされるため、ここで説明しているすべてのセクションや情報が含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6667f-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="6667f-126">ネットワーク構成図の編集</span><span class="sxs-lookup"><span data-stu-id="6667f-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="6667f-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="6667f-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="6667f-128">Skype for Business Server 2015 計画ツールでデザイナーが行う作業の大部分は、ネットワークダイアグラム上のエントリの IP アドレスと完全修飾ドメイン名 (FQDN) のエントリを定義する作業で構成されます。</span><span class="sxs-lookup"><span data-stu-id="6667f-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="6667f-129">このページに入力された情報は、計画ツールに含まれるレポートおよび他の情報に引き継がれします。</span><span class="sxs-lookup"><span data-stu-id="6667f-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![計画ツールネットワーク図](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="6667f-131">計画ツールは、IP アドレスと FQDN の既定のテキストを含むネットワーク ダイアグラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="6667f-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="6667f-132">ネットワーク ダイアグラムを編集して値を入力するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6667f-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="6667f-133">作業を開始するネットワークの部分を選択します。</span><span class="sxs-lookup"><span data-stu-id="6667f-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="6667f-134">たとえば、テキストをダブルクリックし、[access1.contoso.com] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6667f-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="6667f-135">開くダイアログ ボックスに、サーバー access1.contoso.com の実際の FQDN と実際の IP アドレスを入力し、131.107.155.3 に置き換わります。</span><span class="sxs-lookup"><span data-stu-id="6667f-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="6667f-136">**[OK]** をクリックしてエントリを保存します。</span><span class="sxs-lookup"><span data-stu-id="6667f-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="6667f-137">IP アドレスと FQDN の編集を続行し、プール内のサーバーのドメイン ネーム システム (DNS) 負荷分散に使用するハードウェア ロード バランサーまたはサーバーのエントリの仮想 IP アドレスを入力していきます。</span><span class="sxs-lookup"><span data-stu-id="6667f-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="6667f-p111">計画ツールには便利な機能があり、設計者がプール内の各サーバーを個別に編集する代わりに IP アドレス範囲およびサーバー ホスト名を増分して割り当てることができます。次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="6667f-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="6667f-140">プールされたフロントエンド サーバーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6667f-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="6667f-141">ダイアログ ボックスが開いたら、[このクラスター内のすべての同等のサーバーの開始点として **、IPs** と FQDN を使用しますか?</span><span class="sxs-lookup"><span data-stu-id="6667f-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="6667f-142">たとえば、最初のサーバーの開始値は fe0101.contoso.com、IP アドレスは 192.168.21.122 です。</span><span class="sxs-lookup"><span data-stu-id="6667f-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="6667f-143">フロントエンド fe0.contoso.com **FQDN に「fe0.contoso.com」** と入力し、フロント エンド サーバー **の IP** アドレスに「192.168.21.131」と入力し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6667f-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="6667f-144">自動インクリメント機能は、プール内のすべてのサーバーを fe01 ~ fe06 に更新し、すべての IP アドレスを 192.168.21.131 から 136 に更新します。</span><span class="sxs-lookup"><span data-stu-id="6667f-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="6667f-145">すべての編集が完了したら、次の手順を実行してトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="6667f-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="6667f-146">計画ツールのデザインを保存するには、[**ファイル**] をクリックし、[トポロジの保存] または [トポロジに名前を付けて保存]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6667f-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="6667f-147">**[名前を付けて計画ツールを保存]** ダイアログ ボックスが表示された場合、**[ファイル名]** にファイル名を入力して **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6667f-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6667f-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="6667f-148">See also</span></span>
<span data-ttu-id="6667f-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="6667f-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="6667f-150">設計の編集</span><span class="sxs-lookup"><span data-stu-id="6667f-150">Editing the Design</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)