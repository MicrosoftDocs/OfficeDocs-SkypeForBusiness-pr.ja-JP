---
title: 'Lync Server 2013: アーカイブ用のストレージのセットアップ'
description: 'Lync Server 2013: アーカイブ用に記憶域をセットアップします。'
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
ms.openlocfilehash: f7ee431b17b31c49ace7fae1f90d79ec6de2ada4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554243"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="c629b-103">Lync Server 2013 でのアーカイブ用の記憶域のセットアップ</span><span class="sxs-lookup"><span data-stu-id="c629b-103">Setting up storage for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c629b-104">_**トピックの最終更新日:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="c629b-104">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="c629b-105">Lync Server 2013 のアーカイブ記憶域には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c629b-105">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="c629b-106">**データストレージ**    データストレージは IM コンテンツを格納するために必要です。</span><span class="sxs-lookup"><span data-stu-id="c629b-106">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="c629b-107">**ファイル記憶域**    会議 (会議) コンテンツのデータストレージおよびファイルストレージを保存するには、ファイルストレージが必要です。</span><span class="sxs-lookup"><span data-stu-id="c629b-107">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="c629b-108">データ ストレージのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c629b-108">Setting Up Data Storage</span></span>

<span data-ttu-id="c629b-109">Lync Server 2013 でアーカイブ用のデータストレージをセットアップするための要件は、アーカイブデータの保存方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c629b-109">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="c629b-110">Exchange ストレージを使用してアーカイブデータを保存するために、Lync Server 2013 アーカイブを Exchange 展開と統合します。</span><span class="sxs-lookup"><span data-stu-id="c629b-110">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="c629b-111">アーカイブデータを格納する個別の SQL Server データベースサーバーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="c629b-111">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="c629b-112">アーカイブ データ用の Exchange ストレージのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c629b-112">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="c629b-113">アーカイブデータのストレージ用に Exchange をセットアップするには、exchange の展開で Exchange 2013 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-113">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="c629b-114">さらに、ユーザーメールボックスは Exchange 2013 サーバー上に配置されている必要があり、メールボックスが In-Place ホールドに設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-114">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="c629b-115">Exchange 2013 の構成の詳細については、「Exchange 製品のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c629b-115">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="c629b-116">アーカイブ データのストレージ用 SQL Server データベースのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c629b-116">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="c629b-117">Lync Server 2013 のアーカイブには、展開と Exchange を統合しない限り、アーカイブされたデータを格納するための SQL Server データベースソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="c629b-117">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="c629b-118">SQL Server アーカイブデータベースの場合は、アーカイブデータベースをホストするコンピューターに SQL Server をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-118">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="c629b-119">フロントエンド プールのバックエンド データベースに使用するものと同じ SQL インスタンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c629b-119">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="c629b-120">パフォーマンスを最大限に高めるために、中央管理ストアとは別のコンピューター上にアーカイブ データベースを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-120">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="c629b-121">Lync server 2013 コンポーネントの併置の詳細については、「サポート」のドキュメントの「supported [server 併置する in lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c629b-121">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c629b-122">各データベースサーバーは、サポートされているバージョンの SQL Server を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-122">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="c629b-123">サポートされているバージョンの詳細については、「計画」のドキュメントの「 [Lync Server 2013 でのアーカイブの技術要件](lync-server-2013-technical-requirements-for-archiving.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c629b-123">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="c629b-124">アーカイブを展開して有効にする前に、SQL Server プラットフォームをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-124">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="c629b-125">トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c629b-125">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="c629b-126">インストール手順の一部を含め、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c629b-126">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="c629b-127">SQL Server の詳細については、SQL Server TechCenter の「」を参照してください [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) 。</span><span class="sxs-lookup"><span data-stu-id="c629b-127">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c629b-128">Sql server エージェントサービスのスタートアップの種類が自動で、アーカイブデータベースを保持している SQL インスタンスに対して SQL Server エージェントサービスが実行されていることを確認します。これにより、sql server エージェントサービスの制御下で、既定のアーカイブ SQL Server メンテナンスジョブをスケジュールに従って実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c629b-128">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="c629b-129">ファイル ストレージのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c629b-129">Setting Up File Storage</span></span>

<span data-ttu-id="c629b-130">アーカイブでは、フロントエンドプールまたは Standard Edition サーバーをセットアップするときに指定した Lync Server 2013 ファイル共有を使用します。</span><span class="sxs-lookup"><span data-stu-id="c629b-130">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="c629b-131">アーカイブに使用するファイル共有を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c629b-131">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="c629b-132">サポートされているファイルストレージシステムの詳細については、「サポート」のドキュメントの「 [Lync Server 2013 のファイルストレージサポート](lync-server-2013-file-storage-support.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c629b-132">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

