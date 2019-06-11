---
title: 'Lync Server 2013: アーカイブデータベースのオプションを変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a98c2efc0dc956a6b8c33f2fcf065f629e5e57d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="f26ba-102">Lync Server 2013 でアーカイブデータベースのオプションを変更する</span><span class="sxs-lookup"><span data-stu-id="f26ba-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f26ba-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f26ba-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f26ba-104">いずれかのユーザーのために SQL Server ストレージを使用してアーカイブを展開している場合は、次のデータベース記憶域を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f26ba-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="f26ba-105">アーカイブストレージとして別の SQL Server データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="f26ba-106">これには、プライマリアーカイブデータベースと、SQL Server ミラーリングで使用するデータベースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f26ba-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="f26ba-107">Exchange 2013 サーバーにアーカイブデータとファイルを保存するには、Microsoft Exchange 統合に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f26ba-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="f26ba-108">すべてのユーザーが Exchange 2013 サーバーを使用していて、展開内のすべてのユーザーに対して Microsoft Exchange ストレージを使用する場合は、SQL Server ストアデータベースをトポロジから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f26ba-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="f26ba-109">これらの変更を行うには、トポロジビルダーを実行し、変更を行ってから、トポロジをもう一度公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f26ba-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="f26ba-110">トポロジービルダーを使用して、この操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f26ba-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="f26ba-111">Exchange 2013 サーバーを使っていない Lync ユーザーがいる場合を除き、**アーカイブ Sql server ストア**または**sql server ストアのミラーリング**情報を有効にしないようにします。</span><span class="sxs-lookup"><span data-stu-id="f26ba-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="f26ba-112">[アーカイブデータベース] オプションを変更するには</span><span class="sxs-lookup"><span data-stu-id="f26ba-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="f26ba-113">Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="f26ba-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f26ba-114">トポロジは、[ローカルユーザー] グループのメンバーであるアカウントを使用して定義できますが、トポロジを公開するためには、" <STRONG>Domain Admins</STRONG> " グループと "RTCUniversalSer" のメンバーであるアカウントを使用する必要があります。 <STRONG>verAdmins</STRONG>グループ、および Lync Server 2013 ファイルストアで使用しているファイル共有に対してフルコントロールのアクセス許可 (つまり読み取り、書き込み、変更) を持ちます (つまり、トポロジビルダーは必要な任意のアクセス制御リストを構成できます。Dacl)、または同等の権限を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="f26ba-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="f26ba-115">トポロジビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="f26ba-116">コンソール プールで、アーカイブを展開したフロントエンド プールに移動し、データベース オプションを変更するフロントエンド プールの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26ba-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="f26ba-117">[**アクション**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26ba-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="f26ba-118">[**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26ba-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="f26ba-119">[**アーカイブ**] まで下方向にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="f26ba-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="f26ba-120">[**アーカイブ**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="f26ba-121">別の既存の SQL Server ストアに変更するには、[**SQL Server ストアのアーカイブ**] ドロップダウン リスト ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="f26ba-122">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26ba-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="f26ba-123">新しい SQL Server ストアを定義するには、[**新規**] をクリックし、[**新しい SQL Server ストアの定義**] ダイアログ ボックスで次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="f26ba-124">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26ba-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="f26ba-125">新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f26ba-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="f26ba-126">[ **Sql SERVER fqdn**] で、新しい SQL Server ストアを作成するサーバーの fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="f26ba-127">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="f26ba-128">指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="f26ba-129">ミラーリング用に SQL Server ストアを追加するか、SQL Server ストア ミラーリングとして別の既存の SQL Server ストアに変更するには、[**SQL Server ストア ミラーリングの有効化**] を選択して、以下の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="f26ba-130">ミラーリング用の既存の SQL Server ストアを使用するには、[**アーカイブ SQL server ストアミラー** ] ドロップダウンリストボックスで、ミラーリングに使用する sql server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26ba-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="f26ba-131">ミラーリング用の新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f26ba-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="f26ba-132">[ **Sql SERVER fqdn**] で、新しい sql server ストアを作成する sql SERVER の fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="f26ba-133">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="f26ba-134">指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="f26ba-135">Sql Server のミラーリングを有効にしており、SQL Server ミラーリング監視 (プライマリ SQL Server サーバーの正常性を検出できる別の SQL Server インスタンス) を追加または変更する場合は、[ **Sql server ミラーリング監視を使用する] を選択します。[自動フェールオーバーを有効にする**] チェックボックスをオンにして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f26ba-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="f26ba-136">[ **Sql SERVER fqdn**] で、新しい SQL server ミラーリング監視を作成するサーバーの fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="f26ba-137">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="f26ba-138">指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="f26ba-139">Exchange 2013 サーバーにアーカイブデータとファイルを保存するために Microsoft Exchange の統合に切り替えるには (展開のすべてのユーザーが Exchange 2013 サーバーに所属している場合)、アーカイブデータベースのすべての情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="f26ba-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f26ba-140">Exchange 2013 サーバーを使っていない Lync ユーザーがいる場合は、SQL Server ストアの情報を削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="f26ba-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="f26ba-141">構成を保存するには、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26ba-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f26ba-142">トポロジビルダーで行った変更は、新しいトポロジを公開するまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="f26ba-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="f26ba-143">詳細については、「更新されたトポロジを公開して、展開ドキュメントの<A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Lync Server 2013 でアーカイブデータベースを追加する」を</A>参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26ba-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

