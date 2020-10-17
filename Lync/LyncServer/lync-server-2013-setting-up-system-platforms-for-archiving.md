---
title: 'Lync Server 2013: アーカイブ用のシステムプラットフォームのセットアップ'
description: 'Lync Server 2013: アーカイブ用のシステムプラットフォームのセットアップ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f210083451ae8fcb87c53e52b5512de6f1f18d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554183"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="663db-103">Lync Server 2013 でのアーカイブ用のシステムプラットフォームのセットアップ</span><span class="sxs-lookup"><span data-stu-id="663db-103">Setting up system platforms for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="663db-104">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="663db-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="663db-105">アーカイブの展開を開始する前に、システム要件を満たすハードウェアに、必要なオペレーティング システムとその他の必須ソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="663db-105">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="663db-106">**Lync Server 2013 プラットフォーム**    Lync Server 2013 の展開には、アーカイブサーバーがありません。</span><span class="sxs-lookup"><span data-stu-id="663db-106">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="663db-107">代わりに、統合データ収集エージェントはフロントエンドサーバーと Standard Edition サーバー上で実行されてアーカイブ用のデータをキャプチャするため、アーカイブをホストするために個別のシステムプラットフォームは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="663db-107">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="663db-108">**データストレージプラットフォーム**    Lync Server 2013 では、次のいずれかを使用してデータを保存できます。</span><span class="sxs-lookup"><span data-stu-id="663db-108">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="663db-109">**Microsoft Exchange 統合**    アーカイブデータを格納するために別のデータベースをセットアップするのではなく、Exchange 2013 展開を使用して Lync Server 2013 アーカイブデータを保存する場合は、exchange の展開で Exchange 2013 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="663db-109">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="663db-110">Exchange 2013 用のシステムプラットフォームのセットアップの詳細については、「Exchange 製品のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="663db-110">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="663db-111">**SQL Server**    アーカイブデータの保存に別の SQL Server データベースを使用する場合は、Microsoft Exchange 統合を使用するのではなく、アーカイブを展開する前にデータベースのシステムプラットフォームを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="663db-111">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="663db-112">特定のシステムプラットフォームの要件は、アーカイブデータベースに Microsoft SQL Server 2008 R2 と Microsoft SQL Server 2012 のどちらを使用するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="663db-112">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="663db-113">これらのデータベースのシステムプラットフォームの設定の詳細については、Microsoft SQL Server 2008 R2 および Microsoft SQL Server 2012 製品ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="663db-113">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="663db-114">**ファイルサーバープラットフォーム**    Lync Server 2013 では、フロントエンドサーバーまたは Standard Edition サーバーをセットアップするときに、ファイル記憶域として指定したのと同じ場所に Lync Server アーカイブファイルが保存されます。</span><span class="sxs-lookup"><span data-stu-id="663db-114">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="663db-115">ファイル記憶域をアーカイブするために別の場所を指定することはできません。そのため、アーカイブファイルの保存には個別のシステムプラットフォームは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="663db-115">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="663db-116">Microsoft Exchange 統合2013を使用している場合、アーカイブされた Lync コミュニケーションのファイルは exchange 2013 サーバーに格納され、これらの Exchange サーバーに所属するユーザーには保存されます。</span><span class="sxs-lookup"><span data-stu-id="663db-116">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

