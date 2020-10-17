---
title: 'Lync Server 2013: トポロジを公開するための要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f4186a351876b874a8b84963f9923369511f65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511824"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="fd5de-102">Lync Server 2013 でトポロジを公開するための要件</span><span class="sxs-lookup"><span data-stu-id="fd5de-102">Requirements to publish a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd5de-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fd5de-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fd5de-104">このトピックでは、トポロジビルダーまたは Lync Server 2013 管理シェルコマンドラインインターフェイスを使用しているかどうかにかかわらず、トポロジの公開に固有のインフラストラクチャおよびソフトウェア要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd5de-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="fd5de-105">これらの要件は、すべての Lync Server 2013 管理ツールに適用される一般的なオペレーティングシステム、ソフトウェア、およびアクセス許可の要件に加えてあります。</span><span class="sxs-lookup"><span data-stu-id="fd5de-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="fd5de-106">トポロジを公開する前に、すべての管理ツールの要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fd5de-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="fd5de-107">Active Directory ドメインサービスの準備手順が既に完了している場合は、作成する Lync Server 2013 展開の同じドメインまたはフォレストに参加しているコンピューター上でトポロジビルダーを実行する必要があります。これにより、そのコンピューターで管理ツールを使用してトポロジを正常に公開することができます。</span><span class="sxs-lookup"><span data-stu-id="fd5de-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="fd5de-p102">トポロジに定義されているコンピューターは、ドメイン (エッジ サーバーを除く)、および AD DS に参加する必要があります。ただし、トポロジを公開するときにコンピューターがオンラインである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fd5de-p102">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS. However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="fd5de-110">プールのファイル共有を作成し、リモート ユーザーが使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd5de-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="fd5de-111">Enterprise Edition フロントエンドプールを公開するには、SQL Server ベースのバックエンドサーバーが、サーバーを展開するドメインに参加しており、リモートユーザーが使用できるようにするための適切なファイアウォールルールで構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd5de-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="fd5de-112">ファイアウォール例外の指定の詳細については、「 [Lync server 2013 を使用した SQL Server のファイアウォール要件につい](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd5de-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="fd5de-113">SQL Server の構成の詳細については、「 [CONFIGURE Sql server For Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd5de-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fd5de-114">Standard Edition サーバーには、公開された構成を受け付ける、併置されたデータベースがあります。</span><span class="sxs-lookup"><span data-stu-id="fd5de-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="fd5de-115">最初に、Lync Server 展開ウィザードで [ <STRONG>最初の Standard Edition サーバーの準備</STRONG> ] セットアップタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd5de-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="fd5de-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd5de-116">See Also</span></span>


[<span data-ttu-id="fd5de-117">Lync Server 2013 でトポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="fd5de-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="fd5de-118">Lync Server 2013 でのセットアップのアクセス許可の委任</span><span class="sxs-lookup"><span data-stu-id="fd5de-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="fd5de-119">Lync Server 2013 の管理ツールソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="fd5de-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="fd5de-120">Lync Server 2013 でのサーバーおよびツールのオペレーティングシステムのサポート</span><span class="sxs-lookup"><span data-stu-id="fd5de-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="fd5de-121">Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fd5de-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

