---
title: Skype for Business Server 2015 でのトポロジの編集
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: 最初のインタビューによる質問を完了すると、サイトの完全修飾ドメイン名 (FQDN) と IP アドレスを編集できます。 これを行うには、[グローバル トポロジ] ページで、編集するサイトをダブルクリックします。
ms.openlocfilehash: 75f2bd04f09b6638071faff1aa70dc8870d11fea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895147"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="0060d-104">Edit the topology in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0060d-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="0060d-p102">最初のインタビューによる質問を完了すると、サイトの完全修飾ドメイン名 (FQDN) と IP アドレスを編集できます。これを行うには、[**グローバル トポロジ**] ページで、編集するサイトをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0060d-p102">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="0060d-107">計画ツールは、選択したサイトのサイトのトポロジを表示します。</span><span class="sxs-lookup"><span data-stu-id="0060d-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="0060d-108">サイト ページの下部には、次の 4 つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="0060d-108">At the bottom of the site page are four tabs:</span></span>

![計画ツール、サイト トポロジ](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="0060d-110">サイト トポロジが推奨されているトポロジの概要を視覚的に表示されているページです。</span><span class="sxs-lookup"><span data-stu-id="0060d-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="0060d-111">エッジ ネットワーク ダイアグラム] ビューのエッジ ネットワーク ダイアグラムのページでは、デザイナーが計画ツールでの作業のほとんどが。</span><span class="sxs-lookup"><span data-stu-id="0060d-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="0060d-112">IP の編集可能なエントリのアドレスと Fqdn サーバー、プール、および両方のハードウェアとドメイン ネーム システム (DNS) の負荷分散装置、図は、ビジネス サーバー 2015 トポロジの推奨される Skype のネットワーク構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="0060d-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="0060d-113">エッジ管理レポート - エッジ管理レポートには、合計で 4 つのレポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0060d-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![[エッジ管理レポート] ページ](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="0060d-115">サマリー レポート - エッジ ネットワーク構成の設定の全般的なレポートです。</span><span class="sxs-lookup"><span data-stu-id="0060d-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="0060d-116">[  \*\*エッジ ネットワーク図  \*\*] ページの値を、実際の展開で使用する、トポロジの TCP/IP および FQDN の値に編集する場合、それらのアドレスと名前がここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0060d-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="0060d-117">それ以外の場合、既定のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0060d-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="0060d-118">証明書を報告する-証明書のレポートは、サブジェクト名とトポロジに必要な証明書のサブジェクトの別名に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0060d-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="0060d-119">ファイアウォール レポートに、ファイアウォールには、インフラストラクチャで周辺ファイアウォールを構成するのには必要な情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0060d-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="0060d-120">IP アドレス (既定値または編集された値)、サーバーの役割、送信元 IP と送信元ポート、宛先 IP と宛先ポート、トランスポート プロトコル、アプリケーション プロトコル、および関連する注記が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0060d-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="0060d-121">DNS レポート - DNS レポートには、作成する必要がある DNS エントリの関連情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0060d-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="0060d-122">正しい動作に必要なレコードの種類、FQDN、IP アドレス、およびコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0060d-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="0060d-123">サイト概要 - サイトの概要は、最初の面接の質問に答えてか、**デザイン サイト**内の値に値を入力して選択内容の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="0060d-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="0060d-124">処理能力に関する情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="0060d-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0060d-125">サイトの概要ページの情報は、設計ごとにカスタマイズされるため、ここで説明しているすべてのセクションや情報が含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0060d-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="0060d-126">ネットワーク構成ダイアグラムの編集</span><span class="sxs-lookup"><span data-stu-id="0060d-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="0060d-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="0060d-127"></span></span>

<span data-ttu-id="0060d-128">ビジネス サーバー 2015 計画ツールのデザイナーが、Skype では、作業のほとんどは、ネットワーク ダイアグラム] ビューでエントリの完全修飾ドメイン名 (Fqdn) と IP アドレスのエントリを定義するので構成されます。</span><span class="sxs-lookup"><span data-stu-id="0060d-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="0060d-129">レポートおよび計画ツールに含まれるその他の情報にもこのページで入力した情報が引き継がれます。</span><span class="sxs-lookup"><span data-stu-id="0060d-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![計画ツール、ネットワーク図](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="0060d-131">計画ツールでは、IP アドレスと Fqdn の既定のテキストでネットワーク図を作成します。</span><span class="sxs-lookup"><span data-stu-id="0060d-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="0060d-132">ネットワーク ダイアグラムを編集して値を入力するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0060d-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="0060d-p110">ネットワークのセクションを選択して作業を開始します。たとえば、**access1.contoso.com** というテキストをダブルクリックします。表示されるダイアログ ボックスで、サーバー access1.contoso.com の実際の FQDN と実際の IP アドレスを入力します (131.107.155.3 を置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="0060d-p110">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="0060d-136">[**OK**] をクリックしてエントリを保存します。</span><span class="sxs-lookup"><span data-stu-id="0060d-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="0060d-137">IP アドレスと FQDN の編集を続行し、プール内のサーバーのドメイン ネーム システム (DNS) 負荷分散に使用するハードウェア ロード バランサーまたはサーバーのエントリの仮想 IP アドレスを入力していきます。</span><span class="sxs-lookup"><span data-stu-id="0060d-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="0060d-p111">計画ツールには便利な機能があり、設計者がプール内の各サーバーを個別に編集する代わりに IP アドレス範囲およびサーバー ホスト名を増分して割り当てることができます。次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="0060d-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="0060d-p112">プールされているフロント エンド サーバーをダブルクリックします。ダイアログ ボックスが表示されたら、[**このクラスター内の対応するすべてのサーバーの開始点としてこの IP と FQDN を使用しますか?**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0060d-p112">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="0060d-142">たとえば、最初のサーバーの開始値は fe0101.contoso.com で、IP アドレスは 192.168.21.122 です。</span><span class="sxs-lookup"><span data-stu-id="0060d-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="0060d-143">[フロント エンド サーバーの FQDN] に「**fe0.contoso.com**」、[**フロント エンド サーバーの IP アドレス**] に「192.168.21.131」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0060d-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="0060d-144">自動増分機能により、プール内のすべてのサーバーが fe01 ～ fe06 に更新され、すべての IP アドレスが 192.168.21.131 ～ 136 に更新されます。</span><span class="sxs-lookup"><span data-stu-id="0060d-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="0060d-145">すべての編集が完了したら、次の手順を実行してトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="0060d-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="0060d-146">計画ツールのデザインを保存するには、[**ファイル**] メニューし、[**トポロジの保存**] または [**名前を付けてトポロジを保存**します。</span><span class="sxs-lookup"><span data-stu-id="0060d-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="0060d-147">[**名前を付けて計画ツールを保存**] ダイアログ ボックスが表示された場合、[**ファイル名**] にファイル名を入力して [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0060d-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0060d-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="0060d-148">See also</span></span>
<span data-ttu-id="0060d-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="0060d-149"></span></span>

[<span data-ttu-id="0060d-150">Editing the Design</span><span class="sxs-lookup"><span data-stu-id="0060d-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
