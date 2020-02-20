---
title: 'Lync Server 2013: アーカイブ用のストレージのセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a87522269396a6ca9e362ded0454a55b3e105061
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="9ae0b-102">Lync Server 2013 でのアーカイブ用の記憶域のセットアップ</span><span class="sxs-lookup"><span data-stu-id="9ae0b-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ae0b-103">_**トピックの最終更新日:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="9ae0b-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="9ae0b-104">Lync Server 2013 のアーカイブ記憶域には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="9ae0b-105">**データストレージ**   データストレージは IM コンテンツを格納するために必要です。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="9ae0b-106">**ファイルストレージ**   ファイルストレージは、会議 (会議) コンテンツのデータストレージおよびファイルストレージを格納するために必要です。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="9ae0b-107">データ ストレージのセットアップ</span><span class="sxs-lookup"><span data-stu-id="9ae0b-107">Setting Up Data Storage</span></span>

<span data-ttu-id="9ae0b-108">Lync Server 2013 でアーカイブ用のデータストレージをセットアップするための要件は、アーカイブデータの保存方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="9ae0b-109">Exchange ストレージを使用してアーカイブデータを保存するために、Lync Server 2013 アーカイブを Exchange 展開と統合します。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="9ae0b-110">アーカイブデータを格納する個別の SQL Server データベースサーバーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="9ae0b-111">アーカイブ データ用の Exchange ストレージのセットアップ</span><span class="sxs-lookup"><span data-stu-id="9ae0b-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="9ae0b-112">アーカイブデータのストレージ用に Exchange をセットアップするには、exchange の展開で Exchange 2013 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="9ae0b-113">また、ユーザーメールボックスは Exchange 2013 サーバー上に配置され、メールボックスがインプレース保持に配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="9ae0b-114">Exchange 2013 の構成の詳細については、「Exchange 製品のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="9ae0b-115">アーカイブ データのストレージ用 SQL Server データベースのセットアップ</span><span class="sxs-lookup"><span data-stu-id="9ae0b-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="9ae0b-116">Lync Server 2013 のアーカイブには、展開と Exchange を統合しない限り、アーカイブされたデータを格納するための SQL Server データベースソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="9ae0b-117">SQL Server アーカイブデータベースの場合は、アーカイブデータベースをホストするコンピューターに SQL Server をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="9ae0b-118">フロントエンド プールのバックエンド データベースに使用するものと同じ SQL インスタンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="9ae0b-119">パフォーマンスを最大限に高めるために、中央管理ストアとは別のコンピューター上にアーカイブ データベースを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="9ae0b-120">Lync server 2013 コンポーネントの併置の詳細については、「サポート」のドキュメントの「supported [server 併置する in lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="9ae0b-121">各データベースサーバーは、サポートされているバージョンの SQL Server を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="9ae0b-122">サポートされているバージョンの詳細については、「計画」のドキュメントの「 [Lync Server 2013 でのアーカイブの技術要件](lync-server-2013-technical-requirements-for-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="9ae0b-123">アーカイブを展開して有効にする前に、SQL Server プラットフォームをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="9ae0b-124">トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="9ae0b-125">インストール手順の一部を含め、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="9ae0b-126">SQL Server の詳細については、SQL Server TechCenter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045)の「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-126">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ae0b-127">SQL Server エージェントサービスのスタートアップの種類が自動で、アーカイブデータベースを保持している SQL インスタンスに対して SQL Server エージェントサービスが実行されていることを確認します。これにより、既定のアーカイブ SQL Server メンテナンスジョブが、そのスケジュールに従って、SQL Server エージェントサービスの制御。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="9ae0b-128">ファイル ストレージのセットアップ</span><span class="sxs-lookup"><span data-stu-id="9ae0b-128">Setting Up File Storage</span></span>

<span data-ttu-id="9ae0b-129">アーカイブでは、フロントエンドプールまたは Standard Edition サーバーをセットアップするときに指定した Lync Server 2013 ファイル共有を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="9ae0b-130">アーカイブに使用するファイル共有を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="9ae0b-131">サポートされているファイルストレージシステムの詳細については、「サポート」のドキュメントの「 [Lync Server 2013 のファイルストレージサポート](lync-server-2013-file-storage-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ae0b-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

