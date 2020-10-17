---
title: 'Lync Server 2013: 付録 B: 存続可能ブランチアプライアンスの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a766ae86d4c74d874f1db747c137f54cf568d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523224"
---
# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="1f3da-102">付録 B: Lync Server 2013 での存続可能ブランチアプライアンスの管理</span><span class="sxs-lookup"><span data-stu-id="1f3da-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f3da-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1f3da-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1f3da-104">このトピックでは、存続可能ブランチアプライアンスを管理する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="1f3da-105">具体的には、存続可能ブランチアプライアンスの置換と名前変更、および存続可能 Branch Appliance が関連付けられている Lync Server 2013 フロントエンドプールの変更方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="1f3da-106">存続可能ブランチ アプライアンスを置き換えるには</span><span class="sxs-lookup"><span data-stu-id="1f3da-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="1f3da-107">存続可能ブランチアプライアンス上のすべての Lync Server 2013 サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="1f3da-108">(存続可能 Branch Appliance ベンダーのドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1f3da-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="1f3da-109">勧めドメインから存続可能 Branch アプライアンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="1f3da-110">Active Directory ドメインサービスの存続可能 Branch Appliance コンピューターオブジェクトを削除します。そのためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="1f3da-111">Enterprise Admins グループのメンバーとしてメンバー サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="1f3da-112">[**スタート**]、[**管理ツール**]、[**Active Directory ユーザーとコンピューター**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="1f3da-113">存続可能 Branch Appliance オブジェクトを右クリックし、[ **削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="1f3da-114">存続可能 Branch Appliance コンピューターオブジェクトをもう一度追加します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="1f3da-115">(「 [Lync Server 2013 で存続可能 Branch Appliance を Active Directory に追加する」を](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1f3da-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="1f3da-116">Active Directory のレプリケーションが行われるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="1f3da-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="1f3da-117">[Lync Server 管理シェル] を開き、「 **Enable-CSTopology**方法」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="1f3da-118">新しい存続可能 Branch Appliance をネットワークに接続し、「 [存続可能 Branch appliance Or server With Lync server 2013-central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 」および「 [Deploy The 存続可能 Branch appliance Or Server with lync server 2013-Branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="1f3da-119">存続可能ブランチ アプライアンスの名前を変更するには</span><span class="sxs-lookup"><span data-stu-id="1f3da-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="1f3da-120">ユーザーをセントラル サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-120">Move users to the central site.</span></span> <span data-ttu-id="1f3da-121">詳細については、「 [Move users to a Lync Server 2013」](lync-server-2013-move-users-to-another-pool.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f3da-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="1f3da-122">存続可能ブランチアプライアンス上のすべての Lync Server 2013 サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="1f3da-123">(存続可能 Branch Appliance ベンダーのドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1f3da-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="1f3da-124">トポロジから存続可能 Branch アプライアンスを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="1f3da-125">[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="1f3da-126">コンソールツリーで、[ **ブランチサイト**] を展開し、存続可能ブランチアプライアンスをクリックして、操作ウィンドウで [ **削除** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="1f3da-127">ドメインから存続可能 Branch アプライアンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="1f3da-128">Active Directory 内の存続可能 Branch Appliance コンピューターオブジェクトを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="1f3da-129">Enterprise Admins グループのメンバーとしてドメイン コントローラーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="1f3da-130">[**スタート**]、[**管理ツール**]、[**Active Directory ユーザーとコンピューター**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="1f3da-131">存続可能 Branch Appliance オブジェクトを右クリックし、[ **削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="1f3da-132">存続可能ブランチアプライアンスを出荷時の既定値に復元します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="1f3da-133">(存続可能 Branch Appliance ベンダーのドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1f3da-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="1f3da-134">「 [Lync server 2013-中央サイトタスクを使用した存続可能ブランチアプライアンスまたはサーバーの展開](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 」の手順に従って、「 [lync server 2013-branch site task」を使用して存続可能 branch Appliance または server を展開](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="1f3da-135">名前を変更した存続可能 Branch Appliance にユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="1f3da-136">詳細については、「 [Move users to a Lync Server 2013」](lync-server-2013-move-users-to-another-pool.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f3da-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="1f3da-137">存続可能ブランチ アプライアンスが関連付けられている Lync Server のフロントエンド プールを変更するには</span><span class="sxs-lookup"><span data-stu-id="1f3da-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="1f3da-138">存続可能ブランチアプライアンスから中央サイトの Lync Server フロントエンドプールにユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="1f3da-139">詳細については、「 [Move users to a Lync Server 2013」](lync-server-2013-move-users-to-another-pool.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f3da-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="1f3da-140">存続可能ブランチアプライアンス上のすべての Lync Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="1f3da-141">(存続可能 Branch Appliance ベンダーのドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1f3da-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="1f3da-142">存続可能 Branch Appliance が関連付けられている Lync Server フロントエンドプールを更新するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="1f3da-143">[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="1f3da-144">[**ブランチ サイト**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="1f3da-145">変更する存続可能 Branch Appliance オブジェクトを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="1f3da-146">[復元] で、存続可能ブランチアプライアンスが関連付けられる新しいフロントエンドプールを選択し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="1f3da-147">コンソールツリーで、新しい存続可能ブランチアプライアンスを右クリックし、[ **トポロジ**] をクリックして、[ **公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="1f3da-148">存続可能ブランチアプライアンス上のすべての Lync Server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="1f3da-149">存続可能ブランチアプライアンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="1f3da-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="1f3da-150">詳細については、「 [存続可能ブランチアプライアンスまたはサーバー上の Lync server 2013 のホームユーザー](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f3da-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="1f3da-151">中央サイトの Lync Server フロントエンドプールから存続可能ブランチアプライアンスにユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="1f3da-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

