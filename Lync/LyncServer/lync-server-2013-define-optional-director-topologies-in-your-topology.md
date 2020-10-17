---
title: 'Lync Server 2013: トポロジにオプションのディレクタートポロジを定義する'
description: 'Lync Server 2013: トポロジにオプションのディレクタートポロジを定義します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bc82108d4277969489739fc81db07ec6f96bb96
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542654"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="b2f44-103">Lync Server 2013 のトポロジにオプションのディレクタートポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="b2f44-103">Define optional Director topologies in your topology for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2f44-104">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b2f44-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b2f44-105">Lync Server 2013 のディレクターは、単一インスタンスサーバーにすることも、高可用性と容量を実現するために複数のディレクターの負荷分散プールとしてインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b2f44-105">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="b2f44-106">ハードウェア負荷分散とドメインネームシステム (DNS) 負荷分散の両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b2f44-106">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="b2f44-107">このトピックでは、ディレクタープールの DNS 負荷分散を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2f44-107">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="b2f44-108">サーバーの役割を追加または削除するときに、トポロジを適切に公開、有効化、または無効化するには、[**RTCUniversalServerAdmins**] グループと [**Domain Admins**] グループのメンバーであるユーザーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-108">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="b2f44-109">サーバーの役割を追加するための適切な管理者権限とアクセス許可を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="b2f44-109">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="b2f44-110">詳細については、「Standard Edition サーバーまたは Enterprise Edition server 展開ドキュメント」の「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2f44-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="b2f44-111">その他の構成変更の場合は、**RTCUniversalServerAdmins** グループのメンバーシップのみが必要となります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-111">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="b2f44-112">このトピックでは、2つのディレクタートポロジのトポロジを定義および公開する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2f44-112">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="b2f44-113">ディレクターを定義するには (単一インスタンス)</span><span class="sxs-lookup"><span data-stu-id="b2f44-113">To define the Director (single instance)</span></span>

  - <span data-ttu-id="b2f44-114">ディレクターを定義するには (複数のディレクター プール)</span><span class="sxs-lookup"><span data-stu-id="b2f44-114">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="b2f44-115">ディレクターを定義するには (単一インスタンス)</span><span class="sxs-lookup"><span data-stu-id="b2f44-115">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="b2f44-116">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b2f44-117">[ようこそ] ページで、**[既存の展開からのトポロジのダウンロード]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-117">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="b2f44-118">[**トポロジを名前を付けて保存**] ダイアログ ボックスに、既存のトポロジのローカル コピーの名前と場所を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-118">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="b2f44-119">ディレクターを追加するサイトを展開し、**[ディレクター プール]** を右クリックし、**[新しいディレクター プール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-119">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="b2f44-120">[**ディレクター プールの FQDN を定義する**] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2f44-120">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="b2f44-121">[**プールの FQDN**] に、ディレクター プールの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="b2f44-121">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="b2f44-122">[**単一コンピューターのプール**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-122">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="b2f44-123">[**ファイル共有の定義**] ダイアログ ボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2f44-123">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="b2f44-124">既存のファイル共有を使用するには、**[以前に定義したファイル共有を使用する]** をクリックし、一覧からファイル共有を選択して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-124">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="b2f44-125">新しいファイル共有を作成するには、**[新しいファイル共有の定義]** をクリックし、**[ファイル サーバーの FQDN]** にファイル共有の場所の FQDN を入力し、**[ファイル共有]** に共有の名前を入力します。**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-125">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b2f44-126">この手順で指定するファイル共有は、トポロジを公開する前に存在している必要があります。また、この手順で作成するファイル共有は、トポロジを公開する前に作成している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-126">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="b2f44-127">ディレクターに割り当てられるファイル共有は実際には使用されないため、組織内で任意のプールのファイル共有を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b2f44-127">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="b2f44-128">[**Web サービス URL を指定する**] ダイアログ ボックスの [**外部ベース URL**] で、ディレクターの FQDN を指定し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-128">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b2f44-129">この名前は、インターネット DNS サーバーから解決できる必要があります。また、その URL への HTTP/HTTPS 要求をリッスンし、そのディレクターの外部 Web サービス仮想ディレクトリに要求をプロキシ処理する、リバース プロキシのパブリック IP アドレスを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-129">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b2f44-130">フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-130">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="b2f44-131">たとえば、フロントエンドサーバーの外部 Web サービスの FQDN を <STRONG>pool01.contoso.com</STRONG>として定義した場合、別のフロントエンドプールまたはフロントエンドサーバーに <STRONG>pool01.contoso.com</STRONG> を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2f44-131">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="b2f44-132">ディレクターを展開している場合は、ディレクターまたはディレクタープールに対して定義されている外部 Web サービスの FQDN が、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーとも一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-132">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="b2f44-133">内部 web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンドプール、ディレクター、またはディレクタープールとは一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-133">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="b2f44-134">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="b2f44-134">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="b2f44-135">ディレクターを定義するには (複数のディレクター プール)</span><span class="sxs-lookup"><span data-stu-id="b2f44-135">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="b2f44-136">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-136">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b2f44-137">[ようこそ] ページで、**[既存の展開からのトポロジのダウンロード]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-137">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="b2f44-138">[**トポロジを名前を付けて保存**] ダイアログ ボックスに、既存のトポロジのローカル コピーの名前と場所を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-138">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="b2f44-139">ディレクターを追加するサイトを展開し、**[ディレクター プール]** を右クリックし、**[新しいディレクター プール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-139">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="b2f44-140">[**ディレクター プールの FQDN を定義する**] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2f44-140">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="b2f44-141">**[プールの FQDN]** に、ディレクター プールの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="b2f44-141">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="b2f44-142">**[複数コンピューターのプール]** をクリックし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-142">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="b2f44-143">[**このプール内のコンピューターの定義**] ダイアログ ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2f44-143">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="b2f44-144">最初のプール メンバーのコンピューター FQDN を指定して、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-144">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="b2f44-p104">追加するコンピューターごとに前のステップを繰り返します。終了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-p104">Repeat the previous step for each computer that you want to add. When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="b2f44-147">[**ファイル共有の定義**] ダイアログ ボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2f44-147">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="b2f44-148">既存のファイル共有を使用するには、**[以前に定義したファイル共有を使用する]** をクリックし、一覧からファイル共有を選択して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-148">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="b2f44-149">新しいファイル共有を作成するには、**[新しいファイル共有の定義]** をクリックし、**[ファイル サーバーの FQDN]** にファイル共有の場所の FQDN を入力し、**[ファイル共有]** に共有の名前を入力します。**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-149">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b2f44-150">この手順で指定するファイル共有は、トポロジを公開する前に存在している必要があります。また、この手順で作成するファイル共有は、トポロジを公開する前に作成している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-150">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="b2f44-151">ディレクターに割り当てられるファイル共有は実際には使用されないため、組織内で任意のプールのファイル共有を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b2f44-151">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="b2f44-152">[**Web サービス URL を指定する**] ダイアログ ボックスの [**外部ベース URL**] で、ディレクターの FQDN を指定し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-152">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b2f44-153">名前は、インターネット DNS サーバーから解決可能で、リバース プロキシのパブリック IP アドレスを指す必要があります。リバース プロキシは、その URL に送信された HTTP/HTTPS 要求をリッスンし、ディレクター プールの外部 Web サービス仮想ディレクトリにプロキシします。</span><span class="sxs-lookup"><span data-stu-id="b2f44-153">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b2f44-154">フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-154">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="b2f44-155">たとえば、フロントエンドサーバーの外部 Web サービスの FQDN を <STRONG>pool01.contoso.com</STRONG>として定義した場合、別のフロントエンドプールまたはフロントエンドサーバーに <STRONG>pool01.contoso.com</STRONG> を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2f44-155">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="b2f44-156">ディレクターを展開している場合は、ディレクターまたはディレクタープールに対して定義されている外部 Web サービスの FQDN が、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーとも一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-156">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="b2f44-157">内部 web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンドプール、ディレクター、またはディレクタープールとは一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2f44-157">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="b2f44-158">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="b2f44-158">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

