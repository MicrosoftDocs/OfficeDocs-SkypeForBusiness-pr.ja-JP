---
title: 'Lync Server 2013: Lync Server 2013 トポロジへのアーカイブデータベースの追加'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebc2f06e6e3fa2646989e4697354c71f7f0249da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521394"
---
# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="9a295-102">Lync Server 2013 トポロジへのアーカイブデータベースの追加</span><span class="sxs-lookup"><span data-stu-id="9a295-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a295-103">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="9a295-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="9a295-104">アーカイブをサポートするために展開を構成する前に、トポロジにアーカイブを組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a295-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="9a295-105">このトピックの情報では、トポロジビルダーを使用して既存のトポロジにアーカイブを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a295-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a295-106">Microsoft Exchange 統合を使用して、展開内のすべてのユーザーの Exchange 2013 サーバーにアーカイブデータとファイルを保存する場合は、 <STRONG>アーカイブ Sql server ストア</STRONG> を指定しないか、 <STRONG>sql server ストアミラーリング</STRONG> 情報を使用してください。</span><span class="sxs-lookup"><span data-stu-id="9a295-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="9a295-107">トポロジにアーカイブデータベースのサポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="9a295-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="9a295-108">Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="9a295-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a295-109">トポロジを定義するには、ローカルの Users グループのメンバーであるアカウントを使用しますが、トポロジを公開するには、 <STRONG>ドメイン管理者</STRONG> グループと <STRONG>RTCUniversalServerAdmins</STRONG> グループのメンバーであるアカウントを使用する必要があります (このトポロジを使用する必要があります)。これには、Lync server 2013 ファイルストアに使用しているファイル共有に対するフルコントロールのアクセス許可 (つまり、読み取り、書き込み、および変更) があります (つまり、トポロジビルダーが必要な随意アクセス制御リスト (dacl) を構成したり、または同等の権限を持つアカウントを構成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9a295-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="9a295-110">トポロジ ビルダーを開始します。</span><span class="sxs-lookup"><span data-stu-id="9a295-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="9a295-111">コンソールツリーで、アーカイブを展開するフロントエンドプールに移動してから、アーカイブを展開するフロントエンドプールの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a295-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="9a295-112">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a295-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="9a295-113">[**プロパティの編集 **] ダイアログ ボックスで、[**全般**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a295-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="9a295-114">[**アーカイブ**] まで下方向にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="9a295-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="9a295-115">[ **アーカイブ** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9a295-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="9a295-116">[ **アーカイブ SQL Server ストア** ] で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a295-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="9a295-117">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a295-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="9a295-118">すべてのユーザーが Microsoft Exchange Server 2013 以降に所属している場合は、Exchange のすべてのユーザーの Lync communications をアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="9a295-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="9a295-119">この場合、SQL Server アーカイブストアを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9a295-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="9a295-120">新しい SQL Server ストアを指定するには、[ **新規**] をクリックし、[ **新しい sql Server ストアの定義** ] ダイアログボックスで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9a295-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="9a295-121">[ **Sql server の fqdn**] で、新しい SQL server ストアを作成するサーバーの fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a295-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="9a295-122">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a295-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="9a295-123">指定した SQL Server インスタンスがミラーリング関係にある場合は、[ **この sql インスタンスはミラーリングの関係に** ある] チェックボックスをオンにし、[ **ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a295-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="9a295-124">SQL Server ストアミラーリングを使用する場合は、[ **Sql Server ストアミラーリングの有効化**] を選択し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9a295-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="9a295-125">既存の SQL Server ストアをミラーリングに使用するには、[ **アーカイブ SQL server ストアミラー** ] ドロップダウンリストボックスで、ミラーリングに使用する sql server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a295-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="9a295-126">ミラーリング用の新しい SQL Server ストアを指定するには、[ **新規**] をクリックし、[ **新しい sql Server ストアの定義** ] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9a295-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="9a295-127">[ **Sql server の fqdn**] で、新しい sql server ストアを作成する対象の sql SERVER の fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a295-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="9a295-128">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a295-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="9a295-129">指定した SQL Server インスタンスがミラーリング関係にある場合は、[ **この sql インスタンスはミラーリングの関係に** ある] チェックボックスをオンにし、[ **ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a295-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="9a295-130">Sql Server のミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリの SQL Server サーバーとミラーインスタンスの正常性を検出できる3つの独立した SQL Server インスタンス) を含める場合は、[ **Sql server ミラーリング監視を使用して自動フェールオーバーを有効** にする] チェックボックスをオンにして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9a295-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="9a295-131">[ **Sql server の fqdn**] で、新しい SQL server ミラーリング監視を作成するサーバーの fqdn を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a295-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="9a295-132">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a295-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="9a295-133">指定した SQL Server インスタンスがミラーリング関係にある場合は、[ **この sql インスタンスはミラーリングの関係に** ある] チェックボックスをオンにし、[ **ミラーポート番号**] でポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a295-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="9a295-134">構成を保存するには、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a295-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

