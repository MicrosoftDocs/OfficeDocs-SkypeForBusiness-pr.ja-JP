---
title: 'Lync Server 2013: アーカイブデータベースオプションの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8961b33a7b576559115c3afaa36e07b795d69ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="21680-102">Lync Server 2013 でのアーカイブデータベースオプションの変更</span><span class="sxs-lookup"><span data-stu-id="21680-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21680-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="21680-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="21680-104">SQL Server ストレージを使用して、ユーザーのためにアーカイブストレージ用にアーカイブを展開する場合は、次のデータベース記憶域の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="21680-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="21680-105">別の SQL Server データベースをアーカイブストレージとして使用します。</span><span class="sxs-lookup"><span data-stu-id="21680-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="21680-106">これには、プライマリアーカイブデータベースと、SQL Server ミラーリングに使用する任意のデータベースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="21680-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="21680-107">Exchange 2013 サーバーにアーカイブデータおよびファイルを保存するには、Microsoft Exchange 統合に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="21680-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="21680-108">すべてのユーザーが Exchange 2013 サーバーに所属しており、展開内のすべてのユーザーに対して Microsoft Exchange ストレージを使用する場合は、SQL Server ストアデータベースをトポロジから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21680-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="21680-109">これらの変更を行うには、トポロジビルダーを実行し、変更を行ってからトポロジを再度公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21680-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="21680-110">これを行うには、トポロジビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="21680-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="21680-111">Exchange 2013 サーバーに所属していない Lync ユーザーがいない場合は、[ **Sql server ストアのアーカイブ**] または [ **sql server ストアミラーリングの有効化**] の情報を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="21680-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="21680-112">アーカイブ データベース オプションを変更するには</span><span class="sxs-lookup"><span data-stu-id="21680-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="21680-113">Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="21680-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21680-114">トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用しますが、トポロジにコンポーネントを追加するために必要なトポロジを公開するには、 <STRONG>Domain Admins</STRONG>グループおよび<STRONG>RTCUniversalServerAdmins</STRONG>グループのメンバーであり、かつ、Lync Server 2013 ファイルストアに使用しているファイル共有のフルコントロールのアクセス許可 (つまり、読み取り、書き込み、および変更) を持つアカウントを使用する必要があります (つまり、トポロジビルダーが必要な随意アクセス制御リストを構成できるようにします。Dacl)、またはそれと同等の権限を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="21680-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="21680-115">トポロジ ビルダーを開始します。</span><span class="sxs-lookup"><span data-stu-id="21680-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="21680-116">コンソール プールで、アーカイブを展開したフロントエンド プールに移動し、データベース オプションを変更するフロントエンド プールの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21680-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="21680-117">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21680-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="21680-118">[**プロパティの編集 **] ダイアログ ボックスで、[**全般**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21680-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="21680-119">[**アーカイブ**] まで下方向にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="21680-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="21680-120">[**アーカイブ**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="21680-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="21680-121">別の既存の SQL Server ストアに変更するには、[**アーカイブ SQL Server ストア**] ドロップダウン リスト ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="21680-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="21680-122">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21680-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="21680-123">新しい SQL Server ストアを定義するには、[**新規作成**] をクリックし、[**新しい SQL Server ストアの定義**] ダイアログ ボックスで次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="21680-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="21680-124">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21680-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="21680-125">新しい SQL Server ストアを指定するには、[**新規**] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="21680-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="21680-126">[ **Sql server の fqdn**] で、新しい SQL server ストアを作成するサーバーの fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="21680-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="21680-127">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="21680-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="21680-128">指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスはミラーリングの関係に**ある] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="21680-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="21680-129">ミラーリング用に SQL Server ストアを追加するか、SQL Server ストア ミラーリングとして別の既存の SQL Server ストアに変更するには、[**SQL Server ストア ミラーリングを有効にする**] を選択して、以下の作業をします。</span><span class="sxs-lookup"><span data-stu-id="21680-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="21680-130">既存の SQL Server ストアをミラーリングに使用するには、[**アーカイブ SQL server ストアミラー** ] ドロップダウンリストボックスで、ミラーリングに使用する sql server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21680-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="21680-131">ミラーリング用の新しい SQL Server ストアを指定するには、[**新規**] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="21680-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="21680-132">[ **Sql server の fqdn**] で、新しい sql server ストアを作成する対象の sql SERVER の fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="21680-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="21680-133">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="21680-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="21680-134">指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスはミラーリングの関係に**ある] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="21680-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="21680-135">Sql Server ミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリの SQL Server サーバーとミラーインスタンスの正常性を検出できる別の SQL Server インスタンス) を追加または変更する場合は、[ **sql server ミラーリング監視を使用して自動フェールオーバーを有効**にする] チェックボックスをオンにして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="21680-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="21680-136">[ **Sql server の fqdn**] で、新しい SQL server ミラーリング監視を作成するサーバーの fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="21680-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="21680-137">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="21680-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="21680-138">指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスはミラーリングの関係に**ある] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="21680-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="21680-139">Exchange 2013 サーバーにアーカイブデータおよびファイルを格納するために Microsoft Exchange 統合に切り替えるには (展開内のすべてのユーザーが Exchange 2013 サーバーに所属している場合)、アーカイブデータベースに関するすべての情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="21680-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="21680-140">Exchange 2013 サーバーに所属していない Lync ユーザーがいる場合は、SQL Server ストアの情報を削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="21680-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="21680-141">構成を保存するには、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21680-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="21680-142">トポロジビルダーで行った変更は、新しいトポロジを公開するまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="21680-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="21680-143">詳細については、「展開」のドキュメントの「<A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">更新されたトポロジを公開して Lync Server 2013 にアーカイブデータベースを追加する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21680-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

