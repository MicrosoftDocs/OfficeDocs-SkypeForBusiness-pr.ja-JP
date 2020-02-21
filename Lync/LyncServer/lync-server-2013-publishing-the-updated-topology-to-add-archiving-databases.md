---
title: 'Lync Server 2013: 更新されたトポロジを公開してアーカイブデータベースを追加する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff09dc330c7194ebe3657220c20a6138dc2f9a4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="67704-102">更新されたトポロジを公開して Lync Server 2013 にアーカイブデータベースを追加する</span><span class="sxs-lookup"><span data-stu-id="67704-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67704-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="67704-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="67704-104">トポロジビルダーでトポロジを更新した後は、アーカイブを構成して使用する前に、トポロジを中央管理ストアに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67704-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="67704-105">このデータの読み取り専用コピーはトポロジ内のすべてのサーバーにレプリケートされ、すべてのサーバーは、トポロジおよび他の構成の変更と同期された状態で維持されます。</span><span class="sxs-lookup"><span data-stu-id="67704-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="67704-106">更新したトポロジを公開するには</span><span class="sxs-lookup"><span data-stu-id="67704-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="67704-107">Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="67704-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67704-108">トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用しますが、トポロジを公開するには、サーバーをトポロジに追加する必要があります。 <STRONG>Domain Admins</STRONG>グループおよび<STRONG>RTCUniversalServerAdmins</STRONG>グループのメンバーであり、かつ、Lync server 2013 ファイルストアに使用しているファイル共有のフルコントロールのアクセス許可 (つまり、読み取り、書き込み、および変更) を持つアカウントを使用する必要があります (つまり、トポロジビルダーが必要な随意アクセス制御リスト (dacl) を構成できるようにする必要があります。、またはそれと同等の権限を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="67704-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="67704-109">トポロジビルダーを使用して、前のセクションで作成したトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="67704-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="67704-110">コンソールツリーで、[ **Lync Server 2013**] を右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67704-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="67704-111">[**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67704-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="67704-112">[**データベースの作成**] ページで、データベースが選択されていることを確認して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67704-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67704-113">データベースを作成するための適切なアクセス許可を持っていない場合、ここでのデータベースの選択を取り消して、適切なアクセス許可を持つ別のユーザーがデータベースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="67704-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="67704-114">必要な管理者権限とアクセス許可の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">deployment permissions For Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67704-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="67704-115">トポロジビルダーを使用してインストールできるのは、専用の SQL Server サーバー上のデータベースだけです。</span><span class="sxs-lookup"><span data-stu-id="67704-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="67704-116">他のサーバーコンポーネントと併置されている SQL Server サーバー上のデータベースは、そのコンピューターでローカルセットアップを実行してインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="67704-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="67704-117">[**公開ウィザードの完了**] ページで、トポロジが正常に公開されたことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67704-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="67704-118">トポロジを公開した後、コンテンツをアーカイブする前に、アーカイブのオプションおよびポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67704-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="67704-119">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 でのアーカイブのサポートの構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67704-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

