---
title: 'Lync Server 2013: トポロジにオプションのディレクター トポロジを定義する'
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
ms.openlocfilehash: 86f3c78730e8c866e3838f22a1267a57bb3d237b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="d6f01-102">Lync Server 2013 のトポロジにオプションのディレクター トポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="d6f01-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6f01-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d6f01-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d6f01-104">Lync Server 2013 ディレクターは、単一インスタンスのサーバーにすることも、複数のディレクターの負荷分散プールとしてインストールして可用性と容量を高めることもできます。</span><span class="sxs-lookup"><span data-stu-id="d6f01-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="d6f01-105">ハードウェア負荷分散とドメインネームシステム (DNS) の負荷分散は両方ともサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d6f01-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="d6f01-106">このトピックでは、ディレクタープールの DNS 負荷分散を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6f01-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="d6f01-107">トポロジを正常に発行、有効化、または無効にするには、サーバーの役割を追加または削除するときに、 **RTCUniversalServerAdmins**と**domain Admins**グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="d6f01-108">また、サーバーの役割を追加するための適切な管理者権限と権限を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6f01-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="d6f01-109">詳細については、Standard Edition server または Enterprise Edition server 展開ドキュメントの「 [Lync server 2013 でのセットアップ権限の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6f01-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="d6f01-110">その他の構成変更については、 **RTCUniversalServerAdmins**グループのメンバーシップのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="d6f01-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="d6f01-111">このトピックでは、2つのディレクタートポロジのトポロジを定義して公開するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6f01-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="d6f01-112">ディレクターを定義するには (単一インスタンス)</span><span class="sxs-lookup"><span data-stu-id="d6f01-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="d6f01-113">ディレクター (複数のディレクタープール) を定義するには</span><span class="sxs-lookup"><span data-stu-id="d6f01-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="d6f01-114">ディレクターを定義するには (単一インスタンス)</span><span class="sxs-lookup"><span data-stu-id="d6f01-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="d6f01-115">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d6f01-116">[ようこそ] ページで、[**既存の展開からトポロジをダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="d6f01-117">[名前を付け**てトポロジを保存**] ダイアログボックスで、既存のトポロジのローカルコピーの名前と場所を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="d6f01-118">ディレクターを追加する予定のサイトを展開し、[**ディレクタープール**] を右クリックして、[**新しいディレクタープール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="d6f01-119">[**ディレクタープールの FQDN の定義**] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d6f01-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="d6f01-120">[**プールの fqdn**] に、ディレクタープールの fqdn を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6f01-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="d6f01-121">[**単一コンピュータープール**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="d6f01-122">[**ファイル共有の定義**] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d6f01-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="d6f01-123">既存のファイル共有を使用するには、[**以前定義したファイル共有を使用**する] をクリックし、一覧からファイル共有を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="d6f01-124">新しいファイル共有を作成するには、[**新しいファイル共有の定義**] をクリックし、[**ファイルサーバー fqdn**] でファイル共有の場所の FQDN を入力して、[**ファイル共有**] に共有の名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d6f01-125">この手順で指定または作成したファイル共有は、トポロジを公開する前に存在しているか、作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="d6f01-126">ディレクターに割り当てられているファイル共有は、実際には使用されていないため、組織内の任意のプールのファイル共有を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d6f01-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="d6f01-127">[ **Web サービスの URL の指定**] ダイアログボックスの [**外部ベース URL**] で、ディレクターの FQDN を指定し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d6f01-128">この名前は、インターネット DNS サーバーから解決できる必要があります。また、その URL への HTTP/HTTPS 要求をリッスンし、そのユーザーをそのディレクターの外部 Web サービスの仮想ディレクトリにプロキシする、リバースプロキシのパブリック IP アドレスをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d6f01-129">複数のフロントエンドプールまたはフロントエンドサーバーがある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="d6f01-130">たとえば、フロントエンドサーバーの外部 Web サービス FQDN を<STRONG>pool01.contoso.com</STRONG>として定義する場合、別のフロントエンドプールまたはフロントエンドサーバーに対して<STRONG>pool01.contoso.com</STRONG>を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d6f01-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="d6f01-131">ディレクターも展開する場合、任意のディレクターまたはディレクタープール用に定義された外部 Web サービスの FQDN は、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="d6f01-132">自己定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="d6f01-133">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="d6f01-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="d6f01-134">ディレクター (複数のディレクタープール) を定義するには</span><span class="sxs-lookup"><span data-stu-id="d6f01-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="d6f01-135">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d6f01-136">[ようこそ] ページで、[**既存の展開からトポロジをダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="d6f01-137">[名前を付け**てトポロジを保存**] ダイアログボックスで、既存のトポロジのローカルコピーの名前と場所を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="d6f01-138">ディレクターを追加する予定のサイトを展開し、[**ディレクタープール**] を右クリックして、[**新しいディレクタープール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="d6f01-139">[**ディレクタープールの FQDN の定義**] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d6f01-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="d6f01-140">[**プールの fqdn**] に、ディレクタープールの fqdn を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6f01-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="d6f01-141">[**複数のコンピュータープール**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="d6f01-142">[**このプールのコンピューターの定義**] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d6f01-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="d6f01-143">最初のプールメンバーのコンピューターの FQDN を指定し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="d6f01-144">追加するコンピューターごとに、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d6f01-144">Repeat the previous step for each computer that you want to add.</span></span> <span data-ttu-id="d6f01-145">完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-145">When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="d6f01-146">[**ファイル共有の定義**] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d6f01-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="d6f01-147">既存のファイル共有を使用するには、[**以前定義したファイル共有を使用**する] をクリックし、一覧からファイル共有を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="d6f01-148">新しいファイル共有を作成するには、[**新しいファイル共有の定義**] をクリックし、[**ファイルサーバー fqdn**] でファイル共有の場所の FQDN を入力して、[**ファイル共有**] に共有の名前を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d6f01-149">この手順で指定または作成したファイル共有は、トポロジを公開する前に存在しているか、作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="d6f01-150">ディレクターに割り当てられているファイル共有は、実際には使用されていないため、組織内の任意のプールのファイル共有を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d6f01-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="d6f01-151">[ **Web サービスの URL の指定**] ダイアログボックスの [**外部ベース URL**] で、ディレクターの FQDN を指定し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6f01-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d6f01-152">この名前は、インターネット DNS サーバーから解決できる必要があります。また、その URL に送信された HTTP/HTTPS 要求をリッスンし、それらをそのディレクタープールの外部 Web サービスの仮想ディレクトリにプロキシする、リバースプロキシのパブリック IP アドレスをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d6f01-153">複数のフロントエンドプールまたはフロントエンドサーバーがある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="d6f01-154">たとえば、フロントエンドサーバーの外部 Web サービス FQDN を<STRONG>pool01.contoso.com</STRONG>として定義する場合、別のフロントエンドプールまたはフロントエンドサーバーに対して<STRONG>pool01.contoso.com</STRONG>を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d6f01-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="d6f01-155">ディレクターも展開する場合、任意のディレクターまたはディレクタープール用に定義された外部 Web サービスの FQDN は、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="d6f01-156">自己定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f01-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="d6f01-157">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="d6f01-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

